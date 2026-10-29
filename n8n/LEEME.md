# Flujo de n8n: solicitudes al tutor

Borrador del 29/10/2026. **Todavía no se probó en un n8n real.** El archivo
JSON es válido, pero hay que importarlo y probarlo antes de usarlo con una
familia.

## Qué hace

1. Recibe el pedido del teléfono en `POST /webhook/solicitud`, con
   `familia_id`, `tipo` (app, sitio o tiempo), `nombre`, `motivo` y
   `minutos`.
2. Un agente con la API de Claude (modelo Haiku, el más barato) lo clasifica:
   apuestas, finanzas, cripto, préstamos u otro, con un nivel de riesgo y un
   resumen para el tutor.
3. Si es de apuestas, lo rechaza ahí mismo y se lo dice al teléfono.
4. Si no, le avisa al teléfono que el pedido llegó y le manda al tutor un
   Telegram con botones de Aprobar y Rechazar.
5. Si el tutor aprueba, llama a la API del MDM para habilitarlo.

Si el asistente falla, el pedido igual le llega al tutor, marcado como riesgo
alto.

## Para importarlo

1. En n8n: Workflows, Import from file, elegir `solicitudes.json`.
2. Crear dos credenciales:
   - **Anthropic (x-api-key):** tipo Header Auth, nombre `x-api-key`, valor
     la clave de la API de Claude.
   - **Telegram del servicio:** el token del bot de Telegram del servicio.
3. Cargar las variables de entorno `TUTOR_CHAT_ID` y `MDM_API_URL`.

## Lo que falta

- Buscar el tutor según `familia_id` (hoy usa un solo `TUTOR_CHAT_ID`).
- Exigir dos aprobaciones cuando la familia tenga dos tutores.
- La llamada real al MDM, cuando se elija entre Scalefusion y Hexnode.
- Avisarle al teléfono el resultado final (aprobado o rechazado).
- WhatsApp en lugar de Telegram, si las familias lo prefieren.
- Un segundo flujo que avise al tutor si el teléfono deja de reportarse.
- Registrar cada pedido.

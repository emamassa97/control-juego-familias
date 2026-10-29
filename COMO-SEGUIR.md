# Cómo seguir

Estado al 29/10/2026.

## Decidido

- Es un servicio para muchas familias. La empresa es dueña del servidor de
  control (MDM), de la app de solicitudes y de los flujos de n8n; cada familia
  es un cliente separado.
- Modelo: servicio de instalación sobre el teléfono propio de cada familia.
  El alquiler de teléfonos ya protegidos queda para más adelante.
- Funciona en Android (Device Owner) y en iPhone (supervisado). No hay Mac:
  para iPhone se usa iMazing Configurator desde una PC.
- Las solicitudes pasan por n8n, con un agente de la API de Claude que las
  clasifica.

## Hecho

- Documento de diseño: https://claude.ai/artifact/TZcfZRBjUUT8GZScjLAwTr
- Guía de instalación para técnicos: `docs/guia-instalacion.md` (borrador).
- Primer flujo de n8n: `n8n/solicitudes.json` (sin probar en un n8n real).

## Preguntas abiertas

- Qué MDM: Scalefusion o Hexnode (pedir precios y probar la API).
- Qué modelos de teléfono tienen las primeras familias.
- Si iMazing Configurator supervisa bien las versiones actuales de iOS.
- Si algún banco argentino ofrece bloqueo de apuestas para adultos.
- Revisión de un abogado: condiciones de Apple y Google, contrato con la
  familia, ley de datos personales.

## Próximos pasos

1. Elegir el MDM y conectar la llamada real en el flujo de n8n.
2. Probar el flujo en un n8n real con un teléfono de prueba.
3. Armar la app de solicitudes del teléfono.
4. Flujo que avise al tutor si el teléfono deja de reportarse.

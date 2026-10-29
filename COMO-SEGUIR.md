# Cómo seguir

Estado al 29/10/2026.

## Cambio de rumbo (29/10/2026, más tarde)

Emanuel pidió algo más sencillo y rápido de instalar. Lo recomendado ahora,
sin borrar el teléfono ni usar computadora (15 a 20 minutos):

- AppBlock Premium en Android y iPhone, con el tutor como contacto de
  aprobación (los desbloqueos le llegan por correo).
- Gamban para todo lo de apuestas.
- En iPhone (iOS 26.4 o más), el tutor pone el código de Tiempo en pantalla,
  que impide borrar las apps o quitarles el permiso.
- Costo aproximado: US$72 al año por persona.
- Hueco: en Android el modo seguro las apaga; en iPhone borrar el teléfono
  las quita. El tutor revisa de vez en cuando; el aviso automático llega con
  la app propia (estimado 4 a 6 meses).

La guía de `docs/guia-instalacion.md` y el flujo de n8n son del modo
«blindado» con MDM, que queda para casos graves. Falta la guía de la versión
simple.

## Decidido (antes del cambio)

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

1. Probar la versión simple (AppBlock + Gamban) en un Android y un iPhone
   reales y escribir su guía de instalación.
2. Elegir el MDM y conectar la llamada real en el flujo de n8n.
3. Probar el flujo en un n8n real con un teléfono de prueba.
4. Armar la app de solicitudes del teléfono.
5. Flujo que avise al tutor si el teléfono deja de reportarse.

# FAQ

## General

**¿Qué es centinelAI?**
Una plataforma de observabilidad con IA que filtra el 99% del ruido
y solo interrumpe a tu equipo cuando algo crítico necesita atención humana.

**¿Reemplaza a Prometheus, Grafana o Datadog?**
No. Se integra con tu stack existente sin reemplazar nada.

**¿Cuánto tiempo tarda la instalación?**
Aproximadamente 10 minutos para el primer conector.

## Técnico

**¿Qué pasa si centinelAI tiene una interrupción?**
Tus alertas siguen generándose en tus herramientas existentes.
centinelAI está en la ruta de notificaciones, no en la de monitorización.

**¿Dónde se almacenan los datos?**
En Supabase (PostgreSQL) en la UE (Irlanda).

**¿La IA tiene acceso a mi infraestructura?**
No. El agente solo lee metadatos de eventos (RBAC de solo lectura).
Claude AI solo ve los metadatos del evento, nunca tu código o datos.

**¿Es fiable el score de IA?**

| Tipo de alerta | Fiabilidad |
|----------------|------------|
| CrashLoopBackOff | ✅ Alta |
| OOMKilled | ✅ Alta |
| ImagePullBackOff | ✅ Alta |
| Alertas Prometheus | 🟡 Media |
| Alertas de negocio | 🔴 Baja |

**¿Qué modelos de IA usa centinelAI?**
- Scorer y Correlador: Claude Haiku
- Notificador y Postmortem: Claude Sonnet

## Privacidad

**¿Anthropic tiene acceso a mis datos?**
Los datos se envían a la API de Anthropic para el análisis.
Anthropic no usa datos de la API para entrenar modelos.
Ver: [anthropic.com/privacy](https://anthropic.com/privacy)

## Precios

**¿Qué incluye el plan Starter?**
Gratuito para siempre, hasta 5 servicios, scoring con reglas básicas.
Sin tarjeta de crédito.

**¿Qué incluye el plan Team?**
99€/mes: hasta 25 servicios, Claude AI scoring, Slack, postmortem y correlador.

**¿Cuánto cuesta el plan Pro?**
Precio a consultar según tamaño del equipo.
Escribe a [info@centinelai.io](mailto:info@centinelai.io?subject=centinelAI Pro).

## Soporte

**¿Cómo contacto con soporte?**
- Email: [info@centinelai.io](mailto:info@centinelai.io)
- Docs: [github.com/centinel-AI/docs](https://github.com/centinel-AI/docs)

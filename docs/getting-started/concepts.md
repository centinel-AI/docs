# Conceptos clave

## Score de alerta (0-100)

| Score | Estado | Acción |
|-------|--------|--------|
| 0-29 | 🟢 UP | Sin notificación |
| 30-69 | 🟡 DEGRADED | Solo visible en dashboard |
| 70-89 | 🟠 DOWN | Notificación a Slack + Email |
| 90-100 | 🔴 CRITICAL | Notificación urgente |

## Grupos de alertas

El deduplicador agrupa eventos similares del mismo servicio
en ventanas de 5 minutos. 50 eventos del mismo CrashLoop
generan solo 1 notificación.

## Servicios

centinelAI detecta automáticamente los servicios en cuanto
recibe la primera alerta:
- Pod de Kubernetes: `production/api-payments`
- Alerta de Prometheus: `HighMemoryUsage`
- Proyecto de GitLab: `myorg/api-payments`

## Incidentes

Un incidente es un evento declarado manualmente (desde Slack
o el dashboard) que agrupa todas las alertas relacionadas.
Al resolver un incidente, centinelAI genera un postmortem con IA.

## Plan y acceso a IA

| Función | Starter | Team | Pro |
|---------|---------|------|-----|
| **Precio** | **0€/mes** | **99€/mes** | **A consultar** |
| Servicios | 5 | 25 | Ilimitados |
| Webhook receiver | ✅ | ✅ | ✅ |
| Deduplicación | ✅ | ✅ | ✅ |
| Score con reglas | ✅ | ✅ | ✅ |
| Score con Claude AI | ❌ | ✅ | ✅ |
| Correlador IA | ❌ | ✅ | ✅ |
| Notificador Slack | ❌ | ✅ | ✅ |
| Postmortem con IA | ❌ | ✅ | ✅ |

# Servicios

La vista de servicios muestra todas las integraciones activas como tarjetas
con su estado actual y score en tiempo real.

## ServiceCard

Cada tarjeta muestra:

| Campo | Descripción |
|-------|-------------|
| Nombre | Identificador del servicio (`namespace/pod` o `alertname`) |
| Estado | UP / DEGRADED / DOWN / CRITICAL |
| Score | Último score calculado (0-100) |
| Última alerta | Timestamp del último evento recibido |
| Fuente | Kubernetes / Prometheus / Grafana / GitLab |

## Estados

| Estado | Color | Score |
|--------|-------|-------|
| UP | 🟢 Verde | 0-29 |
| DEGRADED | 🟡 Amarillo | 30-69 |
| DOWN | 🟠 Naranja | 70-89 |
| CRITICAL | 🔴 Rojo | 90-100 |

## Acciones

Desde cada tarjeta puedes:
- **Ver detalle** — Historial completo de alertas del servicio
- **Declarar incidente** — Crea un incidente vinculado al servicio
- **Ajustes** — Configura el umbral de notificación del servicio

## Límite de servicios

| Plan | Servicios |
|------|-----------|
| Starter | 3 |
| Team | 25 |
| Pro | Ilimitados |

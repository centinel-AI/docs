# Archivo de alertas

El archivo de alertas muestra el historial completo de todos los eventos
recibidos por centinelAI, incluyendo los filtrados (score < 70).

## Columnas

| Columna | Descripción |
|---------|-------------|
| Timestamp | Fecha y hora del evento |
| Servicio | Servicio afectado |
| Reason | Tipo de alerta (`CrashLoopBackOff`, etc.) |
| Score | Score asignado por el pipeline |
| Estado | Notificado / Filtrado / En incidente |
| Fuente | Conector de origen |

## Filtros disponibles

- **Rango de fechas** — Filtra por período
- **Servicio** — Muestra solo alertas de un servicio
- **Score mínimo** — Filtra por gravedad
- **Fuente** — Kubernetes / Prometheus / Grafana / GitLab
- **Estado** — Notificado / Filtrado

## Exportación

El archivo puede exportarse en CSV desde el botón **Exportar**
en la esquina superior derecha.

## Retención de datos

| Plan | Retención |
|------|-----------|
| Starter | 7 días |
| Team | 30 días |
| Pro | 90 días |

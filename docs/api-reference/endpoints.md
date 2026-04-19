# Endpoints REST

## Servicios

### GET /api/services

Devuelve todos los servicios de la organización.

```bash
curl https://centinelai.io/api/services \
  -H "Authorization: Bearer TU_API_TOKEN"
```

```json
[
  {
    "id": "uuid",
    "name": "api-payments",
    "namespace": "production",
    "status": "critical",
    "score": 92,
    "lastAlertAt": "2026-04-18T10:05:00Z"
  }
]
```

### GET /api/services/:id

Devuelve el detalle de un servicio con sus alertas recientes.

## Incidentes

### GET /api/incidents

```bash
curl https://centinelai.io/api/incidents \
  -H "Authorization: Bearer TU_API_TOKEN"
```

### POST /api/incidents

Crea un incidente manualmente.

```json
{
  "title": "Fallo en api-payments",
  "serviceId": "uuid",
  "severity": "critical"
}
```

### PATCH /api/incidents/:id

Actualiza el estado de un incidente.

```json
{ "status": "resolved" }
```

Cuando el status cambia a `resolved`, centinelAI genera automáticamente
el postmortem si el plan es Team o Pro.

## Alertas

### GET /api/alerts

Historial paginado de alertas.

| Query param | Descripción | Default |
|-------------|-------------|---------|
| `page` | Número de página | 1 |
| `limit` | Resultados por página | 50 |
| `serviceId` | Filtrar por servicio | — |
| `from` | Fecha de inicio (ISO 8601) | — |
| `to` | Fecha de fin (ISO 8601) | — |

# REST Endpoints

## Services

### GET /api/services

Returns all services in the organization.

```bash
curl https://centinelai.io/api/services \
  -H "Authorization: Bearer YOUR_API_TOKEN"
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

Returns the detail of a service with its recent alerts.

## Incidents

### GET /api/incidents

```bash
curl https://centinelai.io/api/incidents \
  -H "Authorization: Bearer YOUR_API_TOKEN"
```

### POST /api/incidents

Creates an incident manually.

```json
{
  "title": "api-payments failure",
  "serviceId": "uuid",
  "severity": "critical"
}
```

### PATCH /api/incidents/:id

Updates the status of an incident.

```json
{ "status": "resolved" }
```

When the status changes to `resolved`, centinelAI automatically generates
the postmortem if the plan is Team or Pro.

## Alerts

### GET /api/alerts

Paginated alert history.

| Query param | Description | Default |
|-------------|-------------|---------|
| `page` | Page number | 1 |
| `limit` | Results per page | 50 |
| `serviceId` | Filter by service | — |
| `from` | Start date (ISO 8601) | — |
| `to` | End date (ISO 8601) | — |

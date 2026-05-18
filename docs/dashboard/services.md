# Services

The services view shows all active integrations as cards
with their current status and real-time score.

## ServiceCard

Each card shows:

| Field | Description |
|-------|-------------|
| Name | Service identifier (`namespace/pod` or `alertname`) |
| Status | UP / DEGRADED / DOWN / CRITICAL |
| Score | Latest calculated score (0-100) |
| Last alert | Timestamp of the last received event |
| Source | Kubernetes / Prometheus / Grafana / GitLab |

## Statuses

| Status | Color | Score |
|--------|-------|-------|
| UP | 🟢 Green | 0-29 |
| DEGRADED | 🟡 Yellow | 30-69 |
| DOWN | 🟠 Orange | 70-89 |
| CRITICAL | 🔴 Red | 90-100 |

## Actions

From each card you can:
- **View detail** — Full alert history for the service
- **Declare incident** — Create an incident linked to the service
- **Settings** — Configure the notification threshold for the service

## Service limits

| Plan | Services |
|------|----------|
| Starter | 5 |
| Team | 25 |
| Pro | Unlimited |

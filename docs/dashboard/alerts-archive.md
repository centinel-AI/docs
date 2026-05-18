# Alerts Archive

The alerts archive shows the complete history of all events
received by centinelAI, including filtered ones (score < 70).

## Columns

| Column | Description |
|--------|-------------|
| Timestamp | Event date and time |
| Service | Affected service |
| Reason | Alert type (`CrashLoopBackOff`, etc.) |
| Score | Score assigned by the pipeline |
| Status | Notified / Filtered / In incident |
| Source | Origin connector |

## Available filters

- **Date range** — Filter by period
- **Service** — Show only alerts from one service
- **Minimum score** — Filter by severity
- **Source** — Kubernetes / Prometheus / Grafana / GitLab
- **Status** — Notified / Filtered

## Export

The archive can be exported as CSV from the **Export** button
in the top-right corner.

## Data retention

| Plan | Retention |
|------|-----------|
| Starter | 7 days |
| Team | 30 days |
| Pro | 90 days |

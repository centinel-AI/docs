# Grafana Alerting

## Contact point configuration

| Field | Value |
|-------|-------|
| Name | centinelAI |
| Integration | Webhook |
| URL | `https://centinelai.io/api/webhooks/grafana` |
| HTTP Method | POST |
| Authorization Header Scheme | Bearer |
| Authorization Header Credentials | YOUR_API_TOKEN |

## Notification policy

- Go to **Alerting → Notification policies → Add policy**
- Contact point: `centinelAI`

## Supported format

```json
{
  "alerts": [{
    "status": "firing",
    "labels": { "alertname": "HighCPU", "severity": "warning" },
    "annotations": { "summary": "CPU usage high" }
  }]
}
```

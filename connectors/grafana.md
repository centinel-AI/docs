# Grafana Alerting

## Configuración del contact point

| Campo | Valor |
|-------|-------|
| Name | centinelAI |
| Integration | Webhook |
| URL | `https://centinelai.io/api/webhooks/grafana` |
| HTTP Method | POST |
| Authorization Header Scheme | Bearer |
| Authorization Header Credentials | TU_API_TOKEN |

## Notification policy

- Ve a **Alerting → Notification policies → Add policy**
- Contact point: `centinelAI`

## Formato soportado

```json
{
  "alerts": [{
    "status": "firing",
    "labels": { "alertname": "HighCPU", "severity": "warning" },
    "annotations": { "summary": "CPU usage high" }
  }]
}
```

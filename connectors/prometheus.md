# Prometheus / Alertmanager

## Configuración en alertmanager.yml

```yaml
receivers:
  - name: centinelai
    webhook_configs:
      - url: https://centinelai.io/api/webhooks/prometheus
        send_resolved: false
        http_config:
          bearer_token: TU_API_TOKEN

route:
  receiver: centinelai
  group_by: [alertname, namespace]
  group_wait: 10s
  group_interval: 30s
  repeat_interval: 2m
```

## Test con curl

```bash
curl -X POST https://centinelai.io/api/webhooks/prometheus \
  -H "Authorization: Bearer TU_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "version": "4",
    "status": "firing",
    "alerts": [{
      "status": "firing",
      "labels": { "alertname": "HighMemoryUsage", "severity": "critical" },
      "annotations": { "summary": "Memory above 90%" },
      "startsAt": "2026-04-18T10:00:00Z",
      "fingerprint": "test123"
    }]
  }'
```

Respuesta: `{"received": true, "eventIds": ["uuid"]}`

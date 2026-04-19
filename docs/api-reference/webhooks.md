# Webhooks

## POST /api/webhooks/kubernetes

```bash
curl -X POST https://centinelai.io/api/webhooks/kubernetes \
  -H "Authorization: Bearer TU_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "namespace": "production",
    "podName": "api-payments-abc",
    "reason": "CrashLoopBackOff",
    "message": "Back-off restarting failed container",
    "count": 8,
    "nodeName": "node-1",
    "involvedObjectKind": "Pod",
    "firstTime": "2026-04-18T10:00:00Z",
    "lastTime": "2026-04-18T10:05:00Z"
  }'
```

## POST /api/webhooks/prometheus

```bash
curl -X POST https://centinelai.io/api/webhooks/prometheus \
  -H "Authorization: Bearer TU_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "version": "4",
    "status": "firing",
    "alerts": [{
      "status": "firing",
      "labels": { "alertname": "HighMemory", "severity": "critical" },
      "annotations": { "summary": "Memory above 90%" },
      "startsAt": "2026-04-18T10:00:00Z",
      "fingerprint": "abc123"
    }]
  }'
```

## POST /api/webhooks/grafana

Mismo formato que Prometheus con array `alerts`.

## POST /api/webhooks/gitlab

```bash
curl -X POST https://centinelai.io/api/webhooks/gitlab \
  -H "X-Gitlab-Token: TU_API_TOKEN" \
  -H "X-Gitlab-Event: Pipeline Hook" \
  -H "Content-Type: application/json" \
  -d '{
    "object_kind": "pipeline",
    "object_attributes": { "status": "failed", "ref": "main" },
    "project": { "name": "my-service" }
  }'
```

## Respuesta estándar

```json
{ "received": true, "eventId": "uuid" }
```

## Códigos de respuesta

| Código | Significado |
|--------|-------------|
| 200 | Evento recibido correctamente |
| 401 | Token inválido o ausente |
| 400 | Payload malformado |
| 500 | Error interno |

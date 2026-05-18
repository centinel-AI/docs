# Webhooks

## POST /api/webhooks/kubernetes

```bash
curl -X POST https://centinelai.io/api/webhooks/kubernetes \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
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
  -H "Authorization: Bearer YOUR_API_TOKEN" \
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

Same format as Prometheus with an `alerts` array.

## POST /api/webhooks/gitlab

```bash
curl -X POST https://centinelai.io/api/webhooks/gitlab \
  -H "X-Gitlab-Token: YOUR_API_TOKEN" \
  -H "X-Gitlab-Event: Pipeline Hook" \
  -H "Content-Type: application/json" \
  -d '{
    "object_kind": "pipeline",
    "object_attributes": { "status": "failed", "ref": "main" },
    "project": { "name": "my-service" }
  }'
```

## Standard response

```json
{ "received": true, "eventId": "uuid" }
```

## Response codes

| Code | Meaning |
|------|---------|
| 200 | Event received successfully |
| 401 | Invalid or missing token |
| 400 | Malformed payload |
| 500 | Internal error |

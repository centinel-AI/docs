# API Reference

## Base URL

```
https://centinelai.io
```

## Authentication

All endpoints use Bearer token authentication:

```bash
Authorization: Bearer YOUR_API_TOKEN
```

## Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/webhooks/kubernetes` | Kubernetes events |
| `POST` | `/api/webhooks/prometheus` | Alertmanager alerts |
| `POST` | `/api/webhooks/grafana` | Grafana alerts |
| `POST` | `/api/webhooks/gitlab` | GitLab CI/CD events |
| `GET` | `/api/install/k8s/manifest.yaml` | K8s installation manifest |
| `POST` | `/api/slack/actions` | Slack button actions |

## Response codes

| Code | Meaning |
|------|---------|
| `200` | Event received successfully |
| `400` | Malformed payload |
| `401` | Invalid or missing token |
| `500` | Internal error |

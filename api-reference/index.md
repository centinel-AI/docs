# API Reference

## Base URL

```
https://centinelai.io
```

## Autenticación

Todos los endpoints usan Bearer token authentication:

```bash
Authorization: Bearer TU_API_TOKEN
```

## Endpoints

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `POST` | `/api/webhooks/kubernetes` | Eventos de Kubernetes |
| `POST` | `/api/webhooks/prometheus` | Alertas de Alertmanager |
| `POST` | `/api/webhooks/grafana` | Alertas de Grafana |
| `POST` | `/api/webhooks/gitlab` | Eventos de GitLab CI/CD |
| `GET` | `/api/install/k8s/manifest.yaml` | Manifest de instalación K8s |
| `POST` | `/api/slack/actions` | Acciones de botones de Slack |

## Códigos de respuesta

| Código | Significado |
|--------|-------------|
| `200` | Evento recibido correctamente |
| `400` | Payload malformado |
| `401` | Token inválido o ausente |
| `500` | Error interno |

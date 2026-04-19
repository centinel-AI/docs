# GitLab CI/CD

## Configuración

Ve a tu proyecto → **Settings → Webhooks → Add new webhook**:

| Campo | Valor |
|-------|-------|
| URL | `https://centinelai.io/api/webhooks/gitlab` |
| Secret token | TU_API_TOKEN |
| Trigger | ✅ Pipeline events, ✅ Job events |

## Test con curl

```bash
curl -X POST https://centinelai.io/api/webhooks/gitlab \
  -H "X-Gitlab-Token: TU_API_TOKEN" \
  -H "X-Gitlab-Event: Pipeline Hook" \
  -H "Content-Type: application/json" \
  -d '{
    "object_kind": "pipeline",
    "object_attributes": { "status": "failed", "ref": "main", "duration": 127 },
    "project": { "name": "api-payments", "path_with_namespace": "myorg/api-payments" }
  }'
```

## Correlación automática

centinelAI correlaciona fallos de pipeline de GitLab con eventos de Kubernetes
del mismo servicio automáticamente.

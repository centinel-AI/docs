# GitLab CI/CD

## Setup

Go to your project → **Settings → Webhooks → Add new webhook**:

| Field | Value |
|-------|-------|
| URL | `https://centinelai.io/api/webhooks/gitlab` |
| Secret token | YOUR_API_TOKEN |
| Trigger | ✅ Pipeline events, ✅ Job events |

## Test with curl

```bash
curl -X POST https://centinelai.io/api/webhooks/gitlab \
  -H "X-Gitlab-Token: YOUR_API_TOKEN" \
  -H "X-Gitlab-Event: Pipeline Hook" \
  -H "Content-Type: application/json" \
  -d '{
    "object_kind": "pipeline",
    "object_attributes": { "status": "failed", "ref": "main", "duration": 127 },
    "project": { "name": "api-payments", "path_with_namespace": "myorg/api-payments" }
  }'
```

## Automatic correlation

centinelAI automatically correlates GitLab pipeline failures
with Kubernetes events from the same service.

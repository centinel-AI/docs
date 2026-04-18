# Conectores

| Conector | Tipo | Endpoint | Estado |
|----------|------|----------|--------|
| [Kubernetes](./kubernetes.md) | Input (agente) | Push automático | ✅ |
| [Prometheus](./prometheus.md) | Input (webhook) | `/api/webhooks/prometheus` | ✅ |
| [Grafana](./grafana.md) | Input (webhook) | `/api/webhooks/grafana` | ✅ |
| [GitLab CI/CD](./gitlab.md) | Input (webhook) | `/api/webhooks/gitlab` | ✅ |
| [Slack](./slack.md) | Output | — | ✅ |
| GitHub Actions | Input | — | 🔜 |
| Datadog | Input | — | 🔜 |
| PagerDuty | Output | — | 🔜 |

## Autenticación

```
Authorization: Bearer TU_API_TOKEN
```

Encuentra tu token en **centinelai.io → Conectores → cualquier conector**.

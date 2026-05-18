# Quick start — 10 minutes

## Prerequisites

- Account at [centinelai.io](https://centinelai.io) (free, no credit card)
- A Kubernetes cluster with `kubectl` configured
- Or Prometheus + Alertmanager

## Option A — Kubernetes (recommended)

!!! tip "Step 1 — Apply the manifest"
    One command creates the namespace, RBAC and the agent:

    ```bash
    kubectl apply -f https://centinelai.io/api/install/k8s/manifest.yaml
    ```

    This creates:

    - Namespace: `centinela-system`
    - ServiceAccount: `centinela-agent` (read-only)
    - ClusterRole + ClusterRoleBinding
    - Agent deployment

!!! tip "Step 2 — Create the secret"
    Find your API token in **centinelai.io → Connectors → Kubernetes**

    ```bash
    kubectl create secret generic centinela-token \
      --from-literal=SENTINEL_TOKEN="your-api-token" \
      --from-literal=SENTINEL_API_URL="https://centinelai.io" \
      -n centinela-system
    ```

!!! tip "Step 3 — Restart and verify"
    ```bash
    kubectl rollout restart deployment/centinela-agent -n centinela-system
    kubectl logs -n centinela-system -l app=centinela-agent -f
    ```

    Expected logs:
    ```
    [INFO] In-cluster config loaded
    [INFO] Watching cluster events...
    ```

!!! tip "Step 4 — Generate your first test alert"
    ```bash
    kubectl run crash-test \
      --image=busybox \
      --restart=Always \
      -- sh -c "echo 'crashing'; exit 1"
    ```

    Clean up once verified:
    ```bash
    kubectl delete pod crash-test
    ```

!!! success "Done!"
    Within 60 seconds you'll see the first alerts in your dashboard.
    [Go to dashboard →](https://centinelai.io/dashboard)

---

## Option B — Prometheus + Alertmanager

```yaml
receivers:
  - name: centinelai
    webhook_configs:
      - url: https://centinelai.io/api/webhooks/prometheus
        send_resolved: false
        http_config:
          bearer_token: YOUR_API_TOKEN

route:
  receiver: centinelai
  group_wait: 10s
  group_interval: 30s
  repeat_interval: 2m
```

Reload:
```bash
curl -X POST http://localhost:9093/-/reload
```

## Option C — Grafana Alerting

1. **Alerting → Contact points → Add contact point**
2. Type: **Webhook**
3. URL: `https://centinelai.io/api/webhooks/grafana`
4. HTTP Method: `POST`
5. Authorization Header Scheme: `Bearer`
6. Authorization Header Credentials: `YOUR_API_TOKEN`

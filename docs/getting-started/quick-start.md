# Quick Start — 10 minutos

## Requisitos previos

- Cuenta en [centinelai.io](https://centinelai.io) (gratis, sin tarjeta)
- Un cluster de Kubernetes con `kubectl` configurado
- O Prometheus + Alertmanager

## Opción A — Kubernetes (recomendado)

!!! tip "Paso 1 — Aplica el manifest"
    Un solo comando crea el namespace, RBAC y el agente:

    ```bash
    kubectl apply -f https://centinelai.io/api/install/k8s/manifest.yaml
    ```

    Esto crea:

    - Namespace: `centinela-system`
    - ServiceAccount: `centinela-agent` (solo lectura)
    - ClusterRole + ClusterRoleBinding
    - Deployment del agente

!!! tip "Paso 2 — Crea el secret"
    Encuentra tu token en **centinelai.io → Conectores → Kubernetes**

    ```bash
    kubectl create secret generic centinela-token \
      --from-literal=SENTINEL_TOKEN="tu-api-token" \
      --from-literal=SENTINEL_API_URL="https://centinelai.io" \
      -n centinela-system
    ```

!!! tip "Paso 3 — Reinicia y verifica"
    ```bash
    kubectl rollout restart deployment/centinela-agent -n centinela-system
    kubectl logs -n centinela-system -l app=centinela-agent -f
    ```

    Logs esperados:
    ```
    [INFO] In-cluster config loaded
    [INFO] Watching cluster events...
    ```

!!! tip "Paso 4 — Genera tu primera alerta de prueba"
    ```bash
    kubectl run crash-test \
      --image=busybox \
      --restart=Always \
      -- sh -c "echo 'crashing'; exit 1"
    ```

    Limpia cuando hayas verificado:
    ```bash
    kubectl delete pod crash-test
    ```

!!! success "¡Listo!"
    En 60 segundos verás las primeras alertas en tu dashboard.
    [Ver dashboard →](https://centinelai.io/dashboard)

---

## Opción B — Prometheus + Alertmanager

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
  group_wait: 10s
  group_interval: 30s
  repeat_interval: 2m
```

Recarga:
```bash
curl -X POST http://localhost:9093/-/reload
```

## Opción C — Grafana Alerting

1. **Alerting → Contact points → Add contact point**
2. Tipo: **Webhook**
3. URL: `https://centinelai.io/api/webhooks/grafana`
4. HTTP Method: `POST`
5. Authorization Header Scheme: `Bearer`
6. Authorization Header Credentials: `TU_API_TOKEN`

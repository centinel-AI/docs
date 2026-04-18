# Kubernetes

## Instalación

### Paso 1 — Aplica el manifest completo

```bash
kubectl apply -f https://centinelai.io/api/install/k8s/manifest.yaml
```

Incluye: Namespace, ServiceAccount, ClusterRole, ClusterRoleBinding, Deployment.

### Paso 2 — Crea el secret

```bash
kubectl create secret generic centinela-token \
  --from-literal=SENTINEL_TOKEN="TU_API_TOKEN" \
  --from-literal=SENTINEL_API_URL="https://centinelai.io" \
  -n centinela-system
```

### Paso 3 — Reinicia

```bash
kubectl rollout restart deployment/centinela-agent -n centinela-system
```

### Paso 4 — Verifica

```bash
kubectl get pods -n centinela-system
kubectl logs -n centinela-system -l app=centinela-agent --tail=20
```

## Eventos detectados

| Reason | Severity | Descripción |
|--------|----------|-------------|
| `CrashLoopBackOff` | critical | Pod reiniciándose continuamente |
| `OOMKilled` | critical | Eliminado por falta de memoria |
| `ImagePullBackOff` | warning | No se puede descargar la imagen |
| `BackOff` | warning | Backoff general |
| `NodeNotReady` | critical | Nodo no disponible |

## Desinstalación

```bash
kubectl delete -f https://centinelai.io/api/install/k8s/manifest.yaml
kubectl delete secret centinela-token -n centinela-system
```

## Imagen del agente

```
ghcr.io/centinel-ai/agent:latest
```

Código: [github.com/centinel-AI/agent](https://github.com/centinel-AI/agent)

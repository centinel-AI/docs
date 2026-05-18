# Kubernetes

## Installation

### Step 1 — Apply the full manifest

```bash
kubectl apply -f https://centinelai.io/api/install/k8s/manifest.yaml
```

Includes: Namespace, ServiceAccount, ClusterRole, ClusterRoleBinding, Deployment.

### Step 2 — Create the secret

```bash
kubectl create secret generic centinela-token \
  --from-literal=SENTINEL_TOKEN="YOUR_API_TOKEN" \
  --from-literal=SENTINEL_API_URL="https://centinelai.io" \
  -n centinela-system
```

### Step 3 — Restart

```bash
kubectl rollout restart deployment/centinela-agent -n centinela-system
```

### Step 4 — Verify

```bash
kubectl get pods -n centinela-system
kubectl logs -n centinela-system -l app=centinela-agent --tail=20
```

## Detected events

| Reason | Severity | Description |
|--------|----------|-------------|
| `CrashLoopBackOff` | critical | Pod restarting continuously |
| `OOMKilled` | critical | Killed due to out-of-memory |
| `ImagePullBackOff` | warning | Cannot pull the container image |
| `BackOff` | warning | General backoff |
| `NodeNotReady` | critical | Node unavailable |

## Uninstallation

```bash
kubectl delete -f https://centinelai.io/api/install/k8s/manifest.yaml
kubectl delete secret centinela-token -n centinela-system
```

## Agent image

```
ghcr.io/centinel-ai/agent:latest
```

Source: [github.com/centinel-AI/agent](https://github.com/centinel-AI/agent)

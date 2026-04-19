# Pipeline de IA

centinelAI usa un pipeline de 4 agentes construido sobre Inngest
(step functions durables) y Claude AI de Anthropic.

## Arquitectura del pipeline

```mermaid
flowchart TD
    A[🔔 Webhook recibido\nK8s · Prometheus · GitLab] --> B

    B[1️⃣ Deduplicador\nReglas · Sin IA] --> C
    B --> D[Grupo existente\nañade evento]

    C[Grupo nuevo creado] --> E

    E[2️⃣ Scorer\nClaude Haiku] --> F{Score}

    F -->|Score < 30| G[🟢 UP\nSin notificación]
    F -->|30-69| H[🟡 DEGRADED\nDashboard only]
    F -->|> 70| I

    I[3️⃣ Correlador\nClaude Haiku] --> J

    J[4️⃣ Notificador\nClaude Sonnet] --> K[📱 Slack\nBlock Kit]
    J --> L[📧 Email\nResend]
```

## Agentes

| Agente | Modelo | Tiempo | Función |
|--------|--------|--------|---------|
| [Deduplicador](deduplicator.md) | Reglas | ~100ms | Agrupa eventos similares |
| [Scorer](scorer.md) | Claude Haiku | ~2s | Puntúa 0-100 |
| [Correlador](correlator.md) | Claude Haiku | ~2s | Encuentra patrones |
| [Notificador](notifier.md) | Claude Sonnet | ~5s | Genera notificación |
| [Postmortem](postmortem.md) | Claude Sonnet | ~10s | Análisis post-incidente |

## Eventos de Inngest

```
centinelai/alert.received    → Deduplicador
centinelai/group.created     → Scorer
centinelai/group.scored      → Correlador
centinelai/group.critical    → Notificador (solo si score > 70)
```

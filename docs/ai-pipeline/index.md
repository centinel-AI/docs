# AI Pipeline

centinelAI uses a 4-agent pipeline built on Inngest
(durable step functions) and Claude AI by Anthropic.

## Full flow

```mermaid
flowchart TD
    A[🔔 Webhook received\nK8s · Prometheus · GitLab] --> B

    B[1️⃣ Deduplicator\nRules · No AI] --> C
    B --> D[Existing group\nadds event]

    C[New group created] --> E

    E[2️⃣ Scorer\nClaude Haiku] --> F{Score}

    F -->|Score < 30| G[🟢 UP\nNo notification]
    F -->|30-69| H[🟡 DEGRADED\nDashboard only]
    F -->|> 70| I

    I[3️⃣ Correlator\nClaude Haiku] --> J

    J[4️⃣ Notifier\nClaude Sonnet] --> K[📱 Slack\nBlock Kit]
    J --> L[📧 Email\nResend]
```

## Agents

| Agent | Model | Time | Function |
|-------|-------|------|----------|
| [Deduplicator](deduplicator.md) | Rules | ~100ms | Groups similar events |
| [Scorer](scorer.md) | Claude Haiku | ~2s | Scores 0-100 |
| [Correlator](correlator.md) | Claude Haiku | ~2s | Finds patterns |
| [Notifier](notifier.md) | Claude Sonnet | ~5s | Generates notification |
| [Postmortem](postmortem.md) | Claude Sonnet | ~10s | Post-incident analysis |

## Inngest events

```
centinelai/alert.received    → Deduplicator
centinelai/group.created     → Scorer
centinelai/group.scored      → Correlator
centinelai/group.critical    → Notifier (only if score > 70)
```

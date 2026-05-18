# Notifier

## Function
Generates natural language notifications and sends them to Slack and/or Email
when a group exceeds score > 70.

## Model
Claude Sonnet

## Availability
Only available on **Team** and **Pro** plans.

## Slack message structure

```
🔴 CRITICAL — api-payments (score: 92)

CrashLoopBackOff in production/api-payments-abc
15 restarts in the last 10 minutes.

Probable cause: database connection failure
after the 10:03 deployment.

Recommended actions:
• Check logs: kubectl logs -n production api-payments-abc
• Verify PostgreSQL connectivity
• Consider rolling back to the previous deployment

[🚨 Declare incident] [💤 Snooze 1h] [📊 View dashboard]
```

## Notification channels

| Channel | Configuration |
|---------|---------------|
| Slack | Bot Token + channel in **Connectors → Slack** |
| Email | Address configured in **Settings → Notifications** |

## Notification threshold

Notifications are only sent when `score >= 70`. Configurable per service
from the dashboard at **Services → [service] → Settings**.

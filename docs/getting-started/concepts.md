# Key concepts

## Alert score (0-100)

| Score | Status | Action |
|-------|--------|--------|
| 0-29 | 🟢 UP | No notification |
| 30-69 | 🟡 DEGRADED | Dashboard only |
| 70-89 | 🟠 DOWN | Slack + Email notification |
| 90-100 | 🔴 CRITICAL | Urgent notification |

## Alert groups

The deduplicator groups similar events from the same service
in 5-minute windows. 50 events from the same CrashLoop
generate only 1 notification.

## Services

centinelAI automatically detects your infrastructure services
as soon as it receives the first alert:
- Kubernetes pod: `production/api-payments`
- Prometheus alert: `HighMemoryUsage`
- GitLab project: `myorg/api-payments`

## Incidents

An incident is a manually declared event (from Slack or the dashboard)
that groups all related alerts. When you resolve an incident,
centinelAI generates an automatic AI postmortem.

## Plan and AI access

| Feature | Starter | Team | Pro |
|---------|---------|------|-----|
| **Price** | **€0/month** | **€99/month** | **Custom** |
| Services | 5 | 25 | Unlimited |
| Rule-based scoring | ✅ | ✅ | ✅ |
| Claude AI scoring | ❌ | ✅ | ✅ |
| AI correlator | ❌ | ✅ | ✅ |
| Slack notifications | ❌ | ✅ | ✅ |
| AI postmortem | ❌ | ✅ | ✅ |

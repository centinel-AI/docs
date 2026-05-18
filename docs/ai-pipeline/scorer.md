# Alert Scorer

## Function
Evaluates each alert group and assigns a score from 0 to 100.

## Scoring factors (Claude Haiku)

- Alert type (`CrashLoopBackOff` > `BackOff`)
- Number of events and frequency
- Service criticality
- History of similar alerts

## Rule-based scoring (Starter plan)

| Reason | Score |
|--------|-------|
| CrashLoopBackOff | 85 |
| OOMKilled | 80 |
| NodeNotReady | 90 |
| ImagePullBackOff | 60 |
| BackOff | 40 |

## AI scoring (Team/Pro plan)

Claude Haiku analyses the full context and generates a score
with a natural language explanation.

Example score_reason:
> "Critical CrashLoopBackOff on payments service in production.
> 15 restarts in 10 minutes indicates a persistent, not transient failure.
> High business impact. Score: 92/100"

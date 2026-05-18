# Correlator

## Function
Detects patterns and relationships between alerts from different services
to identify systemic root causes.

## Model
Claude Haiku

## Availability
Only available on **Team** and **Pro** plans.

## How it works

When a group receives a score > 30, the correlator analyses:
- Active alerts on other services in the same namespace
- Recent infrastructure events (nodes, network)
- GitLab pipeline failures from the same repository

If a pattern is detected, the group is enriched with a `correlations` field:

```json
{
  "correlations": [
    {
      "serviceId": "production/api-gateway",
      "reason": "HighLatency",
      "confidence": 0.87,
      "explanation": "api-gateway shows high latency since the same timestamp"
    }
  ]
}
```

## Correlation example

A `NodeNotReady` on `node-3` can automatically correlate with
all pods running on that node, raising the score of each one
and identifying the root cause as a node failure, not an application issue.

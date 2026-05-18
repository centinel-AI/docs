# Incidents

The incidents section allows you to manage critical events declared
by the team and view AI-generated postmortems.

## Incident lifecycle

```
OPEN → INVESTIGATING → RESOLVED
```

| Status | Description |
|--------|-------------|
| OPEN | Incident declared, unassigned |
| INVESTIGATING | Someone is working on it |
| RESOLVED | Incident closed — postmortem generated |

## Create an incident

From the dashboard:
1. Click **Declare incident** on a ServiceCard or alert
2. Add title and severity
3. The incident is open and visible to the whole team

From Slack:
- Click the **🚨 Declare incident** button on a notification

## Resolve an incident

1. Open the incident from the list
2. Click **Resolve incident**
3. Add a resolution note (optional)
4. centinelAI automatically generates the postmortem (Team/Pro plans)

## Postmortem

On resolution, the postmortem appears on the **Postmortem** tab of the incident.
It can be exported as `.md` to include in the team wiki.

See [Postmortem Generator](../ai-pipeline/postmortem.md) for more details.

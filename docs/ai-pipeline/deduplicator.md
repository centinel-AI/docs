# Deduplicator

## Function
Groups similar events from the same service to avoid duplicate notifications.

## Algorithm

The deduplicator operates with **5-minute** windows. When a new event arrives:

1. Looks for an open group from the same service with the same `reason`
2. If found, adds the event to the group and updates the counter
3. If not found, creates a new group and emits `centinelai/group.created`

## Grouping criteria

| Field | Use |
|-------|-----|
| `serviceId` | Identifies the affected service |
| `reason` | Event type (`CrashLoopBackOff`, etc.) |
| Time window | 5 minutes from the first event |

## Result

50 events from the same `CrashLoopBackOff` on the same pod
generate **1 single group** with `count: 50`.

## Availability

Available on all plans (Starter, Team, Pro).

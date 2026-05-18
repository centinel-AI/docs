# Connectors

centinelAI receives alerts via authenticated HTTP webhooks
or through the Kubernetes agent.

## Available

<div class="grid cards" markdown>

-   :material-kubernetes:{ .lg .middle } **Kubernetes**

    ---

    Python agent with read-only RBAC.
    Detects events in real time with no additional configuration.

    **Setup:** ~2 min
    [:octicons-arrow-right-24: Configure](kubernetes.md)

-   :material-chart-timeline-variant:{ .lg .middle } **Prometheus**

    ---

    Compatible with Alertmanager webhook v4.
    Zero changes to your existing configuration.

    **Setup:** ~5 min
    [:octicons-arrow-right-24: Configure](prometheus.md)

-   :material-chart-areaspline:{ .lg .middle } **Grafana**

    ---

    Compatible with Grafana Alerting (new format).
    Webhook contact point with Bearer auth.

    **Setup:** ~3 min
    [:octicons-arrow-right-24: Configure](grafana.md)

-   :fontawesome-brands-gitlab:{ .lg .middle } **GitLab CI/CD**

    ---

    Pipeline events and job failures.
    Automatic correlation with Kubernetes events.

    **Setup:** ~3 min
    [:octicons-arrow-right-24: Configure](gitlab.md)

-   :fontawesome-brands-slack:{ .lg .middle } **Slack**

    ---

    Rich notifications with action buttons.
    Declare incidents without leaving Slack.

    **Setup:** ~2 min
    [:octicons-arrow-right-24: Configure](slack.md)

</div>

## Coming soon

| Connector | Status |
|-----------|--------|
| GitHub Actions | 🔜 In development |
| Datadog | 🔜 Planned |
| PagerDuty | 🔜 Planned |
| AWS CloudWatch | 🔜 Planned |

## Authentication

```
Authorization: Bearer YOUR_API_TOKEN
```

!!! tip "Where to find your token"
    Go to **centinelai.io → Connectors → any connector**
    and you'll see your API Token at the top of the page.

---
hide:
  - navigation
  - toc
---

# centinelAI Documentation

<div class="hero" markdown>

<div class="hero-content" markdown>

## Your SRE that never sleeps. { .hero-title }

centinelAI absorbs all the noise from your infrastructure with AI,
filters 99% automatically and only alerts when something is critical.
**Without changing your stack.**

[Get started in 10 minutes](getting-started/quick-start.md){ .md-button .md-button--primary .hero-cta }
[View connectors](connectors/index.md){ .md-button }

</div>

</div>

---

## How it works

<div class="grid cards" markdown>

-   :material-webhook:{ .lg .middle } **Receives alerts**

    ---

    Webhooks from Kubernetes, Prometheus, Grafana and GitLab.
    Set up in under 10 minutes.

    [:octicons-arrow-right-24: View connectors](connectors/index.md)

-   :material-robot:{ .lg .middle } **AI analyses it**

    ---

    4 agents powered by Claude AI evaluate each alert in context.
    Score from 0 to 100 with a natural language explanation.

    [:octicons-arrow-right-24: AI Pipeline](ai-pipeline/index.md)

-   :material-bell-alert:{ .lg .middle } **Only interrupts when it matters**

    ---

    Only score >70 reaches your team — with probable cause,
    impact and recommended actions.

    [:octicons-arrow-right-24: View notifier](ai-pipeline/notifier.md)

-   :material-file-document-edit:{ .lg .middle } **Automatic postmortem**

    ---

    When an incident is resolved, Claude Sonnet generates the full
    postmortem with timeline and root cause.

    [:octicons-arrow-right-24: View postmortem](ai-pipeline/postmortem.md)

</div>

---

## Available connectors

<div class="grid cards" markdown>

-   :material-kubernetes:{ .lg .middle } **Kubernetes**

    ---

    Python agent in your cluster. Detects CrashLoops, OOMKills,
    ImagePullBackOff and more in real time.

    [:octicons-arrow-right-24: Configure](connectors/kubernetes.md)

-   :material-chart-timeline-variant:{ .lg .middle } **Prometheus / Grafana**

    ---

    Webhook receiver compatible with Alertmanager and Grafana Alerting.
    Zero-config with your existing stack.

    [:octicons-arrow-right-24: Configure](connectors/prometheus.md)

-   :fontawesome-brands-gitlab:{ .lg .middle } **GitLab CI/CD**

    ---

    Detects pipeline failures and correlates deploys with
    infrastructure anomalies automatically.

    [:octicons-arrow-right-24: Configure](connectors/gitlab.md)

-   :fontawesome-brands-slack:{ .lg .middle } **Slack**

    ---

    Rich notifications with action buttons. Declare incidents
    and snooze alerts without leaving Slack.

    [:octicons-arrow-right-24: Configure](connectors/slack.md)

</div>

---

## Plans

| | **Starter** | **Team** | **Pro** |
|--|:-----------:|:--------:|:-------:|
| Price | **€0/mo** | **€99/mo** | **Custom** |
| Services | 5 | 25 | Unlimited |
| Claude AI scoring | ❌ | ✅ | ✅ |
| Slack + Email | ❌ | ✅ | ✅ |
| AI Postmortem | ❌ | ✅ | ✅ |

!!! success "Immediate ROI"
    A 2h incident with 10 engineers = **€4,000**.
    centinelAI Team = **€99/month**. Preventing 1 incident per month → **ROI of 3,940%**.

[Create free account](https://centinelai.io/register){ .md-button .md-button--primary }
[View all plans](plans/index.md){ .md-button }

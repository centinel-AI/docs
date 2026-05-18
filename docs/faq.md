# FAQ

## General

**What is centinelAI?**
An AI-powered observability platform that filters 99% of the noise
and only interrupts your team when something critical needs human attention.

**Does it replace Prometheus, Grafana or Datadog?**
No. It integrates with your existing stack without replacing anything.

**How long does installation take?**
Approximately 10 minutes for the first connector.

## Technical

**What happens if centinelAI has an outage?**
Your alerts keep firing in your existing tools.
centinelAI sits in the notification path, not the monitoring path.

**Where is data stored?**
In Supabase (PostgreSQL) in the EU (Ireland).

**Does the AI have access to my infrastructure?**
No. The agent only reads event metadata (read-only RBAC).
Claude AI only sees event metadata — never your code or data.

**How reliable is the AI score?**

| Alert type | Reliability |
|------------|-------------|
| CrashLoopBackOff | ✅ High |
| OOMKilled | ✅ High |
| ImagePullBackOff | ✅ High |
| Prometheus alerts | 🟡 Medium |
| Business alerts | 🔴 Low |

**Which AI models does centinelAI use?**
- Scorer and Correlator: Claude Haiku
- Notifier and Postmortem: Claude Sonnet

## Privacy

**Does Anthropic have access to my data?**
Data is sent to the Anthropic API for analysis.
Anthropic does not use API data to train models.
See: [anthropic.com/privacy](https://anthropic.com/privacy)

## Pricing

**What does the Starter plan include?**
Free forever, up to 5 services, rule-based scoring.
No credit card required.

**What does the Team plan include?**
€99/month: up to 25 services, Claude AI scoring, Slack, postmortem and correlator.

**How much does the Pro plan cost?**
Custom pricing based on team size.
Write to [info@centinelai.io](mailto:info@centinelai.io?subject=centinelAI Pro).

## Support

**How do I contact support?**
- Email: [info@centinelai.io](mailto:info@centinelai.io)
- Docs: [github.com/centinel-AI/docs](https://github.com/centinel-AI/docs)

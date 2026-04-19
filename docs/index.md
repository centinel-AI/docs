---
hide:
  - navigation
  - toc
---

# centinelAI Documentation

<div class="hero" markdown>

<div class="hero-content" markdown>

## Tu SRE que nunca duerme. { .hero-title }

centinelAI absorbe todo el ruido de tu infraestructura con IA,
filtra el 99% automáticamente y solo avisa cuando hay algo crítico.
**Sin cambiar tu stack.**

[Empezar en 10 minutos](getting-started/quick-start.md){ .md-button .md-button--primary .hero-cta }
[Ver conectores](connectors/index.md){ .md-button }

</div>

</div>

---

## ¿Cómo funciona?

<div class="grid cards" markdown>

-   :material-webhook:{ .lg .middle } **Recibe alertas**

    ---

    Webhooks desde Kubernetes, Prometheus, Grafana y GitLab.
    Instalación en menos de 10 minutos.

    [:octicons-arrow-right-24: Ver conectores](connectors/index.md)

-   :material-robot:{ .lg .middle } **IA lo analiza**

    ---

    4 agentes con Claude AI evalúan cada alerta en contexto.
    Score de 0 a 100 con explicación en lenguaje natural.

    [:octicons-arrow-right-24: Pipeline de IA](ai-pipeline/index.md)

-   :material-bell-alert:{ .lg .middle } **Solo interrumpe cuando importa**

    ---

    Solo score >70 llega a tu equipo. Con causa probable,
    impacto y acciones recomendadas.

    [:octicons-arrow-right-24: Ver notificador](ai-pipeline/notifier.md)

-   :material-file-document-edit:{ .lg .middle } **Postmortem automático**

    ---

    Al resolver un incidente, Claude Sonnet genera el postmortem
    completo con timeline y causa raíz.

    [:octicons-arrow-right-24: Ver postmortem](ai-pipeline/postmortem.md)

</div>

---

## Conectores disponibles

<div class="grid cards" markdown>

-   :simple-kubernetes:{ .lg .middle } **Kubernetes**

    ---

    Agente Python en tu cluster. Detecta CrashLoops, OOMKills,
    ImagePullBackOff y más en tiempo real.

    [:octicons-arrow-right-24: Configurar](connectors/kubernetes.md)

-   :simple-prometheus:{ .lg .middle } **Prometheus / Grafana**

    ---

    Webhook receiver compatible con Alertmanager y Grafana Alerting.
    Zero-config con tu stack existente.

    [:octicons-arrow-right-24: Configurar](connectors/prometheus.md)

-   :simple-gitlab:{ .lg .middle } **GitLab CI/CD**

    ---

    Detecta fallos de pipeline y correlaciona deploys con
    anomalías de infraestructura automáticamente.

    [:octicons-arrow-right-24: Configurar](connectors/gitlab.md)

-   :simple-slack:{ .lg .middle } **Slack**

    ---

    Notificaciones ricas con botones de acción. Declara incidentes
    y silencia alertas sin salir de Slack.

    [:octicons-arrow-right-24: Configurar](connectors/slack.md)

</div>

---

## Planes

| | Starter | Team | Pro |
|--|---------|------|-----|
| **Precio** | 0€/mes | 249€/mes | 499€/mes |
| **Servicios** | 3 | 25 | Ilimitados |
| Score con reglas | ✅ | ✅ | ✅ |
| Score con Claude AI | ❌ | ✅ | ✅ |
| Correlador IA | ❌ | ✅ | ✅ |
| Notificaciones Slack | ❌ | ✅ | ✅ |
| Postmortem con IA | ❌ | ✅ | ✅ |

[Ver todos los planes](plans/index.md){ .md-button }

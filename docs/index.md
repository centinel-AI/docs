---
hide:
  - navigation
  - toc
---

<div class="hero" markdown>

## De 1.000 alertas al día<br>a 3 interrupciones que importan. { .hero-title }

centinelAI absorbe todo el ruido de tu infraestructura con IA,
filtra el 99% automáticamente y solo avisa cuando hay algo crítico.
**Sin cambiar tu stack. Sin agentes complejos.**

[Empezar en 10 minutos →](getting-started/quick-start.md){ .md-button .md-button--primary }
[Ver conectores](connectors/index.md){ .md-button }

</div>

---

## ¿Cómo funciona?

<div class="grid cards" markdown>

-   :material-download-network:{ .lg .middle } **1. Recibe todas las alertas**

    ---

    Webhooks desde Kubernetes, Prometheus, Grafana y GitLab.
    Un agente Python ligero en tu cluster. Instalación en **10 minutos**.

    [:octicons-arrow-right-24: Ver conectores](connectors/index.md)

-   :material-brain:{ .lg .middle } **2. IA lo filtra todo**

    ---

    4 agentes con **Claude AI** evalúan cada alerta en contexto.
    Score de 0 a 100 con explicación en lenguaje natural.

    [:octicons-arrow-right-24: Pipeline de IA](ai-pipeline/index.md)

-   :material-bell-check:{ .lg .middle } **3. Solo interrumpe cuando importa**

    ---

    Solo **score >70** llega a tu equipo. Con causa probable,
    impacto estimado y acciones recomendadas.

    [:octicons-arrow-right-24: Ver notificador](ai-pipeline/notifier.md)

-   :material-file-document-edit:{ .lg .middle } **4. Postmortem automático**

    ---

    Al resolver un incidente, **Claude Sonnet** genera el postmortem
    completo con timeline, causa raíz y acciones preventivas.

    [:octicons-arrow-right-24: Ver postmortem](ai-pipeline/postmortem.md)

</div>

---

## Pipeline de 4 agentes IA

```mermaid
flowchart LR
    A["🔔 1.000 alertas/día\nK8s · Prometheus · GitLab"]
    --> B["1️⃣ Deduplicador\n200 grupos"]
    --> C["2️⃣ Scorer\nClaude Haiku\n40 señales"]
    --> D["3️⃣ Correlador\nClaude Haiku"]
    --> E["4️⃣ Notificador\nClaude Sonnet\n3 avisos útiles"]

    style A fill:#FEF2F2,stroke:#ef4444,color:#1A1A2E
    style B fill:#FFF7ED,stroke:#f97316,color:#1A1A2E
    style C fill:#FEFCE8,stroke:#eab308,color:#1A1A2E
    style D fill:#F0FDF4,stroke:#22c55e,color:#1A1A2E
    style E fill:#F3F1FF,stroke:#5B4FCF,color:#1A1A2E
```

---

## Conectores disponibles

<div class="grid cards" markdown>

-   :simple-kubernetes: **Kubernetes**

    **✅ Disponible** · Setup ~2 min

    Agente Python con RBAC read-only. Detecta CrashLoops, OOMKills,
    ImagePullBackOff y más en tiempo real.

    [:octicons-arrow-right-24: Configurar](connectors/kubernetes.md)

-   :simple-prometheus: **Prometheus / Grafana**

    **✅ Disponible** · Setup ~5 min

    Compatible con Alertmanager y Grafana Alerting.
    Zero-config con tu stack existente.

    [:octicons-arrow-right-24: Configurar](connectors/prometheus.md)

-   :simple-gitlab: **GitLab CI/CD**

    **✅ Disponible** · Setup ~3 min

    Pipeline events y job failures. Correlación automática
    con eventos de Kubernetes.

    [:octicons-arrow-right-24: Configurar](connectors/gitlab.md)

-   :simple-slack: **Slack**

    **✅ Disponible** · Setup ~2 min

    Notificaciones ricas con botones de acción. Declara incidentes
    y silencia alertas sin salir de Slack.

    [:octicons-arrow-right-24: Configurar](connectors/slack.md)

</div>

---

## Planes

| | **Starter** | **Team** | **Pro** |
|--|:-----------:|:--------:|:-------:|
| Precio | **0€/mes** | **249€/mes** | **499€/mes** |
| Servicios | 3 | 25 | Ilimitados |
| Score con Claude AI | ❌ | ✅ | ✅ |
| Slack + Email | ❌ | ✅ | ✅ |
| Postmortem IA | ❌ | ✅ | ✅ |

!!! success "ROI inmediato"
    Un incidente de 2h con 10 ingenieros = **4.000€**.
    centinelAI Team = **249€/mes**. Previniendo 1 incidente al mes → **ROI 1.507%**.

[Crear cuenta gratis](https://centinelai.io/register){ .md-button .md-button--primary }
[Ver todos los planes](plans/index.md){ .md-button }

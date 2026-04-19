# Conectores

centinelAI recibe alertas a través de webhooks HTTP autenticados
o mediante el agente de Kubernetes.

## Disponibles

<div class="grid cards" markdown>

-   :simple-kubernetes:{ .lg .middle } **Kubernetes**

    ---

    Agente Python con RBAC de solo lectura.
    Detecta eventos en tiempo real sin configuración adicional.

    **Setup:** ~2 min
    [:octicons-arrow-right-24: Configurar](kubernetes.md)

-   :simple-prometheus:{ .lg .middle } **Prometheus**

    ---

    Compatible con Alertmanager webhook v4.
    Cero cambios en tu configuración existente.

    **Setup:** ~5 min
    [:octicons-arrow-right-24: Configurar](prometheus.md)

-   :simple-grafana:{ .lg .middle } **Grafana**

    ---

    Compatible con Grafana Alerting (nuevo formato).
    Contact point tipo Webhook con Bearer auth.

    **Setup:** ~3 min
    [:octicons-arrow-right-24: Configurar](grafana.md)

-   :simple-gitlab:{ .lg .middle } **GitLab CI/CD**

    ---

    Pipeline events y job failures.
    Correlación automática con eventos de Kubernetes.

    **Setup:** ~3 min
    [:octicons-arrow-right-24: Configurar](gitlab.md)

-   :simple-slack:{ .lg .middle } **Slack**

    ---

    Notificaciones ricas con botones de acción.
    Declara incidentes sin salir de Slack.

    **Setup:** ~2 min
    [:octicons-arrow-right-24: Configurar](slack.md)

</div>

## Próximamente

| Conector | Estado |
|----------|--------|
| GitHub Actions | 🔜 En desarrollo |
| Datadog | 🔜 Planificado |
| PagerDuty | 🔜 Planificado |
| AWS CloudWatch | 🔜 Planificado |

## Autenticación

Todos los endpoints usan Bearer token:

```bash
Authorization: Bearer TU_API_TOKEN
```

!!! tip "¿Dónde encuentro mi token?"
    Ve a **centinelai.io → Conectores → cualquier conector** 
    y verás tu API Token en la parte superior de la página.

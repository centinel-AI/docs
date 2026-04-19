# Dashboard

El dashboard de centinelAI muestra el estado en tiempo real
de toda tu infraestructura monitorizada.

## Secciones principales

<div class="grid cards" markdown>

-   :material-view-dashboard:{ .lg .middle } **Servicios**

    ---

    ServiceCards con estado (UP/DEGRADED/DOWN), score de riesgo
    y sparklines de actividad de las últimas 2 horas.

    [:octicons-arrow-right-24: Ver guía](services.md)

-   :material-alert-circle:{ .lg .middle } **Incidentes**

    ---

    Gestión completa de incidentes con vista lista y timeline.
    Postmortem automático al resolver.

    [:octicons-arrow-right-24: Ver guía](incidents.md)

-   :material-archive:{ .lg .middle } **Archivo de alertas**

    ---

    Historial completo de todas las alertas recibidas
    con filtros por severidad, source y score.

    [:octicons-arrow-right-24: Ver guía](alerts-archive.md)

</div>

## Stats en tiempo real

| Métrica | Descripción |
|---------|-------------|
| **Alerts today** | Total de alertas recibidas hoy |
| **Filtered** | Alertas absorbidas sin interrumpir al equipo |
| **Interruptions sent** | Notificaciones enviadas a Slack/Email |
| **Open incidents** | Incidentes activos actualmente |

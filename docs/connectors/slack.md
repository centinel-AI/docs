# Slack

Slack es un conector de **salida** — centinelAI envía notificaciones
cuando detecta alertas críticas (score > 70).

## Configuración

!!! note "Paso 1 — Crea una Slack App"
    Ve a [api.slack.com/apps](https://api.slack.com/apps) →
    **Create New App → From scratch**

    - Nombre: `centinelAI`
    - Selecciona tu workspace

!!! note "Paso 2 — Añade los scopes"
    **OAuth & Permissions → Bot Token Scopes:**

    - `chat:write`
    - `chat:write.public`
    - `channels:read`

!!! note "Paso 3 — Instala y copia el token"
    Click **Install to Workspace** → autoriza.
    Copia el **Bot User OAuth Token** (`xoxb-...`).

    Además, activa **Interactivity & Shortcuts → ON** con Request URL:
    `https://centinelai.io/api/slack/actions`

!!! note "Paso 4 — Configura en centinelAI"
    Ve a [centinelai.io/connectors/slack](https://centinelai.io/connectors/slack)
    e introduce el token y el canal (ej: `#alerts`).

!!! note "Paso 5 — Invita el bot"
    En Slack, dentro del canal `#alerts`:
    ```
    /invite @centinelAI
    ```

!!! success "Slack configurado"
    Las alertas con score >70 llegarán a tu canal con botones de acción.

---

## Botones de acción

| Botón | Acción |
|-------|--------|
| 🚨 Declarar incidente | Crea un incidente en centinelAI |
| 💤 Snooze 1h | Silencia la alerta 1 hora |
| 📊 Ver dashboard | Abre el dashboard |

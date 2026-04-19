# Slack

Slack es un conector de **salida** — centinelAI envía notificaciones
cuando detecta alertas críticas (score > 70).

## Configuración

### 1. Crea una Slack App
[api.slack.com/apps](https://api.slack.com/apps) → **Create New App → From scratch**
- Nombre: `centinelAI`
- Selecciona tu workspace

### 2. Añade Bot Token Scopes
**OAuth & Permissions → Bot Token Scopes**:
- `chat:write`
- `chat:write.public`
- `channels:read`

### 3. Instala en tu workspace
Click **Install to Workspace** → autoriza.
Copia el **Bot User OAuth Token** (`xoxb-...`).

### 4. Activa Interactivity
**Interactivity & Shortcuts → ON**
Request URL: `https://centinelai.io/api/slack/actions`

### 5. Configura en centinelAI
**centinelai.io → Conectores → Slack**:
- Bot Token (`xoxb-...`)
- Canal (ej: `#alerts`)
- Click **Guardar**

### 6. Invita el bot al canal
```
/invite @centinelAI
```

## Botones de acción

| Botón | Acción |
|-------|--------|
| 🚨 Declarar incidente | Crea un incidente en centinelAI |
| 💤 Snooze 1h | Silencia la alerta 1 hora |
| 📊 Ver dashboard | Abre el dashboard |

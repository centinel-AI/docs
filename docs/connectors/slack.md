# Slack

Slack is an **output** connector — centinelAI sends notifications
when it detects critical alerts (score > 70).

## Setup

### 1. Create a Slack App
[api.slack.com/apps](https://api.slack.com/apps) → **Create New App → From scratch**
- Name: `centinelAI`
- Select your workspace

### 2. Add Bot Token Scopes
**OAuth & Permissions → Bot Token Scopes**:
- `chat:write`
- `chat:write.public`
- `channels:read`

### 3. Install to workspace
Click **Install to Workspace** → authorize.
Copy the **Bot User OAuth Token** (`xoxb-...`).

### 4. Enable Interactivity
**Interactivity & Shortcuts → ON**
Request URL: `https://centinelai.io/api/slack/actions`

### 5. Configure in centinelAI
**centinelai.io → Connectors → Slack**:
- Bot Token (`xoxb-...`)
- Channel (e.g. `#alerts`)
- Click **Save**

### 6. Invite the bot to the channel
```
/invite @centinelAI
```

## Action buttons

| Button | Action |
|--------|--------|
| 🚨 Declare incident | Creates an incident in centinelAI |
| 💤 Snooze 1h | Silences the alert for 1 hour |
| 📊 View dashboard | Opens the centinelAI dashboard |

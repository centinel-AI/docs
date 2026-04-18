# Pipeline de IA

## Flujo completo

```
Webhook recibido
    ↓ centinelai/alert.received
[1] Deduplicador (reglas)
    ↓ centinelai/group.created
[2] Scorer — Claude Haiku
    ↓ centinelai/group.scored
[3] Correlador — Claude Haiku
    ↓ centinelai/group.critical (score > 70)
[4] Notificador — Claude Sonnet
    ↓
Slack + Email
```

## Agentes

| Agente | Modelo | Función |
|--------|--------|---------|
| [Deduplicador](./deduplicator.md) | Reglas | Agrupa eventos similares en 5 min |
| [Scorer](./scorer.md) | Claude Haiku | Puntúa 0-100 |
| [Correlador](./correlator.md) | Claude Haiku | Encuentra patrones entre servicios |
| [Notificador](./notifier.md) | Claude Sonnet | Genera notificación con causa y acciones |
| [Postmortem](./postmortem.md) | Claude Sonnet | Análisis post-incidente |

# Incidentes

La sección de incidentes permite gestionar eventos críticos declarados
por el equipo y ver los postmortems generados por IA.

## Ciclo de vida de un incidente

```
OPEN → INVESTIGATING → RESOLVED
```

| Estado | Descripción |
|--------|-------------|
| OPEN | Incidente declarado, sin asignar |
| INVESTIGATING | Alguien está trabajando en ello |
| RESOLVED | Incidente cerrado — se genera postmortem |

## Crear un incidente

Desde el dashboard:
1. Click **Declarar incidente** en una ServiceCard o alerta
2. Añade título y severidad
3. El incidente queda abierto y visible para todo el equipo

Desde Slack:
- Click en el botón **🚨 Declarar incidente** de una notificación

## Resolver un incidente

1. Abre el incidente desde la lista
2. Click **Resolver incidente**
3. Añade una nota de resolución (opcional)
4. centinelAI genera automáticamente el postmortem (planes Team/Pro)

## Postmortem

Al resolver, el postmortem aparece en la pestaña **Postmortem** del incidente.
Puede exportarse en formato `.md` para incluirlo en la wiki del equipo.

Ver [Generador de Postmortem](../ai-pipeline/postmortem.md) para más detalles.

# Notificador

## Función
Genera notificaciones en lenguaje natural y las envía a Slack y/o Email
cuando un grupo supera score > 70.

## Modelo
Claude Sonnet

## Disponibilidad
Solo disponible en planes **Team** y **Pro**.

## Estructura del mensaje Slack

```
🔴 CRITICAL — api-payments (score: 92)

CrashLoopBackOff en production/api-payments-abc
15 reinicios en los últimos 10 minutos.

Causa probable: fallo en la conexión a base de datos
tras el deploy de las 10:03.

Acciones recomendadas:
• Revisar logs: kubectl logs -n production api-payments-abc
• Verificar conectividad a PostgreSQL
• Considerar rollback al deploy anterior

[🚨 Declarar incidente] [💤 Snooze 1h] [📊 Ver dashboard]
```

## Canales de notificación

| Canal | Configuración |
|-------|--------------|
| Slack | Bot Token + canal en **Conectores → Slack** |
| Email | Dirección configurada en **Ajustes → Notificaciones** |

## Umbral de notificación

Solo se notifica cuando `score >= 70`. Configurable por servicio
desde el dashboard en **Servicios → [servicio] → Ajustes**.

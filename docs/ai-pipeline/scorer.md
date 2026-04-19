# Alert Scorer

## Función
Evalúa cada grupo de alertas y asigna un score de 0-100.

## Factores de scoring (Claude Haiku)

- Tipo de alerta (`CrashLoopBackOff` > `BackOff`)
- Número de eventos y frecuencia
- Criticidad del servicio
- Historial de alertas similares

## Score con reglas (plan Starter)

| Reason | Score |
|--------|-------|
| CrashLoopBackOff | 85 |
| OOMKilled | 80 |
| NodeNotReady | 90 |
| ImagePullBackOff | 60 |
| BackOff | 40 |

## Score con IA (plan Team/Pro)

Claude Haiku analiza el contexto completo y genera un score
con explicación en lenguaje natural.

Ejemplo de score_reason:
> "CrashLoopBackOff crítico en servicio de pagos en producción.
> 15 reinicios en 10 minutos indica fallo persistente, no transitorio.
> Alto impacto en negocio. Score: 92/100"

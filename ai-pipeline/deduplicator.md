# Deduplicador

## Función
Agrupa eventos similares del mismo servicio para evitar notificaciones duplicadas.

## Algoritmo

El deduplicador opera con ventanas de **5 minutos**. Cuando llega un nuevo evento:

1. Busca un grupo abierto del mismo servicio con el mismo `reason`
2. Si existe, añade el evento al grupo y actualiza el contador
3. Si no existe, crea un nuevo grupo y emite `centinelai/group.created`

## Criterios de agrupación

| Campo | Uso |
|-------|-----|
| `serviceId` | Identifica el servicio afectado |
| `reason` | Tipo de evento (`CrashLoopBackOff`, etc.) |
| Ventana temporal | 5 minutos desde el primer evento |

## Resultado

50 eventos del mismo `CrashLoopBackOff` en el mismo pod
generan **1 único grupo** con `count: 50`.

## Disponibilidad

Disponible en todos los planes (Starter, Team, Pro).

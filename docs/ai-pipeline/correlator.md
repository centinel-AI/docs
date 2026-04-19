# Correlador

## Función
Detecta patrones y relaciones entre alertas de distintos servicios
para identificar causas raíz sistémicas.

## Modelo
Claude Haiku

## Disponibilidad
Solo disponible en planes **Team** y **Pro**.

## Cómo funciona

Cuando un grupo recibe un score > 30, el correlador analiza:
- Alertas activas en otros servicios del mismo namespace
- Eventos recientes de infraestructura (nodos, red)
- Fallos de pipeline de GitLab del mismo repositorio

Si detecta un patrón, enriquece el grupo con un campo `correlations`:

```json
{
  "correlations": [
    {
      "serviceId": "production/api-gateway",
      "reason": "HighLatency",
      "confidence": 0.87,
      "explanation": "El servicio api-gateway muestra latencia alta desde el mismo timestamp"
    }
  ]
}
```

## Ejemplo de correlación

Un `NodeNotReady` en `node-3` puede correlacionar automáticamente con
todos los pods que corren en ese nodo, elevando el score de cada uno
e identificando la causa raíz como un fallo de nodo, no de aplicación.

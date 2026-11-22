# Segunda mirada

Un `discoverme:revisor`, que no vio la investigación, revisa lo que vas a mostrar: propuestas de síntesis, la estructura de un informe integrado, o un informe (nuevo o una versión nueva).

1. Guarda lo que vas a mostrar (`guardado.md`) y lanza el `revisor` con qué revisar, su ruta, la referencia o plantilla que lo rige y las rutas del registro de evidencia y de las fichas.
2. Resuelve cada bloqueante y pide una confirmación: reanuda al mismo revisor (`SendMessage` a su id) con lo que cambiaste; si no puedes, lanza otro solo con los bloqueantes. Es una sola vuelta: lo que corrijas después de ella se lo dices al usuario.
3. Al presentar, incluye los desafíos que no incorporaste, cada uno con tu respuesta: el usuario ve el debate y decide.

Si no puedes lanzar subagentes, revisa tú con `../agents/revisor.md`, en una pasada aparte y después de guardar.

**Terminado cuando:** el revisor confirmó cada bloqueante, o le dijiste al usuario cuál quedó sin confirmar, y los desafíos abiertos van en lo que ve el usuario.

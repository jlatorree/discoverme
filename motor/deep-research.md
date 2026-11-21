# Deep research

Una investigación la lleva de principio a fin un solo `discoverme:investigador`. Así, quien redacta el informe vio todo lo investigado, y la sesión principal guarda solo la conversación y las decisiones del usuario.

## Roles

| Rol | Quién | Modelo y esfuerzo |
|---|---|---|
| Conversar con el usuario: encuadre, puntos de control, tareas de primera mano, decisiones | La sesión principal, con el skill | Los de la sesión |
| Planificar, repartir, verificar, sintetizar y redactar | Agente `discoverme:investigador` | Opus, xhigh (Extra en la app) |
| Buscar y leer una subpregunta | Agente `discoverme:buscador` | Opus, alto |
| Leer un documento largo | Agente `discoverme:lector` | Opus, alto |

El esfuerzo del investigador no depende del que tenga la sesión. La mayor parte de los tokens (buscar y leer) va en alto.

## Puntos de control

El investigador no habla con el usuario. Todo lo que requiere al usuario (una decisión, un permiso, una anomalía que evaluar juntos) va como punto de control. Cuando el skill marca uno, o el investigador necesita uno, el investigador termina su turno con su propuesta y la pregunta exacta. La sesión se la presenta al usuario, desafía donde haga falta y **reanuda al mismo investigador** con `SendMessage` a su id, pasando la respuesta del usuario textual. Un investigador reanudado conserva todo lo que ya investigó.

## Memoria en disco

Cada nota tiene un solo escritor: los `buscador` y los `lector` devuelven su trabajo, y el investigador escribe. La sesión escribe solo el brief. El investigador guarda en el disco, a medida que avanza, todo lo que verifica o deduce: registro de evidencia, fichas, perfiles y borradores, según `guardado.md`. Si el investigador ya no está (otra sesión, una reanudación que falla), la sesión lanza uno nuevo con las rutas, y retoma desde ahí.

## Procedimiento del investigador

1. **Plan.** Divide la pregunta en 3–6 subpreguntas que no se pisen, cada una con qué responde y qué fuentes priorizar. El plan va en el primer punto de control.
2. **Reparto.** Lanza un `buscador` por subpregunta, en paralelo, cada uno con un encargo que se sostenga solo: la subpregunta, el contexto en dos frases, los criterios de fuentes, lo ya registrado y el formato de vuelta. Cada documento largo va a un `lector`. Si no puedes lanzar subagentes, investiga cada subpregunta tú, una a una.
3. **Verificación.** Verifica cada DOI (`fuentes-academicas.md`), reabre al menos una URL por subpregunta y confirma que dice lo atribuido, une duplicados y marca los vacíos y las contradicciones. Un vacío importante se cubre con una segunda vuelta acotada.
4. **Síntesis y redacción.** Con la plantilla y las reglas de cita del skill. Antes de entregar, pasa su control de calidad.

**Terminado cuando:** cada subpregunta tiene respuesta o un vacío declarado, cada fuente citada está verificada, y el informe está guardado y pasó el control de calidad de su plantilla.

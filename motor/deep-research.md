# Deep research

## Equipo

- `discoverme:buscador`: busca y lee una subpregunta.
- `discoverme:lector`: lee un documento largo.

Trabajan en paralelo, cada uno con su propio contexto, y devuelven solo lo encontrado. Así el tuyo queda para la conversación, la verificación y la síntesis. Si no puedes lanzar subagentes, investiga cada subpregunta tú, una a una.

## Procedimiento

1. **Plan.** Divide la pregunta en 3–6 subpreguntas que no se pisen, cada una con qué responde y qué fuentes priorizar, y revisa las herramientas de captura (`captura-web.md`, "Antes de la pasada profunda"). Preséntalo como punto de control; si el método ya tiene uno en esta fase, va en el mismo.
2. **Reparto.** Lanza un `buscador` por subpregunta, en paralelo, cada uno con un encargo que se sostenga solo: la subpregunta, el contexto en dos frases sin datos confidenciales, qué fuentes priorizar, lo ya registrado o fichado, las herramientas de captura disponibles, la ruta absoluta de la carpeta de capturas y el formato de vuelta. Cada documento largo va a un `lector`.
3. **Verificación.** Verifica cada DOI (`../skills/doime/references/fuentes-academicas.md`), reabre al menos una URL por subpregunta y confirma que dice lo atribuido, busca cada cita literal en su captura, une duplicados y marca los vacíos y las contradicciones. Un vacío importante se cubre con una segunda vuelta acotada.
4. **Guardado.** Guarda lo verificado (`guardado.md`) y sigue con la fase del método.

**Terminado cuando:** cada subpregunta tiene respuesta o un vacío declarado, cada fuente citada está verificada, y lo investigado está guardado.

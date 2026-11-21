# Deep research

Cómo se reparte una investigación grande entre subagentes, y con qué modelo y esfuerzo trabaja cada rol. Lo usan benchme (evidencia de varias alternativas) y doime (revisión completa).

## Roles

| Rol | Quién | Modelo y esfuerzo |
|---|---|---|
| Orquestar: plan, reparto, verificación y decisión | La sesión principal, con el skill | La del usuario |
| Buscar y leer una subpregunta | Agente `discoverme:investigador` | Opus, alto |
| Leer un documento largo (PDF, informe, transcripción) | Agente `discoverme:lector` | Opus, alto |
| Sintetizar y redactar el informe | Agente `discoverme:redactor` | Opus, xhigh |

El esfuerzo máximo va solo a la síntesis, que es donde se juega la calidad del juicio. Si en una investigación real la búsqueda rinde poco, se sube solo ese rol.

Si usas un skill de deep research que lance sus propios subagentes (por ejemplo `deep-research`), pide en cada uno el modelo `opus` con esfuerzo alto, y deja la redacción al `redactor`.

## Pasos

1. **Plan.** Divide la pregunta en 3–6 subpreguntas que no se pisen. Cada una lleva qué responde, qué fuentes priorizar y qué ya está fichado o registrado, para no repetirlo. Muéstrale el plan al usuario antes de lanzar.
2. **Reparto.** Lanza un `investigador` por subpregunta, en paralelo, cada uno con su encargo completo: la subpregunta, el contexto en dos frases, los criterios de fuentes del skill y el formato de vuelta. Los documentos largos que aparezcan van a un `lector` cada uno.
3. **Verificación.** Con lo que vuelve: verifica cada DOI (`fuentes-academicas.md`), reabre al menos una URL por subpregunta y confirma que dice lo atribuido, une duplicados y marca los vacíos y las contradicciones entre subpreguntas. Un vacío importante se cubre con una segunda vuelta acotada.
4. **Síntesis.** Pasa al `redactor` las rutas del material verificado (fichas, registro de evidencia), la plantilla del informe y dónde guardarlo. Revisa su borrador contra las reglas del skill antes de mostrarlo.

**Terminado cuando:** cada subpregunta tiene respuesta o un vacío declarado, cada fuente citada está verificada y el informe del `redactor` pasó la revisión.

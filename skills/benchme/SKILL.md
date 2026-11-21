---
name: benchme
description: 'Benchmark estratégico co-creado: ubica un producto o servicio frente a sus alternativas reales y decide qué igualar, de qué diferenciarse, qué vigilar y qué ignorar. Úsalo cuando pidan un benchmark o análisis competitivo, actualizar uno existente, o su versión ejecutiva o presentación.'
---

# benchme

Co-creas un benchmark con un strategic designer con experiencia. El resultado es un juicio fechado sobre qué hacer frente a las alternativas del cliente. El riesgo que el skill combate es la **convergencia**: terminar igual que todos por compararse con todos.

Pregunta directo y en español; el usuario conoce los marcos, así que explícalos solo si los pide. Pregunta solo lo que cambia el benchmark.

## Reparto

- **El usuario encuadra, elige y juzga**: la decisión, el propósito, sus hipótesis, las alternativas, los pesos, la profundidad, la paradoja central, las posturas y qué sale al comité.
- **Tú conversas**: llevas el triaje y el brief, presentas cada punto de control, desafías y acompañas las tareas de primera mano del usuario.
- **El investigador investiga**: un `discoverme:investigador` reúne, etiqueta, analiza, propone y redacta, según `../../motor/deep-research.md`. Lo lanzas en el paso 2 y lo reanudas en cada paso siguiente con la referencia del paso y la respuesta del usuario, textual.

## Elige la rama

Detecta el modo de guardado (con brainme, invócalo primero) y busca si ya existe un benchmark del tema (`../../motor/guardado.md`).

- **Nuevo** → Flujo.
- **Actualizar** uno existente → Actualizar.
- **Derivar** su versión ejecutiva o una presentación → Derivados.

## Flujo

### 0. Triaje

Clasifica el pedido, propón el modo y deja que el usuario confirme:

- **Paridad**: qué es estándar en la categoría o en una convención → modo **ligero**.
- **Decisión**: el benchmark informa una decisión concreta → modo **completo**.
- **Sin decisión** ("ver qué hace la competencia") → ofrece ambas cosas: el chequeo de paridad ahora, y las tres preguntas del encargo (en el brief) que lo convierten en insumo de decisión. Reencuadras; el pedido siempre recibe respuesta.

Modo ligero: brief de encargo, alternativas, evidencia, imperativos operativos y un informe corto. Los pasos 4 y 5 se hacen en versión breve.

**Terminado cuando:** el usuario confirmó tipo de pedido y modo.

### 1. Brief

Sigue `references/brief.md`.

**Terminado cuando:** el brief está guardado con decisión, encargo, alcance, propósito, profundidad y las hipótesis del usuario, escritas por él antes de ver cualquier síntesis. Lo que no sepa queda "por confirmar con <quién>" y el brief sale listo para reenviar.

### 2. Alternativas

Lanza el investigador con la ruta del brief, el modo, las rutas de guardado y `references/alternativas.md`. Vuelve con el set propuesto como punto de control.

**Terminado cuando:** el usuario aprobó el set, armado con una pasada liviana; cada inclusión y cada exclusión tiene su argumento, con evidencia o marcado como supuesto.

### 3. Evidencia

Antes, revisa con el usuario las herramientas de captura (`../../motor/captura-web.md`, "Antes de la pasada profunda"). Reanuda al investigador con el set aprobado, las herramientas disponibles, `../../motor/evidencia.md` y `../../motor/captura-web.md`. Cuando un criterio o una afirmación necesite respaldo académico, el investigador usa el skill doime en pasada liviana. En paralelo, asigna al usuario sus tareas de primera mano (`../../motor/evidencia.md`, "Primera mano") con sus guías.

**Terminado cuando:** cada alternativa en profundidad tiene evidencia fechada y etiquetada en el registro, cada URL citada fue reabierta y respalda lo atribuido, y las tareas de primera mano figuran como hechas o pendientes.

### 4. Análisis

Reanuda al investigador con `references/analisis.md`. Vuelve con los perfiles y, como punto de control, las pistas sobre los supuestos de la dirección de cada alternativa.

**Terminado cuando:** cada alternativa en profundidad tiene su perfil completo, y la pregunta por los supuestos de su dirección tiene la respuesta del usuario o queda abierta.

### 5. Síntesis

Reanuda al investigador con `references/sintesis.md`. Vuelve con sus propuestas como punto de control; tú desafías y el usuario elige.

**Terminado cuando:** las convenciones de la categoría están contrastadas con los primeros principios; cada ítem comparado tiene postura, razón y evidencia; el steelman de la opción descartada está escrito; el usuario eligió la paradoja central; pasaron las pruebas de cierre; y la vigilancia tiene tripwires.

### 6. Informe madre

Reanuda al investigador con `references/plantillas/informe.md` y las decisiones del usuario. Revisa su borrador antes de mostrarlo. El **informe madre** es siempre el entregable principal; todo lo demás deriva de él.

**Terminado cuando:** el informe vigente está guardado según `../../motor/guardado.md`, la versión anterior (si existe) está en `versiones/` y pasó el control de calidad de la plantilla. Al cerrar, ofrece los derivados.

## Actualizar

Lanza un investigador con el informe vigente y el conocimiento del benchmark (brief, evidencia, perfiles y vigilancia):

1. Revisa cada tripwire y cada suposición: qué cambió.
2. Refresca la evidencia caducada (precios e interfaces primero) y agrega la nueva con fecha.
3. Rehaz con el usuario solo las fases afectadas, con sus puntos de control.
4. Guarda una versión nueva del informe con su registro de cambios: qué cambió y por qué.

**Terminado cuando:** la versión nueva está guardada, el registro de cambios está escrito, cada tripwire está revisado y avisaste qué derivados quedaron desactualizados.

## Derivados

Salen siempre del informe vigente y declaran de qué versión salen.

- **Ejecutiva** → la redacta un investigador con `references/plantillas/ejecutiva.md`.
- **Presentación HTML**, completa o ejecutiva → tú, con `references/presentaciones.md`.

**Terminado cuando:** el derivado está guardado según `../../motor/guardado.md` y declara su versión de origen.

## Guardarraíles

Valen en todas las ramas, para ti y para el investigador.

**Evidencia**
- Cada afirmación remite a una entrada del registro (`../../motor/evidencia.md`).
- Produces coherencia con facilidad, y la coherencia no prueba nada: cada conclusión se apoya en evidencia observada.
- Fuentes públicas y acceso sin login (`../../motor/captura-web.md`). Antes de usar datos internos o de clientes, pregunta.

**Contra la convergencia**
- Cada ítem termina en una postura. El informe compara posturas.
- Recomienda una sola estrategia; si dos opciones se contradicen, el usuario elige.
- Las decisiones de no igualar quedan escritas.

**Contra la copia**
- Toda práctica tomada de otro va con el sistema que la hace funcionar.
- La evidencia incluye fracasos además de éxitos.

**Ética**
- Registros con identidad falsa o compras encubiertas solo con decisión expresa del usuario y dentro de los términos de servicio.

**Formato**
- Títulos en lenguaje de negocio; los marcos van por dentro.
- Las diferencias se presentan como opciones, con un color neutro por postura.

## Referencias

- `references/fuentes.md`: la versión vigente de cada marco que usa el skill, con su fuente y la regla para actualizarla. Consúltala al citar un marco o si el usuario pregunta por su origen.

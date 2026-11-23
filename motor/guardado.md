# Guardado y versiones

## Detecta el modo

- **Con brainme**: el `CLAUDE.md` de la carpeta tiene la sección `## brainme`, o la carpeta tiene `05_exports/` y `01_knowledge/`.
- **Multiproyecto de brainme**: el `CLAUDE.md` tiene la sección `## brainme · multiproyecto` (o `## brainme · espacio`). Los proyectos están en subcarpetas (`proyectos/<año>/<proyecto>/`): pregunta en cuál guardar y sigue con brainme en ese.
- **Sin brainme**: cualquier otro caso. Si la carpeta del proyecto no es clara, pregunta una vez dónde crear `investigacion/`.

Cada encargo tiene un `<tema>` corto, en minúsculas y con guiones (`seguro-vehicular`), y un **archivo del encargo**: los métodos, la pregunta o decisión, el modo o nivel, la fase actual (una sola, siempre al día), el plan y los sets aprobados, y lo que el usuario decidió en cada punto de control, textual. Es lo que otra sesión lee para retomar.

## Con brainme

discoverme escribe en las carpetas de brainme, con sus tipos de nota, y deja a brainme comprobar lo guardado, actualizar su tablero y escribir su bitácora. Para guardar bastan esta página y las notas que ya hay; a brainme lo invoca el usuario, o el `CLAUDE.md` del proyecto si lo pide. Lo que vale guardar como nota es lo que se dedujo; las capturas web y los papers son originales, y las notas apuntan a ellos.

| Qué | Tipo | Carpeta | Nombre |
|---|---|---|---|
| Informe madre, ejecutiva, informe de literatura | entregable | `05_exports/reports/<nombre>/` | `benchmark-<tema>`, `benchmark-<tema>-ejecutiva`, `literatura-<tema>` |
| Informe integrado | entregable | `05_exports/reports/<nombre>/` | `integrado-<tema>` |
| Presentaciones HTML, cada una con su ficha de entregable | entregable | `05_exports/presentations/<nombre>/` | `benchmark-<tema>-deck`, `benchmark-<tema>-deck-ejecutivo` |
| Brief, registro de evidencia, síntesis, vigilancia | conocimiento | `01_knowledge/` | `benchmark-<tema>-brief`, `…-evidencia`, `…-sintesis`, `…-vigilancia` |
| Perfil de cada alternativa; si ya existe, se actualiza | conocimiento | `01_knowledge/` | `<alternativa>` |
| Decisión que informó el encargo, y posturas decididas con su porqué y lo descartado | decision | `02_decisions/` | `benchmark-<tema>-posturas`, `literatura-<tema>-decision` |
| Vacíos, y contradicciones con una decisión vigente | pregunta, una por archivo | `03_open_questions/` | la pregunta en pocas palabras |
| Paper; si ya existe, se amplía | literatura, con `../skills/doime/references/ficha.md` | `04_sources/literature/` | `apellido-anio-palabra-clave` |
| Fuente web no académica que sustenta algo clave | fuente-web | `04_sources/web/` | `sitio-tema` |
| Capturas de páginas y flujos | material de trabajo | `_taller/capturas/<sitio>/<AAAA-MM-DD>/` | — |
| Archivo del encargo | material de trabajo | `_taller/encargos/` | `<tema>` |
| Estructura del informe integrado, que edita el usuario | material de trabajo | `_taller/` | `integrado-<tema>-estructura` |

**Nombres.** Minúsculas, con guiones y sin tildes. Si el `CLAUDE.md` del proyecto declara un **Prefijo de notas**, todos los nombres de la tabla empiezan con él (`acme-benchmark-<tema>-brief`), también las carpetas de los entregables. Los originales y lo de `_taller/` van sin prefijo.

**Al actualizar una nota**, conserva su `origen` y las líneas de su `## Actualizaciones`, y agrega ahí una línea con la fecha y qué cambió.

**Forma de cada nota.** Antes de crear una nota de un tipo, abre una existente del mismo tipo en el proyecto y sigue su forma: frontmatter y secciones. Si no hay ninguna, usa este frontmatter:

- Todas: `titulo`, `tipo`, `fecha`, `proyecto`, `resumen` (una o dos frases), `tags`, `relacionadas` (wikilinks) y `origen: "discoverme <tema> AAAA-MM-DD"`.
- Conocimiento, decisión, pregunta e informe: `autor`, el mismo de las notas del proyecto; si no hay ninguna, pregúntaselo al usuario una vez.
- Informe (`.md` en `05_exports/`): `tipo: entregable`, `version` y `estado` (borrador, en revisión o final), además de lo que pida la plantilla de su método. Si se apoya en notas con `certeza: supuesto`, el texto dice cuáles.
- Registro de evidencia: `largo: si`.
- Conocimiento: `certeza: confirmado` si se apoya en evidencia observada con confianza alta, `certeza: supuesto` si es interpretada o su confianza es moderada o baja; y `como_se_sabe`: la fuente, con el wikilink a su ficha si la tiene, y la fecha de verificación (`"Pérez 2023, [[perez-2023-onboarding-pymes]], verificado 2026-11-21"`).
- Decisión: `estado` (propuesta o tomada) y, si está tomada, `decidido_por`.
- Pregunta: `estado: abierta`, `prioridad` y `quien_puede_responder`.
- Fuente web: `source_url`, `sitio`, `consultado` y `fiabilidad`.
- Ficha de entregable (lo que no es `.md`): `formato`, `archivo`, `version`, `estado` y `generado_con: discoverme`.

Cada entregable va en su carpeta con su versión en el nombre (`literatura-<tema>/literatura-<tema>-v1.md`) y enlaza con wikilinks lo que lo sustenta. Dentro de una tabla, el alias de un wikilink va con `\|` (`[[nota\|E12]]`). Los wikilinks a un entregable llevan su versión (`[[literatura-<tema>-v1]]`); al salir una versión nueva, apúntalos a ella. Lo que ya hay de un tema se encuentra por el nombre de sus notas.

## Sin brainme

```
investigacion/
  indice.md                          un encargo por fila
  encargos/<tema>.md                 archivo del encargo
  benchmarks/<tema>/                 benchme
    conocimiento/                    canónico y vivo: se actualiza en su lugar
      brief.md
      evidencia.md
      sintesis.md
      vigilancia.md
      alternativas/<alternativa>.md
    entregables/
      informe/          <tema>-informe-vN.md + versiones/
      ejecutiva/        <tema>-ejecutiva-vN.md + versiones/
      presentaciones/   <tema>-deck-vN.html, <tema>-deck-ejecutivo-vN.html + versiones/
  literatura/<tema>/                 doime
    informe/            literatura-<tema>-vN.md + versiones/
  integrados/<tema>/                 informe integrado
    <tema>-estructura.md             la edita el usuario
    informe/            <tema>-integrado-vN.md + versiones/
  fichas/                            una por paper, compartidas entre temas y métodos
  capturas/<sitio>/<AAAA-MM-DD>/     páginas y flujos capturados
```

`indice.md` es una tabla: tema, método, decisión que informa, estado (en curso, entregado o en pausa), ruta del entregable vigente y fecha de actualización. Lo que ya hay de un tema se encuentra ahí.

La primera vez que crees `investigacion/` en un proyecto, menciona en una línea que brainme puede llevar estas notas como segundo cerebro del proyecto: si brainme está entre tus skills, que lo configure; si no, que lo instale desde `github.com/jlatorree/brainme`. Una sola vez.

## Versiones (ambos modos)

- Una versión nueva es un archivo nuevo con el número siguiente (`-v2`).
- A la vista queda solo la versión vigente; las anteriores pasan a `versiones/` de su carpeta.
- El conocimiento canónico y las fichas se actualizan en su lugar; la historia queda en el registro de cambios del informe.
- Cada derivado declara al inicio de qué versión del informe sale; el informe integrado es derivado de cada informe que reúne. Al salir un informe nuevo, avisa qué derivados quedaron desactualizados.

## Al cerrar

- **Con brainme**: guarda la decisión que informó el encargo como decisión, o como pregunta abierta si nadie decidió todavía. En la entrega, lista las notas creadas o actualizadas y sugiere en una línea pedirle a brainme que compruebe lo guardado y actualice el tablero; si la investigación responde una pregunta abierta, que la gradúe.
- **Sin brainme**: pon al día la fila del encargo en `indice.md`.

**Terminado cuando:** cada archivo está en su lugar, solo la versión vigente está a la vista, y el índice (sin brainme) o la lista para brainme (con brainme) está al día.

# Guardado y versiones

## Detecta el modo

- **Con brainme**: el proyecto tiene `05_exports/` y `01_knowledge/`, o su `CLAUDE.md` menciona brainme.
- **Sin brainme**: cualquier otro caso. Si la carpeta del proyecto no es clara, pregunta una vez dónde crear la raíz.

Cada encargo tiene un `<tema>` corto, en minúsculas y con guiones (`seguro-vehicular`).

## Con brainme

brainme es la fuente de verdad de su método: qué vale guardar, en qué carpeta, con qué plantilla, cómo se marca lo que se sabe y cómo se versiona. discoverme lo sigue tal como esté vigente.

1. **Al empezar el encargo**, invoca brainme: te pone al día del proyecto y carga su método. Anota su carpeta (la que muestra al cargarse): ahí están `references/` y `templates/`.
2. **Antes de guardar**, aplica su criterio de qué vale guardar y sus reglas de entregables (`references/entregables.md`). Las capturas web y los papers son originales: las notas guardan lo que se dedujo de ellos y apuntan a ellos.
3. **Al lanzar un investigador**, pásale la carpeta de brainme y las rutas donde guarda cada cosa.
4. **Al terminar**, invoca brainme para registrar los entregables, sincronizar y llevar a su tablero lo que cambió: la decisión, las posturas y los próximos pasos.

Lo que produce discoverme, según los tipos de nota de brainme:

| Qué | Tipo en brainme | Nombre |
|---|---|---|
| Informe madre, ejecutiva, presentaciones | entregable | `benchmark-<tema>`, `benchmark-<tema>-ejecutiva`, `benchmark-<tema>-deck`, `benchmark-<tema>-deck-ejecutivo` |
| Informe de literatura | entregable | `literatura-<tema>` |
| Brief, registro de evidencia, vigilancia | conocimiento | `benchmark-<tema>-brief`, `…-evidencia`, `…-vigilancia` |
| Perfil de cada alternativa | conocimiento; si ya existe, se actualiza | `<alternativa>` |
| Posturas decididas, con el porqué y lo descartado | decisión | `benchmark-<tema>-posturas` |
| Vacíos, y contradicciones con una decisión vigente | pregunta abierta, una por archivo | — |
| Paper | fuente de literatura, con `literature-note.md`; si ya existe, se amplía | `apellido-anio-palabra-clave` |
| Fuente web no académica que sustenta algo clave | fuente web, con `web-source.md` | `sitio-tema` |

Los entregables enlazan con wikilinks lo que los sustenta.

Cada nota de conocimiento lleva en el frontmatter cómo se sabe, traducido desde el registro de evidencia (`evidencia.md`):

- `certeza: confirmado` si se apoya en evidencia observada con confianza alta; `certeza: supuesto` si es interpretada o su confianza es moderada o baja.
- `como_se_sabe`: la fuente, con el wikilink a su ficha si la tiene, y la fecha de verificación. Por ejemplo: `"Pérez 2023, [[perez-2023-onboarding-pymes]], verificado 2026-11-21"`.

## Sin brainme

```
benchmarks/<tema>/                         benchme
  conocimiento/                            canónico y vivo: se actualiza en su lugar
    brief.md
    evidencia.md
    vigilancia.md
    alternativas/<alternativa>.md
  entregables/
    informe/          <tema>-informe-vN.md + versiones/
    ejecutiva/        <tema>-ejecutiva-vN.md + versiones/
    presentaciones/   <tema>-deck-vN.html, <tema>-deck-ejecutivo-vN.html + versiones/

literatura/                                doime
  fichas/apellido-anio-palabra-clave.md    compartidas entre temas; se amplían en su lugar
  <tema>/
    informe/          literatura-<tema>-vN.md + versiones/
```

La ficha de cada paper sigue `../skills/doime/references/ficha.md`.

Versiones:

- Una versión nueva es un archivo nuevo con el número siguiente (`-v2`).
- A la vista queda solo la versión vigente; las anteriores pasan a `versiones/` de su carpeta.
- El conocimiento canónico y las fichas se actualizan en su lugar; la historia queda en el registro de cambios del informe.

## Derivados (ambos modos)

Cada derivado declara al inicio de qué versión del informe sale. Al salir un informe nuevo, avisa qué derivados quedaron desactualizados.

**Terminado cuando:** cada archivo está en su lugar, solo la versión vigente está a la vista y, con brainme, brainme sincronizó.

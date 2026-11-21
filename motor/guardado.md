# Guardado y versiones

## Detecta el modo

- **Con brainme**: el proyecto tiene `05_exports/` y `01_knowledge/`, o su `CLAUDE.md` menciona brainme.
- **Sin brainme**: cualquier otro caso. Si la carpeta del proyecto no es clara, pregunta una vez dónde crear la raíz.

Cada encargo tiene un `<tema>` corto, en minúsculas y con guiones (`seguro-vehicular`).

## Con brainme

brainme decide dónde vive cada cosa y discoverme se acomoda a sus carpetas. Para fichas, frontmatter, wikilinks y el orden de versiones manda brainme (su `references/entregables.md`). Al terminar, invoca brainme para registrar los entregables y sincronizar.

Las plantillas de fichas son las de brainme, en la carpeta `templates/` de su plugin: `literature-note.md` para papers y `web-source.md` para fuentes web no académicas. Encuéntralas con `find ~/.claude/plugins -path '*brainme*/templates/literature-note.md'`.

### benchme

| Qué | Dónde |
|---|---|
| Informe madre | `05_exports/reports/benchmark-<tema>/benchmark-<tema>-vN.md` |
| Ejecutiva | `05_exports/reports/benchmark-<tema>-ejecutiva/benchmark-<tema>-ejecutiva-vN.md` |
| Presentación completa | `05_exports/presentations/benchmark-<tema>-deck/benchmark-<tema>-deck-vN.html` + ficha |
| Presentación ejecutiva | `05_exports/presentations/benchmark-<tema>-deck-ejecutivo/benchmark-<tema>-deck-ejecutivo-vN.html` + ficha |
| Brief, evidencia y vigilancia | `01_knowledge/benchmark-<tema>-brief.md`, `…-evidencia.md`, `…-vigilancia.md` |
| Perfil de cada alternativa | `01_knowledge/<alternativa>.md`; si ya existe de otro benchmark, actualízalo |
| Posturas decididas | `02_decisions/benchmark-<tema>-posturas.md`, con el porqué y lo descartado |
| Vacíos | `03_open_questions/`, una pregunta por archivo |

### doime

| Qué | Dónde |
|---|---|
| Ficha de cada paper | `04_sources/literature/apellido-anio-palabra-clave.md`, con `literature-note.md`; si ya existe, se amplía |
| PDF que aporte el usuario | junto a su ficha, con el mismo nombre base |
| Fuente web no académica | `04_sources/web/sitio-tema.md`, con `web-source.md` |
| Informe | `05_exports/reports/literatura-<tema>/literatura-<tema>-vN.md` |
| Vacíos o contradicciones con una decisión | `03_open_questions/`, una pregunta por archivo |

Los entregables enlazan con wikilinks lo que los sustenta: brief, perfiles, fichas, decisiones.

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

Sin brainme, la ficha sigue `../skills/doime/references/ficha.md`.

## Versiones (ambos modos)

- Una versión nueva es un archivo nuevo con el número siguiente (`-v2`).
- A la vista queda solo la versión vigente; las anteriores pasan a `versiones/` de su carpeta.
- El conocimiento canónico y las fichas se actualizan en su lugar; la historia queda en el registro de cambios del informe.
- Cada derivado declara al inicio de qué versión del informe sale. Al salir un informe nuevo, avisa qué derivados quedaron desactualizados.

**Terminado cuando:** cada archivo está en su lugar, solo la versión vigente está a la vista y, con brainme, brainme sincronizó.

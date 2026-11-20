# Guardado y versiones

## Detecta el modo

- **Con brainme**: el proyecto tiene `05_exports/` y `01_knowledge/`, o su `CLAUDE.md` menciona brainme.
- **Sin brainme**: cualquier otro caso. La raíz es `benchmarks/` en la carpeta del proyecto; si la carpeta del proyecto no es clara, pregunta una vez dónde crearla.

Cada benchmark tiene un `<tema>` corto, en minúsculas y con guiones (`seguro-vehicular`).

## Con brainme

brainme decide dónde vive cada cosa y benchme se acomoda a sus carpetas. Para fichas, frontmatter, wikilinks y el orden de versiones manda brainme (su `references/entregables.md`). Al terminar, invoca brainme para registrar los entregables y sincronizar.

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

Los entregables enlazan con wikilinks el brief, los perfiles y las decisiones que los sustentan.

## Sin brainme

```
benchmarks/<tema>/
  conocimiento/                canónico y vivo: se actualiza en su lugar
    brief.md
    evidencia.md
    vigilancia.md
    alternativas/<alternativa>.md
  entregables/
    informe/                   <tema>-informe-vN.md
      versiones/
    ejecutiva/                 <tema>-ejecutiva-vN.md
      versiones/
    presentaciones/            <tema>-deck-vN.html, <tema>-deck-ejecutivo-vN.html
      versiones/
```

## Versiones (ambos modos)

- Una versión nueva es un archivo nuevo con el número siguiente (`-v2`).
- A la vista queda solo la versión vigente; las anteriores pasan a `versiones/` de su carpeta.
- El conocimiento canónico se actualiza en su lugar; la historia queda en el registro de cambios del informe.
- Cada derivado declara al inicio de qué versión del informe sale. Al salir un informe nuevo, avisa qué derivados quedaron desactualizados.

**Terminado cuando:** cada archivo está en su lugar, solo la versión vigente está a la vista y, con brainme, brainme sincronizó.

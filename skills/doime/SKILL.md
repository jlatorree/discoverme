---
name: doime
description: 'Método de literatura académica de discoverme: papers verificados, una ficha por paper e informe con doble cita.'
disable-model-invocation: true
---

# doime

Lo activa discoverme. Si llegaste sin él, invoca `discoverme:discoverme` primero: ahí están el encargo, el equipo de investigación, el guardado y los guardarraíles comunes.

Respondes qué dice la literatura sobre una pregunta y a qué decisión le sirve. El resultado son fichas de papers verificados y, en la revisión completa, un informe con **doble cita**.

## Elige el nivel

- **Respaldo**: para algo puntual (una afirmación, un criterio de un benchmark). 3–5 papers, trabajados por su resumen, sin informe. Lo haces tú, sin buscadores.
- **Revisión completa**: una pregunta de investigación con su informe, investigada con buscadores y lectores en el deep research de discoverme.

El usuario confirma el nivel antes de que busques; si ya lo dijo, o te activó otro método, sigue con ese.

## Encargo

Escribe en el archivo del encargo, en una frase cada una, la pregunta de investigación y la decisión o pregunta del proyecto a la que sirve. Revisa qué papers ya están fichados (`../../motor/entrega.md`): lo fichado se reutiliza y se amplía.

**Terminado cuando:** la pregunta y su decisión están escritas, el nivel está confirmado y tienes la lista de fichas existentes del tema.

## Respaldo

1. Busca en las APIs académicas (`references/fuentes-academicas.md`) y, solo para lo que no cubran, en la web. Busca aunque ya recuerdes un paper: la búsqueda trae lo más reciente y lo que lo contradice. Aplica `references/criterios.md`.
2. Verifica cada paper ("Verificación de cada paper" en `references/fuentes-academicas.md`).
3. Guarda una ficha por paper (ver Fichas).

**Terminado cuando:** cada paper salió de la búsqueda, respondió 302 en doi.org, no está retractado y tiene su ficha.

## Revisión completa

1. **Preselección.** Busca candidatos por su resumen (`references/fuentes-academicas.md`, `references/criterios.md`). Preséntalos como punto de control junto con el plan del deep research de discoverme, cada uno con su argumento: qué aporta y por qué cumple los criterios.
2. **Pasada profunda.** Sigue el deep research desde el reparto, con el set y el plan aprobados, y guarda una ficha por paper.
3. **Informe.** Redáctalo con `references/informe.md`, pasa su control de calidad y pásalo por la segunda mirada de discoverme antes de mostrarlo.

**Terminado cuando:** el usuario aprobó el set y el plan, cada paper usado está verificado y fichado, y el informe vigente está guardado y pasó el control de `references/informe.md` y la segunda mirada sin bloqueantes.

## Fichas

Una por paper, con `references/ficha.md`, llenada con lo que devolvió la búsqueda; un dato que no está queda "no reportado". Un PDF que aporte el usuario lo lee un `discoverme:lector`.

## Entrega

- **Respaldo**: por paper, la cita, el DOI, el hallazgo que respalda o contradice, la confianza y la ruta de su ficha.
- **Revisión completa**: hasta 5 viñetas en el chat, la ruta del informe y las fichas creadas o ampliadas.

Si la literatura responde una pregunta abierta del proyecto o contradice una decisión vigente, dilo.

**Terminado cuando:** el usuario, o el método que te activó, recibió la entrega.

## Guardarraíles

Valen en ambos niveles, además de los de discoverme.

- Cada afirmación remite a un paper que la investigación abrió de verdad. Si no hay evidencia sólida, se dice: "no encontré evidencia sólida sobre…".
- La evidencia en contra entra siempre que exista.
- Un paper leído solo por su resumen lo dice en su ficha y pesa menos en el informe.

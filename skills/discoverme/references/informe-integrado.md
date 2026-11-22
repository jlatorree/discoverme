# Informe integrado

Reúne en un informe lo que varios métodos y fuentes dicen sobre una misma decisión. Se organiza por las ideas que responden a la decisión: cada idea junta la evidencia de donde venga.

El usuario parte de una **estructura sugerida** completa, con todo el panorama a la vista, y la edita. Lo que él deja es lo que se redacta.

## 1. Panorama

Reúne todo lo que hay del tema: informes vigentes con su conocimiento (registros de evidencia, perfiles, vigilancia), fichas de papers, notas del proyecto y lo que aporte el usuario. Si un método está a medias o falta, presenta como punto de control si completarlo o seguir con lo que hay.

**Terminado cuando:** cada material del tema está en la tabla del corpus, con su versión, su solidez y si entra o no, con el motivo.

## 2. Estructura sugerida

Llena la plantilla de abajo con el corpus real y guárdala como archivo (`../../../motor/guardado.md`). Conserva todas las secciones y marca cada una:

- **sugerida**: responde a la decisión y tiene evidencia;
- **opcional**: tiene evidencia, y la decisión se entiende sin ella;
- **sin material**: ayudaría, y el corpus no alcanza; di qué faltaría investigar.

Pásala por la segunda mirada (`../../../motor/segunda-mirada.md`) y preséntala como punto de control: la ruta del archivo, el mensaje tentativo, las ideas en una línea cada una y lo más débil. El usuario edita el archivo o pide los cambios en el chat.

**Terminado cuando:** toda la plantilla está llena, el usuario dio por lista la estructura, y el archivo quedó con `estado: aprobada`.

## 3. Redacción

Relee el archivo antes de redactar: sus secciones, orden, títulos, extensión y formato mandan. Si la edición dejó fuera un choque o un vacío con peso en la decisión, o agregó una sección sin evidencia, dilo antes de redactar y el usuario decide.

Redacta, pasa el control de calidad y la segunda mirada, y guarda.

**Terminado cuando:** el informe sigue la estructura aprobada, pasó el control de calidad y la segunda mirada sin bloqueantes, y está guardado.

## Reglas con cualquier estructura

- **Cita de origen.** Cada afirmación conserva la de su método, con enlace: la del benchmark, a su registro (sin brainme, `[E12](../../../benchmarks/<tema>/conocimiento/evidencia.md)`; con brainme, `[[benchmark-<tema>-evidencia|E12]]`); la de un paper, doble cita.
- **Origen declarado.** El frontmatter lleva `deriva_de`, con cada informe que reúne y su versión.
- **Una fuente cuenta una vez.** Un paper que citan el benchmark y la revisión de literatura es una sola fuente.
- **Solidez.** Usa la confianza de `../../../motor/evidencia.md` y di de qué tipo de evidencia sale cada idea.
- **Choques.** Cuando dos fuentes se contradicen, di qué sostiene cada una, con qué evidencia y qué lo explicaría (contexto, fecha, muestra, interés). Si nada lo explica, queda abierto.
- **Posturas ya decididas.** Se conservan. Si otra fuente contradice una, va como choque y el usuario decide si se reabre.

## Plantilla de la estructura

```markdown
---
tipo: estructura
tema: <tema>
fecha: AAAA-MM-DD
estado: sugerida | aprobada
---
# Estructura del informe integrado: <tema>

Edita este archivo: cambia, mueve, borra o agrega lo que quieras. Avísame en el chat cuando esté.

**Decisión:** … · **Audiencia:** … · **Extensión y formato:** …

## Panorama del corpus

| Material | Versión y fecha | Qué aporta | Solidez | ¿Entra? |
|---|---|---|---|---|

## Secciones

### 1. Mensaje principal (sugerida)
Qué diría: … · Se apoya en: … · Solidez: …

### 2. Decisión y contexto
### 3. Cómo se investigó y con qué corpus

### 4. Hallazgos, una subsección por idea
#### 4.1 <idea, en una afirmación>
Qué diría: … · Mercado: … · Literatura: … · Otras fuentes: … · Solidez: …

### 5. Dónde coinciden las fuentes
### 6. Dónde chocan y qué lo explicaría
### 7. Qué cambia en la decisión: posturas e implicaciones
### 8. Opciones, y qué tendría que ser cierto en cada una
### 9. Explicaciones alternativas y supuestos clave
### 10. Riesgos y qué vigilar
### 11. Lo que no sabemos
### 12. Próximos pasos
### 13. Fuentes y anexos
```

Cada sección lleva su marca y los mismos tres datos de la 1: qué diría, en qué se apoya y su solidez.

## Control de calidad

- [ ] El mensaje principal es una afirmación y responde a la decisión.
- [ ] Están las secciones de la estructura aprobada, en su orden.
- [ ] El corpus está declarado, con versiones y fechas.
- [ ] Cada afirmación conserva su cita de origen, y cada cita existe en su registro o su ficha.
- [ ] Cada choque tiene explicación o quedó abierto.
- [ ] Las posturas ya decididas están como se decidieron, o el usuario las reabrió.
- [ ] Desde la segunda versión, hay registro de cambios.

## Actualizar

Parte de la última estructura aprobada, para que las versiones se puedan comparar. Rehaz el panorama, marca en la estructura qué cambió en el corpus o en la decisión, y vuelve al paso 2 solo con esas secciones.

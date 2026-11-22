# Ficha de paper

Cada ficha es un archivo `apellido-anio-palabra-clave.md`. Su forma es compatible con la ficha de literatura de brainme; si el proyecto ya tiene fichas, sigue la forma de las existentes. Un dato que no está queda "no reportado". Sin brainme, `proyecto` y `relacionadas` se borran.

```markdown
---
titulo: "<Título del paper>"
tipo: literatura
cita: "<cita completa, APA 7>"
autores: "<Apellido, N.; Apellido, N.>"
anio: <AAAA>
venue: "<revista o conferencia>"
doi: "<10.xxxx/xxxxx o sin DOI>"
source_url: "<https://doi.org/10.xxxx/xxxxx o enlace canónico>"
pdf: "<apellido-anio-palabra-clave.pdf si está guardado junto a la ficha, o no>"
peer_reviewed: <sí | no | preprint>
tipo_trabajo: <empírico | revisión sistemática | meta-análisis | teórico | fundacional>
metodo: "<diseño en pocas palabras>"
muestra: "<n, corpus, contexto y país>"
citas: <número a la fecha de consulta>
citas_fuente: "<Crossref | OpenAlex | Semantic Scholar>"
consultado: <AAAA-MM-DD>
leido: <completo | solo abstract>
retracciones: <ninguna | corregido>
fiabilidad: <alta | media | baja>
proyecto: "<nombre del proyecto>"
resumen: "<qué sostiene el paper, en una o dos frases>"
tags: [literatura, <tema>]
relacionadas: ["[[pregunta-o-decision-que-ilumina]]", "[[informe-que-lo-cita]]"]
---

# <Título del paper>

**Cita:** <cita completa, APA 7>
**Enlace:** [<doi.org/10.xxxx/xxxxx>](<https://doi.org/10.xxxx/xxxxx>)

## Resumen (qué sostiene)
Dos a cuatro frases con la tesis central y el aporte.

## Método
Diseño, muestra, contexto y límites del método.

## Hallazgos clave
- <hallazgo, con el dato concreto> (p. <n>)

## Límites y advertencias
- <sesgos, alcance, críticas conocidas, correcciones>

## Por qué entró en la selección
Validez, impacto y actualidad.

## Relevancia para el proyecto
Qué pregunta o decisión ilumina y cómo.

## Citas textuales verificadas
> "<cita corta, verificada contra el original>" (<Apellido>, <año>, p. <n>)
```

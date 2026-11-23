# Redacción y guardado

Cómo se escribe y dónde queda todo lo que hace discoverme. La forma de cada entregable la da la plantilla de su método; esto es cómo se escribe dentro de ella. Si el proyecto tiene su propia guía de redacción, manda esa.

## Redacción

La regla de fondo es que cada frase aporte algo concreto: un dato, un hallazgo, una postura, el paso que sigue.

### Investigación

- Cada afirmación lleva la cita que pide su método (`[E#]` en benchme, doble cita en doime), puesta junto a la afirmación.
- Lo observado y lo interpretado van en frases distintas, y lo interpretado dice de qué se deduce.
- Los juicios sobre el futuro usan la escala de probabilidad de `evidencia.md`, con la confianza en otra frase.
- La incertidumbre se dice una vez y en concreto ("falta confirmar el precio con el proveedor"), en el lugar donde pesa.
- Un vacío se nombra como vacío: qué se buscó y no se encontró.

### Estructuras

- Un contraste se explica con el dato que lo sostiene. El giro dramático ("No es A, es B") sobra.
- Enumera los elementos que haya, sean dos o cinco. Tres ideas seguidas porque suena redondo es una tríada por costumbre.
- Termina el párrafo cuando termina la idea. Una frase-remate que repite lo dicho sobra.
- Afirma directamente. La pregunta retórica que el texto responde enseguida ("¿El resultado? ...") sobra.
- Empieza por lo que importa. Las aperturas y cierres de relleno ("En el mundo actual...", "En conclusión") sobran.

### Palabras

- Muestra el hecho que demuestra algo, en vez de calificarlo con lenguaje promocional ("único", "revolucionario").
- Nombra a cada alternativa, autor o fuente por su nombre, igual en todo el documento.

### Forma

- Negritas con moderación, para lo que el lector tiene que encontrar rápido. Sin emojis.
- Títulos con mayúscula solo en la primera palabra: "Hallazgos del campo".
- Las pausas van con coma, punto o paréntesis, sin raya (—).
- Varía el largo de frases y párrafos: si todos miden lo mismo, suena a plantilla.

**Antes de mostrar un texto o guardarlo**, búscale cada patrón de esta sección y corrígelo.

## Dónde se guarda

Todo va en una sola carpeta:

- En un proyecto con brainme (su `CLAUDE.md` tiene una sección `## brainme`): `_taller/investigacion/`. brainme deja `_taller/` donde está y fuera de su mapa.
- En la raíz de una carpeta multiproyecto de brainme (`## brainme · multiproyecto` o `## brainme · espacio`): pregunta en qué proyecto guardar.
- En cualquier otro caso: `investigacion/`. Si la carpeta del proyecto no es clara, pregunta una vez dónde crearla.

```
investigacion/
  encargos/<tema>.md                 archivo del encargo
  benchmarks/<tema>/                 benchme
    conocimiento/                    vivo: se actualiza en su lugar
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
  fichas/                            una por paper, compartidas entre temas
  capturas/<sitio>/<AAAA-MM-DD>/     páginas y flujos guardados
```

Cada encargo tiene un `<tema>` corto, en minúsculas, con guiones y sin tildes (`seguro-vehicular`). Lo que ya hay de un tema se encuentra en `encargos/`.

**Archivo del encargo**: los métodos, la pregunta o decisión, el modo o nivel, la fase actual (una sola, siempre al día), el plan y los sets aprobados, y lo que el usuario decidió en cada punto de control, textual. Es lo que otra sesión lee para retomar.

**Versiones**
- Una versión nueva es un archivo nuevo con el número siguiente (`-v2`); la anterior pasa a `versiones/` de su carpeta.
- El conocimiento y las fichas se actualizan en su lugar; la historia queda en el registro de cambios del informe.
- Cada derivado declara al inicio de qué versión sale; el informe integrado es derivado de cada informe que reúne. Al salir un informe nuevo, avisa qué derivados quedaron desactualizados.

## Al cerrar

Deja la fase del encargo al día y lista lo guardado. Si el proyecto usa brainme, sugiere en una línea: "pídele a brainme que guarde el informe en el proyecto". brainme decide cómo lo archiva. Si no lo usa y es la primera vez que creas `investigacion/`, menciona una vez que brainme puede llevar estas notas como segundo cerebro del proyecto.

**Terminado cuando:** cada archivo está en su lugar, solo la versión vigente está a la vista y el encargo dice en qué fase quedó.

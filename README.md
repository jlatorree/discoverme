# benchme

Benchmarks estratégicos co-creados con Claude. benchme ubica un producto o servicio frente a sus alternativas reales y ayuda a decidir **qué igualar, de qué diferenciarse, qué vigilar y qué ignorar**, con evidencia trazable y sin caer en la convergencia: terminar igual que todos por compararse con todos.

El resultado no es una tabla con ganador, sino un juicio fechado sobre qué hacer.

## Instalación

En Claude Code:

```
/plugin marketplace add jlatorree/benchme
/plugin install benchme@benchme
```

Para las presentaciones HTML necesitas además el skill [frontend-slides](https://github.com/zarazhangrui/frontend-slides).

## Uso

Pídelo en lenguaje natural:

- "Hazme un benchmark de seguros vehiculares digitales"
- "Actualiza el benchmark de seguro-vehicular"
- "Saca la versión ejecutiva" / "Arma la presentación del benchmark"

## Cómo trabaja

1. **Triaje:** clasifica el pedido (chequeo de paridad, insumo para una decisión o pedido sin decisión) y propone un modo ligero o completo. Reencuadra el pedido, nunca lo niega.
2. **Brief:** decisión, encargo, alcance, propósito, profundidad y tus hipótesis, escritas antes de ver cualquier síntesis de Claude. Sale listo para reenviar a quien pidió el benchmark.
3. **Alternativas:** lo que el cliente haría si tu oferta no existiera, incluido el statu quo, los sustitutos y análogos de otras industrias. Los "fantasmas" van a vigilancia.
4. **Evidencia:** registro con fuente, fecha, tipo y nivel de confianza. Claude hace la investigación documental; tú aportas lo que no se delega: entrevistas, uso propio, lo que sabe ventas.
5. **Análisis:** ingeniería inversa de cada alternativa (qué hace, no qué dice), qué está viendo que tú no, qué es imperativo y qué es elección, su durabilidad y los supuestos de su dirección. Lentes opcionales: lienzo estratégico y ERRC, jobs to be done, cinco fuerzas, y profundidad sistémica o de transición.
6. **Síntesis:** explicaciones rivales, steelman de la opción descartada, paradoja central, una postura por ítem y una lista de vigilancia con *tripwires*.

**Reparto:** Claude reúne, etiqueta, propone y desafía. Tú encuadras, eliges y juzgas.

## Entregables

- **Informe madre** (markdown): siempre. Es el benchmark.
- **Versión ejecutiva** (markdown, 1–2 páginas): a pedido, desde el informe.
- **Presentaciones HTML** (completa o ejecutiva): a pedido, generadas con frontend-slides. Puedes usar el `design.md` de tu empresa o elegir un estilo.

Cada derivado indica de qué versión del informe sale.

## Dónde guarda

- **Con [brainme](https://github.com/jlatorree/brainme):** los entregables van en `05_exports/`, el conocimiento canónico (brief, evidencia, vigilancia, perfiles de alternativas) en `01_knowledge/`, las posturas en `02_decisions/` y los vacíos en `03_open_questions/`.
- **Sin brainme:** crea `benchmarks/<tema>/`, con `conocimiento/` y `entregables/`.

En ambos casos, a la vista queda solo la versión vigente y las anteriores en `versiones/`.

## Fuentes

Los marcos que usa benchme están en [`references/fuentes.md`](references/fuentes.md), con la versión vigente de cada autor y la regla para actualizarlos.

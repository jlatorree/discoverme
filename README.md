# discoverme

Research estratégico co-creado con Claude. Un solo motor de evidencia y dos skills que lo usan:

- **benchme**: benchmarks estratégicos. Ubica un producto o servicio frente a sus alternativas reales y ayuda a decidir **qué igualar, de qué diferenciarse, qué vigilar y qué ignorar**, sin caer en la convergencia: terminar igual que todos por compararse con todos.
- **doime**: revisiones de literatura académica. Busca, verifica y sintetiza papers sobre una pregunta, con una ficha por paper y un informe donde cada afirmación cita su fuente.

Cada skill se activa solo, según lo que pidas, y se llaman entre sí: cuando un criterio del benchmark necesita respaldo académico, benchme le pide a doime una pasada liviana.

## Instalación

En Claude Code:

```
/plugin marketplace add jlatorree/discoverme
/plugin install discoverme@discoverme
```

Para las presentaciones HTML de benchme necesitas además el skill [frontend-slides](https://github.com/zarazhangrui/frontend-slides), y para el informe como página web, el plugin oficial frontend-design.

## Uso

Pídelo en lenguaje natural:

- "Hazme un benchmark de seguros vehiculares digitales"
- "Actualiza el benchmark de seguro-vehicular" / "Saca la versión ejecutiva"
- "¿Qué dice la literatura sobre el abandono en procesos de alta?"
- "Busca papers que respalden esta afirmación"

## Cómo trabaja

### benchme

1. **Triaje:** chequeo de paridad, insumo para una decisión o pedido sin decisión; modo ligero o completo.
2. **Brief:** decisión, encargo, alcance, propósito, profundidad y tus hipótesis, escritas antes de ver cualquier síntesis de Claude.
3. **Alternativas:** una pasada liviana para preseleccionar contigo, incluido el statu quo, los sustitutos y análogos de otras industrias.
4. **Evidencia:** registro con fuente, fecha, tipo y confianza. Tú aportas lo que no se delega: entrevistas, uso propio, lo que sabe ventas.
5. **Análisis:** ingeniería inversa de cada alternativa, imperativos frente a elecciones, durabilidad y supuestos. Lentes opcionales: lienzo estratégico y ERRC, jobs to be done, cinco fuerzas, profundidad sistémica.
6. **Síntesis:** primeros principios frente a convenciones, steelman de la opción descartada, paradoja central, una postura por ítem y vigilancia con *tripwires*.

Entregables: el **informe madre** siempre; a pedido, una versión ejecutiva y presentaciones HTML.

### doime

- **Pasada liviana:** 3–5 papers, por su resumen, para respaldar algo puntual.
- **Revisión completa:** preselección de papers contigo, deep research y un informe con hallazgos, evidencia en contra, implicaciones y límites.

Busca primero en APIs académicas abiertas (Crossref, OpenAlex, arXiv, Europe PMC) y después en la web. Cada DOI se verifica en doi.org y los trabajos retractados quedan fuera.

**Reparto:** Claude reúne, verifica, propone y desafía. Tú encuadras, eliges y juzgas.

## El motor

`motor/` es la fuente única que comparten los skills: reglas de evidencia, captura web, fuentes académicas, cómo se orquesta el deep research y dónde se guarda. Los agentes:

| Agente | Rol | Modelo |
|---|---|---|
| `investigador` | Busca y lee una subpregunta | Opus, esfuerzo alto |
| `lector` | Lee un documento largo | Opus, esfuerzo alto |
| `redactor` | Sintetiza y redacta el informe | Opus, esfuerzo xhigh |

## Acceso sin login

discoverme solo usa acceso público: nada que requiera tu sesión ni cuentas o API keys de terceros. Si una herramienta solo funciona con login, queda fuera; si solo algunas funciones lo piden, quedan fuera esas funciones.

### Herramientas opcionales

Funciona con la búsqueda y la lectura web de Claude. Con muchas fuentes rinde mejor con estas, que el skill revisa y te ofrece instalar:

- [Crawl4AI](https://github.com/unclecode/crawl4ai): páginas como markdown limpio y extracción estructurada sin modelo.
- [Agent Reach](https://github.com/Panniantong/Agent-Reach): YouTube (búsqueda y subtítulos) y búsqueda web alternativa.
- [Playwright MCP](https://github.com/microsoft/playwright-mcp): recorrer flujos públicos y guardar capturas.

## Dónde guarda

- **Con [brainme](https://github.com/jlatorree/brainme):** en sus carpetas y con sus plantillas; los entregables en `05_exports/`, el conocimiento en `01_knowledge/`, las fichas de papers en `04_sources/literature/`.
- **Sin brainme:** `benchmarks/<tema>/` y `literatura/`.

En ambos casos, a la vista queda solo la versión vigente y las anteriores en `versiones/`.

## Fuentes

Los marcos que usa benchme están en [`skills/benchme/references/fuentes.md`](skills/benchme/references/fuentes.md), con la versión vigente de cada autor y la regla para actualizarlos.

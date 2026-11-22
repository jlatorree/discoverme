# discoverme

Investigación estratégica co-creada con Claude. Le pides una investigación a **discoverme**, que actúa como investigador a cargo: entiende el pedido, elige contigo el método y lo conduce hasta el informe.

Métodos disponibles:

- **benchme**: benchmarks estratégicos. Ubica un producto o servicio frente a sus alternativas reales y ayuda a decidir **qué igualar, de qué diferenciarse, qué vigilar y qué ignorar**, sin caer en la convergencia: terminar igual que todos por compararse con todos.
- **doime**: revisiones de literatura académica. Busca, verifica y sintetiza papers sobre una pregunta, con una ficha por paper y un informe donde cada afirmación cita su fuente.

Los métodos se combinan. Cuando un criterio del benchmark necesita respaldo académico, discoverme activa doime en respaldo. Y cuando quieres un solo informe con el benchmark, la literatura y lo demás que tengas del tema, escribe un **informe integrado**: te sugiere la estructura completa, con todo el panorama del corpus, y redacta sobre lo que edites.

## Instalación

En Claude Code:

```
/plugin marketplace add jlatorree/discoverme
/plugin install discoverme@discoverme
```

Para las presentaciones HTML de benchme necesitas además el skill [frontend-slides](https://github.com/zarazhangrui/frontend-slides), y para el informe como página web, el plugin oficial frontend-design.

## Uso

Pídelo en lenguaje natural o con `/discoverme:discoverme`:

- "Hazme un benchmark de seguros vehiculares digitales"
- "Actualiza el benchmark de seguro-vehicular" / "Saca la versión ejecutiva"
- "¿Qué dice la literatura sobre el abandono en procesos de alta?"
- "Busca papers que respalden esta afirmación"
- "Hazme un informe final que integre el benchmark y la literatura"

Para una investigación completa, pon la sesión en esfuerzo Extra: la síntesis y la redacción lo aprovechan.

## Cómo trabaja

```
Tú ⇄ discoverme (la sesión: el investigador)
        ├─ activa un método: benchme, doime
        ├─ reparte el trabajo de campo: buscadores y lectores, en paralelo
        ├─ pasa lo que te muestra por un revisor: propuestas de síntesis e informes
        └─ sigue el motor: evidencia, captura web, deep research, segunda mirada, redacción, guardado
```

- **discoverme** conversa contigo, planifica, reparte, verifica, sintetiza y redacta. Se detiene en cada punto de control para que decidas.
- **Los métodos** dicen qué fases tiene la investigación, qué se decide en cada una y con qué plantilla se entrega.
- **Buscadores y lectores** son agentes que trabajan en paralelo, cada uno con su propio contexto, y devuelven solo lo encontrado. Así la sesión queda libre para conversar y sintetizar.
- **El revisor** llega sin haber visto la investigación. Desafía las propuestas de síntesis y revisa cada informe contra su control de calidad, siguiendo las citas que más pesan hasta su fuente. Lo que no puede llegarte así se corrige antes; los desafíos que quedan abiertos te llegan junto con la propuesta, para que decidas.

| Agente | Rol | Modelo |
|---|---|---|
| `buscador` | Busca y lee una subpregunta | Opus, esfuerzo alto |
| `lector` | Lee un documento largo | Opus, esfuerzo alto |
| `revisor` | Desafía la síntesis y revisa cada informe antes de mostrarlo | Opus, esfuerzo xhigh (Extra), aunque la sesión esté en otro nivel |

**Reparto:** Claude reúne, verifica, propone y desafía. Tú encuadras, eliges y juzgas.

### benchme

1. **Triaje:** chequeo de paridad, insumo para una decisión o pedido sin decisión; modo ligero o completo.
2. **Brief:** decisión, encargo, alcance, propósito, profundidad y tus hipótesis, escritas antes de ver cualquier síntesis de Claude.
3. **Alternativas:** una pasada liviana para preseleccionar contigo, incluido el statu quo, los sustitutos y análogos de otras industrias.
4. **Evidencia:** registro con fuente, fecha, tipo y confianza. Tú aportas lo que no se delega: entrevistas, uso propio, lo que sabe ventas.
5. **Análisis:** ingeniería inversa de cada alternativa, imperativos frente a elecciones, durabilidad y supuestos. Lentes opcionales: lienzo estratégico y ERRC, jobs to be done, cinco fuerzas, profundidad sistémica.
6. **Síntesis:** primeros principios frente a convenciones, steelman de la opción descartada, paradoja central, una postura por ítem y vigilancia con *tripwires*.

Entregables: el **informe madre** siempre; a pedido, una versión ejecutiva y presentaciones HTML.

### doime

- **Respaldo:** 3–5 papers, por su resumen, para algo puntual.
- **Revisión completa:** preselección de papers contigo, deep research y un informe con hallazgos, evidencia en contra, implicaciones y límites.

Busca primero en APIs académicas abiertas (Crossref, OpenAlex, arXiv, Europe PMC) y después en la web. Cada DOI se verifica en doi.org y los trabajos retractados quedan fuera.

### Informe integrado

1. **Panorama:** reúne todo lo que hay del tema, con su versión y su solidez.
2. **Estructura sugerida:** un archivo con todas las secciones posibles, cada una con lo que diría, en qué se apoya y si discoverme la sugiere, la deja opcional o no tiene material. Tú lo editas.
3. **Redacción:** sigue tu versión de la estructura. Organiza por ideas, muestra dónde las fuentes coinciden y dónde chocan, y cada afirmación conserva su cita de origen.

## Acceso sin login

discoverme solo usa acceso público: nada que requiera tu sesión ni cuentas o API keys de terceros. Si una herramienta solo funciona con login, queda fuera; si solo algunas funciones lo piden, quedan fuera esas funciones.

### Herramientas opcionales

Funciona con la búsqueda y la lectura web de Claude. Con muchas fuentes rinde mejor con estas, que discoverme revisa y te ofrece instalar:

- [Crawl4AI](https://github.com/unclecode/crawl4ai): páginas como markdown limpio y extracción estructurada sin modelo.
- [Agent Reach](https://github.com/Panniantong/Agent-Reach): YouTube (búsqueda y subtítulos) y búsqueda web alternativa.
- [Playwright MCP](https://github.com/microsoft/playwright-mcp): recorrer flujos públicos y guardar capturas.

## Dónde guarda

- **Sin brainme:** todo en `investigacion/`, con un `indice.md` y un archivo por encargo para retomarlo, una carpeta por benchmark y por revisión de literatura, informes integrados, fichas de papers compartidas y las capturas web.
- **Con [brainme](https://github.com/jlatorree/brainme):** discoverme escribe en las carpetas de brainme con sus tipos de nota, siguiendo la forma de las notas que ya tiene el proyecto. No invoca a brainme: al terminar te dice qué guardó y te sugiere pedirle a brainme que sincronice.

En ambos casos, a la vista queda solo la versión vigente y las anteriores en `versiones/`.

## Sumar un método

Un método nuevo es un skill en `skills/<método>/`, con `disable-model-invocation: true` para que la entrada sea siempre discoverme, y una fila en la tabla de métodos de `skills/discoverme/SKILL.md`. El skill define sus ramas, sus fases con su "terminado cuando" y sus puntos de control, su plantilla de entrega y sus guardarraíles propios; lo común (encargo, equipo, evidencia, redacción y guardado) ya lo ponen discoverme y `motor/`. Si guarda algo nuevo, suma su carpeta en `motor/guardado.md`.

## Fuentes

Los marcos que usa benchme están en [`skills/benchme/references/fuentes.md`](skills/benchme/references/fuentes.md), con la versión vigente de cada autor y la regla para actualizarlos.

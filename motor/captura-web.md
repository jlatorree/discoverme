# Captura web

## Regla: acceso público, sin cuentas

Solo se usa lo que funciona **sin login del usuario ni cuentas o API keys de terceros**. Si una herramienta solo funciona con login, se descarta; si algunas de sus funciones lo piden, se descartan esas funciones y se usan las demás. Cuando una página o un flujo pide iniciar sesión o registrarse, se detiene ahí: pasa a ser una tarea de primera mano del usuario.

## Embudo

1. **Pasada liviana**: búsqueda y una página (o un resumen) por candidato, lo justo para saber qué es y por qué podría entrar. Sale una lista de candidatos, cada uno con su argumento.
2. **Preselección**: el usuario aprueba el set.
3. **Pasada profunda**: las herramientas de esta página se usan solo sobre el set aprobado.

Rastrear todo a fondo antes de preseleccionar genera volumen sin decisión. En benchme los candidatos son alternativas; en doime, papers.

## Antes de la pasada profunda

Lo hace la sesión, que habla con el usuario. Revisa qué hay disponible y díselo en una línea:

- Crawl4AI: `command -v crwl`
- Agent Reach: `command -v agent-reach`
- Playwright: herramientas `mcp__playwright__*` en la sesión

Si falta alguna, ofrece instalarla (comandos al final) y espera el sí del usuario. Sin ellas, el trabajo sigue con la búsqueda y la lectura web propias de Claude, y las páginas se guardan con `curl`.

## Qué usar para cada evidencia

| Evidencia | Herramienta | Alternativa |
|---|---|---|
| Páginas de cada alternativa: oferta, planes, precios, preguntas frecuentes, términos | Crawl4AI: `crwl <url> -o md-fit -O <archivo>`; varias páginas de un sitio: `--deep-crawl bfs --max-pages <n>` | `curl -sL <url> -o <archivo>.html` para guardarla, y lectura web |
| Los mismos datos en muchos sitios (planes, precios, coberturas) | Crawl4AI con esquema, sin modelo: `crwl <url> -e extraccion.yml -s esquema.json -o json` | Un `discoverme:lector` lee los markdown y llena la tabla |
| Flujos (cotizar, simular, comparar) | Playwright (aislado): recorre el flujo y guarda capturas | Tarea de primera mano del usuario |
| Videos (reseñas, anuncios, demostraciones) | Agent Reach: `agent-reach youtube search <consulta>`, `agent-reach youtube subtitle <url>` | — |
| Búsqueda o lectura cuando la propia rinde poco | `agent-reach web search <consulta>`, `agent-reach web read <url>` | — |
| Historia de precios y mensajes | Wayback Machine: `https://web.archive.org/cdx/search/cdx?url=<url>&output=json` y `https://web.archive.org/web/<AAAAMMDD>/<url>` | — |
| Lo que comunica cada marca en publicidad | Google Ads Transparency Center y Meta Ad Library, con Playwright | — |
| Reseñas de apps | `google-play-scraper` y `app-store-scraper` (npm), instaladas a pedido | Lectura de las tiendas |

Si una herramienta falla o limita el uso, reintenta una vez; si sigue, pasa a la alternativa y declara qué no se pudo capturar.

El esquema de Crawl4AI va en dos archivos. `extraccion.yml`:

```yaml
type: "json-css"
params:
  verbose: false
```

`esquema.json` (un selector base por ítem y un selector por campo):

```json
{"name": "planes", "baseSelector": ".plan", "fields": [
  {"name": "nombre", "selector": "h3", "type": "text"},
  {"name": "precio", "selector": ".precio", "type": "text"}
]}
```

Con muchas páginas, Crawl4AI no gasta tokens al rastrear, un `lector` lee los markdown, y tú verificas al menos un dato por fuente contra el original.

## Copias de respaldo

Cada página que sustenta evidencia se guarda en la carpeta de capturas (`guardado.md`), dentro de `<sitio>/<AAAA-MM-DD>/`: markdown con Crawl4AI o el HTML con `curl`. Las capturas de flujos van en la misma carpeta. Así cada dato tiene respaldo aunque la página cambie.

La lectura web resume con un modelo, y sus comillas pueden no ser literales. Busca cada cita en la página guardada antes de ponerla entre comillas. Si la página no se deja guardar (vacía sin JavaScript, o rechaza la descarga), guarda un extracto, márcalo `extracto` y cita en paráfrasis; si rechaza toda lectura, pasa a ser una tarea de primera mano.

## Fuera de la regla

- **Crawl4AI**: perfiles de navegador (`-p`), extracción o preguntas con modelos externos (`-j`, `-q`) y su nube.
- **Agent Reach**: se usan solo los canales `web` y `youtube`. Queda fuera el resto: `agent-reach read <url>` (elige el canal por su cuenta), `login`, los comandos `browser`, los canales de redes sociales (pueden pasar por un navegador con sesión), la transcripción de audio (pide API key) y GitHub con el CLI `gh` (usa la cuenta del usuario).
- Servicios en la nube que piden cuenta o API key, aunque sean gratuitos.

## Instalación

Pide el sí del usuario antes de cada una.

- **Crawl4AI** (requiere `uv`): `uv tool install crawl4ai --python 3.12 && crawl4ai-setup`. Descarga un navegador. Con `CRAWL4AI_NO_CLOUD_NOTICE=1` se oculta su aviso de la nube.
- **Agent Reach** (requiere `uv`): `uv tool install https://github.com/Panniantong/Agent-Reach/releases/latest/download/agent-reach.zip && agent-reach setup`. El paquete de PyPI con el mismo nombre es otro proyecto. Agrega solo canales sin login.
- **Playwright** (requiere Node): `claude mcp add playwright -s user -- npx -y @playwright/mcp@latest --isolated`. Con `--isolated` no guarda sesiones. Hay que reiniciar la sesión.
- Si falta `uv`: `brew install uv`.

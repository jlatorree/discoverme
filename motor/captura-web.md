# Captura web

## Regla: acceso público, sin cuentas

Solo se usa lo que funciona **sin login del usuario ni cuentas o API keys de terceros**. Si una herramienta solo funciona con login, se descarta; si algunas de sus funciones lo piden, se descartan esas funciones y se usan las demás. Cuando una página o un flujo pide iniciar sesión o registrarse, se detiene ahí: pasa a ser una tarea de primera mano del usuario.

## Embudo

1. **Pasada liviana**: búsqueda y una página (o un resumen) por candidato, lo justo para saber qué es y por qué podría entrar. Sale una lista de candidatos, cada uno con su argumento.
2. **Preselección**: el usuario aprueba el set.
3. **Pasada profunda**: las herramientas de esta página se usan solo sobre el set aprobado.

Rastrear todo a fondo antes de preseleccionar genera volumen sin decisión. En benchme los candidatos son alternativas; en doime, papers.

## Antes de la pasada profunda

Revisa qué hay disponible y díselo al usuario en una línea:

- Crawl4AI: `command -v crwl`
- Agent Reach: `command -v agent-reach`
- Playwright: herramientas `mcp__playwright__*` en la sesión
- frontend-design: el skill está en la lista de skills

Si falta alguna, ofrece instalarla (comandos al final) y espera el sí del usuario. Sin ellas, el trabajo sigue con la búsqueda y la lectura web propias de Claude.

## Qué usar para cada evidencia

| Evidencia | Herramienta | Alternativa |
|---|---|---|
| Páginas de cada alternativa: oferta, planes, precios, preguntas frecuentes, términos | Crawl4AI: `crwl <url> -o md-fit -O <archivo>`; varias páginas de un sitio: `--deep-crawl bfs --max-pages <n>` | Lectura web |
| Los mismos datos en muchos sitios (planes, precios, coberturas) | Crawl4AI con esquema, sin modelo: `crwl <url> -e extraccion.yml -s esquema.json -o json` | Un `discoverme:lector` lee los markdown y llena la tabla |
| Flujos (cotizar, simular, comparar) | Playwright (aislado): recorre el flujo y guarda capturas | Tarea de primera mano del usuario |
| Videos (reseñas, anuncios, demostraciones) | Agent Reach: `agent-reach youtube search <consulta>`, `agent-reach youtube subtitle <url>` | — |
| Búsqueda o lectura cuando la propia rinde poco | `agent-reach web search <consulta>`, `agent-reach web read <url>` | — |
| Historia de precios y mensajes | Wayback Machine: `https://web.archive.org/cdx/search/cdx?url=<url>&output=json` y `https://web.archive.org/web/<AAAAMMDD>/<url>` | — |
| Lo que comunica cada marca en publicidad | Google Ads Transparency Center y Meta Ad Library, con Playwright | — |
| Reseñas de apps | `google-play-scraper` y `app-store-scraper` (npm), instaladas a pedido | Lectura de las tiendas |

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

Con muchas páginas, el subagente ahorra contexto: Crawl4AI no gasta tokens al rastrear, el `lector` lee los markdown, y tú verificas al menos un dato por fuente contra el original.

## Copias de respaldo

Cada página que sustenta evidencia se guarda como markdown fechado, junto al registro de evidencia, en `capturas/<alternativa o sitio>/<AAAA-MM-DD>/`. Las capturas de flujos van en la misma carpeta. Así cada dato tiene respaldo aunque la página cambie.

## Fuera de la regla

- **Crawl4AI**: perfiles de navegador (`-p`), extracción o preguntas con modelos externos (`-j`, `-q`) y su nube.
- **Agent Reach**: `login`, `browser setup` y `browser use`; los canales que pasan por su navegador compartido, porque reutiliza logins (Reddit, X, LinkedIn, Facebook, Instagram); la transcripción de audio (pide API key); y GitHub con el CLI `gh` (usa la cuenta del usuario).
- Servicios en la nube que piden cuenta o API key, aunque sean gratuitos.

## Instalación

Pide el sí del usuario antes de cada una.

- **Crawl4AI** (requiere `uv`): `uv tool install crawl4ai --python 3.12 && crawl4ai-setup`. Descarga un navegador. Con `CRAWL4AI_NO_CLOUD_NOTICE=1` se oculta su aviso de la nube.
- **Agent Reach** (requiere `uv`): `uv tool install https://github.com/Panniantong/Agent-Reach/releases/latest/download/agent-reach.zip && agent-reach setup`. El paquete de PyPI con el mismo nombre es otro proyecto. Agrega solo canales sin login.
- **Playwright** (requiere Node): `claude mcp add playwright -s user -- npx -y @playwright/mcp@latest --isolated`. Con `--isolated` no guarda sesiones. Hay que reiniciar la sesión.
- **frontend-design**: `claude plugin install frontend-design@claude-plugins-official`.
- Si falta `uv`: `brew install uv`.

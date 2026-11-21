# Fuentes académicas

Primera capa de búsqueda de literatura, antes de la búsqueda web: devuelve metadatos estructurados (DOI, venue, año, citas, acceso abierto) que la web da sueltos o mal. Todas responden sin cuenta ni API key; la regla sin login está en `captura-web.md`.

## Qué usar

| Fuente | Para qué | Consulta |
|---|---|---|
| **Crossref** | Metadatos canónicos de cualquier DOI, citas recibidas, tipo de trabajo | `https://api.crossref.org/works?query=<consulta>&rows=20&filter=from-pub-date:2021&select=DOI,title,author,issued,container-title,is-referenced-by-count,type` |
| **OpenAlex** | Búsqueda por relevancia ordenada por citas, enlace abierto, marca de retractado | `https://api.openalex.org/works?search=<consulta>&filter=from_publication_date:2021-01-01&sort=cited_by_count:desc&per-page=25&select=doi,title,publication_year,cited_by_count,is_retracted,primary_location,best_oa_location` |
| **arXiv** | Preprints de computación, física, matemática, economía cuantitativa | `http://export.arxiv.org/api/query?search_query=all:<consulta>&max_results=20&sortBy=relevance` (Atom XML) |
| **Europe PMC** | Salud, biomedicina, psicología; texto completo abierto | `https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=<consulta>&format=json&pageSize=25` |
| **Semantic Scholar** | Solo respaldo, si las demás no alcanzan: sin key suele responder 429 | `https://api.semanticscholar.org/graph/v1/paper/search?query=<consulta>&fields=title,year,venue,citationCount,externalIds` |

- Las consultas van con `curl -s` y la consulta codificada (`+` entre palabras). Pide pocos campos (`select`, `fields`) para que la respuesta sea corta.
- **OpenAlex** comparte un cupo diario gratuito entre todos los de la misma red: úsalo con moderación, pocas consultas y bien armadas. Su aviso sugiere registrar un correo para una key: eso queda fuera.
- Los clásicos fundacionales salen sin filtro de fecha y ordenados por citas.
- Para un tema ya conocido, parte de 2–3 papers clave y sigue sus citas en OpenAlex: `filter=cites:<id de OpenAlex>` (quién los cita) y `referenced_works` (a quién citan).

## Verificación de cada paper

1. **DOI**: `curl -s -o /dev/null -w "%{http_code}" https://doi.org/<DOI>`. 302 es válido; 404 no existe. Lo que no verifica se corrige o sale.
2. **Retracciones y correcciones**: `is_retracted` en OpenAlex y, en Crossref, `https://api.crossref.org/works?filter=updates:<DOI>&select=DOI,update-to`: un ítem con `"type":"retraction"` en `update-to` es un aviso de retracción. Retractado sale; corregido se anota.
3. **Venue**: revisión por pares o venue reputado. Ante una revista desconocida, revisa en OpenAlex su fuente (`primary_location.source`: si está en DOAJ, su editorial) y desconfía de editoriales con señales de revista depredadora (aceptación en días, cobro sin revisión visible, nombres que imitan revistas conocidas). Preprints quedan marcados como tales.
4. **Citas**: anota el número y de qué fuente salió (Crossref y OpenAlex cuentan distinto).

## Texto completo

- Enlace abierto: `best_oa_location.pdf_url` de OpenAlex, el PDF de arXiv o el texto completo de Europe PMC.
- Páginas y PDFs abiertos se leen con la lectura web o Crawl4AI (`captura-web.md`); un documento largo, con el agente `discoverme:lector`.
- Sin enlace abierto se trabaja con el resumen y la ficha lo dice (`leido: solo abstract`). Si el usuario tiene el PDF, lo aporta él.

## Fuera de la regla

Google Scholar (sin API y bloquea la automatización), Elicit, Consensus, scite y CORE (piden cuenta o key), las keys de OpenAlex y Semantic Scholar, Unpaywall (pide un correo) y las descargas de SSRN (piden sesión).

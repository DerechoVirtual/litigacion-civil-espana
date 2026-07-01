# Litigacion civil Espana

Plugin de litigacion civil, mercantil y de familia para despachos de abogados en Espana
(LO 1/2025, LEC vigente, EGA), conectado de fabrica a Jurisprudenciator y Dropbox.

## Conectores

- **Jurisprudenciator** (MCP remoto) - via de busqueda y verificacion de jurisprudencia
  espanola. Resuelve el captcha/antidescargas del CENDOJ en el servidor y cubre TS, AN,
  AP, TSJ y juzgados (civil, penal, contencioso, social, militar).
  Endpoint: `https://mcp.jurisprudenciator.lexiaipro.org/mcp`
  Tools: `buscar_sentencias`, `buscar_por_cita`, `leer_sentencias`, `opciones_busqueda`,
  `resolver_captcha`, `estado`.
- **Dropbox** (MCP remoto oficial) - gestion documental del despacho.
  Endpoint: `https://mcp.dropbox.com/mcp`. Requiere iniciar sesion (OAuth) al activarlo.

Al instalar el plugin solo hay que activar los conectores en el chat/proyecto.

## Instalacion

```
claude plugin marketplace add <owner>/litigacion-civil-espana
claude plugin install litigacion-civil-espana@litigacion-civil-espana
```

O desde la app: `+` -> "Anadir plugins..." -> pegar la URL del repositorio.

## Skills

Incluye las skills de cartera de asuntos y redaccion de escritos: intake y briefing de
asuntos, demandas, contestaciones, recursos (reposicion, apelacion, casacion y queja),
ejecucion y oposicion a la ejecucion, declinatoria, medidas cautelares, nulidad de
clausulas abusivas, conclusiones y prueba, incidente de nulidad, terminacion anticipada,
MASC, cronologias, cuadros de elementos, interrogatorios, tasaciones de costas, burofax,
hoja de encargo y mas. La configuracion del despacho se hace con `/cold-start-interview`
y `/customize`.

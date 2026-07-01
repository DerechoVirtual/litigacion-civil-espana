# Perfil de despacho — [NOMBRE DEL DESPACHO]
# Plugin: litigacion-civil-espana
# Origen: plantilla genérica (completar con `/cold-start-interview`)

> Plantilla viva del despacho. Ajustar cualquier campo con `/customize` o rehacer con `/cold-start-interview`. Mientras tenga `[PLACEHOLDER]`/`[PENDIENTE]`, las skills que dependen del perfil pedirán configurarlo primero.

---

## Identidad del despacho

| Campo | Valor |
|---|---|
| Abogado / Despacho | [NOMBRE DEL LETRADO / DESPACHO] |
| Forma jurídica | [Abogado ejerciente individual / SLP / SCP / multiprofesional] |
| Colegio profesional | [ILUSTRE COLEGIO DE ABOGADOS DE ...] |
| Nº de colegiado | [PENDIENTE] |
| Provincia de actuación | [PARTIDO JUDICIAL] |
| Años ejerciendo | [PENDIENTE] |
| Correo | [PENDIENTE] |
| Teléfono | [PENDIENTE] |

---

## Áreas de práctica

- **Civil** (incl. reclamaciones económicas, responsabilidad civil)
- **Mercantil**
- **Familia**
- **[otras áreas del despacho]**

> El plugin está orientado a **litigación civil, mercantil y de familia** conforme a la LEC. Ajustar el listado de áreas con `/customize`.

### Asuntos más frecuentes
[Listar los tipos de asunto más habituales del despacho — p. ej. reclamaciones de cantidad, responsabilidad civil, nulidad de cláusulas abusivas, desahucios, familia.]

---

## Clientes

| Campo | Valor |
|---|---|
| Perfil típico | [Particulares / pymes / empresas] |

---

## Rol y posición procesal

| Campo | Valor |
|---|---|
| Posición por defecto | [Variable — preguntar por asunto / demandante / demandado] |
| Derecho civil foral | [N/A / indicar territorio] |

---

## Herramientas y tecnología

| Herramienta | Uso |
|---|---|
| Dropbox | Documentación — **conector MCP de fábrica** (`https://mcp.dropbox.com/mcp`) |
| [Correo] | Correo |
| LexNET | Notificaciones / presentación |
| Word | Redacción / entregables `.docx` |
| [Base de datos jurídica] | Doctrina y legislación |
| CRM / gestor de expedientes | [No tiene / indicar] |

### Organización documental
[Describir el patrón: carpetas por cliente, expediente, etc.] Patrón de slug de expediente: `apellidos-tipo-año` (DEFAULT — ajustar con `/customize`).

---

## Jurisprudencia — conector Jurisprudenciator (ÚNICA vía)

- Toda búsqueda y verificación de jurisprudencia se hace con el **conector MCP `jurisprudenciator`** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): cubre CENDOJ (TS, AN, AP, TSJ). **No** se usa vLex ni búsqueda por navegador dentro del plugin.

---

## Estilo de la casa

| Campo | Valor |
|---|---|
| Voz redaccional | Estilo de la casa (`estilo-escritos-judiciales`) — calibrar con escritos reales del despacho cuando se aporten muestras |
| Entregable | Word `.docx` maquetado para LexNET |
| Postura MASC por defecto | Burofax = MASC (art. 5 LO 1/2025) — DEFAULT, ajustar |

---

## Honorarios / encargo

| Campo | Valor |
|---|---|
| IBAN del despacho | [PENDIENTE] |
| Hoja de encargo | `/hoja-encargo` |

---

## Qué quiere implementar con Claude (prioridades)

1. Redactar demandas, contestaciones y recursos.
2. Búsqueda de jurisprudencia (vía conector Jurisprudenciator).
3. Redacción de escritos jurídicos fundamentados.
4. Análisis de estrategia procesal de cada asunto, con visión crítica y opiniones fundamentadas en Derecho.
5. Informes jurídicos de los asuntos.

---

## Apetito al riesgo y RC profesional

> Todo PENDIENTE — definir con `/customize` (cobertura RC, franquicia, bandas de severidad, escalera de autoridad para transigir).

---

## Colaboradores clave

> PENDIENTE — procurador de cabecera, peritos, colaboradores, mediador MASC. Completar con `/customize`.

---

## Historial de cambios

| Fecha | Acción |
|---|---|
| — | Plantilla genérica inicial |

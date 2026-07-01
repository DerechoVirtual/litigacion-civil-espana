---
name: subsuncion-juridica
description: Jurisprudencia SIEMPRE con el conector MCP jurisprudenciator (tools buscar_sentencias, buscar_por_cita, leer_sentencias); es la unica via, sin vLex ni Google Chrome. Pulido y revision de escritos para conectar jurisprudencia con hechos concretos del asunto. Transforma citas sueltas en argumentacion subsuntiva. Usar con pulir escrito o conectar jurisprudencia.
---

# Subsunción jurídica — pulido del escrito

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- AUTOMÁTICAMENTE tras `redactar-demanda`, `redactar-contestacion`, `recurso-apelacion`, etc.
- Petición explícita: "pulir escrito", "conectar jurisprudencia con hechos"
- Cuando una primera versión cita STS pero no la conecta al caso concreto

## Patrón a corregir (citas "sueltas")

❌ MAL:

> "...la jurisprudencia del Tribunal Supremo en STS [ECLI] establece que el incumplimiento
> contractual debe ser esencial. En el presente caso, la contraparte no cumplió..."

✅ BIEN (subsuntivo):

> "...la jurisprudencia del Tribunal Supremo, en STS [ECLI], exige que el incumplimiento
> contractual sea ESENCIAL para activar la resolución del 1124 CC. Aplicada esta doctrina
> al presente caso, la falta de entrega de la mercancía pactada en plazo no es accesoria
> ni subsanable: era el OBJETO MISMO del contrato (cláusula segunda del Doc. Nº 3), y su
> ausencia ha obligado al cliente a aprovisionarse alternativamente con un coste
> documentado de 12.500 € (Doc. Nº 9). Concurre, por tanto, el carácter esencial que el
> Supremo exige para fundar la resolución contractual con devolución del precio anticipado
> e indemnización de daños."

## Flujo

### 1. Leer escrito

Cargar el documento generado por skill aguas arriba.

### 2. Localizar citas jurisprudenciales

Identificar cada STS / SAP / TJUE / TC citado.

### 3. Para cada cita, comprobar:

- ¿Hay HECHOS del caso citados expresamente?
- ¿La cita lleva al "por tanto, aplicado al caso concreto..."?
- ¿Se nombra el Documento Nº [X] que sostiene la conexión?

### 4. Si la cita está "suelta"

Reescribir la frase añadiendo:
- **El elemento jurisprudencial concreto** (qué doctrina sienta la STS)
- **La subsunción al caso** (hecho concreto del cliente que materializa el elemento)
- **La conclusión jurídica derivada** (qué tiene que hacer el tribunal)

### 5. Eliminar redundancia

Si dos STS dicen lo mismo, citar la más reciente y la unificadora. No abrumar con jurisprudencia repetitiva.

### 6. Output

Escrito pulido + diff frente al original, marcando los cambios.

## Reglas

1. **Jurisprudencia que no conecta es jurisprudencia perdida.** Si una cita no aterriza en el caso, fuera.
2. **Cada cita = un punto subsuntivo concreto.** No "como la jurisprudencia mayoritaria entiende..." (vago) sino "como la STS [ECLI] establece que [doctrina concreta], aplicado al presente caso [hecho concreto]..."
3. **Documentos Nº [X] son la cuerda** entre hechos y doctrina. Si la frase no menciona el documento, no está subsumiendo.
4. **NO inventar.** Si no se puede aterrizar la cita con los documentos existentes, marcar `[REVISAR: jurisprudencia citada no aterrizada — eliminar o sustituir]`.

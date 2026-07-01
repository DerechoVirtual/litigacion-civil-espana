---
name: revision-secreto-profesional
description: Primera pasada de clasificacion de comunicaciones bajo el secreto profesional del abogado art 542.3 LOPJ y art 5 EGA. Marca cubiertos, dudosos y no cubiertos. Usar con revisar secreto profesional.
---

# Revisión de secreto profesional

## Cuándo activar

- "Revisar secreto profesional", "clasificar comunicaciones"
- Ante requerimiento judicial de aportar documentación que pueda incluir comunicaciones cubiertas
- Antes de aportación documental en pleito (filtrar lo que NO se debe aportar)
- Tras intercambio masivo de correos en un asunto

## Marco

- **Art. 542.3 LOPJ** — Los abogados deberán guardar secreto de todos los hechos o noticias de que conozcan por razón de cualquiera de las modalidades de su actuación profesional, no pudiendo ser obligados a declarar sobre los mismos.
- **Art. 5 EGA** — Secreto profesional del abogado (deber y derecho)
- **Art. 199 CP** — Tipificación penal de revelación.
- **Excepciones**: Ley 10/2010 PBC/FT (obligación de comunicación bajo ciertos supuestos), proceso penal con autorización judicial específica (art. 32-33 EGA), consentimiento del cliente.

## Categorización por defecto

### ✅ Claramente cubierto (NO aportar):
- Correos abogado ↔ cliente durante la relación profesional
- Notas internas del abogado sobre la estrategia
- Borradores no firmados de escritos
- Comunicaciones del abogado con peritos contratados para asesoramiento (antes de su nombramiento judicial)
- Comunicaciones con colaboradores externos en el contexto del asunto

### 🟡 Dudoso (marcar para revisión letrada):
- Correos abogado-cliente cuyo asunto es mixto jurídico-empresarial (ej. "redacción contrato mercantil + consejo sobre la operación")
- Comunicaciones con peritos tras su nombramiento judicial (parte del expediente, no secreto)
- Comunicaciones que involucran a terceros (familia del cliente, otros profesionales)
- Comunicaciones donde el cliente comunica intención de cometer ilícito futuro (la actuación profesional sólo protege el secreto sobre actos pasados o legítimos)
- Documentos del cliente entregados al abogado pero no creados por él

### ❌ Claramente NO cubierto (aportar si se requiere):
- Documentos del cliente preexistentes a la relación profesional (contratos, facturas — son del cliente)
- Comunicaciones del cliente con terceros que no son su abogado
- Hechos públicos
- Documentos del proceso (autos, sentencias, escritos presentados)

## Flujo

### 1. Cargar input

- Lista de comunicaciones / documentos a clasificar (carpeta, lote, intercambio de correos)
- Asunto + relación temporal entre los documentos y la apertura del encargo profesional

### 2. Clasificar cada documento

Para cada uno:
- Asignar categoría (✅ cubierto / 🟡 dudoso / ❌ no cubierto)
- Razón breve (en una frase)

### 3. Output

`matters/<slug>/secreto-profesional-review.md`:

```markdown
# Revisión de secreto profesional — [slug]
Total documentos: [N]

## Cubiertos (N) — NO aportar
- [Doc 1] Correo cliente-abogado [fecha] — asunto: [...] — razón: comunicación durante encargo profesional
- ...

## Dudosos (N) — REVISIÓN LETRADA OBLIGATORIA
- [Doc 5] Correo abogado-perito [fecha] — razón: el perito fue después nombrado judicialmente, dudosa cobertura tras nombramiento
- ...

## No cubiertos (N) — Pueden aportarse si se requiere
- [Doc 12] Factura del cliente a contraparte [fecha] — razón: documento preexistente a relación profesional
- ...

## Recomendaciones
- Antes de aportar lote, decidir caso por caso los 🟡
- Si requerimiento judicial: posible motivo de oposición sobre los ✅
- Si pleito penal: revisar arts. 32-33 EGA específicamente
```

### 4. Decision tree

> 1. **Revisar los 🟡 uno a uno** con el letrado
> 2. **Preparar oposición fundada al requerimiento** si afecta a documentos ✅
> 3. **Aportar los ❌** si así se ha decidido

## Reglas

1. **El secreto pertenece al cliente** (es renunciable por él, no por el abogado). Si el cliente quiere aportar comunicación abogado-cliente, puede hacerlo.
2. **Excepciones tasadas**: Ley 10/2010 PBC/FT, autorización judicial específica en penal.
3. **NUNCA hacer juicio definitivo automatizado.** Esto es primera-pasada. El letrado revisa los 🟡 antes de aportar.
4. **Conservar documentos en originales**: aunque no se aporten al expediente, conservarlos en el despacho con cabecera de secreto.

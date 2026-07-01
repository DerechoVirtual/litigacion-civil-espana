---
name: burofax-intake
description: Pre-redaccion de burofax. Recoge contexto sobre partes, hechos, base juridica, leverage, BATNA, plazo razonable y filtros de confidencialidad. Usar con preparar burofax o necesito reclamar.
---

# Intake de burofax

## Cuándo activar

- "Preparar burofax", "redactar burofax", "necesito reclamar a X"
- "Burofax MASC para Ley 1/2025"
- "Requerimiento extrajudicial previo a demanda"

## Flujo

### 1. Identificación

Vía `AskUserQuestion`:
- Slug del burofax (apellidos contraparte + tipo)
- Tipo de burofax:
  - Reclamación de cantidad
  - Resolución contractual + reclamación (1124 CC)
  - Cese y desistimiento (PI / honor / competencia desleal)
  - Devolución de fianza arrendaticia (LAU 36)
  - Preaviso desahucio falta de pago
  - Documentación MASC art. 5 Ley 1/2025
  - Otro

### 2. Partes

- Cliente (remitente)
- Destinatario (datos completos: nombre/razón social, NIF/CIF, domicilio para notificaciones)

### 3. Hechos y base

- Hechos breves (3-5 frases)
- Base jurídica del requerimiento (cita de artículos: 1124 CC / 1100 CC / 36 LAU / etc.)
- Documentos que sostienen el requerimiento (contratos, facturas, recibos, escrituras)

### 4. Pretensión

- Concreta: cuantía exacta / cumplimiento específico / cese de actividad / devolución
- Plazo razonable para cumplir (mínimo 15 días recomendable, 30 si es MASC)

### 5. Leverage y BATNA

- ¿Qué pasa si no cumple? (demanda monitorio/ordinario, ejecución, otros)
- ¿Estamos dispuestos a negociar? Si sí, qué margen
- ¿Hay riesgo reputacional o relacional que limite el tono?

### 6. Filtros de confidencialidad

- ¿Marcamos "sin perjuicio"? (típico para negociación que no quiera vincular en pleito)
- ¿Marcamos "como acto preparatorio del MASC art. 5 Ley 1/2025"?
- ¿Marcamos confidencialidad de la oferta?
- ¿Quién firma: cliente directamente / letrado / ambos?

### 7. Salida

Escribir `burofaxes/<slug>/intake.md`:

```markdown
# Intake — Burofax [slug]

**Fecha:** [...]
**Tipo:** [...]
**Cliente:** [...]
**Destinatario:** [...]

## Hechos
[...]

## Base jurídica
[...]

## Pretensión
[...]

## Plazo concedido
[...]

## Leverage / BATNA
[...]

## Filtros
- Sin perjuicio: sí/no
- MASC art. 5 Ley 1/2025: sí/no
- Confidencialidad: sí/no
- Firmante: [...]

## Documentos a adjuntar
- [...]
- [...]
```

## Decision tree

> **¿Pasamos a redactar?**
> 1. **Redactar Word** — `/burofax-draft <slug>`
> 2. **Editar intake antes** — dime qué cambiar
> 3. **Lo dejo guardado para más tarde** — intake.md queda escrito

## Reglas

1. **Plazo razonable mínimo 15 días** para reclamaciones; **30 días si es MASC** del art. 5 Ley 1/2025.
2. **Confidencialidad** debe pactarse expresamente — si no se pacta, la otra parte puede usar el burofax en pleito.
3. **Identificación completa del destinatario** o el burofax no acredita notificación.

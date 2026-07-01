---
name: portfolio-status
description: Rollup de la cartera de asuntos. Distribucion por riesgo, plazos proximos, asuntos estancados y anomalias. Usar con donde estoy, estado cartera o cuantos asuntos abiertos.
---

# Estado de cartera

## Cuándo activar

- "¿Dónde estoy?", "estado cartera", "qué tengo encima"
- "Cuántos asuntos abiertos", "rollup", "panorama"
- "Plazos esta semana", "qué tengo que hacer urgente"
- Antes de reunión de planificación

## Flujo

### 1. Leer fuente de verdad

- `matters/_log.yaml` — todos los asuntos
- Por defecto filtrar `status: open` (incluir closed con `--all`)

### 2. Calcular agregados

- **Distribución por riesgo:** count por `risk` ({critico, alto, medio, bajo})
- **Distribución por tipo:** count por `type`
- **Distribución por posición:** count por `side` (actor / demandado / mixto)
- **Próximos plazos (14 días):** ordenar por `next_deadline`, mostrar los que caen en los próximos 14 días
- **Asuntos estancados:** `last_updated` >30 días
- **Asuntos sin MASC acreditado** (con tipo que lo exige): cualquier `masc_acreditado: no` en asuntos donde el tipo requiera (ordinario, verbal no exento, desahucio, divorcio contencioso)
- **Cuantía total cartera:** suma de `cuantia` (informativa)

### 3. Detectar anomalías

Marcadores automáticos:
- 🔴 Asunto con `next_deadline` ya pasada (deadline incumplida)
- 🟠 Asunto con `next_deadline` <7 días sin actualización
- 🟡 Asunto `last_updated` >60 días sin movimiento
- 🟡 Asunto sin `procurador` cuando el tipo lo requiere
- 🟡 Asunto sin `cuantia` (cuando el tipo permite cuantificación)
- 🔴 Demanda en preparación >30 días sin MASC acreditado

### 4. Output

```
⚠️ Nota del revisor: lectura completa de _log.yaml · N asuntos abiertos · M anomalías marcadas

## Cartera (al [FECHA])

**Asuntos abiertos:** N
**Distribución por riesgo:** 🔴 Crítico: A · 🟠 Alto: B · 🟡 Medio: C · 🟢 Bajo: D
**Distribución por tipo:** ordinario: X · verbal: Y · monitorio: Z · ...
**Cuantía total estimada:** XX.XXX €

### Próximos plazos (próximos 14 días)

| Fecha | Slug | Acción | Riesgo |
|---|---|---|---|
| ... | ... | ... | ... |

### Anomalías (N)

🔴 [slug] — Plazo incumplido: [fecha pasada] — [qué era]
🟠 [slug] — MASC no acreditado y demanda en preparación
🟡 [slug] — Sin movimiento desde [fecha]

### Asuntos críticos (más cercanos)

[3-5 entradas con: slug, nombre, riesgo, próximo plazo, última actualización]
```

### 5. Decision tree

> **¿Qué hago ahora?**
> 1. **Deep dive en uno** — `/briefing-asunto <slug>` para ver detalle
> 2. **Resolver anomalías** — empezar por las 🔴
> 3. **Generar emails a colaboradores** — `/colaboradores-status` para semana
> 4. **Cerrar asuntos terminados** — si la lista incluye candidatos a cerrar
> 5. **Dashboard interactivo** — montar `create_artifact` con la cartera (recomendable si N>10)

📊 **Verlo como dashboard?** Si N > 10, ofrecer artifact con: summary stats arriba, tabla color-coded sortable por riesgo/plazo, gráfico de distribución, nota del revisor. En Cowork renderiza inline.

## Variantes

- `--all`: incluir cerrados
- `--risk-high`: solo alto/crítico
- `--by-procurador`: agrupar por procurador asignado
- `--by-tribunal`: agrupar por tribunal de instancia

## Reglas

1. **Severity floor.** Un asunto marcado `critico` en log no puede mostrarse como rutinario en rollup.
2. **No inventar plazos.** Si `next_deadline` está vacío, mostrar "—", no asumir.
3. **Asuntos cerrados fuera de rollup activo** salvo `--all`.

---
name: briefing-asunto
description: Briefing profundo de un asunto. Posicion actual, cambios, proximo plazo, cuestiones abiertas y re-evaluacion de riesgo. Usar con briefing o donde estamos con el asunto.
---

# Briefing de asunto

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- "Briefing de [slug]", "ponme al día con [asunto]"
- "Dónde estamos con [asunto]"
- Antes de reunión con cliente, llamada con procurador, vista, audiencia previa
- Cuando un colaborador externo pide estado

## Flujo

### 1. Identificar asunto

Si no se da slug, listar candidatos por:
- Asunto activo en CLAUDE.md
- Asuntos con `next_deadline` próximo
- Últimos actualizados

### 2. Leer fuentes

- `matters/<slug>/matter.md` — intake + tesis
- `matters/<slug>/history.md` — eventos
- Fila correspondiente de `_log.yaml`
- Escritos en `matters/<slug>/escritos/` (lista con fechas)
- Jurisprudencia archivada en `matters/<slug>/jurisprudencia/`
- Cronología si existe en `matters/<slug>/cronologia.md`

### 3. Sintetizar briefing

Estructura:

```
**[Slug] — [Nombre del asunto]**
Cliente: [nombre + posición procesal]
Contraparte: [nombre + abogado contraparte]
Tribunal: [Tribunal de Instancia + sección]
Cuantía: [€]
Estado: [open / stayed]
Riesgo: [icono + nivel]
Materialidad: [alta/media/baja]

---

## Tesis del asunto
[2-3 frases — la "historia" que vamos a contar]

## Posición procesal actual
[En qué fase está: pre-demanda / contestación pendiente / audiencia previa fijada / esperando sentencia / apelación / ejecución]

## Hitos desde la última actualización
[Eventos de history.md desde el último briefing — fechas + qué ocurrió]

## Próximo plazo crítico
[Fecha + qué hay que hacer + cómputo: "20 días hábiles desde notificación del XX-XX, vence el YY-YY"]

## Cuestiones abiertas
- [pregunta 1 que necesita decisión]
- [pregunta 2 que necesita información del cliente]

## Re-evaluación de riesgo
[Sigue siendo X o ha cambiado? Si cambia, propuesta de nuevo nivel y razón]

## Jurisprudencia clave en el asunto
- [STS o SAP con ECLI/ROJ — punto que sostiene]
- ...

## MASC
[Acreditado sí/no — si no, qué falta]

## Conservación documental
[Acreditada al cliente / pendiente / liberada]
```

### 4. Decision tree

> **¿Qué hago ahora?**
> 1. **Redactar el siguiente escrito** — `/redactar-demanda` / `/redactar-contestacion` / `/recurso-apelacion`
> 2. **Actualizar history con nuevos hitos** — `/actualizar-asunto <slug>`
> 3. **Cronología defensiva u ofensiva** — `/cronologia <slug>`
> 4. **Cuadro de elementos** — `/cuadro-elementos <slug>`
> 5. **Preparar interrogatorio** — `/preparacion-interrogatorio <slug> <nombre>`
> 6. **Tirar de jurisprudencia** — el conector MCP `jurisprudenciator` (`buscar_sentencias`)

## Reglas

1. **No reinventar la tesis.** Si `matter.md` tiene tesis, usarla. Si en `history.md` se cambió, marcarlo.
2. **Cómputo de plazos siempre hábiles** (LEC 133). Sábados no hábiles. Agosto inhábil salvo medidas urgentes.
3. **Pre-flight check** del conector `jurisprudenciator` antes de citar nueva jurisprudencia en el briefing.
4. **No narrar acciones del plugin** ("estoy leyendo history.md..."). Solo el briefing limpio.

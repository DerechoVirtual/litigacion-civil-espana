---
name: matter-workspace
description: Gestionar workspaces de asunto. Crear, listar, cambiar, cerrar o desligar el asunto activo. Usar con cambiar asunto, listar mis asuntos o asunto activo.
---

# Gestión de workspaces de asunto

## Cuándo activar

- "Nuevo asunto" → derivar a `/asunto-intake`
- "Listar mis asuntos" / "qué tengo abierto" → `list`
- "Cambiar a asunto X" / "trabaja en X" → `switch`
- "Cerrar asunto X" → derivar a `/cerrar-asunto`
- "Trabaja a nivel despacho" / "sin asunto activo" → `detach`
- Cuando un skill necesita saber qué asunto está activo

## Subcomandos

### `list`

Leer `matters/_log.yaml`. Mostrar tabla compacta:

| Slug | Nombre | Estado | Riesgo | Tipo | Próximo plazo |
|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... |

Filtros opcionales:
- `--active` (default): solo `status: open`
- `--all`: incluir cerrados
- `--closed`: solo cerrados
- `--risk-high`: solo riesgo alto/crítico

### `switch <slug>`

1. Verificar que el slug existe en `_log.yaml`.
2. Si existe, escribir `## Workspaces de asuntos` → `Asunto activo: <slug>` en CLAUDE.md de config.
3. Confirmar: "✅ Asunto activo: <slug> (<nombre>). Riesgo: <riesgo>. Próximo plazo: <fecha>."
4. Si no existe, mostrar fuzzy match con los más cercanos y preguntar.

### `new <nombre>`

Derivar a `/asunto-intake` con `<nombre>` como sugerencia.

### `close <slug>`

Derivar a `/cerrar-asunto`.

### `detach`

Escribir `Asunto activo: ninguno` en CLAUDE.md. Skills trabajarán a nivel despacho (contexto general, sin carpeta de asunto).

### `status`

Mostrar:
- Asunto activo (o "ninguno — trabajo a nivel despacho")
- Cross-matter context (`on` / `off`)
- Carpeta del asunto activo: `matters/<slug>/`
- Última actualización
- Próximo plazo crítico

## Cuando un skill pregunta

Si un skill de trabajo (redactar-demanda, briefing-asunto, cronología, etc.) necesita asunto y no hay ninguno activo:

> "Workspaces de asunto están habilitados. ¿Qué asunto? Opciones:
> 1. Trabajar en uno existente: [primeros 5 slugs con nombre]
> 2. Crear nuevo: dime el nombre y disparo `/asunto-intake`
> 3. Trabajar a nivel despacho (sin asunto): responde 'sin asunto'."

## Reglas

1. **Asunto activo es único.** No hay multi-activo.
2. **Cross-matter context off por defecto.** Un skill en asunto A no lee archivos del B.
3. **Detach no borra nada.** Solo desactiva el contexto.
4. **`Asunto activo: ninguno`** no equivale a "ningún asunto en cartera". Solo significa que el contexto activo es general.

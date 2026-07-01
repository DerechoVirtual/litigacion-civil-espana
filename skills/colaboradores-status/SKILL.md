---
name: colaboradores-status
description: Genera borradores semanales de emails de estado a colaboradores externos como procurador, perito o abogado colaborador. Usar con estado a colaboradores o emails al procurador esta semana.
---

# Estado a colaboradores externos

## Cuándo activar

- Lunes mañana (rutina recomendada)
- "Estado al procurador", "emails de la semana"
- Tras hitos procesales que requieran activar colaboradores

## Flujo

### 1. Leer cartera

`matters/_log.yaml` filtrar `status: open` y agrupar por procurador / perito / abogado colaborador.

### 2. Para cada colaborador

Generar un borrador con TODOS los asuntos donde participa:

```
Para: [procurador@email]
Asunto: Asuntos activos — petición de estado [semana del AAAA-MM-DD]

Estimado/a [Procurador],

Por favor, me confirmes el estado actualizado de los siguientes asuntos:

1. [Slug 1] — [Nombre] — TI Civil [N] Sección [X] de [Provincia]
   - Procedimiento: [tipo + nº]
   - Último plazo conocido: [fecha + acción]
   - Pregunta concreta: [si tiene resolución pendiente / notificación / etc.]

2. [Slug 2] — [Nombre] — [...]
   ...

Especialmente urgente: [los que tengan plazo en <14 días]

Gracias.

[NOMBRE DEL LETRADO]
Colegiado nº [...] [COLEGIO DE ABOGADOS]
```

### 3. Gmail MCP

Si Gmail MCP está autenticado, crear borrador real en Gmail listo para revisar y enviar.

Si no, escribir markdown en `colaboradores-status/[fecha]/[slug-colaborador].md`.

### 4. Resumen general

`colaboradores-status/[fecha]/_summary.md`:

```markdown
# Estado a colaboradores — Semana del [AAAA-MM-DD]

## Procuradores
- [Procurador 1]: N asuntos — borrador generado
- [Procurador 2]: M asuntos — borrador generado

## Peritos
- [Perito 1]: K asuntos — borrador generado

## Abogados colaboradores
- [Colaborador 1]: J asuntos — borrador generado

## Asuntos sin colaborador asignado
[Listar para que el letrado los revise]
```

### 5. Decision tree

> 1. **Revisar y enviar borradores** desde Gmail
> 2. **Personalizar uno concreto** — dime cuál
> 3. **Programar como recurrente cada lunes** — vía scheduled-tasks

## Reglas

1. **NO enviar automáticamente.** Solo borradores. el letrado revisa y dispara.
2. **Una pregunta concreta por asunto** — no "estado en general".
3. **Agrupar por colaborador**, no por asunto. Más eficiente para el colaborador.
4. **Marcar urgencias** explícitamente al principio del email.

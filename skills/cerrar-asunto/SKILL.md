---
name: cerrar-asunto
description: Cerrar asunto. Captura outcome, lecciones aprendidas y archiva fuera de la cartera activa sin borrar. Usar con cerrar asunto o asunto terminado.
---

# Cerrar asunto

## Cuándo activar

- "Cerrar [slug]", "[asunto] está terminado"
- Sentencia firme + plazo de apelación agotado
- Transacción suscrita y cobrada
- Desistimiento firme
- Ejecución completada (cobro íntegro o insolvencia archivada)
- Carencia de objeto sobrevenida

## Flujo

### 1. Verificar pertinencia

- Comprobar `status: open` en `_log.yaml`.
- Si ya está `closed`, avisar y no duplicar.
- Si `next_deadline` está a <14 días, preguntar dos veces.

### 2. Capturar outcome

Vía `AskUserQuestion`:

- **Tipo de cierre:**
  - Sentencia firme estimatoria total
  - Sentencia firme estimatoria parcial
  - Sentencia firme desestimatoria
  - Transacción judicial homologada
  - Transacción extrajudicial
  - Desistimiento del actor
  - Allanamiento del demandado
  - Caducidad de la instancia
  - Acumulación a otro asunto (apuntar slug receptor)
  - Renuncia / retirada del encargo
- **Cuantía finalmente recuperada / pagada** (si aplica)
- **Costas:** a favor / en contra / sin pronunciamiento
- **Recursos pendientes:** sí (cuál) / no
- **Honorarios cobrados / pendientes**

### 3. Lecciones (opcional)

- Una frase: qué aprendiste del asunto
- ¿Cambiarías algo de la estrategia con la perspectiva de hoy?
- ¿Hay algo de este asunto que deba viajar al `CLAUDE.md` del despacho? (ej. "este tipo de cláusula se resuelve mejor con esta tesis")

### 4. Actualizar estado

#### `matters/<slug>/matter.md`

Añadir sección al final:
```
---

## Cierre — [AAAA-MM-DD]

**Outcome:** [tipo]
**Cuantía recuperada/pagada:** [€]
**Costas:** [a favor / en contra / sin pronunciamiento]
**Recursos pendientes:** [no / sí: <descripción>]
**Honorarios:** [cobrados / pendientes]

**Lección:** [una frase]
```

#### `matters/<slug>/history.md`

```
[AAAA-MM-DD] CIERRE — [tipo de cierre]. [resumen 1-2 frases]
```

#### `matters/_log.yaml`

- `status: closed`
- `closed: AAAA-MM-DD`
- `outcome: <tipo>`
- `last_updated: hoy`
- Si tiene recurso pendiente: NO cerrar — preguntar si crear sub-asunto de apelación y mantener el principal `stayed`.

### 5. Archivar artefactos

NO mover archivos. Quedan donde están en `matters/<slug>/` para histórico.

Si workspaces de asunto y el asunto cerrado era el activo, escribir `Asunto activo: ninguno` en CLAUDE.md.

### 6. Si el outcome implica seguimiento

- **Costas a favor pendientes de tasación:** ofrecer crear sub-asunto o usar `/tasacion-costas <slug>`.
- **Cobro pendiente tras sentencia firme:** ofrecer crear asunto de ejecución forzosa con `/redactar-demanda-ejecutiva` o seguir en el mismo asunto.
- **Honorarios pendientes:** ofrecer `/jura-cuentas` si el procurador o el cliente no paga.
- **Aprendizaje que toca al despacho:** si dijo "esto debería viajar al CLAUDE.md", proponer línea concreta a añadir y abrir `/customize`.

### 7. Output

```
✅ Asunto [slug] cerrado.

**Outcome:** [tipo]
**Cuantía:** [€]
**Costas:** [a favor / en contra]
**Archivado:** matters/<slug>/ (intacto, retenido en cartera con status=closed)

[Si tiene seguimientos pendientes:]
**Pendiente:** [tasación de costas / ejecución / honorarios]
**Sugerido:** [siguiente comando]
```

## Reglas

1. **No borrar.** Cerrar = `status: closed`. Los archivos quedan para histórico.
2. **Recurso pendiente bloquea cierre.** El asunto solo se cierra cuando es firme. Si hay apelación viva, mantener `status: stayed` o abrir sub-asunto.
3. **Honorarios pendientes ≠ asunto abierto.** El asunto puede cerrarse aunque haya cobro pendiente; pero registrar en `outcome` y considerar `/jura-cuentas`.
4. **Lecciones que viajan al despacho** se escriben a CLAUDE.md, no a la carpeta del asunto cerrado.

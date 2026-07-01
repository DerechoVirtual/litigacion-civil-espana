---
name: customize
description: Editar un campo del perfil de despacho sin re-correr todo el cold-start. Cambiar provincia, colaboradores, calibracion de riesgo, plantillas, integraciones. Usar con cambiar mi perfil o customize.
---

# Customize — editar un campo concreto

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- "Cambiar mi [campo]"
- "Actualizar mi perfil"
- "Editar [sección]"
- "Añadir procurador / perito / plantilla / contraparte habitual"
- "Mi provincia ha cambiado a X"

## Flujo

### 1. Comprobar que hay perfil

Leer `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md`. Si tiene `[PLACEHOLDER]` masivos, derivar a `/cold-start-interview` — customize no es el camino para configurar desde cero.

### 2. Detectar qué campo

Si el usuario nombra el campo, ir directo. Si no, mostrar menú:

```
¿Qué cambiamos?
1. Despacho (forma jurídica, colegio, provincia, colegiado)
2. Rol procesal y posición default
3. Colaboradores (procurador / perito / abogado colaborador / mediador)
4. Calibración de riesgo (apetito / bandas / autoridad para transigir / RC)
5. Panorama (Tribunales habituales, contrapartes, Derecho civil foral)
6. Estilo de la casa (voz, briefing al cliente, plantillas, MASC default)
7. Almacenamiento documental (carpeta raíz, slug pattern)
8. Conflictos (método)
9. Integraciones (conector `jurisprudenciator` — re-comprobar)
10. Documentos semilla (apuntadores a plantillas)
```

### 3. Hacer el cambio

Vía `AskUserQuestion`:
- Mostrar valor actual
- Pedir nuevo valor
- Confirmar antes de escribir

### 4. Validaciones

- **Provincia cambia → revisar Tribunales habituales** (preguntar si también cambian)
- **Posición procesal cambia → revisar plantillas activas** (las que se usen)
- **Colegio profesional cambia → revisar colegiado nº** (no encaja a otro colegio)
- **Cambio masivo de calibración riesgo → recomendar `/cold-start-interview --redo`**

### 5. Escribir

Editar `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md` modificando solo la línea/sección afectada. Mantener el resto idéntico.

El perfil de este plugin es autónomo del despacho; el cambio se guarda solo en su `CLAUDE.md` y no se comparte con ningún otro plugin.

### 6. Output

```
✅ Actualizado.

**Campo:** [nombre]
**Antes:** [valor anterior]
**Ahora:** [valor nuevo]

[Si dispara otras revisiones:]
**Posibles ajustes en cadena:** [sugerencias]
```

## Reglas

1. **Un campo por sesión.** Si el usuario quiere cambiar varios, hacerlos secuencialmente uno a uno (confirmando cada uno).
2. **NUNCA borrar campos.** Si el usuario quiere "vaciar" un campo, dejar `[PENDIENTE]` con nota, no borrar la fila.
3. **Cambios cross-plugin:** advertir si el campo está en `## Perfil del despacho`.

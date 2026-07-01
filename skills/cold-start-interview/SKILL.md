---
name: cold-start-interview
description: Configurar perfil de despacho de litigacion civil España. Captura especialidad, provincia, calibracion de riesgo, colaboradores, estilo de la casa. Usar con configurar plugin, cold-start, setup, redo.
---

# Cold-start del plugin de litigación civil España

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

Este skill escribe `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md` con tu perfil de práctica. Sin completar este paso, los demás skills paran y piden ejecutarlo.

## Cuándo activar

- Primera instalación del plugin (el `CLAUDE.md` está con marcadores `[PLACEHOLDER]`)
- Petición explícita: "configura el plugin", "cold-start", "setup", "vuelve a preguntarme el perfil"
- Flag `--redo` o `--check-integrations`

## Flujo de la entrevista

### Bloque 0: Comprobación previa

1. Leer `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md` si existe.
2. Si existe y NO tiene `[PLACEHOLDER]`, preguntar al usuario: "Ya tienes una configuración previa. ¿Quieres (a) re-correr todo desde cero, (b) editar un campo concreto con `/customize`, o (c) solo comprobar integraciones?"
3. Si no existe o tiene marcadores, seguir el flujo.

### Bloque 1: Despacho

Vía `AskUserQuestion` (bloques de 2-4 preguntas):

- Nombre del despacho / forma jurídica ([NOMBRE DEL LETRADO] ejerciente nº X / SLP / SCP / multiprofesional)
- Especialidad principal (civil / mercantil / familia / mixto / otro)
- Tamaño (solo / 2-3 / pequeño / mediano)
- Colegio profesional ([COLEGIO DE ABOGADOS] — [PARTIDO JUDICIAL] por defecto; ICAM / ICAB / ICAV / otro)
- Provincia(s) de actuación habitual
- Colegiado nº

### Bloque 2: Rol y posición procesal

- Rol: despacho-propio-solo / despacho-propio-equipo / abogado-colaborador-externo / pasante / otro
- Posición por defecto: actor / demandado / mixto-default-actor / mixto-default-demandado / varía
- (Si mixto) ¿Qué porcentaje aproximado? Solo para calibración futura.

### Bloque 3: Colaboradores clave

Preguntar uno a uno; permitir "no aplica":
- Procurador de cabecera (nombre + colegio + provincia)
- Procurador de territorio secundario (si actúa fuera de provincia principal)
- Perito económico habitual
- Perito técnico habitual
- Abogado colaborador penal (si los asuntos derivan a penal)
- Abogado colaborador laboral
- Mediador / experto MASC

### Bloque 4: Apetito al riesgo y RC profesional

- Postura general (cita libre): "fight principled / settle nuisance / evitar precedentes adversos / pelear cualquier asunto del cliente"
- Bandas de severidad cuantitativas (alta/media/baja en €)
- Bandas de probabilidad (alta/media/baja en %)
- Cobertura RC profesional: aseguradora + límite por siniestro + franquicia
- Umbral de comunicación urgente al cliente
- Escalera de autoridad para transigir (cuantías + decisor + documento de respaldo)

### Bloque 5: Panorama procesal

- Tribunales de Instancia habituales (sección + provincia)
- Audiencia Provincial habitual
- Derecho civil foral aplicable (N/A / Cataluña / Aragón / Galicia / Baleares / Navarra / País Vasco)
- Frecuencia de cada tipo de asunto (matriz: reclamación cantidad, desahucio, divorcio, cláusulas abusivas, RC contractual, RC extracontractual, propiedad horizontal, arrendamientos, sucesiones, mercantil, concursal)
- Contrapartes habituales si las hay (despachos contrarios que se ven con frecuencia)

### Bloque 6: Almacenamiento documental

- Carpeta raíz de asuntos (ej. C:/Asuntos/, Google Drive Despacho, OneDrive)
- ¿Compartes con cliente por email o por carpeta compartida?
- Patrón de slug por defecto (apellidos-tipo-año)

### Bloque 7: Conflictos

- Método: base-personal / colaboradores / informal / formal-colegio
- Qué se chequea (cliente actual, ex-cliente 5 años, parte adversa otros asuntos)
- ¿Bloquea intake antes de aceptar? sí / no / soft

### Bloque 8: Estilo de la casa

- Voz redaccional: por defecto pluma de la casa (estilo `estilo-escritos-judiciales`). Confirmar o pedir variantes.
- Briefing al cliente: formato + tono + cadencia
- Comunicación con procurador: formato + postura presupuestaria
- Postura por defecto ante MASC: "burofax-es-MASC" / "MASC formal con mediador" / "intento documentado por correo certificado" / "por asunto"

### Bloque 9: Integraciones (`--check-integrations`)

Comprobar disponibilidad real (no solo configuración):
- Conector `jurisprudenciator` (MCP remoto) → **única** vía de jurisprudencia del plugin; comprobar que responde (`estado` / `buscar_sentencias`). Si funciona, marca ✓
- Scheduled-tasks MCP → comprobar disponibilidad

Registrar en la tabla `## Integraciones disponibles` del CLAUDE.md.

### Bloque 10: Documentos semilla (opcional)

Preguntar si tiene plantillas existentes que pueda apuntar (modelos de demanda, hoja de encargo, minuta, política RGPD). Solo apuntadores; no copia.

## Salida

Escribir todo a `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md`. Si el directorio padre no existe, crearlo. Usar la PLANTILLA de `CLAUDE.md` que viaja con el plugin (`CLAUDE.md` en la raíz del plugin) como esqueleto, reemplazando `[PLACEHOLDER]` por las respuestas.

Para campos con multi-elección (matriz de severidad, integraciones, bandas), mantener la estructura de tabla.

Después de escribir el archivo, mostrar al usuario:
- "✅ Configurado. Tu perfil está en `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md`."
- Próximos pasos sugeridos: "Crea tu primer asunto con `/asunto-intake [nombre-asunto]`."
- Si el conector salió ✗: "jurisprudenciator no respondió — no se podrá buscar ni verificar jurisprudencia y las citas se marcarán como `[verificar]`. Activa el conector jurisprudenciator en el chat/proyecto."

## Variantes

- `--redo`: ignora el archivo existente; sobreescribe.
- `--check-integrations`: NO re-pregunta; solo actualiza la tabla `## Integraciones disponibles`.
- `--quick`: versión 2-minutos con solo: despacho, provincia, posición procesal, MASC default. Pone defaults razonables en lo demás y marca esos campos con `# DEFAULT — editar después con /customize`.

## Reglas

1. NUNCA escribir datos del usuario en el `CLAUDE.md` que viaja con el plugin. Siempre en la ruta de config (`~/.claude/plugins/config/...`).
2. NUNCA continuar con campos `[PLACEHOLDER]` cuando un skill de trabajo lo pida. Detenerse y pedir al usuario que complete con cold-start o customize.
3. El cold-start es FORMAL: no asumir respuestas, preguntar todo. Solo `--quick` o `--check-integrations` permiten defaults.

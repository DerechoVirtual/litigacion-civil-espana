---
name: asunto-intake
description: Intake de un nuevo asunto civil, mercantil o de familia. Recoge identificacion, conflictos, fuente, hechos, triage de riesgo, MASC y fechas criticas. Usar con nuevo asunto o intake este asunto.
---

# Intake de asunto — Litigación civil España

## Cuándo activar

- "Nuevo asunto", "intake", "abrir asunto", "vamos a empezar con este caso"
- Tras `/burofax-received` o `/requerimiento-judicial` cuando el triage escala a asunto
- Cuando hay una demanda recibida que requiere contestación

## Prerrequisito

`~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/CLAUDE.md` debe estar configurado. Si no, parar y derivar a `/cold-start-interview`.

## Flujo

### Bloque 1: Identificación

Vía `AskUserQuestion`:
- Nombre corto del asunto (para el slug — apellidos cliente + tipo)
- Cliente (persona física: nombre + DNI; persona jurídica: razón social + NIF)
- Contraparte (si conocida; "desconocida" si todavía no)
- Domicilio del cliente para notificaciones
- Tipo de asunto: reclamación-cantidad / desahucio / divorcio / cláusulas-abusivas / RC-contractual / RC-extracontractual / propiedad-horizontal / arrendamientos / sucesiones / mercantil / concursal / otro

### Bloque 2: Conflictos

Comprobar contra el método configurado en CLAUDE.md:
- ¿Es el cliente actual o de los últimos 5 años?
- ¿Es la contraparte cliente actual o ex-cliente?
- ¿Hay parte adversa en otro asunto activo coincidente?
- Si cualquier conflicto: detener intake y avisar. Si soft, registrar y seguir.

### Bloque 3: Fuente

- ¿Cómo llega el cliente? (recomendación / web / oficio del turno / despacho / colaborador)
- ¿Hoja de encargo firmada? Si no, recordar firmar antes de actos procesales.
- ¿Provisión de fondos? Cuantía + cobrada o pendiente.

### Bloque 4: Posición procesal

- Actor o demandado en este asunto (puede diferir del default del despacho)
- Si demandado, ¿ha sido notificada ya la demanda? Si sí, capturar fecha (plazo de contestación = 20 días hábiles desde notificación, LEC 404 ordinario / 438 verbal).

### Bloque 5: Hechos y pretensión

Capturar en libre forma:
- Resumen de hechos en 3-5 frases
- Pretensión principal (cuantía, condena específica, declaración, constitutiva)
- Pretensiones accesorias (intereses, costas)
- Cuantía exacta o estimada

### Bloque 6: Triage de riesgo

Aplicar matriz severidad × probabilidad del CLAUDE.md:
- Severidad estimada (alta/media/baja) según las bandas configuradas
- Probabilidad estimada (alta/media/baja) según las bandas configuradas
- Etiqueta resultante (Crítico / Prioritario / Rutina / Vigilar)
- Mapping a `_log.yaml`: critico / alto / medio / bajo

### Bloque 7: Materialidad

- Cuantía: alta / media / baja relativa al cliente
- Relación con el cliente (cliente recurrente / único asunto / cliente de relación)
- ¿Afecta a reputación del cliente?

### Bloque 8: Colaboradores y representación

- Procurador asignado (tomar default del CLAUDE.md o preguntar)
- Si el procedimiento exige procurador (regla general LEC 23 — todo menos verbal <2000 € y monitorio sin oposición)
- Perito necesario? Si sí, ¿cuál de los habituales?
- ¿Abogado colaborador? (si requiere especialidad cruzada)

### Bloque 9: Conservación documental

- ¿Hay riesgo de pérdida de prueba? (correos del cliente, contratos, registros bancarios)
- Generar comunicación al cliente recordando deber de conservación. Marcar `legal_hold: pending` en log para que `/conservacion-documental --emitir` la genere.

### Bloque 10: Fechas críticas

Capturar y calcular:
- Fecha de los hechos (para prescripción)
- Plazo de prescripción aplicable (art. 1964 CC — 5 años acciones personales; art. 1968 CC — 1 año responsabilidad extracontractual; art. 1969 CC para resto; o legislación foral)
- Si demandado: fecha de notificación + plazo de contestación (20 días LEC 404/438, computar como hábiles)
- MASC: ¿exento? (monitorio, ejecución, medidas cautelares previas, jurisdicción voluntaria, alimentos urgentes a menores) — si no exento, marcar `masc_acreditado: no` y planificar.
- Próxima fecha límite a vigilar

### Bloque 11: Posición inicial

- Tesis del asunto en 2-3 frases (la "historia" que vamos a contar)
- Puntos débiles ya identificados
- Cuestión jurídica central (ej. "interpretación cláusula penal art. 1152 CC", "validez de cláusula suelo", "imputación de gastos hipotecarios")

## Salida

1. Crear carpeta `~/.claude/plugins/config/derecho-virtual/litigacion-civil-espana-pro/matters/<slug>/`
2. Escribir `matter.md` con:
   - Cabecera `RESERVADO Y CONFIDENCIAL — SECRETO PROFESIONAL DEL ABOGADO`
   - Datos identificativos
   - Hechos y pretensión
   - Triage de riesgo
   - Tesis inicial
   - Fechas críticas
   - Colaboradores
   - Próximos pasos
3. Crear `history.md` con primera entrada `[AAAA-MM-DD] INTAKE — asunto creado.`
4. Crear subcarpetas `escritos/`, `jurisprudencia/`
5. Añadir fila a `matters/_log.yaml`:

```yaml
- slug: garcia-perez-reclamacion-2026
  name: García Pérez — Reclamación cantidad
  status: open
  side: actor
  risk: medio
  type: ordinario
  cuantia: 18500
  procurador: María López ([COLEGIO DE ABOGADOS] 1234)
  tribunal: TI Civil [PARTIDO JUDICIAL], Sección 4ª
  contraparte: Construcciones Sur SL
  abogado_contraparte: pendiente
  next_deadline: 2026-06-15  # MASC formal
  materiality: media
  related_matters: []
  conservacion_documental: pending
  masc_acreditado: no
  opened: 2026-05-13
  last_updated: 2026-05-13
  notas: "Demanda en preparación. Burofax-MASC pendiente."
```

6. Si workspaces de asunto están habilitados (default sí), preguntar: "¿Hacer este asunto el activo?" Si sí, escribir en CLAUDE.md → `## Workspaces de asuntos` → `Asunto activo: <slug>`.

## Reglas

1. **NUNCA crear asunto sin chequeo de conflictos.** Si hay conflicto duro, parar.
2. **NUNCA omitir el MASC.** Si el tipo de asunto exige MASC y `masc_acreditado: no`, todo skill de redacción de demanda parará hasta que se genere acta MASC o se documente intento.
3. **Calcular prescripción al intake**, no después. Es el dato que decide si el asunto tiene sentido aceptar.
4. **Fechas en formato AAAA-MM-DD.** Convertir relativas ("la semana que viene") a absolutas.

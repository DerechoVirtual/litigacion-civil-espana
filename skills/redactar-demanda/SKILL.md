---
name: redactar-demanda
description: Redaccion exhaustiva de demandas civiles, mercantiles y de familia conforme a LEC y LO 1/2025. No redacta al primer disparo, recorre cinco fases. Word maquetado obligatorio. Usar con redactar demanda, preparar demanda, interponer, monitorio, verbal, ordinario, desahucio.
---

# Redactar demanda civil — flujo maestro de 5 fases

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Marco normativo de referencia — LO 1/2025 (CRÍTICO, comprobar SIEMPRE)

La **Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia** (en vigor el **3 de abril de 2025**) reformó la LEC. Tener siempre presente:

- **Cuantía → procedimiento.** El umbral del juicio verbal por razón de la cuantía pasó de 6.000 € a **15.000 €**:
  - Asuntos de **hasta 15.000 € (≤ 15.000)** → **juicio verbal** (art. 250.2 LEC).
  - Asuntos que **excedan de 15.000 € (> 15.000)** → **juicio ordinario** (art. 249.2 LEC).
  - ⚠️ **Prohibido usar el viejo umbral de 6.000 €.** Ejemplo: un asunto de 13.500 € es **verbal**, no ordinario.
- **Juicio verbal por materia** (art. 250.1 LEC), *cualquiera que sea la cuantía*: desahucios, alimentos, retracto, propiedad horizontal con reclamación dineraria, división de cosa común, acciones individuales sobre condiciones generales de la contratación, nulidad por usura, etc.
- **MASC** (art. 5): requisito de procedibilidad — acreditar intento previo salvo asuntos exentos.
- **Tribunales de Instancia.** La LO 1/2025 sustituyó a los Juzgados de Primera Instancia por los **Tribunales de Instancia**: los antiguos Juzgados de Primera Instancia ya no existen. El órgano competente es **siempre el Tribunal de Instancia, Sección Civil, de [provincia]** — encabezar siempre así.
- **Recurso de apelación:** se interpone directamente, **sin previo anuncio**.
- **LAJ** (Letrado/a de la Administración de Justicia): denominación vigente; nunca "Secretario Judicial".

## Regla cardinal

**NO REDACTAR AL PRIMER DISPARO.** Recorrer las 5 fases SIEMPRE. Saltar fases = entregable inservible.

## Prerrequisitos

1. `CLAUDE.md` del despacho configurado.
2. Asunto creado vía `/asunto-intake` (slug obligatorio).
3. Si workspaces de asunto están habilitados, asunto activo en su contexto.

## Fase 1 — Documentación

Pedir al usuario aportar (o señalar dónde están):

- Hechos del cliente (declaración, cronología informal)
- Contratos, facturas, burofaxes previos
- Documentación de identificación de las partes
- Si hay procedimiento previo o relacionado, sentencias previas
- Si hay cláusula compromisoria / sumisión expresa
- Documentación que acredite intento MASC (si no exento)

Validar lectura completa antes de continuar (ver `## Input grande` del CLAUDE.md).

## Fase 2 — Batería de preguntas (AskUserQuestion obligatorio)

Mínimo 4 baterías de 2-4 preguntas cada una:

### Batería A — Procedimiento aplicable

- Cuantía exacta o estimada → umbral **LO 1/2025**: **≤ 15.000 € = verbal** (art. 250.2 LEC); **> 15.000 € = ordinario** (art. 249.2 LEC). Nunca el viejo umbral de 6.000 €.
- Tipo de pretensión (dineraria líquida / declarativa / constitutiva / mixta)
- ¿Cabe monitorio? (deuda dineraria, líquida, vencida, exigible, documentada — LEC 812)
- ¿Cabe juicio verbal por materia especial, cualquiera que sea la cuantía? (desahucio, alimentos, retracto, propiedad horizontal, división de cosa común, condiciones generales, usura — art. 250.1 LEC)
- Si no procede verbal por materia ni por cuantía (> 15.000 €), juicio ordinario.

### Batería B — Competencia

- Territorial: domicilio del demandado (LEC 50-58). Si fuero especial aplicable.
- Objetiva: cuantía + materia → Tribunal de Instancia, Sección Civil. Si mercantil (>art. 86 ter LOPJ), Sección Mercantil.
- Funcional: si hay sumisión expresa LEC 54-55, validar.

### Batería C — MASC (Ley Orgánica 1/2025, de 2 de enero, art. 5)

- ¿Es asunto exento de MASC? (monitorio, ejecución, medidas cautelares previas, alimentos urgentes menores, jurisdicción voluntaria). Si exento, registrar.
- Si no exento: ¿se ha intentado MASC? Tipo (mediación / conciliación / oferta vinculante / opinión neutral / negociación directa documentada).
- Documento que lo acredita (acta del mediador / burofax con propuesta y plazo / carta de oferta vinculante con acuse).
- Si NO se ha intentado: PARAR redacción. Generar primero acta MASC vía `/masc-acta` o burofax documentado vía `/burofax-draft`.

### Batería D — Cuantía, intereses y costas

- Cuantía: principal + intereses devengados hasta fecha de demanda + intereses futuros (calcular legales art. 1108 CC, o convencionales si pactados, o demora art. 7 Ley 3/2004 si operación comercial).
- ¿Se piden costas? (sí por defecto en estimación íntegra, LEC 394)
- ¿Cabe condena en costas a la contraparte? (criterio del vencimiento con excepciones art. 394.1 LEC)

### Batería E — Prueba (opcional pero recomendado)

- Documental: lista preliminar (relacionar con hechos)
- Testigos previstos (nombre, relación con los hechos)
- Pericial: pendiente / dictamen elaborado / no necesaria
- Interrogatorio de partes: sí / no
- Reconocimiento judicial: necesario / no

## Fase 3 — Viabilidad y MASC

Análisis crítico antes de seguir:

- **Prescripción:** ¿hay riesgo? Si la demanda llega cerca del plazo, marcar y considerar interrupción adicional.
- **Caducidad de la acción:** ej. acciones rescisorias (1299 CC), nulidad relativa, etc.
- **Legitimación activa y pasiva:** verificar que el cliente puede demandar y que el demandado es el correcto.
- **Litispendencia:** ¿hay procedimiento previo entre las mismas partes y por el mismo objeto?
- **Cosa juzgada:** ¿hay sentencia firme sobre el mismo objeto?
- **MASC acreditado** (si no exento): bloquear redacción si no.

Output de la fase 3: **dictamen breve de viabilidad** en 4-6 líneas antes de seguir.

## Fase 4 — Estrategia

Definir antes de redactar:

- **Tesis jurídica central:** la "historia" que vamos a contar en 2-3 frases
- **Fundamento legal principal:** artículo(s) CC / CCo / LEC / LAU / LH / legislación foral aplicable
- **Fundamento legal secundario:** doctrina civil (autonomía privada, buena fe, abuso de derecho, etc.)
- **Pretensiones del Suplico:**
  - Principal (la condena específica)
  - Subsidiarias (por orden)
  - Accesorias (intereses, costas)
- **Posibles excepciones de la contraria:** anticipar y preparar rebatimiento
- **Prueba clave:** qué documento / testigo / pericial sostiene cada hecho

## Fase 5 — Jurisprudencia (mínimo 4 STS con ECLI verificado y párrafo literal)

Buscar/verificar jurisprudencia con el conector MCP `jurisprudenciator` (`buscar_sentencias` por tema, `buscar_por_cita` para verificar un ECLI/ROJ, `leer_sentencias` para extraer el texto). Es la **única** vía de jurisprudencia del plugin:

- **Mínimo 4 STS del Tribunal Supremo** con ECLI verificado
- **Opcionalmente SAP de Audiencia Provincial relevante** del territorio
- **Doctrina relevante del TJUE** si la materia tiene componente europeo (consumidores, etc.)

### Obtención del párrafo literal — OBLIGATORIO

Para cada sentencia que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=` del punto que sostiene) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se va a entrecomillar en el escrito. No se cita ninguna sentencia de la que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y reproducida textualmente; cualquier paráfrasis va sin comillas.

### Ficha por sentencia (preparar antes de redactar)

Para CADA cita, dejar lista esta ficha:
- ECLI (ej. `ECLI:ES:TS:2023:1234`)
- ROJ (ej. `ROJ: STS 1234/2023`)
- Tribunal + Sala + Sección
- Fecha
- Magistrado ponente
- **Párrafo literal** (cita textual verificada vía `leer_sentencias`, entrecomillada)
- *Ratio decidendi* en 1-2 frases (paráfrasis, sin comillas)
- **Hecho concreto del asunto** al que se ancla
- **Argumento** de subsunción que se construye a partir de ella

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL DEL FONDO

El Fundamento de Derecho del fondo **NO** amontona sentencias ni las cita "en bloque". Se redacta como una **secuencia de bloques aislados, uno por sentencia**, y cada bloque agota su sentencia antes de pasar a la siguiente. Para cada sentencia, en este orden:

1. **Identificar la resolución**: "La Sentencia de la Sala Primera del Tribunal Supremo de [fecha] (ECLI/ROJ, ponente Excmo. Sr. [...])...".
2. **Reproducir el párrafo literal** entrecomillado, tal cual se extrajo con `leer_sentencias`.
3. **Anclar al hecho** concreto del asunto ("Trasladada esta doctrina a nuestro caso, donde [hecho]...").
4. **Desarrollar el argumento** de subsunción: por qué ese pronunciamiento resuelve este punto a favor del cliente.
5. **Cerrar y transicionar** al punto siguiente, que abre el bloque de la siguiente sentencia.

Una idea jurídica → una sentencia → un bloque desarrollado y cerrado. Prohibido el "cajón de sastre" de citas seguidas sin desarrollo individual.

**PROHIBIDO inventar sentencias y PROHIBIDO inventar el párrafo.** Si `jurisprudenciator` no devuelve una sentencia que sostenga el punto, o no se logra extraer el párrafo literal, decirlo y o (a) reformular el argumento, o (b) marcar `[REVISAR: jurisprudencia no encontrada — verificar manualmente]`.

## Fase 6 — Redacción

Estructura obligatoria (LEC 399 ordinario / 437 verbal):

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

DON/DOÑA [Nombre Procurador], Procurador/a de los Tribunales y de [nombre cliente],
mayor de edad, [con DNI/NIF], según acredito mediante poder que acompaño como
DOCUMENTO Nº 1, bajo la dirección letrada de DON/DOÑA [NOMBRE DEL LETRADO], abogado/a
del Ilustre Colegio de [...] colegiado nº [...], ante el Tribunal comparezco y, como
mejor proceda en Derecho, DIGO:

Que mediante el presente escrito formulo DEMANDA DE [JUICIO ORDINARIO/VERBAL/...] en
ejercicio de [ACCIÓN] frente a [parte demandada], con domicilio en [...], en base a
los siguientes:

HECHOS
[I, II, III, IV... — numerados, cada uno con su prueba documental asociada]

FUNDAMENTOS DE DERECHO

I.- DE LA COMPETENCIA Y PROCEDIMIENTO
[Tribunal de Instancia + territorial + cuantía + procedimiento aplicable]

II.- DE LA POSTULACIÓN
[Procurador + abogado conforme LEC 23 y 31]

III.- DEL MASC
[Acreditación del intento previo art. 5 Ley Orgánica 1/2025 + documento acreditativo]

IV.- DEL FONDO
[Epígrafes numerados correlativos y con título propio (1.- ... / 2.- ... / 3.- ...),
una línea argumental por epígrafe. Jurisprudencia en SECUENCIA: un bloque por sentencia
(cita → párrafo literal entrecomillado → anclaje al hecho → desarrollo → transición),
según el "Método secuencial de redacción jurisprudencial" de la Fase 5]

V.- DE LOS INTERESES
[Art. 1108 CC / convencionales / demora art. 7 Ley 3/2004]

VI.- DE LAS COSTAS
[Art. 394 LEC]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito junto con los documentos
acompañados, lo admita, me tenga por personado y parte en la representación que ostento,
y, en su día, previos los trámites legales, dicte sentencia por la que:

1.º [Pretensión principal]
2.º [Pretensión subsidiaria, si la hay]
3.º Imponga las costas a la parte demandada.

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]

OTROSÍ DIGO [si hace falta: prueba anticipada, embargo preventivo, etc.]
```

### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Numeración de hechos romanos, fundamentos romanos
- Negrita estratégica en encabezados de cada bloque (HECHOS, FUNDAMENTOS, SUPLICO)

### Redacción y estilo discursivo (OBLIGATORIO)

- **Numeración correlativa, nunca "v1/v2".** Los Fundamentos de Derecho se rotulan con ordinales (PRIMERO.-, SEGUNDO.-, TERCERO.- …). Cuando un Fundamento (típicamente el del fondo) se divida en apartados, numerarlos de forma correlativa y con título propio: "**1.- La obligación de pago del precio…**", "**2.- La excepción de contrato no cumplido…**". **Prohibido** rotular como "IV.1", "V.2", "v1", "v2" o anidamientos tipo "5.1".
- **Encadenado discursivo con conectores VARIADOS.** Cada párrafo enlaza con el anterior mediante marcadores de orden y progresión: *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Conviene añadir / Por último*. El escrito debe leerse como una secuencia en la que cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula.** Prohibido reutilizar una misma muletilla de transición (p. ej. abrir todos los bloques jurisprudenciales con "Trasladada esta doctrina al caso"). Alternar las expresiones de anclaje: "Proyectada esta doctrina sobre los hechos…", "Llevada esta doctrina a nuestro supuesto…", "Aplicado este criterio al caso…", "Si trasladamos lo anterior a los hechos probados…".
- **Explicación desarrollada.** Cada argumento se expone completo: premisa normativa → doctrina → hecho → conclusión. Nada de afirmaciones sin desarrollar.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Fase 7 — Pulido con estilo de la casa

Aplicar **automáticamente** el skill `estilo-escritos-judiciales`:
- Inyectar estructura tripartita, contrastes "una cosa es X / otra es Y", explicación del por qué antes del qué
- Cero adjetivos vacíos, cero postureo
- Cierre estratégico

## Fase 8 — Subsunción

Aplicar **automáticamente** el skill `subsuncion-juridica`:
- Conectar cada STS con los hechos concretos del asunto
- Eliminar citas jurisprudenciales "sueltas" — todas deben atar a un hecho

## Fase 9 — Verificación ECLI

Verificar **automáticamente y como último paso** cada ECLI/ROJ con el conector `jurisprudenciator` (`buscar_por_cita`):
- Si alguna sentencia no se valida, marcar `[REVISAR: ECLI no validado]` y NO entregar hasta que se sustituya o verifique manualmente.

## Salida

1. Word .docx maquetado en `matters/<slug>/escritos/demanda-v1.docx`
2. Versión interna con nota del revisor y tags inline (en `matters/<slug>/escritos/demanda-v1-INTERNO.docx`)
3. Resumen markdown con:
   - Bottom line del asunto en 3 frases
   - Lista de documentos acompañados
   - Mapa de jurisprudencia citada (tabla: ECLI / Tribunal / fecha / punto sostenido)
   - Próximos pasos (firma + presentación LexNET)

## Decision tree post-entrega

> **¿Qué hacemos ahora?**
> 1. **Versión final saneada** (sin nota del revisor) — confirmar y dejarlo limpio
> 2. **Cuadro de elementos** — `/cuadro-elementos <slug> --ofensivo` para revisar cobertura probatoria
> 3. **Cronología ofensiva** — `/cronologia <slug>` para acompañar al Tribunal
> 4. **Solicitud de medidas cautelares** — si procede `/medidas-cautelares <slug>`
> 5. **Ajustar tono o secciones** — dime qué cambiar

## Reglas

1. **PROHIBIDO redactar al primer disparo.** 5 fases obligatorias.
2. **PROHIBIDO inventar jurisprudencia.** ECLI verificado o `[REVISAR]`.
3. **PROHIBIDO omitir MASC.** Si no exento y no acreditado, parar.
4. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los antiguos Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
5. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ) desde LOPJ vigente.
6. **PROHIBIDO entregar texto plano.** Word .docx maquetado.
7. **PROHIBIDO anunciar el recurso de apelación.** Se interpone directamente desde LO 1/2025.
8. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo medidas urgentes.

---
name: nulidad-clausulas-abusivas
description: Redaccion de demandas de nulidad de clausulas abusivas en contratos con consumidores (clausula suelo, gastos hipotecarios, IRPH, tarjetas revolving/usura, comisiones de apertura/descubierto/reclamacion de posiciones) conforme a TRLGDCU, LCGC, Directiva 93/13/CEE y LO 1/2025. No redacta al primer disparo, recorre cinco fases. Word maquetado obligatorio. Usar con nulidad de clausula abusiva, clausula suelo, gastos hipotecarios, IRPH, revolving, usura, comision de apertura, reclamar al banco, control de transparencia.
---

# Nulidad de cláusulas abusivas (consumidores) — flujo maestro de 5 fases

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Marco normativo de referencia — LO 1/2025 (CRÍTICO, comprobar SIEMPRE)

La **Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia** (en vigor el **3 de abril de 2025**) reformó la LEC. Para las acciones de nulidad de cláusulas abusivas tener siempre presente:

- **PROCEDIMIENTO — clave de esta skill.** La **acción individual sobre condiciones generales de la contratación / cláusulas abusivas** se tramita por **JUICIO VERBAL POR RAZÓN DE LA MATERIA** (art. 250.1 LEC), **cualquiera que sea la cuantía**. ⚠️ **NO se rige por el umbral de los 15.000 €**: aunque la cantidad a restituir supere ampliamente esa cifra, el cauce sigue siendo el **verbal por materia**, no el ordinario. No confundir con el verbal/ordinario por cuantía del resto de demandas del plugin.
- **Control de oficio de la abusividad.** El tribunal puede y debe apreciar de oficio el carácter abusivo de una cláusula (doctrina TJUE consolidada; art. 83 TRLGDCU). Conviene invocarlo expresamente, sin que ello descargue al demandante de fundamentar y pedir.
- **Tribunales de Instancia.** La LO 1/2025 sustituyó a los Juzgados de Primera Instancia por los **Tribunales de Instancia**: los antiguos Juzgados de Primera Instancia ya no existen. El órgano competente es **siempre el Tribunal de Instancia, Sección Civil, de [PARTIDO JUDICIAL]** — encabezar siempre así.
- **MASC** (art. 5): requisito de procedibilidad. En materia de **consumo / cláusulas abusivas frente a entidades bancarias**, valorar la **exención o las particularidades** del intento previo (reclamación previa a la entidad / servicio de atención al cliente, oferta vinculante, negociación documentada). Comprobar si el asunto encaja en un supuesto exento o si basta la reclamación previa al banco; documentarlo en todo caso.
- **Recurso de apelación:** se interpone directamente, **sin previo anuncio**.
- **LAJ** (Letrado/a de la Administración de Justicia): denominación vigente; nunca "Secretario Judicial".

## Regla cardinal

**NO REDACTAR AL PRIMER DISPARO.** Recorrer las 5 fases SIEMPRE. Saltar fases = entregable inservible.

## Prerrequisitos

1. `CLAUDE.md` del despacho configurado.
2. Asunto creado vía `/asunto-intake` (slug obligatorio).
3. Si workspaces de asunto están habilitados, asunto activo en su contexto.

## Cuándo activar

Activar ante cualquiera de estos supuestos (acción individual de un consumidor frente a una entidad de crédito o predisponente):

- **Cláusula suelo** — limitación a la baja del tipo variable en préstamo hipotecario.
- **Gastos hipotecarios** — repercusión al consumidor de gastos de notaría, registro, gestoría, tasación, AJD.
- **IRPH** — índice de referencia de préstamos hipotecarios (control de transparencia).
- **Tarjetas revolving / usura** — crédito al consumo revolving con TAE desproporcionada → acción de nulidad por usura (Ley de 1908).
- **Comisiones** — comisión de apertura, comisión por descubierto, comisión por reclamación de posiciones deudoras.
- Triggers de lenguaje natural: "nulidad de cláusula abusiva", "cláusula suelo", "gastos hipotecarios", "IRPH", "revolving", "usura", "comisión de apertura", "reclamar al banco", "control de transparencia".

## Marco sustantivo aplicable (desarrollar en los Fundamentos de Derecho)

Esta acción se construye sobre el siguiente bloque normativo, que ha de invocarse de forma encadenada:

- **TRLGDCU** — Real Decreto Legislativo 1/2007, por el que se aprueba el texto refundido de la Ley General para la Defensa de los Consumidores y Usuarios:
  - **Art. 80** — requisitos de las cláusulas no negociadas individualmente (concreción, claridad, sencillez; buena fe y justo equilibrio).
  - **Arts. 82-83** — concepto de cláusula abusiva, listado y **efectos de la nulidad**: la cláusula abusiva es **nula de pleno derecho y se tendrá por no puesta**, subsistiendo el contrato sin posibilidad de integración/moderación (art. 83, redacción tras STJUE).
- **Ley 7/1998, de Condiciones Generales de la Contratación (LCGC)** — control de incorporación (arts. 5 y 7) y régimen de las condiciones generales predispuestas e impuestas.
- **Directiva 93/13/CEE** del Consejo, sobre cláusulas abusivas en los contratos celebrados con consumidores — marco europeo; control de transparencia y efecto disuasorio; interpretación conforme a la jurisprudencia del **TJUE**.
- **Art. 1303 CC** — **efecto restitutorio**: declarada la nulidad, las partes deben restituirse recíprocamente lo percibido en virtud de la cláusula nula, con sus frutos/intereses. Base de la devolución de cantidades.
- **Ley de 23 de julio de 1908, de Represión de la Usura (Ley Azcárate)** — para **tarjetas revolving**: nulidad del contrato de crédito por usurario cuando el interés sea notablemente superior al normal del dinero y manifiestamente desproporcionado.

### Triple control de las cláusulas predispuestas

Toda la acción se articula sobre el **triple control** —que se proyecta como epígrafes correlativos del Fundamento del fondo—:

1. **Control de incorporación** (arts. 5 y 7 LCGC) — la cláusula debe haberse incorporado conforme a las reglas de transparencia documental (legibilidad, accesibilidad, entrega).
2. **Control de transparencia** (material, no solo formal) — el consumidor debe haber podido conocer la carga jurídica y económica real de la cláusula; doctrina del **TJUE** y del **TS**.
3. **Control de contenido / abusividad** (arts. 82-83 TRLGDCU) — desequilibrio importante, contrario a la buena fe, en perjuicio del consumidor.

## Fase 1 — Documentación

Pedir al usuario aportar (o señalar dónde están):

- **Escritura de préstamo hipotecario / contrato de tarjeta o de crédito** completo (clausulado predispuesto).
- **Oferta vinculante / FIPER / FEIN** y documentación precontractual entregada al consumidor.
- Cuadro de amortización, recibos, extractos y liquidaciones (para el cálculo de lo indebidamente cobrado).
- Facturas de notaría, registro, gestoría, tasación y modelo de AJD (en gastos hipotecarios).
- Extractos de la tarjeta revolving: TAE aplicada, disposiciones, intereses y comisiones cobradas (en usura).
- Reclamación previa a la entidad / respuesta del servicio de atención al cliente / del Banco de España, si la hubo.
- Acreditación de la **condición de consumidor** del cliente (destino ajeno a actividad empresarial/profesional).
- Documentación que acredite intento MASC / reclamación previa al banco (si no exento).

Validar lectura completa antes de continuar (ver `## Input grande` del CLAUDE.md).

## Fase 2 — Batería de preguntas (AskUserQuestion obligatorio)

Mínimo 4 baterías de 2-4 preguntas cada una:

### Batería A — Identificación de la cláusula y procedimiento

- ¿Qué cláusula(s) se impugnan? (suelo / gastos / IRPH / revolving-usura / comisión de apertura / descubierto / reclamación de posiciones). Una demanda puede acumular varias.
- ¿Cuál es la **condición de consumidor** del cliente? (préstamo/tarjeta para fin ajeno a su actividad).
- Recordar el cauce: **juicio verbal por materia** (art. 250.1 LEC), **cualquiera que sea la cuantía** — no se aplica el umbral de 15.000 €.
- ¿La cláusula fue **negociada individualmente** o es condición general predispuesta e impuesta? (carga de la prueba de la negociación al predisponente).

### Batería B — Competencia

- Territorial: por consumidor, fuero del **domicilio del consumidor** (criterio TJUE / art. 52 LEC y fueros de protección). Confirmar partido judicial ([PARTIDO JUDICIAL] u otro).
- Objetiva: materia (condiciones generales / cláusulas abusivas) → Tribunal de Instancia, Sección Civil.
- ¿Hay sumisión expresa en el contrato? Si la hay, valorar su **nulidad** por abusiva frente al consumidor (no vincula al consumidor).

### Batería C — MASC / reclamación previa (Ley Orgánica 1/2025, de 2 de enero, art. 5)

- ¿El asunto está **exento** de MASC o le aplican particularidades por ser materia de consumo frente a entidad bancaria? Registrar el análisis.
- ¿Se presentó **reclamación previa** a la entidad / servicio de atención al cliente / Banco de España? Aportar copia y respuesta (o silencio).
- Documento que acredita el intento (burofax con propuesta y plazo / reclamación al SAC con acuse / acta de negociación).
- Si NO se ha intentado y no es exento: PARAR redacción. Generar primero el intento documentado vía `/burofax-draft` o `/masc-acta`.

### Batería D — Cantidades a restituir, intereses y costas

- **Cálculo de lo indebidamente cobrado** por la cláusula nula (suelo: diferencial cobrado de más; gastos: importe de los gastos repercutidos; revolving: todo lo pagado por encima del principal dispuesto; comisiones: importe de cada comisión).
- Periodo afectado y soporte documental de cada partida (cuadro de cálculo como documento).
- **Intereses**: del art. 1303 CC (interés legal sobre cada cantidad desde su cobro) y, en su caso, intereses procesales (art. 576 LEC).
- ¿Se piden costas? (sí por defecto en estimación íntegra, LEC 394; recordar la doctrina TJUE sobre que la imposición de costas no debe disuadir al consumidor).

### Batería E — Prueba (opcional pero recomendado)

- Documental: escritura/contrato + oferta vinculante + extractos + cuadro de cálculo (relacionar con hechos).
- Pericial económica: dictamen de recálculo (suelo/revolving) — pendiente / elaborado / no necesaria.
- Interrogatorio del representante de la entidad: sí / no.
- Documental de transparencia: información precontractual entregada (o su ausencia).

## Fase 3 — Viabilidad y MASC

Análisis crítico antes de seguir:

- **Imprescriptibilidad de la nulidad / prescripción de la restitución.** La acción de nulidad de pleno derecho de la cláusula abusiva no prescribe; valorar el régimen de prescripción de la **acción de restitución** de cantidades a la luz de la jurisprudencia del TJUE y del TS (dies a quo). Marcar riesgo si procede.
- **Condición de consumidor**: verificar que el cliente actúa como consumidor; si no, la acción no se sostiene en el régimen de consumidores (replantear).
- **Cosa juzgada / litispendencia**: ¿hubo acción colectiva, allanamiento previo o devolución parcial del banco que afecte al objeto?
- **Carácter predispuesto e impuesto** de la cláusula (no negociada individualmente).
- **MASC / reclamación previa acreditado** (si no exento): bloquear redacción si no.

Output de la fase 3: **dictamen breve de viabilidad** en 4-6 líneas antes de seguir.

## Fase 4 — Estrategia

Definir antes de redactar:

- **Tesis jurídica central:** la cláusula es condición general predispuesta que no supera el control de transparencia ni el de contenido, es abusiva y, por tanto, nula y no puesta, con la consiguiente restitución íntegra ex art. 1303 CC. (En revolving: contrato usurario → nulidad ex Ley de 1908, restitución de lo pagado sobre el principal.)
- **Fundamento legal principal:** arts. 80 y 82-83 TRLGDCU + LCGC + Directiva 93/13/CEE + art. 1303 CC (y Ley de 1908 si usura).
- **Fundamento legal secundario:** buena fe contractual, control de oficio, prohibición de integración/moderación de la cláusula nula.
- **Pretensiones del Suplico:**
  - Principal: declaración de nulidad de la(s) cláusula(s) por abusiva(s).
  - Consecuencia: restitución de las cantidades indebidamente cobradas + intereses ex art. 1303 CC.
  - Accesorias: recálculo del cuadro de amortización (en su caso) + costas.
- **Posibles excepciones de la contraria:** negociación individual, transparencia cumplida, acto propio/confirmación, prescripción de la restitución, caducidad de la acción → anticipar y preparar rebatimiento.
- **Prueba clave:** escritura/contrato, oferta vinculante (o su ausencia), extractos y cuadro de cálculo/pericial.

## Fase 5 — Jurisprudencia (mínimo 4 resoluciones con ECLI verificado y párrafo literal)

Buscar/verificar jurisprudencia con el conector MCP `jurisprudenciator` (`buscar_sentencias` por tema, `buscar_por_cita` para verificar un ECLI/ROJ, `leer_sentencias` para extraer el texto). Es la **única** vía de jurisprudencia del plugin. En esta materia, la jurisprudencia clave es:

- **TJUE** — sobre **control de transparencia** y **efecto restitutorio** (alcance de la nulidad y devolución íntegra de cantidades a favor del consumidor; límites a la moderación; control de oficio).
- **Tribunal Supremo, Sala Primera** — doctrina interna sobre cláusula suelo, gastos hipotecarios, IRPH, comisiones y usura en revolving.
- **Opcionalmente SAP** del territorio (Audiencia Provincial de [PARTIDO JUDICIAL] u otra) cuando aporte criterio aplicativo.

**TODA cita se verifica con `jurisprudenciator`** (`buscar_por_cita` / `leer_sentencias`) o se marca `[REVISAR]`. **NO inventar ECLI ni párrafos** —ni del TJUE ni del TS—.

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

Estructura obligatoria (demanda de juicio verbal — LEC 437):

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

DON/DOÑA [Nombre Procurador], Procurador/a de los Tribunales y de [nombre cliente],
mayor de edad, [con DNI/NIF], en su condición de CONSUMIDOR, según acredito mediante
poder que acompaño como DOCUMENTO Nº 1, bajo la dirección letrada de DON [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados de [COLEGIO/CIUDAD], colegiado nº [...], ante
el Tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que mediante el presente escrito formulo DEMANDA DE JUICIO VERBAL en ejercicio de
ACCIÓN INDIVIDUAL DE NULIDAD DE CONDICIONES GENERALES / CLÁUSULAS ABUSIVAS con
reclamación de cantidad, frente a [entidad demandada], con domicilio en [...], en base
a los siguientes:

HECHOS
[I, II, III, IV... — numerados: la contratación y condición de consumidor; el clausulado
predispuesto impugnado; la información precontractual recibida (o su ausencia); las
cantidades indebidamente cobradas con su cuadro de cálculo; la reclamación previa al banco.
Cada hecho con su prueba documental asociada]

FUNDAMENTOS DE DERECHO

I.- DE LA COMPETENCIA Y PROCEDIMIENTO
[Acción individual sobre condiciones generales / cláusulas abusivas → JUICIO VERBAL POR
MATERIA (art. 250.1 LEC), CUALQUIERA QUE SEA LA CUANTÍA. Fuero del domicilio del consumidor]

II.- DE LA POSTULACIÓN
[Procurador + abogado conforme LEC 23 y 31]

III.- DEL MASC / RECLAMACIÓN PREVIA
[Acreditación del intento previo / reclamación a la entidad (art. 5 LO 1/2025) o de su
exención en materia de consumo + documento acreditativo]

IV.- DEL FONDO
[Epígrafes numerados correlativos y con título propio. Estructura recomendada del triple
control y efectos:
1.- DEL CONTROL DE INCORPORACIÓN (arts. 5 y 7 LCGC)
2.- DEL CONTROL DE TRANSPARENCIA (material; doctrina TJUE y TS)
3.- DE LA ABUSIVIDAD (arts. 82-83 TRLGDCU; Directiva 93/13/CEE; control de oficio)
4.- DE LOS EFECTOS RESTITUTORIOS (art. 1303 CC y jurisprudencia del TJUE; nulidad de
   pleno derecho, cláusula no puesta, prohibición de moderación, restitución íntegra)
5.- DE LOS INTERESES (art. 1303 CC / art. 576 LEC)
6.- DE LAS COSTAS (art. 394 LEC)
— una línea argumental por epígrafe. En revolving, sustituir el bloque por la acción de
USURA (Ley de 1908): interés notablemente superior al normal y desproporcionado → nulidad
del crédito y restitución de lo pagado sobre el principal. Jurisprudencia en SECUENCIA: un
bloque por sentencia (cita → párrafo literal entrecomillado → anclaje al hecho → desarrollo
→ transición), según el "Método secuencial de redacción jurisprudencial" de la Fase 5]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito junto con los documentos
acompañados, lo admita, me tenga por personado y parte en la representación que ostento,
y, en su día, previos los trámites legales, dicte sentencia por la que:

1.º DECLARE la NULIDAD, por abusiva, de la(s) cláusula(s) de [suelo / gastos /
   IRPH / comisión de ... / o la nulidad por usura del contrato de tarjeta], teniéndola(s)
   por no puesta(s).
2.º CONDENE a la demandada a RESTITUIR a mi representado la cantidad de [...] euros
   indebidamente cobrada en aplicación de dicha(s) cláusula(s), más los intereses legales
   de cada cantidad desde su respectivo cobro (art. 1303 CC), con recálculo del cuadro de
   amortización en su caso.
3.º Imponga las costas a la parte demandada.

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]

OTROSÍ DIGO PRIMERO [cuantía y su carácter — el procedimiento es verbal por materia con
independencia de aquélla]
OTROSÍ DIGO SEGUNDO [proposición de prueba: documental, pericial económica, interrogatorio]
OTROSÍ DIGO TERCERO [si procede: solicitud de control de oficio de la abusividad]
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

- **Numeración correlativa, nunca "v1/v2".** Los Fundamentos de Derecho se rotulan con ordinales (PRIMERO.-, SEGUNDO.-, TERCERO.- …). Cuando un Fundamento (típicamente el del fondo) se divida en apartados, numerarlos de forma correlativa y con título propio: "**1.- Del control de incorporación…**", "**2.- Del control de transparencia…**". **Prohibido** rotular como "IV.1", "V.2", "v1", "v2" o anidamientos tipo "5.1".
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
- Conectar cada sentencia (TJUE / TS) con los hechos concretos del asunto (la cláusula concreta, la información recibida, las cantidades cobradas)
- Eliminar citas jurisprudenciales "sueltas" — todas deben atar a un hecho

## Fase 9 — Verificación ECLI

Verificar **automáticamente y como último paso** cada ECLI/ROJ con el conector `jurisprudenciator` (`buscar_por_cita`):
- Si alguna sentencia no se valida, marcar `[REVISAR: ECLI no validado]` y NO entregar hasta que se sustituya o verifique manualmente.

## Salida

1. Word .docx maquetado en `matters/<slug>/escritos/nulidad-clausulas-abusivas-v1.docx`
2. Versión interna con nota del revisor y tags inline (en `matters/<slug>/escritos/nulidad-clausulas-abusivas-v1-INTERNO.docx`)
3. Resumen markdown con:
   - Bottom line del asunto en 3 frases
   - Lista de documentos acompañados (escritura/contrato, oferta vinculante, extractos, cuadro de cálculo)
   - Cuadro de cantidades a restituir (partida / periodo / importe)
   - Mapa de jurisprudencia citada (tabla: ECLI / Tribunal / fecha / punto sostenido)
   - Próximos pasos (firma + presentación LexNET)

## Decision tree post-entrega

> **¿Qué hacemos ahora?**
> 1. **Versión final saneada** (sin nota del revisor) — confirmar y dejarlo limpio
> 2. **Cuadro de elementos** — `/cuadro-elementos <slug> --ofensivo` para revisar cobertura probatoria
> 3. **Cronología ofensiva** — `/cronologia <slug>` (contratación → cobros → reclamación previa)
> 4. **Reclamación previa / burofax** — si falta documentarla, `/burofax-draft <slug>`
> 5. **Ajustar tono o secciones** — dime qué cambiar

## Reglas

1. **PROHIBIDO redactar al primer disparo.** 5 fases obligatorias.
2. **Procedimiento: JUICIO VERBAL POR MATERIA (art. 250.1 LEC), cualquiera que sea la cuantía.** NO se rige por el umbral de 15.000 € — error grave tramitarlo como ordinario por el importe a restituir.
3. **Control de oficio de la abusividad.** Invocar expresamente la facultad-deber del tribunal de apreciar de oficio el carácter abusivo (art. 83 TRLGDCU; doctrina TJUE).
4. **Efecto restitutorio íntegro ex Gutiérrez Naranjo.** Declarada la nulidad, restitución total de cantidades sin limitación temporal de los efectos: la cláusula es nula de pleno derecho y se tiene por no puesta, sin moderación ni integración (art. 1303 CC + doctrina TJUE/TS). Verificar la cita concreta con `jurisprudenciator`.
5. **En revolving, acción de usura.** El cauce es la nulidad del contrato de crédito por usurario (Ley de 1908): interés notablemente superior al normal del dinero y manifiestamente desproporcionado → restitución de lo pagado por encima del principal dispuesto.
6. **PROHIBIDO inventar jurisprudencia.** ECLI verificado con `jurisprudenciator` (TJUE y TS) o `[REVISAR]`.
7. **PROHIBIDO omitir MASC / reclamación previa.** Si no exento y no acreditado, parar; en consumo, valorar exención/particularidades.
8. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los antiguos Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
9. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
10. **PROHIBIDO entregar texto plano.** Word .docx maquetado.
11. **PROHIBIDO anunciar el recurso de apelación.** Se interpone directamente desde LO 1/2025.
12. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo medidas urgentes.

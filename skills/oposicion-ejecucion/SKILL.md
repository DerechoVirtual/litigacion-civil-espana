---
name: oposicion-ejecucion
description: Escrito de oposicion a la ejecucion conforme a los arts. 556-559 LEC y LO 1/2025. Defiende al ejecutado distinguiendo titulos judiciales (motivos tasados art. 556), titulos no judiciales (art. 557, incluida clausula abusiva) y defectos procesales (art. 559). Word maquetado obligatorio. Usar con oponerse a la ejecucion, oposicion al despacho de ejecucion, defender al ejecutado, motivos de oposicion, arts. 556-559.
---

# Oposición a la ejecución

> ⚖️ **Jurisprudencia — primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave). Única vía del plugin (no vLex, no Chrome).

## Marco normativo de referencia — LO 1/2025

- La **Ley Orgánica 1/2025, de 2 de enero**, de medidas en materia de eficiencia del Servicio Público de Justicia (en vigor el **3 de abril de 2025**), reformó la Ley de Enjuiciamiento Civil.
- **Plazo de oposición: 10 días** desde la notificación del auto que despacha ejecución (**art. 556.1 LEC**). Plazo hábil y preclusivo — vencido, ya no cabe oponerse por motivos de fondo.
- **Motivos de oposición:**
  - **Títulos judiciales, arbitrales y de acuerdos de mediación → art. 556 LEC** (motivos tasados de fondo).
  - **Títulos no judiciales ni arbitrales → art. 557 LEC** (motivos de fondo más amplios, incluida la **cláusula abusiva**).
  - **Cualquier título, defectos procesales → art. 559 LEC**.
- **Efecto suspensivo (CRÍTICO):** la oposición de fondo del **art. 557** (títulos no judiciales) **suspende** el curso de la ejecución (art. 557.2 LEC). La oposición por **defectos procesales del art. 559 NO suspende** la ejecución (art. 559.2 LEC), salvo que el tribunal lo acuerde. La oposición del art. 556 a títulos judiciales **no suspende** por regla general.
- **Órgano competente:** la oposición se sustancia ante el **"Tribunal de Instancia, Sección Civil"** (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- Nomenclatura: **"Letrado/a de la Administración de Justicia (LAJ)"**, nunca "Secretario Judicial".
- La fundamentación, cuando cite jurisprudencia, sigue el **método secuencial** descrito más abajo.

## Cuándo activar

- "Oponerse a la ejecución", "oposición al despacho de ejecución", "oposición a la ejecución"
- "Defender al ejecutado", "me han despachado ejecución"
- "Motivos de oposición", "arts. 556-559 LEC"
- "Pago acreditado / pluspetición / prescripción de la deuda ejecutada"
- "Cláusula abusiva en el título" (préstamo, hipoteca, póliza)
- "Defectos procesales del despacho de ejecución / nulidad del despacho"

## Flujo

### 1. Calificación del título y del cauce de oposición

Vía `AskUserQuestion`, lo primero es identificar **qué título** se ejecuta, porque de ello dependen los motivos disponibles:

- ¿El título es **judicial, arbitral o acuerdo de mediación** (sentencia firme, auto de homologación, laudo, acta de mediación homologada)? → cauce de fondo del **art. 556**.
- ¿El título es **no judicial ni arbitral** (escritura pública, póliza intervenida, letra-cheque-pagaré, certificación)? → cauce de fondo del **art. 557**.
- ¿Hay **defectos procesales** en el despacho con independencia del tipo de título? → **art. 559**, compatible con el motivo de fondo.
- Fecha de **notificación del auto** que despachó ejecución → de ahí se cuentan los **10 días hábiles** (art. 556.1).

### 2. Motivos de oposición disponibles según el cauce

#### (a) Oposición a títulos judiciales, arbitrales o de mediación — motivos TASADOS del art. 556 LEC

Numerus clausus; solo caben:

1. **Pago o cumplimiento** de lo ordenado en la sentencia, laudo o acuerdo, que se **acredite documentalmente** (art. 556.1).
2. **Caducidad de la acción ejecutiva** (art. 518 LEC: 5 años desde la firmeza para sentencias y resoluciones judiciales o arbitrales).
3. **Pactos y transacciones** que se hubiesen convenido para evitar la ejecución, siempre que **consten en documento público** (art. 556.1).

> Fuera de estos tres motivos, **no cabe** discutir el fondo de lo ya resuelto: la cosa juzgada blinda el título judicial.

#### (b) Oposición a títulos no judiciales ni arbitrales — motivos del art. 557 LEC

Cauce más amplio. Caben, entre otros:

1. **Pago** que pueda acreditarse documentalmente.
2. **Compensación** de crédito **líquido** que resulte de documento con fuerza ejecutiva.
3. **Pluspetición o exceso** en la cantidad reclamada.
4. **Prescripción y caducidad** del derecho o de la acción.
5. **Quita, espera o pacto** de no pedir, que conste documentalmente.
6. **Transacción**, siempre que conste en documento público.
7. **Carácter abusivo de cláusulas** que constituyan el fundamento de la ejecución o que hubiesen determinado la cantidad exigible (control de oficio y a instancia de parte; relevante en préstamos, hipotecas y pólizas frente a consumidores).

> Recordatorio de efecto: **la oposición del art. 557 SUSPENDE** el curso de la ejecución (art. 557.2).

#### (c) Oposición por defectos procesales — art. 559 LEC

Compatible con la oposición de fondo y disponible **para cualquier título**:

1. **Falta de capacidad o de representación** del ejecutante, o no acreditarla debidamente.
2. **Falta de los requisitos del título** o del despacho de ejecución que la ley exige (p. ej. cantidad no líquida, vencida o exigible; título que no reúne los presupuestos del art. 517 / 520).
3. **Nulidad radical del despacho de ejecución** por no contener la sentencia o el laudo pronunciamientos de condena, o por no cumplir el documento los requisitos legales para llevar aparejada ejecución, o por infracción del art. 551 al despachar.

> Recordatorio de efecto: **la oposición por defectos procesales del art. 559 NO suspende** la ejecución (salvo que el tribunal lo acuerde motivadamente).

### 3. Estrategia defensiva

Antes de redactar, definir:

- **Cauce y motivo(s)** que se invocan, ordenados por fuerza (primero el que cierra la ejecución; subsidiariamente los de reducción).
- **Prueba documental** que sostiene cada motivo (recibo de pago, documento de quita, escritura de transacción, contrato con la cláusula cuestionada, liquidación que evidencia la pluspetición).
- **Objetivo del SUPLICO:** ¿estimación total (dejar sin efecto la ejecución) o parcial (reducir la cantidad por pluspetición / nulidad de cláusula)?
- **Anticipar la réplica del ejecutante** y preparar el rebatimiento.

### 4. Fundamentación con jurisprudencia

Construir el Fundamento de Derecho del fondo siguiendo el método de abajo. Para la oposición de consumidores por **cláusula abusiva** suele ser pertinente doctrina del **TJUE** y del **TS** (Sala Primera). Verificar todo ECLI/ROJ con `jurisprudenciator`.

#### Método secuencial de redacción jurisprudencial — REGLA CARDINAL DEL FONDO

El Fundamento de Derecho del fondo **NO** amontona sentencias ni las cita "en bloque". Se redacta como una **secuencia de bloques aislados, uno por sentencia**, y cada bloque agota su sentencia antes de pasar a la siguiente. Para cada sentencia, en este orden:

1. **Identificar la resolución**: "La Sentencia de la Sala Primera del Tribunal Supremo de [fecha] (ECLI/ROJ, ponente Excmo. Sr. [...])...".
2. **Reproducir el párrafo literal** entrecomillado, tal cual se extrajo con `leer_sentencias`.
3. **Anclar al hecho** concreto del asunto ("Trasladada esta doctrina a nuestro caso, donde [hecho]...").
4. **Desarrollar el argumento** de subsunción: por qué ese pronunciamiento resuelve este punto a favor del cliente.
5. **Cerrar y transicionar** al punto siguiente, que abre el bloque de la siguiente sentencia.

Una idea jurídica → una sentencia → un bloque desarrollado y cerrado. Prohibido el "cajón de sastre" de citas seguidas sin desarrollo individual.

**PROHIBIDO inventar sentencias y PROHIBIDO inventar el párrafo.** Si `jurisprudenciator` no devuelve una sentencia que sostenga el punto, o no se logra extraer el párrafo literal, decirlo y o (a) reformular el argumento, o (b) marcar `[REVISAR: jurisprudencia no encontrada — verificar manualmente]`.

##### Obtención del párrafo literal — OBLIGATORIO

Para cada sentencia que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=` del punto que sostiene) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se va a entrecomillar en el escrito. No se cita ninguna sentencia de la que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y reproducida textualmente; cualquier paráfrasis va sin comillas.

##### Ficha por sentencia (preparar antes de redactar)

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

### 5. Redacción

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

DON/DOÑA [Procurador], Procurador/a de los Tribunales y de [ejecutado/a], según poder
que obra en autos, bajo la dirección letrada de DON/DOÑA [NOMBRE DEL LETRADO], en el
procedimiento de ejecución [tipo] nº [...], ante el Tribunal comparezco y, como mejor
proceda en Derecho, DIGO:

Que, habiéndome sido notificado el Auto de fecha [...] por el que se despacha ejecución
frente a mi representado, y dentro del plazo de DIEZ DÍAS del artículo 556.1 de la Ley
de Enjuiciamiento Civil, formulo OPOSICIÓN A LA EJECUCIÓN, con base en los siguientes:

HECHOS

PRIMERO.- Del despacho de ejecución notificado
[Auto, fecha de notificación, cantidad despachada, título que se ejecuta]

SEGUNDO.- Del título y de su naturaleza
[Judicial / no judicial → determina el cauce de oposición]

TERCERO.- De los hechos que fundan la oposición
[Pago acreditado / pluspetición / prescripción / cláusula abusiva / defecto procesal,
cada uno con su prueba documental asociada]

FUNDAMENTOS DE DERECHO

PRIMERO.- De la tempestividad de la oposición
[Plazo de 10 días hábiles desde la notificación del auto — art. 556.1 LEC]

SEGUNDO.- Del cauce procesal de oposición
[Art. 556 si título judicial/arbitral/mediación; art. 557 si título no judicial;
y/o art. 559 por defectos procesales — justificar cuál o cuáles]

TERCERO.- Del motivo o motivos de oposición de fondo
[Desarrollo del motivo concreto. Si se subdivide, apartados correlativos con título
propio: "1.- Del pago acreditado documentalmente…", "2.- De la pluspetición…".
Jurisprudencia en SECUENCIA: un bloque por sentencia (cita → párrafo literal
entrecomillado → anclaje al hecho → desarrollo → transición), según el "Método
secuencial de redacción jurisprudencial"]

CUARTO.- Del efecto suspensivo
[Solo si cauce art. 557: la oposición suspende el curso de la ejecución (art. 557.2).
Si cauce art. 559: la oposición NO suspende salvo acuerdo del tribunal (art. 559.2)]

QUINTO.- De las costas
[Art. 561 LEC — costas de la oposición según su estimación o desestimación]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito junto con los documentos
acompañados, lo admita, tenga por formulada en tiempo y forma OPOSICIÓN A LA EJECUCIÓN
despachada frente a mi representado y, previos los trámites legales, dicte auto por el
que:

1.º Estime la oposición y deje sin efecto la ejecución despachada, archivándose las
actuaciones, con imposición de costas a la parte ejecutante.
2.º Subsidiariamente, reduzca la ejecución a la cantidad realmente debida de [...] €,
por concurrir [pluspetición / nulidad de la cláusula que determina lo exigible].

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]

OTROSÍ DIGO PRIMERO: [Si cauce art. 557: que se acuerde la SUSPENSIÓN del curso de la
ejecución conforme al art. 557.2 LEC mientras se sustancia la oposición.]

OTROSÍ DIGO SEGUNDO: [Si procede: solicitud de vista (art. 560 LEC), prueba documental
o pericial sobre la liquidación, etc.]
```

#### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Numeración de hechos y fundamentos con ordinales correlativos (PRIMERO.-, SEGUNDO.- …)
- Negrita estratégica en encabezados de cada bloque (HECHOS, FUNDAMENTOS, SUPLICO, OTROSÍ)

#### Redacción y estilo discursivo (OBLIGATORIO)

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

### 6. Pulido + verificación

`estilo-escritos-judiciales` + verificación de ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`, si se citan STS). Si alguna sentencia no se valida, marcar `[REVISAR: ECLI no validado]` y NO entregar hasta sustituir o verificar manualmente.

## Salida

- Word .docx maquetado en `matters/<slug>/escritos/oposicion-ejecucion-v1.docx`
- Si el asunto es nuevo, registrarlo como sub-asunto con `tipo: oposicion-ejecucion` y `posicion: ejecutado`.

## Reglas

1. **Motivos TASADOS según el tipo de título.** Título judicial/arbitral/mediación → solo los tres motivos del art. 556 (pago/cumplimiento documentado, caducidad de la acción ejecutiva, pactos y transacciones en documento público). Título no judicial → motivos del art. 557 (incluida cláusula abusiva). Defectos procesales → art. 559. **Prohibido** invocar en un cauce un motivo que no le corresponde.
2. **Plazo: 10 días hábiles** desde la notificación del auto que despacha ejecución (art. 556.1 LEC). Preclusivo — vencido, no cabe oposición de fondo.
3. **Solo la oposición de fondo del art. 557 SUSPENDE** la ejecución (art. 557.2). La del art. 559 (defectos procesales) NO suspende salvo acuerdo del tribunal (art. 559.2). No prometer suspensión donde no procede.
4. **PROHIBIDO inventar jurisprudencia.** ECLI verificado vía `jurisprudenciator` o `[REVISAR]`.
5. **PROHIBIDO entregar texto plano.** Entregable Word `.docx` maquetado para LexNET.
6. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
7. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
8. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo medidas urgentes.

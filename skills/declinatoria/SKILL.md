---
name: declinatoria
description: Declinatoria de los arts. 63-65 LEC para denunciar la falta de jurisdiccion o de competencia (objetiva, territorial, funcional, internacional) o la sumision del asunto a arbitraje o mediacion. Plazo perentorio y efecto suspensivo. Usar con declinatoria, falta de competencia, falta de jurisdiccion, sumision a arbitraje, competencia territorial, competencia objetiva, arts. 63-65 LEC.
---

# Declinatoria — falta de jurisdicción o de competencia (arts. 63-65 LEC)

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- "Declinatoria", "plantear declinatoria", "interponer declinatoria"
- "Falta de competencia" (objetiva / territorial / funcional)
- "Falta de jurisdicción", "falta de competencia internacional"
- "Sumisión a arbitraje", "cláusula compromisoria", "sometido a mediación"
- "El juzgado no es competente", "competencia territorial/objetiva", "arts. 63-65 LEC"

## Marco normativo de referencia — LO 1/2025

La **Ley Orgánica 1/2025, de 2 de enero**, de medidas en materia de eficiencia del Servicio Público de Justicia (en vigor el **3 de abril de 2025**), reformó la Ley de Enjuiciamiento Civil. Para la declinatoria lo clave es:

- **Régimen legal:** declinatoria de los **arts. 63 a 65 LEC**. Es el cauce para que el demandado (o quien pueda ser parte legítima) denuncie la **falta de jurisdicción** o de **competencia** del tribunal ante el que se ha presentado la demanda.
- **Plazo perentorio (art. 64.1 LEC):**
  - **Juicio ordinario:** dentro de los **10 primeros días** del plazo para contestar a la demanda.
  - **Juicio verbal:** dentro de los **5 primeros días** posteriores a la citación o emplazamiento.
  - ⚠️ Plazo de **días hábiles** e improrrogable: transcurrido, opera la **sumisión tácita** (art. 56 LEC) y se pierde la posibilidad de denunciar la incompetencia territorial disponible.
- **Efecto suspensivo (art. 64.1, párr. 2.º LEC):** la presentación de la declinatoria **suspende**, hasta que sea resuelta, el plazo para contestar a la demanda y el curso del procedimiento principal. Esa suspensión **no obsta** a la práctica de actuaciones de aseguramiento de prueba ni a medidas cautelares de urgencia.
- **Lugar de presentación (art. 63.2 LEC):** puede presentarse **ante el tribunal que esté conociendo** del asunto y al que se considera carente de jurisdicción o competencia, **o** ante el **tribunal del domicilio del demandado**, que la remitirá por el medio más rápido al tribunal ante el que se hubiera presentado la demanda.
- **Órgano destinatario:** "**Tribunal de Instancia, Sección Civil**" (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- **Terminología:** "**Letrado/a de la Administración de Justicia (LAJ)**", **nunca** "Secretario Judicial".

La cita de jurisprudencia, cuando proceda, sigue el **método secuencial** del apartado siguiente.

## Flujo

### 1. Identificar el defecto que se denuncia

Acotar con precisión cuál es el vicio, porque condiciona el SUPLICO y el efecto:

- **Falta de jurisdicción** (art. 63.1 LEC):
  - El asunto está **sometido a arbitraje** (cláusula compromisoria / convenio arbitral) → procede declinatoria por sumisión a árbitros.
  - El asunto está **sometido a mediación** pactada como vía obligatoria.
  - **Falta de competencia internacional** de los tribunales españoles.
  - Corresponde a **otro orden jurisdiccional** (contencioso, social, penal) o a la Administración.
- **Falta de competencia objetiva** (por materia o cuantía → otro tipo de órgano).
- **Falta de competencia territorial** (fuero distinto; reglas LEC 50-60). Recordar que sólo cabe denunciar por declinatoria la territorial **disponible**; la imperativa es apreciable de oficio pero la declinatoria es la vía de parte.
- **Falta de competencia funcional** (p. ej. recurso o incidente que corresponde a otro órgano).

### 2. Acreditación documental

La declinatoria se funda en documentos: **aportar con el escrito** todo aquello en que se sustente la incompetencia o la sumisión (art. 65.1 LEC):

- Convenio arbitral / cláusula compromisoria, o contrato que la contiene.
- Acuerdo de sometimiento a mediación.
- Documentos que acrediten el domicilio real del demandado o el fuero territorial correcto.
- Documentos que acrediten la materia/cuantía determinante de la competencia objetiva.
- Cualquier resolución previa relevante (p. ej. de otro orden jurisdiccional).

### 3. Plazo y cómputo

- Determinar el tipo de procedimiento (ordinario → **10 días**; verbal → **5 días**) y la fecha de emplazamiento/citación.
- Computar en **días hábiles** (sábados, domingos y festivos inhábiles; agosto inhábil salvo urgencia).
- Confirmar que se está **dentro del plazo**; si está agotado, advertir del riesgo de sumisión tácita y replantear la estrategia.

### 4. Efecto suspensivo — advertir y consignarlo

- La sola presentación **suspende** el plazo de contestación y el curso del proceso (art. 64.1 LEC).
- Dejarlo expresamente reflejado en el cuerpo del escrito y, si procede, en un OTROSÍ, para que conste la suspensión.

### Jurisprudencia (cuando proceda fundar la incompetencia con doctrina del TS)

Buscar/verificar con el conector MCP `jurisprudenciator` (`buscar_sentencias` / `buscar_por_cita`). Útil sobre todo para sumisión a arbitraje, eficacia del convenio arbitral, competencia internacional o interpretación de fueros.

### Obtención del párrafo literal — OBLIGATORIO
Para cada sentencia/auto que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=` del punto que sostiene) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se entrecomillará. No se cita nada de lo que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y reproducida textualmente; cualquier paráfrasis va sin comillas.

### Ficha por resolución
Para CADA cita: ECLI (ej. `ECLI:ES:TS:2023:1234`); ROJ (ej. `ROJ: STS 1234/2023`); Tribunal + Sala + Sección; Fecha; ponente; **Párrafo literal** (verificado vía `leer_sentencias`, entrecomillado); *Ratio* en 1-2 frases (paráfrasis); **punto** de incompetencia al que se ancla; **Argumento** de subsunción.

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL DEL FONDO

La fundamentación de la incompetencia **NO** amontona resoluciones ni las cita "en bloque". Se redacta como una **secuencia de bloques aislados, uno por resolución**, y cada bloque agota su sentencia antes de pasar a la siguiente. Para cada sentencia, en este orden:

1. **Identificar la resolución**: "La Sentencia de la Sala Primera del Tribunal Supremo de [fecha] (ECLI/ROJ, ponente Excmo. Sr. [...])...".
2. **Reproducir el párrafo literal** entrecomillado, tal cual se extrajo con `leer_sentencias`.
3. **Anclar al punto** concreto de incompetencia o sumisión ("Proyectada esta doctrina sobre el convenio arbitral suscrito por las partes...").
4. **Desarrollar el argumento** de subsunción: por qué ese pronunciamiento priva de jurisdicción/competencia al tribunal en este caso.
5. **Cerrar y transicionar** al punto siguiente, que abre el bloque de la siguiente resolución.

Una idea jurídica → una resolución → un bloque desarrollado y cerrado. Prohibido el "cajón de sastre" de citas seguidas sin desarrollo individual.

**PROHIBIDO inventar sentencias y PROHIBIDO inventar el párrafo.** Si `jurisprudenciator` no devuelve una resolución que sostenga el punto, o no se logra extraer el párrafo literal, decirlo y o (a) reformular el argumento, o (b) marcar `[REVISAR: jurisprudencia no encontrada — verificar manualmente]`.

### 5. Redacción

### Redacción y estilo discursivo (OBLIGATORIO)

- **Numeración correlativa, nunca "v1/v2".** Los Fundamentos de Derecho se rotulan con ordinales (PRIMERO.-, SEGUNDO.-, TERCERO.- …). Cuando un Fundamento se divida en apartados, numerarlos de forma correlativa y con título propio: "**1.- La existencia de convenio arbitral válido…**", "**2.- La falta de competencia territorial…**". **Prohibido** rotular como "IV.1", "V.2", "v1", "v2" o anidamientos tipo "5.1".
- **Encadenado discursivo con conectores VARIADOS.** Cada párrafo enlaza con el anterior mediante marcadores de orden y progresión: *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Conviene añadir / Por último*. El escrito debe leerse como una secuencia en la que cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula.** Prohibido reutilizar una misma muletilla de transición (p. ej. abrir todos los bloques jurisprudenciales con "Trasladada esta doctrina al caso"). Alternar las expresiones de anclaje: "Proyectada esta doctrina sobre los hechos…", "Llevada esta doctrina a nuestro supuesto…", "Aplicado este criterio al caso…", "Si trasladamos lo anterior a los hechos…".
- **Explicación desarrollada.** Cada argumento se expone completo: premisa normativa → doctrina → hecho → conclusión. Nada de afirmaciones sin desarrollar.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]
(o, en su caso, AL TRIBUNAL DE INSTANCIA DEL DOMICILIO DEL DEMANDADO, art. 63.2 LEC)

Procedimiento: [Juicio Ordinario / Verbal] nº [...]/[año]

DON/DOÑA [Procurador], Procurador/a de los Tribunales y de [demandado], según
acredito mediante poder que acompaño como DOCUMENTO Nº 1, bajo la dirección letrada
de DON/DOÑA [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados de [COLEGIO/CIUDAD],
ante el Tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que, hallándome dentro del plazo legalmente conferido y al amparo de los artículos
63 a 65 de la Ley de Enjuiciamiento Civil, mediante el presente escrito formulo
DECLINATORIA por [falta de jurisdicción / falta de competencia objetiva / territorial /
funcional / sumisión a arbitraje], interesando que este Tribunal se abstenga de conocer,
con base en los siguientes:

HECHOS

PRIMERO.- [Demanda presentada: objeto, fecha de emplazamiento/citación.]
SEGUNDO.- [El defecto: convenio arbitral / fuero correcto / orden jurisdiccional
competente, con remisión al documento que lo acredita.]
TERCERO.- [Tempestividad: dentro de los 10 (ordinario) / 5 (verbal) primeros días.]

FUNDAMENTOS DE DERECHO

PRIMERO.- DE LA ADMISIBILIDAD Y TEMPESTIVIDAD DE LA DECLINATORIA
[Arts. 63 y 64.1 LEC: cauce, plazo de 10/5 días y efecto suspensivo. Lugar de
presentación, art. 63.2.]

SEGUNDO.- DEL DEFECTO DE JURISDICCIÓN/COMPETENCIA QUE SE DENUNCIA
[Desarrollo del fondo: arbitraje (Ley 60/2003) / competencia internacional /
competencia objetiva / territorial (LEC 50-60). Jurisprudencia en SECUENCIA: un
bloque por resolución, según el "Método secuencial de redacción jurisprudencial".]

TERCERO.- DE LA SUSPENSIÓN DEL PROCEDIMIENTO
[Art. 64.1, párr. 2.º LEC: la presentación suspende el plazo de contestación y el
curso del proceso.]

CUARTO.- DE LAS COSTAS
[Art. 65.1/65.5 LEC y régimen general art. 394 LEC.]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito con los documentos
acompañados, lo admita, tenga por formulada en tiempo y forma DECLINATORIA y, previos
los trámites legales, dicte auto por el que, estimándola:

1.º Se abstenga de conocer del presente asunto por [falta de jurisdicción / de
    competencia objetiva / territorial / funcional].
2.º [Según el caso:] sobresea el procedimiento remitiendo a las partes al arbitraje /
    a la mediación pactada; o indique a las partes el tribunal o el orden jurisdiccional
    ante el que han de usar de su derecho; o remita las actuaciones al órgano
    territorialmente competente.
3.º Imponga las costas a la parte demandante.

OTROSÍ DIGO que, conforme al art. 64.1, párrafo segundo, de la LEC, la presentación de
esta declinatoria suspende el plazo para contestar a la demanda y el curso del
procedimiento, lo que intereso se acuerde y haga constar.
SUPLICO AL TRIBUNAL que tenga por hecha la anterior manifestación a los efectos
oportunos.

[Lugar y fecha]
[Firma electrónica del Procurador y del Abogado]
```

### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Numeración de hechos y fundamentos con ordinales (PRIMERO.-, SEGUNDO.- …)
- Negrita estratégica en encabezados de cada bloque (HECHOS, FUNDAMENTOS DE DERECHO, SUPLICO, OTROSÍ)

## Salida

- Word .docx maquetado en `matters/<slug>/escritos/declinatoria-v1.docx`

## Reglas

1. **Plazo perentorio:** **10 días** (juicio ordinario) / **5 días** (juicio verbal) dentro del plazo para contestar, art. 64.1 LEC. Vencido, opera la sumisión tácita (art. 56 LEC) — advertirlo.
2. **Efecto suspensivo:** la presentación **suspende** el plazo de contestación y el curso del proceso; hacerlo constar expresamente.
3. **Acreditación documental:** aportar con el escrito **todos los documentos** en que se funde la incompetencia o la sumisión (convenio arbitral, fuero, materia/cuantía).
4. **PROHIBIDO inventar jurisprudencia.** ECLI verificado vía `jurisprudenciator` o `[REVISAR]`.
5. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
6. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
7. **PROHIBIDO entregar texto plano.** Word .docx maquetado.
8. **Plazos hábiles.** Sábados, domingos y festivos inhábiles. Agosto inhábil salvo medidas urgentes.

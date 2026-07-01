---
name: recurso-casacion-y-queja
description: Recurso de casacion civil ante la Sala Primera del Tribunal Supremo (art. 477 LEC tras el RDL 5/2023, eje del interes casacional) y recurso de queja (art. 494 LEC) contra la denegacion de un recurso. Jurisprudenciator primero. Word maquetado obligatorio. Usar con recurso de casacion, casacion civil, interes casacional, recurrir ante el Tribunal Supremo, recurso de queja, denegacion de recurso, arts. 477 y 494 LEC.
---

# Recurso de casación civil y recurso de queja — flujo de la cúspide

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

> Esta skill cubre **dos recursos distintos de la cúspide** en sub-flujos separados:
> **(A) Casación civil** (art. 477 LEC) ante la **Sala Primera del Tribunal Supremo**, cuyo eje es el **interés casacional**.
> **(B) Queja** (art. 494 LEC), que se interpone **directamente ante el tribunal *ad quem*** cuando se deniega tener por preparado o tramitar un recurso (apelación, casación o extraordinario).

## Marco normativo de referencia — LO 1/2025

La **Ley Orgánica 1/2025, de 2 de enero** (en vigor el **3 de abril de 2025**) reformó la LEC; sobre el régimen de casación incide además la reforma operada por el **Real Decreto-ley 5/2023** en cuanto al **interés casacional**. Para estos recursos, lo clave:

- **Casación civil — arts. 477 a 487 LEC.** El recurso de casación se da frente a las sentencias dictadas en segunda instancia por las Audiencias Provinciales (y resoluciones asimiladas). Recurre la **infracción de norma sustantiva aplicable** para resolver el objeto del proceso.
- **El eje es el INTERÉS CASACIONAL** (art. 477 LEC, redacción tras el RDL 5/2023). Concurre cuando:
  - la sentencia recurrida se **opone a la doctrina jurisprudencial del Tribunal Supremo**;
  - existe **jurisprudencia contradictoria de las Audiencias Provinciales** sobre el punto;
  - se aplican **normas que no llevan en vigor más de cierto tiempo** y sobre las que **no existe doctrina del Tribunal Supremo**, o normas sobre las que **no hay jurisprudencia** del TS.
- **Núcleo material:** la **doctrina jurisprudencial del Tribunal Supremo** es el centro de gravedad del interés casacional; identificarla y confrontarla con la sentencia recurrida es el corazón del escrito.
- **Modelo unificado tras la reforma:** en el **mismo escrito** de casación puede invocarse también la **infracción procesal**, sin que ello permita **mezclar de forma confusa** las cuestiones procesales y las de fondo — cada infracción se articula en su propio motivo, perfectamente diferenciado.
- **Órgano de presentación de la casación.** El escrito de **interposición** se presenta **ante el órgano que dictó la sentencia recurrida** (la Audiencia Provincial, *a quo*) para su **remisión a la Sala Primera del Tribunal Supremo**.
- **Plazo de casación: 20 días** desde la notificación de la sentencia recurrida.
- **Exigencias formales estrictas:** identificación precisa de la **norma sustantiva infringida**, **justificación expresa del interés casacional**, claridad en la separación de motivos. El rigor formal es **causa de inadmisión** si se incumple.
- **Queja — art. 494 LEC.** Procede contra el **auto que deniega** tener por preparado o tramitar un recurso (de apelación, casación o extraordinario). Se interpone **directamente ante el tribunal que debe resolver el recurso no tramitado** (el *ad quem*). **Plazo: 10 días** desde la notificación del auto denegatorio. Su finalidad es que se **revoque la denegación** y se **tramite el recurso**.
- **Órgano de instancia/segunda instancia: "Tribunal de Instancia, Sección Civil"** o **"Audiencia Provincial"** según corresponda (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- **"Letrado/a de la Administración de Justicia (LAJ)"**, nunca "Secretario Judicial".
- (No aplica aquí el umbral de cuantía verbal/ordinario: la vía casacional no se decide por la cuantía sino por el interés casacional.)

> Los **motivos del recurso** se fundan con el **método secuencial de jurisprudencia** (ver Fase 3 / Fase A4). En casación es **CENTRAL**: cada motivo enfrenta la doctrina del TS infringida con un párrafo literal verificado vía `jurisprudenciator`.

## Cuándo activar

- "Recurso de casación", "casación civil", "recurrir en casación"
- "Interés casacional", "infracción de norma sustantiva", "recurrir ante el Tribunal Supremo", "Sala Primera del TS"
- "Recurso de queja", "queja por denegación de recurso", "me han denegado la apelación/casación", "auto denegatorio del recurso"
- Menciones a los arts. **477** (casación) o **494** (queja) LEC

## Prerrequisitos

1. Asunto creado vía `/asunto-intake` (slug obligatorio).
2. **(A) Casación:** sentencia de segunda instancia de la Audiencia Provincial que se recurre, subida al asunto; plazo de 20 días desde notificación NO consumido.
3. **(B) Queja:** auto denegatorio del recurso, subido al asunto; plazo de 10 días desde notificación NO consumido.

---

# (A) RECURSO DE CASACIÓN CIVIL — art. 477 LEC

## Fase A1 — Lectura crítica de la sentencia recurrida

Leer la sentencia de segunda instancia entera. Extraer:

- **Fallo recurrido** y **pronunciamientos** concretos que se combaten.
- **Hechos probados** declarados por la Audiencia (en casación, intangibles salvo error de derecho).
- **Norma(s) sustantiva(s)** aplicada(s) por la Audiencia y **interpretación** que de ellas hace.
- **Doctrina jurisprudencial citada** por la Audiencia: verificar ECLI con `jurisprudenciator` (`buscar_por_cita`).
- ¿Hay además **infracción procesal** que deba articularse en el mismo escrito? Identificarla y mantenerla en motivo separado.

## Fase A2 — Identificación de la norma sustantiva infringida

- Aislar la **norma sustantiva** aplicable para resolver el objeto del proceso que la sentencia infringe (CC, CCo, leyes especiales, etc.).
- Formular con precisión **qué dice la norma** y **cómo la infringe** la sentencia (inaplicación, aplicación indebida, interpretación errónea).
- Una infracción = un motivo. No acumular preceptos heterogéneos en un mismo motivo.

## Fase A3 — Identificación y justificación del INTERÉS CASACIONAL (fase específica y CRÍTICA)

Sin interés casacional justificado, el recurso se **inadmite**. Determinar y **justificar expresamente** la vía:

1. **Oposición a la doctrina jurisprudencial del Tribunal Supremo.** Localizar con `jurisprudenciator` **dos o más STS** que fijen la doctrina infringida y acreditar que la sentencia recurrida **se aparta** de ella.
2. **Jurisprudencia contradictoria de Audiencias Provinciales.** Localizar resoluciones de AAPP que resuelvan el mismo punto en sentido **opuesto**, evidenciando la contradicción que el TS debe unificar.
3. **Norma sin doctrina del TS o de vigencia inferior al tiempo legalmente relevante.** Acreditar la **ausencia de doctrina** del TS sobre la norma aplicada, o que la norma no lleva en vigor el tiempo exigido.

Para cada vía, dejar **escrito el razonamiento del interés casacional** que irá, de forma expresa y separada, en el encabezamiento de cada motivo. Esta justificación es **autónoma** del fondo y no puede darse por implícita.

## Fase A4 — Jurisprudencia (doctrina del TS infringida — núcleo del recurso)

Mediante el conector MCP `jurisprudenciator` (`buscar_sentencias`/`leer_sentencias`):
- STS de la **Sala Primera** que fijen la doctrina sobre el punto (idealmente STS de las que resulte doctrina jurisprudencial consolidada o de unificación).
- AAPP contradictorias si la vía es la del art. 477 por jurisprudencia contradictoria de Audiencias.
- Doctrina del TJUE si la materia tiene componente europeo.

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

> En casación esto es **CENTRAL**: la oposición a la doctrina del TS solo se prueba enfrentando el párrafo literal verificado de la STS infringida con el razonamiento de la sentencia recurrida. Sin párrafo literal verificado no hay motivo de casación.

## Fase A5 — Redacción del escrito de casación

Estructura (art. 477 y ss. LEC):

```
A LA SALA PRIMERA DEL TRIBUNAL SUPREMO
POR MEDIO DE LA AUDIENCIA PROVINCIAL DE [PROVINCIA], SECCIÓN [N]

Procedimiento: [Ordinario/Verbal] nº [...] — Rollo de Apelación nº [...]
Recurrente: [parte] (cliente)
Recurrido: [parte contraria]

DON/DOÑA [Procurador], en la representación que tengo acreditada en autos, bajo la
dirección letrada de DON/DOÑA [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados
de [PARTIDO JUDICIAL], ante la Sala comparezco y, como mejor proceda en Derecho, DIGO:

Que, dentro del plazo de veinte días conferido y al amparo del artículo 477 de la Ley de
Enjuiciamiento Civil, mediante el presente escrito INTERPONGO RECURSO DE CASACIÓN frente a
la sentencia dictada por la Audiencia Provincial de [...], Sección [...], de fecha [...],
notificada el [...], recaída en el Rollo de Apelación nº [...], en base a los siguientes:

ANTECEDENTES DE HECHO

Primero.- [Iter procesal: primera instancia, apelación, sentencia recurrida]
Segundo.- [Fallo recurrido y pronunciamientos que se combaten]
Tercero.- [Notificación, plazo, cumplimiento]

MOTIVOS DEL RECURSO DE CASACIÓN

1.- PRIMER MOTIVO — Infracción del artículo [X] del [Código Civil / ...], norma sustantiva
    aplicable para resolver el objeto del proceso.
    a) Infracción denunciada: [cómo la sentencia infringe la norma]
    b) JUSTIFICACIÓN DEL INTERÉS CASACIONAL: [vía del art. 477 — oposición a doctrina del
       TS / jurisprudencia contradictoria de AAPP / norma sin doctrina del TS]
    c) Desarrollo: doctrina del TS en SECUENCIA (un bloque por sentencia: cita → párrafo
       literal entrecomillado → confrontación con la sentencia recurrida → conclusión),
       según el "Método secuencial de redacción jurisprudencial".

2.- SEGUNDO MOTIVO — Infracción del artículo [Y] del [...].
    a) Infracción denunciada
    b) JUSTIFICACIÓN DEL INTERÉS CASACIONAL
    c) Desarrollo jurisprudencial

[En su caso, MOTIVO POR INFRACCIÓN PROCESAL — articulado de forma separada y diferenciada,
sin mezclarlo con las cuestiones de fondo (art. 469 LEC), con su propia justificación.]

En su virtud,

SUPLICO A LA SALA PRIMERA DEL TRIBUNAL SUPREMO que, teniendo por presentado en tiempo y
forma este escrito, tenga por interpuesto RECURSO DE CASACIÓN frente a la sentencia
reseñada, lo admita a trámite, y, previos los trámites legales, dicte sentencia por la que,
estimando los motivos expuestos:

1.º Case y anule la sentencia recurrida.
2.º [Pretensión sustitutiva: dicte nueva sentencia que resuelva conforme a la doctrina
    jurisprudencial infringida, estimando la demanda / desestimándola].
3.º Imponga las costas conforme a Derecho.

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]
```

---

# (B) RECURSO DE QUEJA — art. 494 LEC

## Fase B1 — Lectura del auto denegatorio

Leer el auto que deniega tener por preparado o tramitar el recurso. Extraer:

- **Qué recurso** se denegó (apelación, casación, extraordinario).
- **Razón de la denegación** invocada por el órgano *a quo*.
- **Fecha de notificación** del auto → cómputo del plazo de **10 días**.
- Por qué la denegación es **improcedente** (el recurso era procedente, se cumplían los requisitos, etc.).

## Fase B2 — Alegaciones sobre la procedencia del recurso denegado

Construir el argumento de que el recurso **sí debía tramitarse**:
- Cumplimiento de los requisitos del recurso denegado (plazo, forma, recurribilidad de la resolución).
- Refutación de la causa de denegación esgrimida en el auto.
- Apoyo jurisprudencial si lo hay (vía `jurisprudenciator`, mismo método secuencial cuando se cite alguna resolución).

## Fase B3 — Redacción del escrito de queja

Estructura (art. 494 LEC) — se interpone **directamente ante el tribunal *ad quem***:

```
A LA [AUDIENCIA PROVINCIAL DE [PROVINCIA] / SALA PRIMERA DEL TRIBUNAL SUPREMO]
(tribunal competente para resolver el recurso indebidamente denegado — ad quem)

Procedimiento de origen: [...] nº [...] — Órgano a quo: [...]
Recurrente en queja: [parte] (cliente)

DON/DOÑA [Procurador], en la representación que tengo acreditada en autos, bajo la
dirección letrada de DON/DOÑA [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados
de [PARTIDO JUDICIAL], ante esa Sala/Audiencia comparezco y, como mejor proceda en Derecho, DIGO:

Que, dentro del plazo de diez días conferido y al amparo del artículo 494 de la Ley de
Enjuiciamiento Civil, mediante el presente escrito INTERPONGO RECURSO DE QUEJA contra el
auto de fecha [...], notificado el [...], dictado por [órgano a quo], que denegó tener por
[preparado/tramitado] el recurso de [apelación/casación/extraordinario], en base a las
siguientes:

ALEGACIONES

Primera.- [Resolución recurrida en su día y recurso intentado]
Segunda.- [Auto denegatorio: razón de la denegación]
Tercera.- [Procedencia del recurso denegado: cumplimiento de requisitos]
Cuarta.- [Refutación de la causa de denegación + apoyo jurisprudencial si lo hay]

En su virtud,

SUPLICO A LA [AUDIENCIA PROVINCIAL / SALA PRIMERA DEL TRIBUNAL SUPREMO] que, teniendo por
presentado en tiempo y forma este escrito, tenga por interpuesto RECURSO DE QUEJA contra el
auto reseñado y, estimándolo, REVOQUE la denegación y ordene que se tenga por
[preparado/admitido] y se TRAMITE el recurso de [apelación/casación/extraordinario]
indebidamente denegado, con lo demás que en Derecho proceda.

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]
```

---

## Redacción y estilo discursivo (OBLIGATORIO)

- **Numeración correlativa, nunca "v1/v2".** Los Motivos del recurso de casación y las Alegaciones de la queja se rotulan con ordinales o cardinales correlativos y con título propio: "**1.- Infracción del artículo…**", "**2.- …**" / "**Primera.- …**". Cuando un motivo se divida en apartados, numerarlos de forma correlativa (a/b/c) y con título propio. **Prohibido** rotular como "IV.1", "V.2", "v1", "v2" o anidamientos tipo "5.1".
- **Encadenado discursivo con conectores VARIADOS.** Cada párrafo enlaza con el anterior mediante marcadores de orden y progresión: *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Conviene añadir / Por último*. El escrito debe leerse como una secuencia en la que cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula.** Prohibido reutilizar una misma muletilla de transición (p. ej. abrir todos los bloques jurisprudenciales con "Trasladada esta doctrina al caso"). Alternar las expresiones de anclaje: "Proyectada esta doctrina sobre los hechos…", "Llevada esta doctrina a nuestro supuesto…", "Aplicado este criterio al caso…", "Si trasladamos lo anterior a los hechos probados…".
- **Explicación desarrollada.** Cada argumento se expone completo: premisa normativa → doctrina → hecho → conclusión. Nada de afirmaciones sin desarrollar.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Fase final — Pulido, subsunción, verificación ECLI

Aplicar **automáticamente** `estilo-escritos-judiciales`, `subsuncion-juridica`, y verificar **como último paso** cada ECLI/ROJ con el conector `jurisprudenciator` (`buscar_por_cita`):
- Si alguna sentencia no se valida, marcar `[REVISAR: ECLI no validado]` y NO entregar hasta que se sustituya o verifique manualmente.

## Salida

- Word .docx maquetado en `matters/<slug>/escritos/recurso-casacion-v1.docx`
- Word .docx maquetado en `matters/<slug>/escritos/recurso-queja-v1.docx`
- Fichas de jurisprudencia (mapa: ECLI / Tribunal / fecha / punto sostenido / vía del interés casacional)
- Maquetación: Times New Roman 12, A4, márgenes 3 cm, justificado, interlineado 1,5; negrita estratégica en encabezados (ANTECEDENTES, MOTIVOS, ALEGACIONES, SUPLICO).
- Decision tree:

> 1. **Refinar tonalidad/longitud** — dime objetivo de palabras
> 2. **Reforzar la justificación del interés casacional** — añadir vía adicional del art. 477
> 3. **Mantener vigilancia de plazos** — `/actualizar-asunto` con la fecha de presentación (20 días casación / 10 días queja)
> 4. **Preparar oposición a la admisión** si la contraria recurre

## Reglas

1. **Rigor formal extremo en casación.** Norma sustantiva infringida identificada con precisión; cada infracción en su propio motivo. El incumplimiento formal es causa de inadmisión.
2. **El interés casacional se justifica EXPRESAMENTE.** Nunca implícito. Indicar la vía del art. 477 (oposición a doctrina del TS / jurisprudencia contradictoria de AAPP / norma sin doctrina del TS) en cada motivo.
3. **No mezclar fondo y proceso de forma confusa.** La infracción procesal, si se invoca en el mismo escrito, va en motivo separado y diferenciado.
4. **PROHIBIDO inventar jurisprudencia.** ECLI verificado vía `jurisprudenciator` o `[REVISAR]`. En casación el párrafo literal de la STS infringida es el núcleo del motivo.
5. **Plazos hábiles.** **Casación: 20 días** desde notificación de la sentencia recurrida, escrito de interposición ante el órgano *a quo* (Audiencia Provincial) para remisión a la Sala Primera del TS. **Queja: 10 días** desde notificación del auto denegatorio, **directamente ante el tribunal *ad quem***.
6. **Órgano: "Tribunal de Instancia, Sección Civil" / "Audiencia Provincial" / "Sala Primera del Tribunal Supremo"** según corresponda (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
7. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
8. **PROHIBIDO entregar texto plano.** Word .docx maquetado para LexNET.
9. Sábados, domingos y festivos no hábiles; agosto inhábil salvo actuaciones urgentes.

---
name: terminacion-anticipada
description: Redaccion de escritos de terminacion anticipada del proceso civil conforme a los arts. 19-22 LEC y LO 1/2025 — allanamiento (art. 21), desistimiento y renuncia (arts. 19-20) y satisfaccion extraprocesal o carencia sobrevenida de objeto (art. 22). Escritos breves de tramite con su SUPLICO y mencion de costas. Usar con allanamiento, allanarse a la demanda, desistir, desistimiento, renuncia a la accion, satisfaccion extraprocesal, carencia sobrevenida de objeto, terminar el pleito, poner fin al proceso.
---

# Terminación anticipada del proceso civil — allanamiento, desistimiento/renuncia y satisfacción extraprocesal

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome. *(En estos escritos de trámite el uso de jurisprudencia es residual; si se necesita, esta es la vía.)*

## Marco normativo de referencia — LO 1/2025 (CRÍTICO, comprobar SIEMPRE)

La terminación anticipada del proceso descansa en el **poder de disposición de las partes** (art. 19 LEC). Tras la reforma operada por la **Ley Orgánica 1/2025, de 2 de enero** (en vigor el **3 de abril de 2025**), tener siempre presente:

- **Art. 19 LEC — Derecho de disposición.** Las partes pueden disponer del objeto del juicio mediante renuncia, allanamiento, desistimiento, transacción o sometimiento a arbitraje/mediación, salvo prohibición legal, interés general o perjuicio de tercero.
- **Art. 20 LEC — Renuncia y desistimiento.**
  - **Renuncia a la acción** (art. 20.1): el actor renuncia al derecho material ejercitado → el tribunal dicta **sentencia absolutoria** del demandado, con **fuerza de cosa juzgada**.
  - **Desistimiento** (art. 20.2-20.3): el actor abandona el proceso, **sin renunciar al derecho** → termina el proceso **sin cosa juzgada** (puede volver a demandarse). Si el demandado ya fue emplazado, requiere su **conformidad** (art. 20.3); si se opone, el **tribunal resuelve** lo que estime; si el demandado no se opone o aún no había sido emplazado, el **LAJ** lo acuerda por decreto.
- **Art. 21 LEC — Allanamiento.** El demandado se conforma con la pretensión del actor.
  - **Total** → el tribunal dicta **sentencia condenatoria** conforme a lo pedido (sin entrar en el fondo), salvo que el allanamiento se haga en fraude de ley, suponga renuncia contra el interés general o perjuicio de tercero (art. 21.1).
  - **Parcial** → a instancia del actor, el tribunal puede dictar **auto** acogiendo las pretensiones allanadas (ejecutable), siguiendo el proceso por las controvertidas (art. 21.2).
- **Art. 22 LEC — Terminación por satisfacción extraprocesal o carencia sobrevenida de objeto.** Cuando, por circunstancias sobrevenidas, deja de haber interés legítimo en obtener la tutela pretendida porque la pretensión **ya ha sido satisfecha fuera del proceso** o por cualquier otra causa → el **LAJ** lo pone en conocimiento de las partes y, si **hay acuerdo**, **decreta** la terminación (con archivo, sin costas). Si **alguna parte se opone** sosteniendo que subsiste interés, el **tribunal** convoca y resuelve por **auto** lo procedente.

### Reglas de costas

- **Allanamiento — art. 395 LEC.** Si el demandado se allana **antes de contestar** la demanda, **no se imponen costas** salvo que el tribunal aprecie **mala fe** (se presume mala fe si antes de la demanda hubo requerimiento fehaciente y justificado de pago, o se inició procedimiento de mediación o conciliación). Si se allana **después** de contestar, costas conforme a la regla general (art. 394 LEC).
- **Desistimiento — art. 396 LEC.** Si se desiste **sin consentimiento del demandado**, las costas se imponen **al actor**. Si el desistimiento es **consentido** por el demandado (o instado por ambos), **no se condena en costas** salvo pacto.
- **Satisfacción extraprocesal / carencia de objeto — art. 22.** Si hay acuerdo, archivo **sin costas**. Si hay controversia sobre quién tenía razón, el tribunal resuelve por auto e impone las costas según **quién habría visto estimada su pretensión** de no mediar la satisfacción (criterio de vencimiento proyectado).

### Órgano y denominaciones

- **Órgano:** "Tribunal de Instancia, Sección Civil, de [provincia]" (LO 1/2025). Los antiguos Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
- **Quién decreta:** en el **desistimiento consentido** y en la **satisfacción extraprocesal con acuerdo**, es el **LAJ** quien decreta la terminación; el **tribunal** solo resuelve por **auto/sentencia** cuando hay oposición o cuando la figura exige resolución judicial (allanamiento, renuncia).
- **"LAJ"** (Letrado/a de la Administración de Justicia): denominación vigente; **nunca** "Secretario Judicial".

## Cuándo activar

- **(A) Allanamiento:** "allanarse a la demanda", "el demandado se allana", "reconocer la pretensión", "allanamiento total", "allanamiento parcial", "allanarse antes de contestar para no pagar costas".
- **(B) Desistimiento / renuncia:** "desistir de la demanda", "retirar la demanda", "desistimiento", "renunciar a la acción", "renuncia al derecho", "abandonar el pleito sin cerrar la puerta a volver a demandar".
- **(C) Satisfacción extraprocesal / carencia sobrevenida de objeto:** "ya me han pagado, hay que cerrar el pleito", "satisfacción extraprocesal", "carencia sobrevenida de objeto", "la pretensión ha quedado sin objeto", "el demandado cumplió fuera del proceso".

## Flujo

### 1. Elegir el tipo (A / B / C) y la posición procesal

Identificar de entrada **qué figura** se está pidiendo y **a quién representa el despacho** (actor o demandado), porque cada figura es propia de una parte:

| Figura | Quién la ejercita | Efecto sobre el derecho | Cosa juzgada |
|---|---|---|---|
| **(A) Allanamiento** (art. 21) | Demandado | Reconoce la pretensión del actor | Sí (sentencia condenatoria conforme a lo pedido) |
| **(B1) Desistimiento** (art. 20.2-3) | Actor | Abandona el proceso, conserva el derecho | **No** — se puede volver a demandar |
| **(B2) Renuncia a la acción** (art. 20.1) | Actor | Renuncia al derecho material | Sí (sentencia absolutoria del demandado) |
| **(C) Satisfacción extraprocesal** (art. 22) | Cualquiera (lo constata el LAJ) | La pretensión queda sin objeto por cumplimiento externo | Archivo; sin pronunciamiento de fondo |

### 2. Verificar requisitos y consecuencias

- **(A) Allanamiento:** ¿es total o parcial? ¿se hace **antes o después** de contestar (impacta costas, art. 395)? ¿el derecho es disponible (no fraude de ley, ni interés general, ni perjuicio de tercero — art. 21.1)? Si el cliente es persona con representación necesaria o el objeto es indisponible, **advertir** de que el tribunal puede rechazar el allanamiento.
- **(B) Desistimiento/renuncia:** distinguir bien las dos figuras (consecuencias opuestas en cosa juzgada). Para el **desistimiento**, comprobar si el demandado **ya fue emplazado** → si lo fue, hace falta su **conformidad** (art. 20.3); si se opone, decide el tribunal. Para la **renuncia**, advertir de que **cierra para siempre** la acción (cosa juzgada).
- **(C) Satisfacción extraprocesal:** acreditar el **cumplimiento sobrevenido** fuera del proceso (justificante de pago, documento de cumplimiento, acuerdo). Anticipar la posible **oposición** de la otra parte y, con ella, el debate de costas (art. 22 → quién tenía razón).

### 3. Advertir al cliente antes de disponer del derecho

**Antes de redactar**, dejar constancia (en el resumen de salida) de la advertencia al cliente sobre el efecto irreversible de la figura escogida:

- Allanamiento → habrá **condena** conforme a lo pedido.
- Renuncia → se **pierde el derecho** con cosa juzgada.
- Desistimiento → se puede **volver a demandar**, pero (si no es consentido) las **costas** son del actor (art. 396).
- Satisfacción extraprocesal → si la otra parte se opone, hay **incidente** y posible condena en costas.

### 4. Redactar el escrito breve

Escrito de trámite, breve y directo (registro de `redactor-escrito-seccion`): encabezamiento → exposición sucinta → SUPLICO con la petición específica y la mención de costas. Numeración correlativa con ordinales (PRIMERO.-, SEGUNDO.- …), **nunca** "v1/v2".

## Plantillas de escrito

### (A) Escrito de allanamiento (art. 21 LEC)

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

[Autos de Juicio [Ordinario/Verbal] nº [.../año]]

DON/DOÑA [Procurador/a], Procurador/a de los Tribunales y de [demandado], según
tengo acreditado en los autos al margen referenciados, bajo la dirección letrada de
DON [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados de [COLEGIO/CIUDAD], ante el
Tribunal comparezco y, como mejor proceda en Derecho, DIGO:

PRIMERO.- Que mediante el presente escrito, y dentro del plazo conferido para
contestar a la demanda, esta parte se ALLANA [TOTALMENTE / PARCIALMENTE, en cuanto a
la pretensión de [...]] a las pretensiones deducidas de contrario, de conformidad con
el artículo 21 de la Ley de Enjuiciamiento Civil.

SEGUNDO.- Que el allanamiento se formula antes de contestar a la demanda, por lo que,
conforme al artículo 395.1 LEC, no procede la imposición de costas a esta parte, al no
concurrir mala fe [no ha existido requerimiento fehaciente y justificado de pago previo
ni procedimiento de mediación o conciliación].

[Si fuera allanamiento parcial:]
TERCERO.- Respecto de las pretensiones no allanadas relativas a [...], esta parte
interesa la continuación del procedimiento, sin perjuicio de que, a instancia del actor,
pueda dictarse auto acogiendo las pretensiones allanadas (art. 21.2 LEC).

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito, tenga por ALLANADA a
esta parte [totalmente / parcialmente] a la demanda y, en consecuencia, dicte
[sentencia condenatoria conforme a lo solicitado por la actora, sin imposición de costas
a esta parte (art. 395.1 LEC) / auto acogiendo las pretensiones allanadas y prosiga el
procedimiento por las restantes (art. 21.2 LEC)].

[Lugar y fecha]
[Firma electrónica del Procurador y del Abogado]
```

### (B) Escrito de desistimiento / renuncia (arts. 19-20 LEC)

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

[Autos de Juicio [Ordinario/Verbal] nº [.../año]]

DON/DOÑA [Procurador/a], Procurador/a de los Tribunales y de [actor], según tengo
acreditado en autos, bajo la dirección letrada de DON [NOMBRE DEL LETRADO], abogado del
Ilustre Colegio de Abogados de [COLEGIO/CIUDAD], ante el Tribunal comparezco y DIGO:

— OPCIÓN DESISTIMIENTO (art. 20.2-3 LEC) —
PRIMERO.- Que mediante el presente escrito esta parte DESISTE del procedimiento al
margen referenciado, sin renuncia al derecho material ejercitado, al amparo del
artículo 20.2 y 3 de la Ley de Enjuiciamiento Civil.

SEGUNDO.- Que [no habiendo sido aún emplazada la parte demandada, procede que el/la
LAJ decrete sin más la terminación del proceso] / [habiendo sido ya emplazada la parte
demandada, se interesa se le confiera traslado a fin de que preste su conformidad
(art. 20.3 LEC)].

TERCERO.- En cuanto a las costas, [siendo consentido el desistimiento, procede que
cada parte abone las causadas a su instancia, sin condena (art. 396.2 LEC)] / [esta
parte asume las costas causadas, conforme al art. 396.1 LEC].

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito, tenga por DESISTIDA a
esta parte del procedimiento y, [previo traslado a la demandada para que preste su
conformidad,] acuerde mediante decreto del/de la LAJ la terminación del proceso y el
archivo de las actuaciones, [sin imposición de costas / con las costas que procedan
conforme al art. 396 LEC].

— OPCIÓN RENUNCIA A LA ACCIÓN (art. 20.1 LEC) —
PRIMERO.- Que mediante el presente escrito esta parte RENUNCIA a la acción ejercitada
y al derecho material en que se funda, al amparo del artículo 20.1 de la Ley de
Enjuiciamiento Civil, siendo plenamente consciente de que ello determina el dictado de
sentencia absolutoria de la parte demandada con fuerza de cosa juzgada.

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito, tenga por formulada la
RENUNCIA a la acción y dicte sentencia absolviendo a la parte demandada, con los efectos
de cosa juzgada inherentes (art. 20.1 LEC).

[Lugar y fecha]
[Firma electrónica del Procurador y del Abogado]
```

### (C) Escrito de satisfacción extraprocesal / carencia sobrevenida de objeto (art. 22 LEC)

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

[Autos de Juicio [Ordinario/Verbal] nº [.../año]]

DON/DOÑA [Procurador/a], Procurador/a de los Tribunales y de [parte], según tengo
acreditado en autos, bajo la dirección letrada de DON [NOMBRE DEL LETRADO], abogado del
Ilustre Colegio de Abogados de [COLEGIO/CIUDAD], ante el Tribunal comparezco y DIGO:

PRIMERO.- Que con posterioridad a la interposición de la demanda, y por circunstancias
sobrevenidas, la pretensión que constituye el objeto del presente procedimiento ha sido
SATISFECHA EXTRAPROCESALMENTE [/ ha quedado sin objeto], por cuanto [describir el hecho:
p. ej. la demandada ha abonado íntegramente la cantidad reclamada con fecha [...], según
se acredita mediante DOCUMENTO Nº 1 que se acompaña].

SEGUNDO.- Que, desaparecido el interés legítimo en obtener la tutela judicial pretendida,
procede la terminación del proceso de conformidad con el artículo 22 de la Ley de
Enjuiciamiento Civil.

TERCERO.- En cuanto a las costas, habiéndose satisfecho la pretensión de esta parte tras
la presentación de la demanda, [no procede especial pronunciamiento, al existir acuerdo
sobre la terminación] / [de existir oposición, deben imponerse a la parte demandada, por
cuanto su pretensión no habría prosperado de no haber mediado el cumplimiento sobrevenido
(art. 22 LEC, criterio del vencimiento)].

SUPLICO AL TRIBUNAL [/ AL/A LA LAJ] que, teniendo por presentado este escrito con el
documento que se acompaña, tenga por manifestada la satisfacción extraprocesal de la
pretensión y acuerde, mediante decreto, la TERMINACIÓN del proceso y el archivo de las
actuaciones; y, de mediar oposición, se convoque a las partes a fin de que el Tribunal
resuelva por auto lo procedente, con el pronunciamiento sobre costas que en Derecho
corresponda (art. 22 LEC).

[Lugar y fecha]
[Firma electrónica del Procurador y del Abogado]
```

### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Numeración de apartados con ordinales (PRIMERO.-, SEGUNDO.- …)
- Negrita estratégica en encabezados (ALLANAMIENTO / DESISTE / RENUNCIA / SUPLICO)

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

### Pulido con estilo de la casa

Si el `CLAUDE.md` así lo configura, aplicar `estilo-escritos-judiciales`: estructura tripartita, contrastes "una cosa es X / otra es Y", explicación del por qué antes del qué; cero adjetivos vacíos, cero postureo.

## Salida

1. Word `.docx` maquetado en `matters/<slug>/escritos/terminacion-anticipada-v1.docx`.
2. Resumen markdown con:
   - Figura escogida (allanamiento / desistimiento / renuncia / satisfacción extraprocesal) y por qué.
   - **Efecto sobre el derecho y cosa juzgada** (irreversibilidad de renuncia/allanamiento; reversibilidad del desistimiento).
   - **Régimen de costas aplicable** (art. 395 / 396 / 22) y resultado previsible.
   - Conformidad necesaria de la otra parte (si desistimiento tras emplazamiento).
   - **Constancia de la advertencia al cliente** antes de disponer del derecho.
   - Próximos pasos (firma + presentación LexNET).

## Decision tree post-entrega

> **¿Qué hacemos ahora?**
> 1. **Versión final saneada** — confirmar y dejarlo limpio.
> 2. **Cerrar el asunto** — `/cerrar-asunto <slug>` tras el decreto/sentencia de terminación.
> 3. **Tasación de costas** — si hay condena, `/tasacion-costas <slug>`.
> 4. **Ajustar tono o secciones** — dime qué cambiar.

## Reglas

1. **Identificar bien la figura.** Allanamiento (demandado), desistimiento ≠ renuncia (ambas del actor, efectos opuestos), satisfacción extraprocesal. Mezclarlas = error grave.
2. **Efectos de cosa juzgada según figura.** Renuncia (art. 20.1) y allanamiento (art. 21) → cosa juzgada. Desistimiento (art. 20.2) → **sin** cosa juzgada, cabe volver a demandar. Dejarlo claro al cliente.
3. **Reglas de costas.** Allanamiento antes de contestar → **sin costas** salvo mala fe (art. 395). Desistimiento no consentido → costas al **actor** (art. 396). Satisfacción extraprocesal → sin costas si hay acuerdo; si hay oposición, según quién tenía razón (art. 22).
4. **Conformidad del demandado en el desistimiento tras emplazamiento** (art. 20.3): si ya fue emplazado, hace falta su conformidad; si se opone, resuelve el tribunal.
5. **Advertir al cliente antes de disponer del derecho** y dejar constancia en el resumen. No se presenta un allanamiento o una renuncia sin advertencia expresa del efecto irreversible.
6. **Quién decreta.** En desistimiento consentido y satisfacción extraprocesal con acuerdo → **decreto del/de la LAJ**. Allanamiento y renuncia → resolución del **Tribunal** (sentencia/auto).
7. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
8. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
9. **PROHIBIDO entregar texto plano.** Word `.docx` maquetado.
10. **PROHIBIDO inventar jurisprudencia.** Si se cita, ECLI verificado vía `jurisprudenciator` (`buscar_por_cita`) o `[REVISAR]`.
11. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo medidas urgentes.

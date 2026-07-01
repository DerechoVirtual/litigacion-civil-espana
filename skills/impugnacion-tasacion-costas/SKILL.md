---
name: impugnacion-tasacion-costas
description: Impugnacion de la tasacion de costas de la contraria conforme a LEC 244-246 y LO 1/2025. Por partidas indebidas (245.2) o por honorarios excesivos del abogado o perito (246), con limite del tercio (394.3). Plazo 10 dias. Word maquetado obligatorio. Usar con impugnar la tasacion de costas, costas indebidas, honorarios excesivos, impugnacion de costas de la contraria, arts. 245-246 LEC.
---

# Impugnación de la tasación de costas — escrito de oposición (arts. 245-246 LEC)

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Marco normativo de referencia — LO 1/2025 (CRÍTICO, comprobar SIEMPRE)

La **Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia** (en vigor el **3 de abril de 2025**) reformó la LEC. Esta skill es el **reverso** de la tasación de costas: aquí **se pelea la tasación practicada por la contraria**. Tener siempre presente:

- **Plazo de impugnación: 10 días** desde el traslado de la tasación de costas practicada por el LAJ (art. 244.1 LEC). Plazo de días hábiles, improrrogable.
- **Dos vías de impugnación, distintas y no confundibles:**
  - **Partidas indebidas** (art. 245.2 LEC): se impugna porque se han incluido conceptos no incluibles, partidas a favor de quien no es perceptor, o gastos sin derecho a su reembolso.
  - **Honorarios excesivos** del abogado, o de perito o profesional no sujeto a arancel (art. 246 LEC): se impugna la cuantía de la minuta por desproporcionada respecto de los criterios orientadores y de la entidad real del pleito.
- **Trámite del exceso (art. 246.1 LEC):** si se impugna por excesivos los honorarios del abogado, **se da traslado al abogado favorecido** por la condena en costas para que se pronuncie sobre la impugnación, y a continuación **se recaba informe del Colegio de Abogados** (criterios orientadores). Para los peritos, informe del Colegio o asociación correspondiente.
- **Resolución (art. 246.3 LEC):** resuelve el **LAJ por decreto**, manteniendo o reformando la tasación. Ese decreto es **recurrible en revisión** ante el tribunal (art. 454 bis LEC). Nunca decir que es "irrecurrible".
- **Límite del tercio (art. 394.3 LEC):** los honorarios del abogado y los derechos del procurador no pueden exceder en su conjunto del **tercio de la cuantía del proceso**, salvo declaración de temeridad. Es un motivo de impugnación de primer orden cuando la minuta lo rebasa.
- **Tribunales de Instancia.** La LO 1/2025 sustituyó a los Juzgados de Primera Instancia por los **Tribunales de Instancia**: los antiguos Juzgados de Primera Instancia ya no existen. El órgano competente es **siempre el Tribunal de Instancia, Sección Civil, de [provincia]** — encabezar siempre así.
- **LAJ** (Letrado/a de la Administración de Justicia): denominación vigente; nunca "Secretario Judicial".

## Cuándo activar

- "Impugnar la tasación de costas", "impugnación de costas de la contraria"
- "Costas indebidas", "honorarios excesivos", "minuta inflada del abogado contrario"
- "Oposición a la tasación practicada", "reducir las costas que nos reclaman"
- Tras recibir el traslado de la tasación de costas practicada por el LAJ a favor de la parte contraria

## Prerrequisitos

1. `CLAUDE.md` del despacho configurado.
2. Asunto creado vía `/asunto-intake` (slug obligatorio).
3. Tener a la vista: la **tasación practicada** por el LAJ (con sus partidas), las **minutas** del abogado y del procurador de la contraria, la **sentencia** con el pronunciamiento de costas y la **cuantía del proceso**.

## Flujo

### Fase 1 — Recibir y analizar la tasación

- Verificar la **fecha del traslado** de la tasación → de ahí arranca el plazo de **10 días** (art. 244.1 LEC). Marcar el día límite.
- Desglosar cada partida de la tasación: honorarios del letrado contrario, derechos del procurador contrario, gastos periciales, indemnización de testigos, otros gastos.
- Identificar la **cuantía del proceso** y el pronunciamiento de costas de la sentencia (a quién y en qué términos se imponen).

### Fase 2 — Detectar partidas INDEBIDAS (art. 245.2 LEC)

Repasar partida a partida buscando conceptos **no incluibles**:

- **Conceptos no incluibles** como costas (gastos internos del cliente, desplazamientos no necesarios, copias o traducciones no judiciales, gestiones extraprocesales).
- **Gastos sin derecho a reembolso** o no causados en el proceso de que se trata.
- **Partidas de quien no es perceptor**: honorarios de profesional que no intervino, o cuya intervención no era preceptiva.
- **IVA mal aplicado**: doble imposición, IVA sobre conceptos exentos, o IVA cuando el favorecido tiene derecho a deducirlo (solo procede el neto).
- **Derechos del procurador mal calculados**: arancel (RD 1373/2003) aplicado sobre cuantía o procedimiento erróneos, suplementos improcedentes.

### Fase 3 — Valorar el EXCESO de honorarios del abogado (art. 246 LEC)

- Comparar la minuta del letrado contrario con los **criterios orientadores del Colegio de Abogados** ([COLEGIO DE ABOGADOS] — Colegio de [PARTIDO JUDICIAL]; otros colegios como referencia) **según la cuantía y el procedimiento** efectivamente seguidos.
- Ponderar la **entidad real del asunto**: complejidad jurídica, fases efectivamente sustanciadas, número de vistas, recursos, dedicación acreditada. Una minuta no se justifica por la mera cuantía si el trabajo desplegado fue menor.
- Recordar que los criterios colegiales son **orientadores, no vinculantes** (STC 87/2017), pero son la referencia objetiva para medir el exceso.
- Si se impugna por excesivos, anticipar el trámite del art. 246.1: traslado al favorecido + **informe del Colegio de Abogados**.

### Fase 4 — Aplicar el límite del tercio (art. 394.3 LEC)

- Sumar honorarios del abogado **+** derechos del procurador de la contraria. Si el conjunto **excede del tercio de la cuantía del proceso**, hay exceso impugnable.
- Excepción: **declaración expresa de temeridad o mala fe** del condenado en costas. Comprobar si la sentencia la contiene; si no, el tope opera.
- La reducción se proyecta sobre la **minuta del letrado** (el arancel del procurador es regulado y no se modera por esta vía).

### Fase 5 — Plazo

- Confirmar que el escrito se presenta **dentro de los 10 días** desde el traslado (art. 244.1 LEC). Fuera de plazo, la impugnación es inadmisible. Plazo de días hábiles; sábados no hábiles; agosto inhábil salvo habilitación.

## Jurisprudencia (sostener los criterios de moderación e indebida inclusión)

Cuando el escrito se apoye en doctrina (criterio del exceso, alcance del tercio, conceptos no incluibles), buscar/verificar las sentencias con el conector MCP `jurisprudenciator` (`buscar_sentencias` por tema, `buscar_por_cita` para verificar un ECLI/ROJ, `leer_sentencias` para extraer el texto). Es la **única** vía de jurisprudencia del plugin.

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

## Plantilla del escrito de impugnación

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]
(O EN SU CASO, A LA LETRADA DE LA ADMINISTRACIÓN DE JUSTICIA)

Procedimiento: [...]
Cliente: [parte condenada en costas / parte a quien se reclama la tasación]

DON/DOÑA [Procurador], en la representación acreditada en autos de [cliente], bajo la
dirección letrada de DON/DOÑA [NOMBRE DEL LETRADO], abogado del Ilustre Colegio de Abogados
de [PARTIDO JUDICIAL], colegiado nº [...], ante el Tribunal comparezco y, como mejor proceda en
Derecho, DIGO:

Que, habiéndose dado traslado a esta parte de la tasación de costas practicada por la
Letrada de la Administración de Justicia con fecha [...] a favor de [parte favorecida],
por importe de [...] €, y dentro del plazo de DIEZ DÍAS del artículo 244.1 de la Ley de
Enjuiciamiento Civil, vengo a FORMULAR IMPUGNACIÓN de dicha tasación de costas, al amparo
de los artículos 245 y 246 LEC, en base a las siguientes:

ALEGACIONES

1.- DE LAS PARTIDAS INDEBIDAS (art. 245.2 LEC)
[Relación, partida por partida, de los conceptos indebidamente incluidos: gastos no
incluibles, partidas de quien no es perceptor, IVA mal aplicado, derechos del procurador
mal calculados. Indicar el importe a excluir por cada uno.]

2.- DE LOS HONORARIOS EXCESIVOS DEL LETRADO (art. 246 LEC)
[Confrontación de la minuta del abogado contrario con los criterios orientadores del [COLEGIO DE ABOGADOS]
según cuantía y procedimiento, y con la entidad real del asunto. Importe que esta parte
considera procedente. Jurisprudencia en SECUENCIA: un bloque por sentencia (cita → párrafo
literal entrecomillado → anclaje al hecho → desarrollo → transición), según el "Método
secuencial de redacción jurisprudencial".]

3.- DEL LÍMITE DEL TERCIO (art. 394.3 LEC)
[Suma de honorarios del abogado + derechos del procurador frente al tercio de la cuantía
del proceso. Acreditar el exceso y, ante la ausencia de declaración de temeridad, la
procedencia de la reducción.]

En su virtud,

SUPLICO AL TRIBUNAL / A LA LAJ que, teniendo por presentado este escrito en tiempo y
forma, lo admita, tenga por IMPUGNADA la tasación de costas practicada y, previos los
trámites legales (entre ellos, en cuanto a los honorarios del Letrado, el traslado al
favorecido y la solicitud de informe al Ilustre Colegio de Abogados de [COLEGIO/CIUDAD] conforme
al art. 246.1 LEC), dicte resolución por la que:

1.º Se EXCLUYAN de la tasación las partidas indebidas relacionadas en la Alegación 1.ª.
2.º Se REDUZCAN los honorarios del Letrado de la contraria al importe que proceda conforme
   a los criterios colegiales y al límite del tercio del art. 394.3 LEC.
3.º Se practique NUEVA TASACIÓN DE COSTAS por la cantidad que resulte.

[Lugar y fecha]
[Firmas del Procurador y del Abogado]

OTROSÍ PRIMERO DIGO que, para el caso de que la resolución no fuera íntegramente estimatoria,
esta parte anuncia su intención de recurrir en revisión el decreto que se dicte (art. 246.3
y 454 bis LEC).
SUPLICO se tenga por hecha la manifestación a los efectos oportunos.

OTROSÍ SEGUNDO DIGO que se acompañan como documentos los justificantes y criterios colegiales
en que se funda la presente impugnación.
SUPLICO se tengan por aportados.
```

### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Alegaciones con numeración correlativa (1.- / 2.- / 3.-), encabezados en negrita estratégica (ALEGACIONES, SUPLICO, OTROSÍ)

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

## Salida

- Word `.docx` maquetado en `matters/<slug>/escritos/impugnacion-tasacion-costas-v1.docx`
- Si se aportan los criterios colegiales del [COLEGIO DE ABOGADOS] y/o el desglose de las partidas indebidas, acompañarlos como documentos numerados.

## Reglas

1. **Plazo de impugnación: 10 días** desde el traslado de la tasación practicada por el LAJ (art. 244.1 LEC). Fuera de plazo, inadmisible.
2. **Distinguir las dos vías:** partidas **indebidas** (art. 245.2) vs honorarios **excesivos** (art. 246). No mezclarlas en una alegación confusa; cada motivo, su apartado.
3. **Informe colegial si se impugna por excesivos.** Anticipar el trámite del art. 246.1: traslado al favorecido + informe del Colegio de Abogados ([COLEGIO DE ABOGADOS]).
4. **Tope del tercio (art. 394.3 LEC)** salvo temeridad declarada en sentencia. Si la minuta + procurador lo rebasan, alegar la reducción.
5. **Resolución: decreto del LAJ recurrible en revisión** (arts. 246.3 y 454 bis LEC). Prohibido decir que es irrecurrible.
6. **PROHIBIDO inventar jurisprudencia.** ECLI verificado vía `jurisprudenciator` o `[REVISAR]`.
7. **PROHIBIDO entregar texto plano.** Word `.docx` maquetado.
8. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
9. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
10. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo habilitación.

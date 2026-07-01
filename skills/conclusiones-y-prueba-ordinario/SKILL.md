---
name: conclusiones-y-prueba-ordinario
description: Fase intermedia del juicio ordinario — proposición e impugnación de prueba en la audiencia previa (arts. 281-287, 427 LEC) y escrito/intervención de conclusiones tras la práctica de la prueba (art. 433 LEC). Word maquetado. Usar con escrito de conclusiones, conclusiones del juicio ordinario, proposición de prueba, impugnar prueba de la contraria, audiencia previa, art. 433.
---

# Conclusiones y prueba en el juicio ordinario — fase intermedia (dos sub-flujos)

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

Esta skill cubre la **fase intermedia del juicio ordinario** y tiene **DOS sub-flujos claramente separados**:

- **(A) Proposición e impugnación de prueba** — el momento de la **audiencia previa** (arts. 281-287 y 427 LEC).
- **(B) Escrito / intervención de conclusiones** — tras la práctica de la prueba en el juicio (art. 433.2-3 LEC).

Identificar SIEMPRE en qué sub-flujo estamos antes de redactar. No mezclar: la proposición de prueba mira hacia adelante (qué se quiere probar); las conclusiones miran hacia atrás (qué quedó probado).

## Marco normativo de referencia — LO 1/2025 (CRÍTICO, comprobar SIEMPRE)

La **Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia** (en vigor el **3 de abril de 2025**) reformó la LEC. La fase intermedia y la valoración de la prueba se rigen por la **LEC reformada**. Tener siempre presente:

- **Órgano competente: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los antiguos Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
- **LAJ** (Letrado/a de la Administración de Justicia): denominación vigente; **nunca** "Secretario Judicial".
- **Prueba — objeto, pertinencia y utilidad** (arts. 281-283 LEC) y **proposición y admisión** (arts. 284-285 LEC) según LEC reformada.
- **Prueba ilícita** (art. 287 LEC): obtenida con vulneración de derechos fundamentales.
- **Aportación documental** (arts. 265 y 270 LEC): con la demanda/contestación, salvo los supuestos tasados de aportación posterior del 270.
- **Posicionamiento sobre documentos de la contraria** (art. 427 LEC): en la audiencia previa cada parte se pronuncia sobre los documentos aportados de contrario (impugnación o reconocimiento).
- **Conclusiones** (art. 433.2-3 LEC): tras la práctica de la prueba, oralmente en el juicio (o por escrito cuando proceda), valorando la prueba practicada y resumiendo los fundamentos.
- **Diligencias finales** (art. 435 LEC): excepcionales, NO se confunden con las conclusiones (ver más abajo).

## Cuándo activar

**Sub-flujo (A) — proposición / impugnación de prueba:**
- "Prepara la proposición de prueba para la audiencia previa"
- "Qué pruebas propongo y cómo justifico su pertinencia"
- "Impugna la prueba de la contraria" / "impugnar documentos del demandado/demandante"
- "Posicionamiento sobre los documentos de contrario (art. 427)"
- "Prueba ilícita" / "impugnar autenticidad documental"

**Sub-flujo (B) — conclusiones:**
- "Redacta el escrito de conclusiones del juicio ordinario"
- "Prepara mi intervención de conclusiones (art. 433)"
- "Valora la prueba practicada hecho por hecho"
- "Conclusiones tras el juicio"

## Prerrequisitos

1. `CLAUDE.md` del despacho configurado.
2. Asunto creado vía `/asunto-intake` (slug obligatorio); procedimiento = **juicio ordinario**.
3. Para (A): demanda y contestación presentadas; documentos de ambas partes identificados.
4. Para (B): prueba ya practicada en el juicio; saber qué se admitió, qué se practicó y con qué resultado.

---

## SUB-FLUJO (A) — Proposición e impugnación de prueba (audiencia previa)

### A.1 — Inventario de hechos controvertidos

Antes de proponer nada, fijar qué hechos quedan **controvertidos** tras demanda y contestación (los admitidos no necesitan prueba, art. 281.3 LEC). Solo se prueba sobre hechos controvertidos y pertinentes al objeto del proceso.

### A.2 — Proposición de medios de prueba

Para CADA medio de prueba que se proponga, justificar **pertinencia** (relación con el objeto del proceso, art. 283.1) y **utilidad** (idoneidad para esclarecer los hechos controvertidos, art. 283.2), **enlazándolo al hecho concreto que prueba**. Medios:

| Medio | Base legal | Para qué |
|---|---|---|
| Documental | arts. 265, 270, 299.1.1.º LEC | Acreditar hechos por documento (público/privado) |
| Interrogatorio de parte | arts. 301-316 LEC | Hechos personales de la contraparte; ficta confessio |
| Testifical | arts. 360-381 LEC | Hechos percibidos por terceros |
| Pericial | arts. 335-352 LEC | Conocimientos técnicos/científicos sobre hechos |
| Reconocimiento judicial | arts. 353-359 LEC | Examen directo por el tribunal de lugar/objeto/persona |

**Regla de oro:** ninguna prueba se propone "por si acaso". Cada medio se ata a un hecho controvertido y se justifica por qué es pertinente y útil para acreditarlo.

### A.3 — Impugnación de la prueba de la contraria

Posicionarse sobre la prueba propuesta y los documentos aportados de contrario:
- **Autenticidad documental** (art. 427.1 LEC): impugnar documentos privados cuya autenticidad no se reconoce; en su caso, abrir la vía del cotejo/pericial.
- **Ilicitud** (art. 287 LEC): prueba obtenida vulnerando derechos fundamentales — solicitar su no admisión y, en su caso, la nulidad.
- **Impertinencia / inutilidad** (arts. 283 LEC): oponerse a la admisión de la prueba que no guarda relación con el objeto o que no sirve para esclarecer los hechos controvertidos.

### A.4 — Plantilla — cuadro de medios de prueba propuestos

Cuadro a incorporar al escrito / a la intervención en la audiencia previa, con cada medio atado a su hecho y su justificación:

| Nº | Medio de prueba | Hecho controvertido que prueba | Pertinencia (art. 283.1) | Utilidad (art. 283.2) |
|---|---|---|---|---|
| 1.º | Documental nº [N] ([descripción]) | Hecho [Primero/...] de la demanda | [relación con el objeto] | [idoneidad para acreditar] |
| 2.º | Interrogatorio de [parte] | Hecho [...] | [...] | [...] |
| 3.º | Testifical de [testigo] | Hecho [...] | [...] | [...] |
| 4.º | Pericial de [perito/materia] | Hecho [...] | [...] | [...] |
| 5.º | Reconocimiento judicial de [objeto/lugar] | Hecho [...] | [...] | [...] |

Y un bloque de impugnación de la prueba de contrario:

```
IMPUGNACIÓN DE LA PRUEBA DE LA CONTRARIA

1.º Documental de contrario.- Se impugna la autenticidad del DOCUMENTO Nº [N]
    aportado por [parte], conforme al art. 427.1 LEC, por [motivo], interesando
    [cotejo / pericial caligráfica / que no se le atribuya valor probatorio].

2.º Prueba ilícita.- Se interesa la no admisión de [medio] por haber sido obtenida
    con vulneración de [derecho fundamental] (art. 287 LEC).

3.º Impertinencia / inutilidad.- Se interesa la inadmisión de [medio] por no guardar
    relación con el objeto del proceso / por inidóneo para esclarecer los hechos
    controvertidos (art. 283 LEC).
```

---

## SUB-FLUJO (B) — Escrito / intervención de conclusiones (art. 433.2-3 LEC)

Tras la práctica de la prueba en el juicio, las conclusiones tienen **dos partes**: (1) **valoración de la prueba practicada, hecho por hecho** (qué quedó acreditado y con qué medio); (2) **resumen jurídico de los fundamentos** que sostienen la pretensión. **No se introducen hechos nuevos** ni se altera la pretensión.

### B.1 — Valoración de la prueba, hecho por hecho

Recorrer los hechos relevantes del pleito **uno por uno** y, para cada uno, decir **qué quedó acreditado** y **con qué medio** (documento Nº, declaración del testigo, dictamen pericial, interrogatorio, reconocimiento judicial). Atar siempre la afirmación al medio que la sostiene. Lo que no haya quedado probado por la contraria, señalarlo.

### B.2 — Resumen jurídico de los fundamentos

Tras la valoración fáctica, recapitular el encaje jurídico: norma aplicable, subsunción de los hechos ya acreditados y, cuando refuerce el punto, la doctrina jurisprudencial. Para la fundamentación jurisprudencial se aplica el método secuencial (bloque de abajo).

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL DEL FONDO

El Fundamento de Derecho del fondo **NO** amontona sentencias ni las cita "en bloque". Se redacta como una **secuencia de bloques aislados, uno por sentencia**, y cada bloque agota su sentencia antes de pasar a la siguiente. Para cada sentencia, en este orden:

1. **Identificar la resolución**: "La Sentencia de la Sala Primera del Tribunal Supremo de [fecha] (ECLI/ROJ, ponente Excmo. Sr. [...])...".
2. **Reproducir el párrafo literal** entrecomillado, tal cual se extrajo con `leer_sentencias`.
3. **Anclar al hecho** concreto del asunto ("Trasladada esta doctrina a nuestro caso, donde [hecho]...").
4. **Desarrollar el argumento** de subsunción: por qué ese pronunciamiento resuelve este punto a favor del cliente.
5. **Cerrar y transicionar** al punto siguiente, que abre el bloque de la siguiente sentencia.

Una idea jurídica → una sentencia → un bloque desarrollado y cerrado. Prohibido el "cajón de sastre" de citas seguidas sin desarrollo individual.

**PROHIBIDO inventar sentencias y PROHIBIDO inventar el párrafo.** Si `jurisprudenciator` no devuelve una sentencia que sostenga el punto, o no se logra extraer el párrafo literal, decirlo y o (a) reformular el argumento, o (b) marcar `[REVISAR: jurisprudencia no encontrada — verificar manualmente]`.

#### Obtención del párrafo literal — OBLIGATORIO

Para cada sentencia que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=` del punto que sostiene) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se va a entrecomillar en el escrito. No se cita ninguna sentencia de la que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y reproducida textualmente; cualquier paráfrasis va sin comillas.

#### Ficha por sentencia (preparar antes de redactar)

Para CADA cita, dejar lista esta ficha:
- ECLI (ej. `ECLI:ES:TS:2023:1234`)
- ROJ (ej. `ROJ: STS 1234/2023`)
- Tribunal + Sala + Sección
- Fecha
- Magistrado ponente
- **Párrafo literal** (cita textual verificada vía `leer_sentencias`, entrecomillada)
- *Ratio decidendi* en 1-2 frases (paráfrasis, sin comillas)
- **Hecho concreto del asunto** (ya acreditado en juicio) al que se ancla
- **Argumento** de subsunción que se construye a partir de ella

### B.3 — Distinción con las diligencias finales (art. 435 LEC)

**Las conclusiones NO son diligencias finales.** Las conclusiones (art. 433) son la valoración final de la prueba ya practicada y el resumen jurídico. Las **diligencias finales** (art. 435) son una práctica probatoria **excepcional y posterior**, acordada de oficio o a instancia de parte, solo en los supuestos tasados (prueba sobre hechos relevantes no practicada por causas ajenas a la parte, o hechos nuevos/de nueva noticia del art. 286). En conclusiones NO se pide practicar prueba nueva; si fuera necesaria, esa es la vía del 435 y se solicita aparte.

### B.4 — Plantilla — estructura de conclusiones

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL, DE [PROVINCIA]

DON/DOÑA [Procurador], en nombre y representación de [parte], en el procedimiento
de JUICIO ORDINARIO Nº [.../año], bajo la dirección letrada de DON [NOMBRE DEL LETRADO],
ante el Tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que, practicada la prueba en el acto del juicio, y al amparo del art. 433.2 y 3 LEC,
formulo CONCLUSIONES en los siguientes términos:

I.- VALORACIÓN DE LA PRUEBA PRACTICADA (hecho por hecho)

   PRIMERO.- Sobre [hecho controvertido nº 1].
   Ha quedado acreditado que [afirmación], según resulta de [DOCUMENTO Nº N /
   declaración del testigo D. [...] / dictamen pericial de [...] / interrogatorio de
   [parte] / reconocimiento judicial]. [Por el contrario, la parte contraria no ha
   probado [...]].

   SEGUNDO.- Sobre [hecho controvertido nº 2].
   [Qué quedó acreditado y con qué medio].

   [Tantos apartados correlativos como hechos relevantes]

II.- FUNDAMENTOS JURÍDICOS (resumen)

   PRIMERO.- [Norma aplicable + subsunción de los hechos YA acreditados].
   SEGUNDO.- [Fundamentación jurisprudencial en SECUENCIA: un bloque por sentencia
   — cita → párrafo literal entrecomillado → anclaje al hecho probado → desarrollo →
   transición, según el "Método secuencial de redacción jurisprudencial"].

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por formuladas estas conclusiones, y a la vista del
resultado de la prueba practicada, dicte sentencia conforme a lo interesado en el
suplico de [la demanda / la contestación], con expresa imposición de costas a la
parte contraria.

[Lugar y fecha]
[Firma electrónica del Procurador y Abogado]
```

> Cuando las conclusiones sean **orales** (regla general del juicio, art. 433.2 LEC), esta misma estructura sirve de **guion de la intervención**: I valoración fáctica hecho por hecho, II resumen jurídico.

### Maquetación

- Times New Roman 12
- A4 vertical
- Márgenes 3 cm
- Justificado
- Interlineado 1,5
- Apartados ordinales (PRIMERO.-, SEGUNDO.-), nunca "v1/v2"
- Negrita estratégica en encabezados de bloque (VALORACIÓN DE LA PRUEBA, FUNDAMENTOS, SUPLICO)

### Redacción y estilo discursivo (OBLIGATORIO)

- **Numeración correlativa, nunca "v1/v2".** Los apartados se rotulan con ordinales (PRIMERO.-, SEGUNDO.-, TERCERO.- …). Cuando un apartado se divida, numerar los sub-puntos de forma correlativa y con título propio: "**1.- La autenticidad del documento…**", "**2.- El valor del testimonio de…**". **Prohibido** rotular como "I.1", "II.2", "v1", "v2" o anidamientos tipo "1.1".
- **Encadenado discursivo con conectores VARIADOS.** Cada párrafo enlaza con el anterior mediante marcadores de orden y progresión: *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Conviene añadir / Por último*. El escrito debe leerse como una secuencia en la que cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula.** Prohibido reutilizar una misma muletilla de transición (p. ej. abrir todos los bloques jurisprudenciales con "Trasladada esta doctrina al caso"). Alternar las expresiones de anclaje: "Proyectada esta doctrina sobre los hechos…", "Llevada esta doctrina a nuestro supuesto…", "Aplicado este criterio al caso…", "Si trasladamos lo anterior a los hechos probados…".
- **Explicación desarrollada.** Cada argumento se expone completo: premisa normativa → doctrina → hecho → conclusión. Nada de afirmaciones sin desarrollar.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Estilo de la casa y verificación

- Aplicar **automáticamente** `estilo-escritos-judiciales` si el CLAUDE.md lo configura: estructura tripartita, contrastes "una cosa es X / otra es Y", explicación del por qué antes del qué; cero adjetivos vacíos.
- Verificar **como último paso** cada ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`): si alguna no se valida, marcar `[REVISAR: ECLI no validado]` y NO entregar hasta sustituir o verificar manualmente.

## Salida

1. **(B) Conclusiones:** Word .docx maquetado en `matters/<slug>/escritos/conclusiones-ordinario-v1.docx`.
2. **(A) Proposición de prueba:** Word .docx maquetado en `matters/<slug>/escritos/proposicion-prueba-v1.docx` (cuando se materialice por escrito o como guion de la audiencia previa).
3. Resumen markdown con:
   - Sub-flujo trabajado (A y/o B)
   - Cuadro de medios de prueba ↔ hecho (para A) o tabla hecho ↔ medio que lo acredita (para B)
   - Mapa de jurisprudencia citada (tabla: ECLI / Tribunal / fecha / punto sostenido)
   - Próximos pasos (firma + presentación LexNET, o guion para la vista)

## Decision tree post-entrega

> **¿Qué hacemos ahora?**
> 1. **Versión final saneada** (sin nota del revisor) — confirmar y dejarlo limpio
> 2. **Pasar del sub-flujo A al B** (o viceversa) — dime cuál
> 3. **Preparar interrogatorio** — `/preparacion-interrogatorio <slug>` para la vista
> 4. **Diligencias finales** — si procede prueba excepcional posterior (art. 435 LEC)
> 5. **Ajustar tono o secciones** — dime qué cambiar

## Reglas

1. **En conclusiones, valorar la prueba HECHO POR HECHO atándola al medio.** Cada hecho acreditado se sostiene en el documento / testigo / pericial / interrogatorio / reconocimiento judicial concreto.
2. **PROHIBIDO introducir hechos nuevos en conclusiones.** Solo se valora lo practicado y se resume el Derecho; nada de pretensiones nuevas.
3. **Pertinencia + utilidad de CADA prueba propuesta.** Ningún medio "por si acaso": cada uno atado a un hecho controvertido y justificado (arts. 283 LEC).
4. **Impugnación documental en el momento del art. 427.** El posicionamiento sobre los documentos de contrario (autenticidad/ilicitud/impertinencia) se hace en la audiencia previa, no después.
5. **No confundir conclusiones (art. 433) con diligencias finales (art. 435).** Las conclusiones no piden prueba nueva.
6. **PROHIBIDO inventar jurisprudencia.** ECLI verificado vía `jurisprudenciator` o `[REVISAR]`.
7. **PROHIBIDO entregar texto plano.** Word .docx maquetado.
8. **Órgano: "Tribunal de Instancia, Sección Civil, de [provincia]"** (LO 1/2025). Los Juzgados de Primera Instancia ya no existen; encabezar siempre con el Tribunal de Instancia.
9. **PROHIBIDO usar "Secretario Judicial".** Es "Letrado/a de la Administración de Justicia" (LAJ).
10. **Plazos hábiles.** Sábados no hábiles. Agosto inhábil salvo actuaciones urgentes.

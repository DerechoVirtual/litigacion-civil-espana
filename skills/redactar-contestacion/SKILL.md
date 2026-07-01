---
name: redactar-contestacion
description: Redaccion de contestacion a la demanda en juicio ordinario o verbal. Cinco fases con excepciones procesales, contestacion al fondo, reconvencion si procede, jurisprudencia verificada. Plazo de veinte dias habiles. Usar con redactar contestacion o contestar la demanda.
---

# Redactar contestación a la demanda

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Marco normativo de referencia — LO 1/2025

- La **Ley Orgánica 1/2025, de 2 de enero**, de medidas en materia de eficiencia del Servicio Público de Justicia (en vigor el **3 de abril de 2025**), reformó la LEC y reordenó los cauces procesales.
- **Umbral del juicio verbal por cuantía: 15.000 €.** Asuntos de cuantía **≤ 15.000 €** se tramitan por **juicio verbal** (art. 250.2 LEC); **> 15.000 €**, por **juicio ordinario** (art. 249.2 LEC). La contestación sigue el cauce del procedimiento de la demanda.
- **Plazo de contestación:** **20 días hábiles** en juicio ordinario. En juicio verbal, la contestación se presenta por escrito en el plazo legal previsto.
- **Órgano:** "**Tribunal de Instancia, Sección Civil**" (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- **Terminología:** "**Letrado/a de la Administración de Justicia (LAJ)**", nunca "Secretario Judicial".
- Tanto las **excepciones procesales** como el **fondo** de la contestación se fundan con el **método secuencial de jurisprudencia** descrito en la Fase 5.

## Cuándo activar

- "Redactar contestación", "contestar la demanda", "demanda contraria"
- "Soy demandado en [X]"
- Tras recibir notificación de demanda
- Tras `/asunto-intake` cuando la posición es demandado

## Prerrequisitos

1. Asunto creado con `side: demandado` y fecha de notificación registrada.
2. Demanda contraria leída íntegramente.
3. Plazo de contestación calculado (20 días hábiles, LEC 404 ordinario / 438 verbal — verbal contestación se hace en la vista pero el guion se prepara escrito).

## Fase 1 — Lectura crítica de la demanda

Leer la demanda contraria entera. Extraer:

- **Identificación correcta** del demandado (¿somos nosotros o hay error)
- **Procedimiento elegido por el actor:** ¿es el correcto?
- **Cuantía declarada:** ¿es la real?
- **Competencia:** ¿el tribunal es competente territorial y objetivamente?
- **Postulación:** ¿procurador y abogado son preceptivos y están bien?
- **MASC:** ¿el actor acredita intento previo? Si no, marcar como posible motivo de inadmisión.
- **Hechos relatados:** desglosar uno a uno
- **Fundamentos de derecho citados**
- **Jurisprudencia citada por el actor:** verificar ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`). Si inventada, marca grave.
- **Pretensiones del Suplico**
- **Documentos acompañados**

## Fase 2 — Excepciones procesales (LEC 416)

Cribar excepciones por orden:

### Bloque 2A — Excepciones previas (LEC 416)
- Falta de capacidad / personalidad / postulación (LEC 416.1.1)
- Cosa juzgada o litispendencia (LEC 416.1.2)
- Inadecuación del procedimiento (LEC 416.1.4) — ej. ordinario cuando debió ser verbal por materia
- Defecto legal en el modo de proponer la demanda (LEC 416.1.5) — confusión, falta de claridad
- Falta de jurisdicción o competencia (declinatoria — esta va aparte, plazo más corto LEC 64-65)
- Sumisión a arbitraje o mediación (LEC 416.1.3)

### Bloque 2B — Excepciones MASC (Ley Orgánica 1/2025, de 2 de enero)
- Falta de acreditación del intento MASC cuando no exento → posible inadmisión

### Bloque 2C — Excepciones de fondo
- Prescripción
- Caducidad
- Pago
- Compensación
- Pluspetición
- Falta de legitimación activa o pasiva

## Fase 3 — Contestación al fondo

Para CADA hecho de la demanda:
- **Reconocer** los que sean ciertos (ahorra prueba)
- **Negar** los que no sean ciertos (la parte que tiene la carga deberá probarlos)
- **Aclarar** los hechos que se admiten con matiz
- **Añadir hechos propios** que la demanda omite

Para CADA fundamento jurídico:
- Rebatir interpretación de la norma
- Rebatir jurisprudencia citada (si la cita es inexacta, decirlo)
- Aportar fundamento alternativo

## Fase 4 — Reconvención (opcional)

Si el demandado tiene pretensión propia contra el actor, valorar reconvención (LEC 406):
- ¿Conexión con la demanda principal?
- ¿Competencia objetiva del mismo tribunal?
- ¿Procedimiento compatible?

Si sí: redactar reconvención al final del escrito, con su propio Suplico.

## Fase 5 — Jurisprudencia (mínimo 4 STS verificadas)

Igual que en `redactar-demanda`: jurisprudencia vía el conector `jurisprudenciator`, ECLI/ROJ obligatorio, doble entregable (escrito + fichas).

### Obtención del párrafo literal — OBLIGATORIO
Para cada sentencia que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=` del punto que sostiene) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se va a entrecomillar en el escrito. No se cita ninguna sentencia de la que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y reproducida textualmente; cualquier paráfrasis va sin comillas.

### Ficha por sentencia (preparar antes de redactar)
Para CADA cita: ECLI; ROJ; Tribunal + Sala + Sección; Fecha; Magistrado ponente; **Párrafo literal** (cita textual verificada vía `leer_sentencias`, entrecomillada); *Ratio decidendi* en 1-2 frases (paráfrasis, sin comillas); **Hecho concreto** del asunto al que se ancla; **Argumento** de subsunción que se construye a partir de ella.

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL DEL FONDO
El Fundamento de Derecho del fondo **NO** amontona sentencias ni las cita "en bloque". Se redacta como una **secuencia de bloques aislados, uno por sentencia**, y cada bloque agota su sentencia antes de pasar a la siguiente. Para cada sentencia, en este orden: 1) **Identificar la resolución** ("La Sentencia de la Sala Primera del Tribunal Supremo de [fecha] (ECLI/ROJ, ponente Excmo. Sr. [...])..."); 2) **Reproducir el párrafo literal** entrecomillado, tal cual se extrajo con `leer_sentencias`; 3) **Anclar al hecho** concreto del asunto; 4) **Desarrollar el argumento** de subsunción; 5) **Cerrar y transicionar** al punto siguiente. Una idea jurídica → una sentencia → un bloque desarrollado y cerrado. Prohibido el "cajón de sastre" de citas seguidas sin desarrollo individual. **PROHIBIDO inventar sentencias y PROHIBIDO inventar el párrafo**; si `jurisprudenciator` no devuelve sentencia que sostenga el punto, marcar `[REVISAR: jurisprudencia no encontrada]`.

## Fase 6 — Redacción

### Redacción y estilo discursivo (OBLIGATORIO)
- **Numeración correlativa, nunca "v1/v2".** Los Fundamentos de Derecho se rotulan con ordinales (PRIMERO.-, SEGUNDO.-, TERCERO.- …). Cuando un Fundamento se divida en apartados, numerarlos correlativos y con título propio ("**1.- ...**", "**2.- ...**"). Prohibido "IV.1", "V.2", "v1", "v2" o anidamientos tipo "5.1".
- **Encadenado discursivo con conectores VARIADOS:** *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Conviene añadir / Por último*. Cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula** de transición (no abrir todos los bloques jurisprudenciales con la misma muletilla). Alternar anclajes: "Proyectada esta doctrina sobre los hechos…", "Llevada a nuestro supuesto…", "Aplicado este criterio al caso…", "Si trasladamos lo anterior…".
- **Explicación desarrollada:** premisa normativa → doctrina → hecho → conclusión. Nada de afirmaciones sin desarrollar.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]
Procedimiento: Juicio [Ordinario/Verbal] nº [...]
Demandante: [...]
Demandado: [cliente]

DON/DOÑA [Procurador], Procurador de los Tribunales y de [cliente], según acredito
mediante poder que acompaño como DOCUMENTO Nº 1, bajo la dirección letrada de
[Abogado], comparezco y, como mejor proceda en Derecho, DIGO:

Que dentro del plazo legalmente conferido, mediante el presente escrito formulo
CONTESTACIÓN A LA DEMANDA interpuesta por [actor] frente a esta parte, oponiéndome
a la misma con base en las siguientes:

EXCEPCIONES PROCESALES Y MATERIALES

I.- [Excepción procesal 1: ej. falta de litisconsorcio]
II.- [Excepción procesal 2]
III.- [Excepción material: ej. prescripción]
...

HECHOS

Primero.- [Negación / matización / hecho propio]
Segundo.- ...

FUNDAMENTOS DE DERECHO

I.- DE LA COMPETENCIA, PROCEDIMIENTO Y POSTULACIÓN
II.- DE LAS EXCEPCIONES PROCESALES
III.- DEL MASC [si la demanda contraria adolece de él]
IV.- DEL FONDO — SUBSUNCIÓN JURÍDICA
V.- DE LA PRUEBA QUE INTERESA ESTA PARTE
VI.- DE LAS COSTAS

[Si hay reconvención:]
RECONVENCIÓN
[Hechos + Fundamentos + Suplico de la reconvención]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito junto con los documentos
acompañados, lo admita, y, en su día, dicte sentencia por la que:

1.º [Pretensión: desestimación íntegra / parcial / acogimiento de excepción]
2.º [Si hay reconvención: estimación de la misma]
3.º Imponga las costas al actor.

[Lugar y fecha]
[Firmas]
```

## Fase 7-9 — Pulido, subsunción, verificación ECLI

Igual que en `redactar-demanda`: aplicar `estilo-escritos-judiciales`, `subsuncion-juridica`, y verificar los ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`).

## Salida

- Word .docx en `matters/<slug>/escritos/contestacion-v1.docx`
- Fichas jurisprudencia en `matters/<slug>/jurisprudencia/`
- Resumen markdown con bottom line + jurisprudencia + próximos pasos

## Reglas

1. **Plazo de contestación: 20 días hábiles** (LEC 404 ordinario / 438 verbal). Cómputo según LEC 133 — sábados no hábiles, agosto inhábil.
2. **Excepciones procesales antes que fondo**, salvo que la procesal lleve a archivo inmediato.
3. **PROHIBIDO usar terminología obsoleta** (LO 1/2025).
4. **PROHIBIDO inventar jurisprudencia** ni atribuir al actor citas que no hizo.
5. **Negación con coherencia.** No negar un hecho que la prueba documental aportada acredita — quema credibilidad.

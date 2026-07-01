---
name: recurso-apelacion
description: Recurso de apelacion civil ante Audiencia Provincial conforme a LEC 458 y LO 1/2025 sin anuncio. Doble ataque a hechos y fundamentos. Cinco a diez STS verificadas. Usar con apelar sentencia, interponer apelacion o recurso de apelacion.
---

# Recurso de apelación civil — flujo de élite

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cambio crítico LO 1/2025

> **El anuncio del recurso de apelación queda SUPRIMIDO.** Ya no se "anuncia" — se interpone
> directamente con escrito ante el órgano que dictó la resolución, dentro de los 20 días hábiles.

## Marco normativo de referencia — LO 1/2025

La **Ley Orgánica 1/2025, de 2 de enero** (en vigor el **3 de abril de 2025**) reformó la LEC. Para el recurso de apelación civil, lo clave:

- **Interposición directa, SIN previo anuncio.** El recurso de apelación se **interpone directamente** mediante escrito; ya **no existe** el trámite de "anuncio de apelación" (no usar nunca esa expresión).
- **Plazo de interposición: 20 días** desde la notificación de la sentencia (art. 458 LEC).
- **Órgano de presentación.** Se interpone **ante el órgano que dictó la resolución** recurrida, para su resolución por la **Audiencia Provincial**.
- **Doble ataque posible.** Cabe impugnar tanto la **valoración de la prueba** (error fáctico) como la **aplicación del Derecho** (infracción normativa o jurisprudencial).
- **Órgano de instancia: "Tribunal de Instancia, Sección Civil"** (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- **"Letrado/a de la Administración de Justicia (LAJ)"**, nunca "Secretario Judicial".

> Los **motivos del recurso** se fundan con el **método secuencial de jurisprudencia** (ver Fase 4).

## Cuándo activar

- "Apelar sentencia/auto", "interponer apelación"
- "Recurso de apelación", "Audiencia Provincial"
- "Recurrir en segunda instancia"
- Apelación de: divorcio, custodia, alimentos, reclamación cantidad, desahucio, propiedad horizontal, cláusulas abusivas

## Prerrequisitos

1. Asunto creado.
2. Sentencia / auto que se recurre subido al asunto.
3. Plazo de 20 días desde notificación NO consumido (verificar día de notificación al procurador).

## Fase 1 — Lectura crítica de la sentencia

Leer la resolución entera. Extraer:

- **Pretensiones del actor** (qué pidió) vs. **Fallo del tribunal** (qué concedió)
- **Hechos probados** declarados por el tribunal
- **Hechos NO probados** por defecto (los no mencionados)
- **Fundamentos de derecho del tribunal**: con qué razonamiento llega al fallo
- **Jurisprudencia citada por el tribunal**: verificar ECLI con `jurisprudenciator` (`buscar_por_cita`)
- **Costas**: a quién + razón

Sintetizar:
- ¿Hay error in iudicando? (error de derecho — interpretación o aplicación de norma)
- ¿Hay error in procedendo? (error de procedimiento — vulneración de norma procesal)
- ¿Hay error en valoración de prueba? (test del art. 218 LEC sobre motivación)
- ¿Hay incongruencia? (omisiva, extra petita, ultra petita)

## Fase 2 — Motivos de impugnación

Estructurar por DOBLE ATAQUE:

### Ataque a los HECHOS

- **Error en valoración de prueba documental:** documentos que el tribunal ignoró o malinterpretó
- **Error en valoración de prueba testifical:** testigos que el tribunal descartó sin razón motivada
- **Error en valoración de prueba pericial:** dictamen contrario que el tribunal no rebatió
- **Falta de motivación en hechos probados:** art. 218 LEC

### Ataque a los FUNDAMENTOS

- **Error en la subsunción:** aplicación incorrecta del precepto
- **Inaplicación de norma debida:** norma que correspondía aplicar y se omitió
- **Aplicación de norma indebida:** norma incorrecta para el caso
- **Error en interpretación jurisprudencial:** STS o doctrina que el tribunal aplicó mal
- **Vulneración del principio dispositivo:** ultra/extra petita

## Fase 3 — Recomendación letrada

Antes de redactar:
- Probabilidad de éxito (alta/media/baja) basado en jurisprudencia de la AP del territorio
- Riesgo de empeorar: ¿hay riesgo de "reformatio in peius" si la contraria también apela?
- Costas del recurso: estimar
- Recomendación al cliente: apelar / no apelar / negociar transacción antes

Outputear este análisis aparte del escrito final, como documento de trabajo para el cliente.

## Fase 4 — Jurisprudencia (5-10 STS verificadas)

Mediante el conector MCP `jurisprudenciator` (`buscar_sentencias`/`leer_sentencias`):
- 5-10 STS con ECLI/ROJ verificado
- Idealmente STS de unificación de doctrina sobre el punto
- SAP del mismo territorio si refuerza
- Doctrina TJUE si aplica (consumidores, etc.)

### Obtención del párrafo literal — OBLIGATORIO
Para cada sentencia que vaya a citarse, **leer el texto con `leer_sentencias`** (con `parrafos=N` y `terminos=`) y **extraer el pasaje literal exacto** (el *ratio decidendi*) que se entrecomillará. No se cita ninguna sentencia de la que no se haya leído y aislado su párrafo. La cita literal va **entre comillas** y textual; la paráfrasis sin comillas.

### Ficha por sentencia (preparar antes de redactar)
Para CADA cita: ECLI; ROJ; Tribunal + Sala + Sección; Fecha; Magistrado ponente; **Párrafo literal** (verificado vía `leer_sentencias`, entrecomillado); *Ratio decidendi* en 1-2 frases; **Hecho/motivo** al que se ancla; **Argumento** de subsunción.

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL
La fundamentación **NO** amontona sentencias. Se redacta como **secuencia de bloques aislados, uno por sentencia**; cada bloque agota su sentencia antes de la siguiente: 1) **Identificar la resolución**; 2) **Reproducir el párrafo literal** entrecomillado; 3) **Anclar** al motivo/hecho concreto; 4) **Desarrollar el argumento** de subsunción; 5) **Cerrar y transicionar**. Una idea → una sentencia → un bloque cerrado. Prohibido el "cajón de sastre". **PROHIBIDO inventar sentencias y el párrafo**; si no hay sentencia, `[REVISAR: jurisprudencia no encontrada]`.

## Fase 5 — Redacción del escrito

Estructura LEC 458:

```
A LA AUDIENCIA PROVINCIAL DE [PROVINCIA]
A TRAVÉS DEL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]

Procedimiento: Juicio [Ordinario/Verbal] nº [...]
Apelante: [parte] (cliente)
Apelado: [parte contraria]

DON/DOÑA [Procurador], en la representación que tengo acreditada en autos, bajo la
dirección letrada de [Abogado], comparezco y, como mejor proceda en Derecho, DIGO:

Que, dentro del plazo conferido y al amparo del artículo 458 de la Ley de Enjuiciamiento
Civil, mediante el presente escrito INTERPONGO RECURSO DE APELACIÓN frente a la
sentencia/auto de fecha [...], notificada el [...], en base a los siguientes:

ANTECEDENTES DE HECHO

Primero.- [Resumen procesal: cómo llegó la sentencia]
Segundo.- [Fallo recurrido textualmente o resumido]
Tercero.- [Notificación, plazo, cumplimiento]

MOTIVOS DEL RECURSO

PRIMER MOTIVO.- ATAQUE A LOS HECHOS — Error en la valoración de la prueba
[Subsección: documental / testifical / pericial]
[Cita STS sobre criterio de revisión en apelación + subsunción a los hechos del caso]

SEGUNDO MOTIVO.- ATAQUE A LOS FUNDAMENTOS — Infracción del art. [X] CC/LEC/...
[Argumento + jurisprudencia + subsunción]

TERCER MOTIVO.- [si hay tercero]
...

FUNDAMENTOS DE DERECHO

I.- DE LA COMPETENCIA Y PROCEDIMIENTO
[Audiencia Provincial, art. 455 LEC, plazo 20 días hábiles]

II.- DE LA APLICACIÓN DE LA LO 1/2025
[Interposición directa sin anuncio]

III.- DEL FONDO
[Desarrollo de los motivos]

IV.- DE LAS COSTAS
[Art. 398 LEC en relación con 394]

En su virtud,

SUPLICO A LA AUDIENCIA PROVINCIAL que, teniendo por presentado en tiempo y forma este
escrito, lo admita, tenga por interpuesto recurso de apelación frente a la sentencia/auto
de fecha [...], previa elevación de los autos, y, en su día, dicte sentencia por la que:

1.º Estime el presente recurso de apelación.
2.º Revoque la sentencia/auto recurrido en los términos expuestos.
3.º [Pretensión sustitutiva: dicte nueva sentencia estimando la demanda / desestimándola].
4.º Imponga las costas de ambas instancias a [parte contraria].

[Lugar y fecha]
[Firmas]
```

### Redacción y estilo discursivo (OBLIGATORIO)
- **Numeración correlativa, nunca "v1/v2".** Ordinales (PRIMERO.-, SEGUNDO.- …) y, en su caso, motivos del recurso numerados correlativos con título propio ("**1.- ...**"). Prohibido "IV.1", "V.2", "v1", "5.1".
- **Conectores VARIADOS:** *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Dicho lo cual / Por último*. Cada punto se aísla, agota y enlaza.
- **No repetir la misma fórmula** de transición; alternar anclajes ("Proyectada esta doctrina…", "Aplicado este criterio…", "Si trasladamos lo anterior…").
- **Explicación desarrollada:** premisa normativa → doctrina → hecho → conclusión.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los motivos con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» (Fase 4) es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** de ese motivo y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Fase 6-8 — Pulido, subsunción, verificación ECLI

Aplicar automáticamente `estilo-escritos-judiciales`, `subsuncion-juridica`, y verificar los ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`).

## Salida

- Word .docx en `matters/<slug>/escritos/recurso-apelacion-v1.docx`
- Análisis de viabilidad (separado) para el cliente: `matters/<slug>/escritos/dictamen-apelacion.docx`
- Fichas jurisprudencia
- Decision tree:

> 1. **Refinar tonalidad/longitud** — dime objetivo de palabras
> 2. **Preparar oposición a un eventual recurso adhesivo de la contraria** — `/redactar-contestacion` adaptado
> 3. **Preparar para vista en apelación** si la AP la fija
> 4. **Mantener vigilancia de plazos** — `/actualizar-asunto` con la fecha de presentación

## Reglas

1. **NO anuncio.** Suprimido por LO 1/2025. Interposición directa.
2. **Plazo: 20 días hábiles** desde notificación.
3. **DOBLE ATAQUE obligatorio:** hechos + fundamentos.
4. **5-10 STS con ECLI verificado.** Inventar es sancionable.
5. **Reformatio in peius:** avisar al cliente del riesgo cuando ambas partes apelen.
6. **Audiencia Provincial competente:** la del territorio del Tribunal de Instancia que dictó.

---
name: medidas-cautelares
description: Solicitud de medidas cautelares LEC 721-747 con fumus boni iuris, periculum in mora y caucion. Embargo preventivo, anotacion preventiva, deposito, intervencion, cese cautelar. Usar con medidas cautelares o embargo preventivo.
---

# Medidas cautelares

> ⚖️ **Jurisprudencia — primero `jurisprudenciator`.** Toda búsqueda/verificación de jurisprudencia se hace con el conector MCP **jurisprudenciator** (`buscar_sentencias`, `buscar_por_cita`, `leer_sentencias`). Es la única vía del plugin (no vLex, no Chrome).

## Marco normativo de referencia — LO 1/2025

La **Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia** (en vigor el 3 de abril de 2025) reformó la LEC. Para cautelares tener presente:
- **Órgano:** "Tribunal de Instancia, Sección Civil" (competencia del tribunal del asunto principal, art. 723 LEC; LO 1/2025, los antiguos Juzgados de Primera Instancia ya no existen).
- **MASC** (art. 5 LO 1/2025): la solicitud de cautelares **previas** está EXENTA del requisito de procedibilidad; pero si son **coetáneas** y el asunto principal exige MASC, ese MASC debe estar acreditado.
- **LAJ** (Letrado/a de la Administración de Justicia): denominación vigente; nunca "Secretario Judicial".

## Cuándo activar

- "Medidas cautelares", "embargo preventivo"
- "Asegurar la sentencia futura", "evitar que [contraparte] disponga de [bien]"
- "Cautelarísimas" (sin audiencia previa, art. 733.2 LEC)
- "Anotación preventiva de demanda"
- "Cese cautelar de [actividad]"

## Marco legal

- LEC 721-747
- **Tres requisitos copulativos:**
  1. **Fumus boni iuris** — apariencia de buen derecho (art. 728.2)
  2. **Periculum in mora** — peligro por la mora procesal (art. 728.1)
  3. **Caución** — para responder de los daños que pueda causar la medida (art. 728.3)
- **Tipos (numerus apertus, art. 727):**
  - Embargo preventivo de bienes
  - Intervención o administración judicial de bienes productivos
  - Depósito de bienes muebles
  - Anotación preventiva de demanda
  - Prohibición de actos de disposición
  - Suspensión de acuerdos sociales
  - Cesación o abstención cautelar (P.I., competencia desleal, derecho al honor)
  - Cualquier otra que asegure efectividad

## Flujo

### 1. Identificación

- Asunto principal (¿se ha presentado demanda? ¿se va a presentar? ¿pendiente de tribunal?)
- Si es PREVIA a la demanda: tras adopción hay que presentar demanda en 20 días (art. 730.2 LEC)
- Si es COETÁNEA a la demanda: junto con ella
- Si es POSTERIOR: justificar nuevos hechos (art. 730.4 LEC)

### 2. Acreditación de fumus boni iuris

Documental que justifique la apariencia:
- Contrato, factura, escritura, sentencia previa, documentación que sostenga la pretensión principal
- Jurisprudencia favorable a la tesis del cliente

**Método secuencial de jurisprudencia (al fundar el fumus):**
- Para cada sentencia, **leer con `leer_sentencias`** y **extraer el párrafo literal exacto** (el *ratio decidendi*) que se entrecomillará. No se cita ninguna de la que no se haya leído y aislado su párrafo. Cita literal entre comillas y textual; paráfrasis sin comillas.
- Ficha por sentencia: ECLI; ROJ; Tribunal + Sala + Sección; fecha; ponente; **párrafo literal**; *ratio* en 1-2 frases; hecho al que se ancla; argumento.
- **Un bloque por sentencia, en secuencia:** 1) identificar la resolución; 2) párrafo literal entrecomillado; 3) anclar al hecho/apariencia concreta; 4) desarrollar la subsunción; 5) cerrar y transicionar. Una idea → una sentencia → un bloque cerrado. Prohibido el "cajón de sastre". **PROHIBIDO inventar** sentencias o el párrafo; si no hay, `[REVISAR: jurisprudencia no encontrada]`.

### 3. Acreditación de periculum in mora

Hechos que demuestren el riesgo:
- Solvencia comprometida del demandado
- Ventas o disposiciones recientes que indican intención de despatrimonialización
- Plazos largos del procedimiento principal vs. urgencia del derecho

### 4. Caución

- Tipos: dinero, aval bancario, póliza, otra (art. 529.3 LEC por remisión)
- Cuantía: proporcional al daño que pueda causar la medida (LEC 728.3) — habitualmente 5-15% del valor de los bienes afectados; juzgado fija al adoptar

### 5. ¿Cautelarísima sin audiencia? (art. 733.2)

Solo si la audiencia previa puede comprometer el buen fin de la medida (ej. cuando el demandado se vaya a deshacer del bien si se entera). Acreditar el riesgo de comprometimiento específico.

### 6. Redacción

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]

DON/DOÑA [Procurador], en la representación acreditada [/que acreditaré], bajo la
dirección letrada de [Abogado], comparezco y, como mejor proceda en Derecho, DIGO:

Que al amparo de los artículos 721 a 747 de la Ley de Enjuiciamiento Civil, mediante
el presente escrito SOLICITO LA ADOPCIÓN DE MEDIDAS CAUTELARES [PREVIAS / COETÁNEAS /
POSTERIORES] [Y, EN SU CASO, INAUDITA PARTE AL AMPARO DEL ART. 733.2 LEC], en base
a los siguientes:

HECHOS

PRIMERO.- Del derecho que se ejercita
[Resumen de la pretensión principal + acreditación documental del fumus]

SEGUNDO.- Del peligro por la mora procesal
[Hechos concretos que acreditan el riesgo + acreditación documental]

TERCERO.- De la medida solicitada
[Tipo + alcance + bienes concretos]

CUARTO.- De la caución que se ofrece
[Importe + tipo]

[QUINTO.- Si cautelarísima: De la procedencia de adopción sin audiencia previa]

FUNDAMENTOS DE DERECHO

I.- DE LA COMPETENCIA Y PROCEDIMIENTO
[LEC 723 — competencia del tribunal del asunto principal]

II.- DEL FUMUS BONI IURIS
[Art. 728.2 LEC + acreditación]

III.- DEL PERICULUM IN MORA
[Art. 728.1 LEC + acreditación]

IV.- DE LA CAUCIÓN
[Art. 728.3 LEC + ofrecimiento]

V.- DEL TIPO DE MEDIDA Y SU PROPORCIONALIDAD
[Art. 727 LEC + adecuación]

[VI.- DE LA ADOPCIÓN INAUDITA PARTE — si aplica]
[Art. 733.2 LEC + justificación del riesgo de comprometimiento]

VII.- DE LAS COSTAS
[Art. 736 LEC]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito y por solicitada la
adopción de medidas cautelares, lo admita, y, previa[s] [audiencia / sin audiencia,
si procede], dicte auto por el que:

1.º Acuerde [tipo de medida concreta: embargo preventivo / anotación preventiva /
   cese cautelar / depósito / intervención].
2.º Determine la caución exigible y forma de prestación.
3.º Ordene [actos concretos de ejecución de la medida: oficiar al Registro, mandar
   a la Policía Judicial, librar mandamiento al banco, etc.].

[Si previa:] OTROSÍ DIGO: Que dentro del plazo de veinte días desde la adopción
presentaré la demanda principal correspondiente, conforme dispone el artículo 730.2
de la Ley de Enjuiciamiento Civil.

[Lugar y fecha]
[Firmas]
```

### Redacción y estilo discursivo (OBLIGATORIO)

- **Numeración correlativa, nunca "v1/v2".** Hechos y Fundamentos con ordinales (PRIMERO.-, SEGUNDO.- …); los apartados que se subdividan, numerados correlativos y con título propio ("**1.- ...**"). Prohibido "IV.1", "V.2", "v1", "5.1".
- **Encadenado con conectores VARIADOS:** *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Por último*. Cada punto se aísla, se agota y se enlaza con el siguiente.
- **No repetir la misma fórmula** de transición; alternar los anclajes ("Proyectada esta doctrina…", "Aplicado este criterio…", "Si trasladamos lo anterior…").
- **Explicación desarrollada:** premisa normativa → doctrina → hecho → conclusión.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Salida

- Word .docx en `matters/<slug>/escritos/medidas-cautelares-v1.docx`

## Reglas

1. **Tres requisitos copulativos.** Faltar uno = denegación.
2. **MASC no aplica si son previas.** Pero si son coetáneas y el asunto principal sí requiere MASC, ese MASC debe estar acreditado.
3. **Caución obligatoria** salvo excepciones legales (algunas materias de familia exentas — alimentos urgentes a menores).
4. **Cautelarísima inaudita parte** se concede excepcionalmente. Acreditar riesgo específico de comprometimiento del buen fin.
5. **Si previa, demanda en 20 días** o la medida se levanta automáticamente y se condena a la parte que la pidió.
6. **Oposición del afectado: 20 días** desde notificación del auto adoptando la medida (LEC 739).

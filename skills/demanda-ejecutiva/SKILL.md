---
name: demanda-ejecutiva
description: Demanda ejecutiva LEC 549. Titulos judiciales como sentencias firmes y extrajudiciales como escrituras y letras de cambio. MASC no requerido. Usar con iniciar ejecucion, demanda ejecutiva o despachar ejecucion.
---

# Demanda ejecutiva

## Cuándo activar

- "Iniciar ejecución", "demanda ejecutiva", "despachar ejecución"
- "Ejecutar sentencia/auto firme"
- "Ejecutar escritura pública / póliza"
- "Ejecutar letra de cambio / cheque / pagaré"
- "Embargo de bienes"

## Marco legal

- Títulos ejecutivos: LEC 517
- Plazo para presentar demanda ejecutiva: depende del título
  - Sentencia: en cualquier momento desde firmeza, sin plazo de caducidad
  - Título extrajudicial (escritura, póliza, letras): prescripción art. 88 LCCh para letras (3 años); resto según naturaleza
- Procedimiento: LEC 549 y ss
- MASC: NO requerido (exención del art. 5 Ley Orgánica 1/2025, de 2 de enero)
- Costas: a cargo del ejecutado salvo excepción (LEC 539, 583)

## Marco normativo de referencia — LO 1/2025

- La **Ley Orgánica 1/2025, de 2 de enero**, de medidas en materia de eficiencia del Servicio Público de Justicia (en vigor el **3 de abril de 2025**), reformó la Ley de Enjuiciamiento Civil.
- **Demanda ejecutiva: art. 549 LEC** — contenido y forma de la demanda con la que se insta el despacho de ejecución.
- **Títulos ejecutivos (art. 517 LEC):**
  - **Judiciales:** sentencias firmes, autos de homologación, laudos arbitrales firmes, acuerdos homologados judicialmente, etc.
  - **Extrajudiciales:** escrituras públicas, pólizas intervenidas por fedatario, letras de cambio, cheques y pagarés, certificaciones no caducadas, etc.
- **El MASC NO es requisito de procedibilidad en la ejecución.** El asunto está **exento del art. 5 LO 1/2025**: la ejecución de un título no exige acreditar intento previo de medio adecuado de solución de controversias.
- **Órgano competente:** el despacho de ejecución se insta ante el **"Tribunal de Instancia, Sección Civil"** (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- Nomenclatura: **"Letrado/a de la Administración de Justicia (LAJ)"**, nunca "Secretario Judicial".
- La fundamentación, cuando cite jurisprudencia (p. ej. para rebatir una oposición a la ejecución), sigue el **método secuencial** descrito más abajo.

## Flujo

### 1. Identificación del título

Vía `AskUserQuestion`:

- Tipo de título ejecutivo (sentencia firme / auto / escritura pública / póliza intervenida / letra-cheque-pagaré / laudo / acta MASC con fuerza ejecutiva por art. 6 Ley Orgánica 1/2025, de 2 de enero, si la hay)
- Datos identificativos del título (número de procedimiento, fecha, notario, número de protocolo, etc.)
- Cantidad líquida ejecutiva: principal + intereses devengados + previsión de intereses futuros + costas (presupuesto provisional según LEC 575)

### 2. Identificación del ejecutado

- Nombre / razón social, DNI/NIF, domicilio
- Bienes conocidos (si los hay): inmuebles, vehículos, cuentas bancarias, salarios
- Si conocemos NIF y nombre, se puede solicitar averiguación patrimonial al Punto Neutro Judicial (LEC 590)

### 3. Cuantía a ejecutar

Calcular en detalle:

| Concepto | Importe |
|---|---|
| Principal | ... € |
| Intereses devengados hasta fecha presentación | ... € |
| Previsión intereses futuros (art. 575 LEC) | ... € (10-30% del principal) |
| Previsión costas (art. 575 LEC) | ... € (10-30% del principal) |
| **TOTAL** | **... €** |

### 4. Medidas a solicitar

Junto con el despacho:
- Embargo de bienes en cantidad suficiente (LEC 588)
- Averiguación patrimonial vía Punto Neutro Judicial (LEC 590)
- Si el ejecutado es persona física: salarios, pensiones, prestaciones (con respeto al SMI inembargable según LEC 607)
- Si hay riesgo de ocultación: embargo preventivo previo o anotación preventiva de embargo

### 5. Redacción

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]

DON/DOÑA [Procurador], en nombre de [ejecutante], según poder que acompaño como
DOCUMENTO Nº 1, bajo la dirección letrada de [Abogado], comparezco y, como mejor
proceda en Derecho, DIGO:

Que mediante el presente escrito formulo DEMANDA EJECUTIVA al amparo de los
artículos 517 y siguientes de la Ley de Enjuiciamiento Civil, frente a [ejecutado/s],
con base en los siguientes:

HECHOS

PRIMERO.- Del título ejecutivo
[Tipo + identificación + carácter ejecutivo y firme]

SEGUNDO.- De la cantidad reclamada
[Detalle: principal + intereses + previsión costas]

TERCERO.- De los bienes a embargar
[Bienes conocidos, si los hay]

FUNDAMENTOS DE DERECHO

I.- DEL TÍTULO EJECUTIVO Y SU FUERZA
[Art. 517 LEC — naturaleza ejecutiva]

II.- DEL TRIBUNAL COMPETENTE
[Art. 545 LEC — el que conoció en primera instancia para sentencias judiciales;
domicilio del ejecutado o lugar del bien para títulos extrajudiciales]

III.- DE LA CANTIDAD LÍQUIDA Y EXIGIBLE
[Art. 549, 571-573 LEC]

IV.- DE LAS MEDIDAS EJECUTIVAS
[Embargo, averiguación patrimonial, etc.]

V.- DE LAS COSTAS
[Art. 539 LEC]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito junto con los documentos
acompañados, lo admita, y se sirva DESPACHAR EJECUCIÓN frente a [ejecutado], por la
cantidad de [...] € de principal, más [...] € presupuestados para intereses y costas,
acordando:

1.º El embargo de bienes en cantidad suficiente.
2.º La averiguación patrimonial al amparo del artículo 590 LEC.
3.º [Si procede: anotación preventiva, retención salarial, etc.]
4.º La imposición de costas al ejecutado.

OTROSÍ DIGO: [Si procede pedir suspensión de plazo de oposición, intervención judicial
de empresa, ejecución no dineraria — adaptar.]

[Lugar y fecha]
[Firmas]
```

### 6. Pulido + verificación

`estilo-escritos-judiciales` + verificación de ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`, si se citan STS).

## Método secuencial de jurisprudencia

### Obtención del párrafo literal — OBLIGATORIO
Para cada resolución que vaya a citarse, **leer el texto con `leer_sentencias`** y **extraer el pasaje literal exacto** que se entrecomillará. No se cita nada sin haber leído y aislado su párrafo. Cita literal entre comillas y textual; paráfrasis sin comillas.

### Ficha por resolución
Para CADA cita: ECLI; ROJ; Tribunal + Sala + Sección; Fecha; ponente; **Párrafo literal** (verificado vía `leer_sentencias`); *Ratio* en 1-2 frases; **punto** al que se ancla; **Argumento**.

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL
La fundamentación **NO** amontona sentencias: **secuencia de bloques aislados, uno por sentencia**; cada bloque la agota antes de la siguiente: 1) identificar; 2) párrafo literal entrecomillado; 3) anclar al punto/título ejecutivo concreto; 4) desarrollar la subsunción; 5) cerrar y transicionar. Una idea → una sentencia → un bloque cerrado. Prohibido el "cajón de sastre". **PROHIBIDO inventar**; si no hay, `[REVISAR: jurisprudencia no encontrada]`.

### Redacción y estilo discursivo (OBLIGATORIO)
- **Numeración correlativa, nunca "v1/v2".** Ordinales y apartados numerados con título propio. Prohibido "IV.1", "V.2", "v1", "5.1".
- **Conectores VARIADOS:** *En primer lugar / En segundo lugar / Siguiendo con lo anterior / A mayor abundamiento / Por su parte / Asimismo / Por último*. Cada punto se aísla, agota y enlaza.
- **No repetir la misma fórmula** de transición; alternar.
- **Explicación desarrollada:** premisa → doctrina → hecho → conclusión.

### Prohibición del esquema robótico (CRÍTICO)

**JAMÁS** redactar el escrito con una plantilla de sub-rótulos fija que se repita en cada motivo, fundamento o bloque. El caso típico a evitar: encabezar todos los bloques con la misma secuencia mecánica **«El pronunciamiento que se combate» → «La infracción» → «La subsunción»**, una y otra vez. Esa repetición delata redacción automática y queda **PROHIBIDA**.

- El «Método secuencial de jurisprudencia» de esta skill es una **lógica interna de razonamiento** —situar la resolución, su doctrina, anclarla al hecho y desarrollarla—, **NO** un juego de etiquetas visibles ni un molde que se calque idéntico en cada bloque.
- Cada motivo o fundamento se escribe como **prosa forense fluida y con forma propia**: distinto arranque, distinta extensión y distinto orden interno según lo que el argumento pida —uno puede abrir por el hecho, otro por la norma infringida, otro por la doctrina del Tribunal Supremo—.
- Si se emplean sub-rótulos, han de ser **descriptivos del contenido concreto** y **distintos** entre sí; nunca el mismo trío repetido.
- **Test de control:** si dos motivos comparten la misma estructura de epígrafes y el mismo ritmo, está mal redactado → reescribir para que cada uno tenga forma propia.

## Salida

- Word .docx en `matters/<slug>/escritos/demanda-ejecutiva-v1.docx`
- Si el asunto es nuevo, crear sub-asunto con `tipo: ejecucion` y `masc_acreditado: no-aplica`.

## Reglas

1. **MASC no aplica.** Ejecución está exenta art. 5 Ley Orgánica 1/2025, de 2 de enero.
2. **Previsión de intereses y costas hasta 30% del principal** salvo regulación específica (art. 575 LEC).
3. **Cantidades líquidas, vencidas y exigibles.** Si no son líquidas, antes hay que liquidar (proceso declarativo).
4. **Inembargabilidad del SMI** (LEC 607). No solicitar retención por debajo.
5. **Oposición del ejecutado: 10 días** desde notificación del auto despachando ejecución (LEC 556 / 557 si es título extrajudicial).

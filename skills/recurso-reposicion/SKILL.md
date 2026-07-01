---
name: recurso-reposicion
description: Recurso de reposicion LEC 451-454 contra providencias y autos no definitivos del Tribunal de Instancia y contra diligencias del LAJ. Plazo cinco dias. Usar con recurso de reposicion o recurrir providencia.
---

# Recurso de reposición

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- "Recurso de reposición", "reposición", "recurrir providencia"
- "Recurrir auto no definitivo"
- "Recurrir diligencia de ordenación"
- "Recurrir decreto del LAJ"

## Marco legal

- **Resoluciones recurribles:**
  - Providencias y autos no definitivos del Tribunal (LEC 451)
  - Diligencias de ordenación y decretos no definitivos del LAJ (LEC 451 bis con redacción vigente)
- **Plazo:** 5 días desde notificación
- **Efecto:** NO suspende ejecución de la resolución recurrida salvo previsión expresa
- **Resolución:** auto que resuelve es irrecurrible salvo dirección anterior (revisión vs decreto LAJ)

## Marco normativo de referencia — LO 1/2025

La **Ley Orgánica 1/2025, de 2 de enero**, de medidas en materia de eficiencia del Servicio Público de Justicia (en vigor el **3 de abril de 2025**), reformó la Ley de Enjuiciamiento Civil. Para el recurso de reposición lo clave es:

- **Régimen legal:** recurso de reposición de los **arts. 451-454 LEC**.
- **Resoluciones recurribles:** providencias y autos no definitivos del **Tribunal de Instancia**, y diligencias de ordenación y decretos no definitivos del **LAJ**.
- **Plazo:** **5 días** desde la notificación, con expresión de la infracción que se entiende cometida.
- **Efecto:** **no suspende** la ejecución de la resolución recurrida salvo excepción legalmente prevista.
- **Órgano destinatario:** "**Tribunal de Instancia, Sección Civil**" (LO 1/2025; los antiguos Juzgados de Primera Instancia ya no existen).
- **Terminología:** "**Letrado/a de la Administración de Justicia (LAJ)**", **nunca** "Secretario Judicial".

La cita de jurisprudencia, cuando proceda, sigue el **método secuencial** del apartado siguiente.

## Flujo

### 1. Identificar resolución

- Tipo: providencia / auto / diligencia ordenación / decreto LAJ
- Fecha de notificación
- Plazo computado (5 días hábiles desde notificación, LEC 133)
- Contenido literal del fallo

### 2. Motivo de impugnación

Único formato: identificar **infracción concreta** de la LEC u otra norma procesal:

- Vulneración de la regla del procedimiento
- Vulneración del derecho a la prueba
- Vulneración del principio dispositivo
- Vulneración del derecho a la tutela judicial efectiva (art. 24 CE)
- Mala interpretación de la LEC sobre cómputo de plazos

### 3. Jurisprudencia (mínimo 2 STS o doctrina TC sobre el punto)

Mediante el conector MCP `jurisprudenciator` (`buscar_sentencias` / `buscar_por_cita`).

### Obtención del párrafo literal — OBLIGATORIO
Para cada sentencia/auto que vaya a citarse, **leer el texto con `leer_sentencias`** y **extraer el pasaje literal exacto** que se entrecomillará. No se cita nada de lo que no se haya leído y aislado su párrafo. Cita literal entre comillas y textual; paráfrasis sin comillas.

### Ficha por resolución
Para CADA cita: ECLI; ROJ; Tribunal + Sala + Sección; Fecha; ponente; **Párrafo literal** (verificado vía `leer_sentencias`); *Ratio* en 1-2 frases; **punto** al que se ancla; **Argumento**.

### Método secuencial de redacción jurisprudencial — REGLA CARDINAL
La fundamentación **NO** amontona resoluciones: **secuencia de bloques aislados, uno por resolución**; cada bloque la agota antes de la siguiente: 1) identificar; 2) párrafo literal entrecomillado; 3) anclar al punto concreto; 4) desarrollar la subsunción; 5) cerrar y transicionar. Una idea → una resolución → un bloque cerrado. Prohibido el "cajón de sastre". **PROHIBIDO inventar**; si no hay, `[REVISAR: jurisprudencia no encontrada]`.

### 4. Redacción

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

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]
(O EN SU CASO, A LA LETRADA DE LA ADMINISTRACIÓN DE JUSTICIA)

Procedimiento: [...]

DON/DOÑA [Procurador], en la representación acreditada en autos, bajo la dirección
letrada de [Abogado], comparezco y, como mejor proceda en Derecho, DIGO:

Que, dentro del plazo conferido y al amparo de los artículos 451 a 454 de la Ley de
Enjuiciamiento Civil, mediante el presente escrito INTERPONGO RECURSO DE REPOSICIÓN
frente a [providencia / auto / diligencia de ordenación / decreto] de fecha [...],
notificad[a/o] el [...], en base al siguiente:

ÚNICO MOTIVO.- Infracción del artículo [...] LEC, por [explicación concreta].

FUNDAMENTOS DE DERECHO

I.- DE LA NATURALEZA DEL RECURSO
[LEC 451 — resolución recurrible / plazo / efectos]

II.- DEL FONDO DEL MOTIVO
[Argumento + jurisprudencia + subsunción al caso]

En su virtud,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito en plazo y forma, lo admita,
y, previos los trámites legales, dicte resolución por la que estime el presente recurso,
deje sin efecto [la resolución recurrida] y, en su lugar, [pretensión sustitutiva].

[Lugar y fecha]
[Firmas]
```

### 5. Salida

- Word .docx en `matters/<slug>/escritos/reposicion-v1.docx`

## Reglas

1. **Plazo crítico: 5 días hábiles.**
2. **Identificar destinatario correcto:** Tribunal (si recurrimos providencia/auto del tribunal) vs LAJ (si recurrimos diligencia/decreto del LAJ).
3. **No suspensión automática.** Si necesitamos suspender, pedirlo expresamente y motivarlo.
4. **Contra el auto que resuelve la reposición** caben:
   - Si la resolución original era del Tribunal: en su día, cuando se dicte sentencia, podrá hacerse valer en apelación.
   - Si era del LAJ: recurso de revisión LEC 454 bis.

---
name: estilo-escritos-judiciales
description: Capa de estilo que aplica la pluma de la casa en cualquier escrito judicial. Estructura tripartita, contrastes, explicacion del por que antes del que, cero adjetivos vacios. Usar con aplica mi estilo o pluma de la casa.
---

# Pluma de la casa — estilo redaccional

> Nota: estos patrones son el estándar de buena redacción judicial de la casa. Calibrar con escritos reales del despacho cuando se disponga de muestras.

## Cuándo activar

- AUTOMÁTICAMENTE tras cualquier skill de redacción (`redactar-demanda`, `redactar-contestacion`, `recurso-apelacion`, `recurso-reposicion`, etc.)
- "Aplica mi estilo", "pásalo por mi pluma", "voz de la casa"
- Antes de la verificación ECLI y entrega final

## Patrones a inyectar

### 1. Estructura tripartita

Cuando el argumento tiene tres patas, presentarlas con paralelismo:

> "Tres son las razones que sostienen esta pretensión: PRIMERO, [...]; SEGUNDO, [...]; TERCERO, [...]"

> "El precepto exige tres requisitos copulativos: (a) que [...], (b) que [...], y (c) que [...]"

### 2. Contrastes "una cosa es X, otra cosa es Y"

Frase que separa supuestos cercanos pero distintos jurídicamente:

> "Una cosa es que el deudor tenga dificultades transitorias para pagar, y otra muy distinta es que pretenda valerse de ellas para incumplir definitivamente la obligación."

> "Una cosa es la cláusula penal pactada como liquidación anticipada de daños (1152 CC), y otra es la cláusula penal moratoria que se acumula a la indemnización ordinaria (1153 CC)."

### 3. Explicación del por qué antes del qué

Antes de afirmar la conclusión jurídica, exponer la razón que la sostiene:

> "Por cuanto la jurisprudencia exige unidad de acto entre el cumplimiento y la liberación, y dado que en el caso de autos el deudor no ha podido acreditar la entrega material del precio, debe concluirse que la obligación de pago subsiste íntegra."

(NO: "El deudor debe pagar. La jurisprudencia exige unidad de acto.")

### 4. Cierre estratégico

Cada fundamento de derecho cierra con frase de tránsito hacia el siguiente o hacia el suplico:

> "En consecuencia, concurre el supuesto de hecho del 1124 CC, lo que habilita a esta parte para instar la resolución contractual con la consiguiente devolución del precio anticipado y la indemnización de daños, como se solicita en el suplico."

### 5. Cero adjetivos vacíos

ELIMINAR:
- "absolutamente claro"
- "manifiestamente improcedente"
- "indubitadamente acreditado"
- "rotundamente probado"
- "evidente"

SUSTITUIR por:
- afirmación + cita + documento concreto
- Si está acreditado, decir cómo (con doc Nº X)
- Si es improcedente, decir por qué (con artículo Y)

### 6. Cero postureo

ELIMINAR:
- "Es de elemental que..."
- "Constituye un brocardo jurídico que..."
- "Como bien recordó el insigne jurista..."
- Latinajos no necesarios ("ad limine litis", "ex officio", "per se" — usar solo si añaden precisión)

MANTENER latinajos útiles:
- "in dubio pro reo" (penal)
- "iura novit curia" (procesal)
- "ratio decidendi" (jurisprudencial)
- Locuciones jurídicas comprensibles para letrados

### 7. Voz activa, frases cortas

PREFERIR:
- "La contraparte incumplió el [fecha]" (activa, 5 palabras)
- en lugar de "El incumplimiento por parte de la contraparte se produjo el [fecha]" (pasiva, 12 palabras)

Frases de 15-25 palabras máximo. Si más, partir.

### 8. Negrita estratégica

- Encabezados de fundamento (FUNDAMENTO DE DERECHO PRIMERO)
- Conceptos clave que el tribunal debe retener (`cláusula esencial`, `plazo de prescripción`, `documento de mayor valor probatorio`)
- NO negritas decorativas que rompen el flujo

### 9. Conectores procesales típicos del despacho

Listado para reciclar:
- "Esta parte sostiene que..."
- "De cuanto antecede se desprende..."
- "Por todo ello, y al amparo de los preceptos citados..."
- "Lo dicho hasta aquí basta para acreditar que..."
- "En su virtud..."
- "Por lo demás, conviene precisar que..."

### 10. Cierre del Suplico — fórmula limpia

Fórmula recurrente:

> "En su virtud, SUPLICO al [órgano] que, teniendo por presentado este escrito junto con
> los documentos acompañados, lo admita, [me tenga por personado y parte / téngase por
> contestada la demanda / téngase por interpuesto el recurso], y, en su día, previos los
> trámites legales, dicte sentencia/resolución por la que: 1.º... 2.º... 3.º Imponga las
> costas a [parte contraria]."

## Flujo

### 1. Cargar escrito

Leer el .docx generado por skill aguas arriba.

### 2. Pasada 1: estructura

- ¿Hay tres argumentos? Aplicar estructura tripartita
- ¿Hay matiz entre dos supuestos? Aplicar "una cosa es X, otra es Y"

### 3. Pasada 2: orden

- En cada FUNDAMENTO, ¿está el "por qué" antes del "qué"?
- Si no, reordenar

### 4. Pasada 3: limpiar adjetivos

- Buscar "absoluta", "manifiesta", "indudable", "rotunda" y eliminar o sustituir

### 5. Pasada 4: latinajos y postureo

- Eliminar latinajos no esenciales
- Eliminar postureo retórico

### 6. Pasada 5: voz activa y frases cortas

- Convertir pasivas en activas
- Partir frases >25 palabras

### 7. Pasada 6: negrita

- Reservar negrita para encabezados y conceptos clave

### 8. Output

Escrito con estilo aplicado, en el mismo formato (.docx). Generar diff frente al original mostrando los cambios.

## Reglas

1. **El estilo no cambia el fondo.** Subsunción jurídica, cita, pin-cite — todo se preserva.
2. **No reescribir lo que ya esté bien.** Si una sección ya cumple los patrones, no tocar.
3. **No aplicar a escritos no judiciales** (burofaxes, emails) automáticamente; solo cuando se pida explícitamente.
4. **Verifica los ECLI/ROJ con `jurisprudenciator`** (`buscar_por_cita`) como último paso antes de entregar.

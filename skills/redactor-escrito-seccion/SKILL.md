---
name: redactor-escrito-seccion
description: Redactar una seccion concreta de un escrito judicial como hechos, fundamento de derecho sobre un punto, suplico o antecedentes procesales. Usar con redacta los hechos o saca el suplico.
---

# Redactor de sección concreta

> ⚖️ **Jurisprudencia — desde 2026-06-28, primero `jurisprudenciator`.** Cualquier búsqueda, localización o verificación de jurisprudencia (sentencias, ECLI/ROJ) que haga esta skill se realiza **PRIMERO** con el conector MCP **jurisprudenciator** (`https://mcp.jurisprudenciator.lexiaipro.org/mcp`): `buscar_sentencias` (lista con ROJ/ECLI/fecha/ponente/resumen), `buscar_por_cita` (verificar un ECLI o ROJ exacto) y `leer_sentencias` (texto íntegro o párrafos clave; el captcha del CENDOJ se resuelve solo en el servidor). Esta es la **única** vía de jurisprudencia del plugin: no se usa vLex ni búsqueda por Google Chrome.

## Cuándo activar

- "Redacta solo los HECHOS de la demanda"
- "Redacta el FUNDAMENTO DE DERECHO sobre [punto]"
- "Saca el SUPLICO"
- "Redacta los ANTECEDENTES PROCESALES de la apelación"
- Cuando necesitas iterar sobre una sección sin reescribir todo

## Secciones soportadas

| Sección | Aplicable a |
|---|---|
| Encabezamiento | Toda demanda / contestación / recurso |
| Antecedentes de hecho / Hechos | Demanda, contestación, recurso |
| Antecedentes procesales | Recurso de apelación, casación |
| Fundamentos de derecho — competencia | Demanda |
| Fundamentos de derecho — procedimiento | Demanda |
| Fundamentos de derecho — postulación | Demanda |
| Fundamentos de derecho — MASC | Demanda (no exenta) |
| Fundamentos de derecho — fondo | Cualquier escrito |
| Fundamentos de derecho — costas | Cualquier escrito |
| Suplico / Petitum | Toda demanda / recurso |
| Otrosíes | Donde proceda |
| Motivos de impugnación | Recurso de apelación / casación |
| Cuestionario de interrogatorio | Pliego para vista |

## Flujo

### 1. Identificar sección + asunto

- Sección a redactar
- Asunto (slug)
- Versión del escrito (v1, v2 si itera)
- Objetivo concreto de la sección (qué tiene que decir)

### 2. Cargar contexto

- `matters/<slug>/matter.md` (tesis)
- `matters/<slug>/cronologia.md` (eventos para HECHOS)
- `matters/<slug>/cuadro-elementos.md` (cobertura probatoria)
- Documentos del asunto

### 3. Aplicar plantilla por tipo de sección

#### HECHOS

```
HECHOS

Primero.- [Hecho 1 narrado en 2-3 frases, con cita documental al final]
   Se acompaña como DOCUMENTO Nº [N] [descripción del documento].

Segundo.- [Hecho 2 narrado, con cita documental]
   Se acompaña como DOCUMENTO Nº [N] [...]

[...]

[Numeración ordinal romana en hechos, no arábiga]
[Cada hecho con prueba documental anexa]
[Estructura cronológica salvo justificación]
```

#### FUNDAMENTO DE DERECHO sobre X

```
[N].- DE [TEMA] (ej. "DE LA RESOLUCIÓN CONTRACTUAL POR INCUMPLIMIENTO")

Es de aplicación al presente caso el artículo [N] del [norma], que dispone:

"[Cita literal del precepto si breve, o paráfrasis si extenso]"

[Desarrollo de la subsunción a los hechos del caso]

[Cita jurisprudencial — ECLI verificado]

En este sentido, la STS [Sala, Sección], núm. [...]/[año], de [fecha]
[ECLI: ES:TS:AAAA:NNNN], ponente [...], establece que:

"[Cita literal o paráfrasis del FJ pertinente]"

Doctrina que aplicada al caso de autos resulta determinante por cuanto [subsunción
a los hechos concretos del asunto: aquí NO mencionar la sentencia abstracta, sino
conectar con el hecho concreto del cliente].

Por todo ello, [conclusión jurídica del fundamento].
```

#### SUPLICO

```
SUPLICO al [Tribunal de Instancia / Audiencia Provincial / Tribunal Supremo] que,
teniendo por presentado este escrito junto con los documentos acompañados, lo admita,
y, en su día, previos los trámites legales, dicte sentencia por la que:

1.º [Pretensión principal — concreta + cuantía exacta si dineraria]
2.º [Pretensión subsidiaria si la hay, por orden]
3.º [Accesorios: intereses, costas]

[Si hay otrosíes, ir tras el SUPLICO]

OTROSÍ DIGO: [petición secundaria — ej. recibimiento del pleito a prueba, designación
de procurador en otra población, copia simple de los autos, etc.]
```

### 4. Aplicar estilo de la casa

Si el CLAUDE.md así lo configura: encadenar con `estilo-escritos-judiciales`. Estructura tripartita, contrastes, explicación del por qué antes del qué.

### 5. Verificación de citas

Si la sección incluye jurisprudencia: verificar cada ECLI/ROJ con `jurisprudenciator` (`buscar_por_cita`).

### 6. Output

Texto de la sección, en formato listo para pegar en el .docx final. No el escrito completo.

### 7. Decision tree

> 1. **Refinar tono** — dime ajustes
> 2. **Próxima sección** — dime cuál
> 3. **Componer escrito completo** — `/redactar-demanda` / `/recurso-apelacion`

## Reglas

1. **Una sección = una pieza.** No mezclar HECHOS con FUNDAMENTOS aunque sean cortos.
2. **Pin-cite obligatorio.** Cada hecho con documento + cada jurisprudencia con ECLI.
3. **NO inventar.** Si falta dato (ej. nombre del ponente de la STS), marcar `[VERIFICAR — pendiente recuperar de jurisprudenciator]`.
4. **Aplicar estilo de la casa** automáticamente si está configurado.

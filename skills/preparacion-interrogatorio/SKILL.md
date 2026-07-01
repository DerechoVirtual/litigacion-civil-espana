---
name: preparacion-interrogatorio
description: Outline de interrogatorio de parte LEC 301-316 o testigo LEC 360-381. Preguntas organizadas por la tesis y material de impugnacion. Usar con preparar interrogatorio o guion para la vista.
---

# Preparación de interrogatorio

## Cuándo activar

- "Preparar interrogatorio de [nombre]"
- "Guion para la vista"
- "Preguntas para [testigo / contraparte]"
- Antes de audiencia previa (definir prueba de interrogatorio)
- Antes de la vista del ordinario

## Tipos

### Interrogatorio de PARTE (LEC 301-316)

- Preguntas **articuladas** (numeradas, sobre hechos personales)
- Pueden ser **preguntas asertivas** con respuesta sí/no
- La parte debe responder; si no responde o lo hace evasivamente, ficta confessio (LEC 304)
- Sólo sobre hechos en los que haya intervenido personalmente o conozca

### Interrogatorio de TESTIGOS (LEC 360-381)

- Preguntas **abiertas** preferentemente (narrativa del testigo)
- Sin sugestión del contenido de la respuesta
- Sólo sobre hechos que conozca por percepción directa
- Hay tachas (LEC 377): parentesco, dependencia, interés, amistad/enemistad, condena

## Flujo

### 1. Identificar al interrogado

- Nombre + relación con el asunto (parte demandante / demandada / testigo)
- ¿Es nuestro o de la contraria?
- Si nuestro: estamos preparando la pregunta para que conteste a la otra parte (anticipar lo que le preguntarán)
- Si suyo: preparamos las preguntas que QUEREMOS hacerle

### 2. Cargar fuentes

- `matters/<slug>/matter.md` (tesis y hechos)
- `matters/<slug>/cronologia.md` (eventos por fecha)
- `matters/<slug>/cuadro-elementos.md` (qué hay que probar / refutar)
- Documentos donde aparece el interrogado (correos, contratos firmados, etc.)

### 3. Construir cronología del interrogado

Filtrar la cronología solo a eventos donde el interrogado fue actor o testigo directo.

### 4. Definir objetivos del interrogatorio

Tres objetivos posibles, priorizar:
- **Confirmar nuestros hechos** (el interrogado los corrobora)
- **Neutralizar los hechos contrarios** (que admita lo que la contraria no quiere oír)
- **Impugnar credibilidad** (si se contradice con documento del expediente)

### 5. Redactar guion

#### Para PARTE:

```
INTERROGATORIO DE LA PARTE — [Nombre]
Procedimiento: [...]
Variante: contradicción (de la contraria) / corroboración (de la nuestra)
Objetivos: [1, 2, 3]

PREGUNTAS

PRIMERA.- Diga ser cierto que el [fecha] firmó usted el contrato que se acompañó como
   DOCUMENTO Nº 3.
   [Objetivo: que admita firma + fecha]
   [Si niega: confrontar con DOCUMENTO Nº 3]

SEGUNDA.- Diga ser cierto que en el día [fecha] recibió el burofax adjuntado como
   DOCUMENTO Nº 7.
   [Objetivo: que admita recepción]
   [Si niega: confrontar con acuse]

TERCERA.- Diga ser cierto que con anterioridad al [fecha] no realizó pago alguno por
   la cantidad de [...] €.
   [Objetivo: que admita el impago]
   [Si niega: pedir extracto bancario / pedir reconocimiento de recibo]

[Continuar...]

NOTAS DE IMPUGNACIÓN

- Si dice "no firmé" → DOC Nº 3 con su firma
- Si dice "no recibí burofax" → DOC Nº 8 acuse de recibo
- Si dice "pagué en mano" → DOC Nº 14 correo donde reconoce que pago pendiente
```

#### Para TESTIGO:

```
INTERROGATORIO DE TESTIGO — [Nombre]
Procedimiento: [...]
Relación con las partes: [empleado de X, vecino, amigo, etc.]
Tachas previsibles: [parentesco / dependencia / amistad — anticipar]

PREGUNTAS

PRIMERA.- ¿Cuál es su relación con D./Dña. [parte X]?
   [Tacha — recoger]

SEGUNDA.- ¿Estuvo usted presente en la reunión del [fecha] entre [partes]? ¿Qué recuerda
   de esa reunión?
   [Objetivo: que cuente narración consistente con nuestra tesis]
   [Si su recuerdo difiere: confrontar con correo/grabación si la hay]

TERCERA.- ¿Tuvo conocimiento del envío del burofax del [fecha]? ¿De dónde?
   [Objetivo: si dice que su empleador lo recibió y no contestó]

[Continuar...]

NOTAS
- Si nuestro testigo, ensayar con él (sin sugerirle respuesta, conforme deontología)
- Si contrario, abrir preguntas para que se extienda y se contradiga
- Reservar las "preguntas trampa" para el final
```

### 6. Output

`matters/<slug>/interrogatorios/[nombre].md`:

Contiene el guion completo + notas de impugnación + cronología filtrada.

### 7. Decision tree

> 1. **Si es nuestro testigo: ensayo** — recordar deontología (no sugerirle respuestas, art. 11 EGA)
> 2. **Si es contrario: ajustar tras audiencia previa** cuando sepamos qué prueba se admite
> 3. **Cuadro de impugnación** — lista compacta de documentos que tener a mano en vista

## Reglas

1. **Parte = preguntas articuladas asertivas** (sí/no); **testigo = abiertas** (narrativa).
2. **Sólo hechos personales o de conocimiento directo.** Las opiniones jurídicas son del letrado, no del interrogado.
3. **Material de impugnación a la mano** — cualquier respuesta evasiva o contradictoria con documento del expediente debe poder confrontarse en el momento.
4. **Ficta confessio (parte)** — si la parte interrogada no comparece, da respuestas evasivas o se niega a contestar, el tribunal puede tener por reconocidos los hechos.
5. **Tachas de testigo (LEC 377)** — recoger las previsibles. Si hay tacha, plantearla por escrito antes de declarar o en vista.
6. **Deontología (art. 11 EGA, art. 31-36 EGA)** — no instruir al testigo en sentido contrario a la verdad.

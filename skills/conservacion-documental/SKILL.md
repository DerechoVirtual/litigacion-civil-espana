---
name: conservacion-documental
description: Comunicacion al cliente sobre deber de conservacion documental ante litigio inminente. Equivalente civil español del legal hold. Usar con comunicar al cliente que conserve documentacion.
---

# Conservación documental — Comunicación al cliente

## Cuándo activar

- Tras `/asunto-intake` cuando hay correos / contratos / registros que el cliente debe conservar
- "El cliente puede destruir [documentación]"
- "Necesito que el cliente no borre los correos"
- Litigio inminente y prueba en poder del cliente

## Marco legal

- **LEC 217** — Carga de la prueba (quien afirma tiene que probar)
- **LEC 328-329** — Exhibición de documentos entre partes / a terceros
- **STS sobre destrucción de prueba** — la pérdida culposa de prueba en poder de quien debía custodiarla puede llevar a presunción contra él
- **LOPDGDD 3/2018** — la conservación de datos personales debe respetar minimización + plazos legales aplicables
- **Plazos legales de conservación** específicos: mercantil (6 años art. 30 CCo), tributaria (4 años o más), laboral (4 años)

## Subcomandos

### `--emitir` (default)

Generar comunicación al cliente:

```
[Lugar y fecha]

Estimado/a [Cliente],

Como sabe, estamos preparando [el procedimiento / el burofax / la respuesta] en el asunto
[referencia interna]. En este contexto, le recuerdo formalmente la importancia de
CONSERVAR Y NO DESTRUIR la siguiente documentación, que puede resultar relevante como
prueba en el procedimiento:

DOCUMENTACIÓN A CONSERVAR

1. [Categoría 1: ej. correos electrónicos con [contraparte] desde [fecha]]
2. [Categoría 2: ej. contratos firmados con [contraparte], incluidos borradores y anexos]
3. [Categoría 3: ej. facturas, albaranes, justificantes de pago]
4. [Categoría 4: ej. comunicaciones internas relativas al asunto]
5. [Etc.]

INSTRUCCIONES CONCRETAS

- NO borre los correos ni vacíe la papelera / archivo
- NO destruya documentos físicos (contratos, facturas)
- Si dispone de copias de seguridad, conserve las que existen al día de hoy
- Si hay empleados con acceso a esta documentación, comuníqueles este deber de
  conservación (puede reenviar este correo)
- Si los sistemas informáticos del cliente borran automáticamente correos pasado
  cierto tiempo, deshabilite ese borrado para las cuentas relevantes
- Conserve también los METADATOS (fechas de envío/recepción, autoría) — no convierta
  los documentos a formatos que los pierdan

DURACIÓN DEL DEBER

Hasta nueva comunicación por mi parte. El procedimiento puede durar varios años y la
documentación puede ser solicitada en distintas fases (audiencia previa, prueba,
ejecución).

CONSECUENCIAS DE LA DESTRUCCIÓN

La pérdida culposa o dolosa de documentación relevante por la parte que debió custodiarla
puede llevar al tribunal a presumir hechos en su contra, además de la responsabilidad civil
por daños que cause a esta parte. Es por eso que insisto en cumplir estrictamente esta
recomendación.

Cualquier duda sobre qué conservar o cómo, contácteme antes de tomar decisión.

Atentamente,

[Firma del letrado]
[Despacho]
```

### `--refrescar`

Reenviar la comunicación tras paso del tiempo (ej. tras audiencia previa, tras presentación de prueba) para confirmar que sigue vigente el deber.

### `--liberar`

Si el asunto se cierra o si la documentación deja de ser relevante (ej. plazo de prescripción transcurrido), comunicar al cliente:

```
[...] el deber de conservación documental que le comuniqué en [fecha anterior] queda
LIBERADO en cuanto a [tipo de documentación], al haberse [cerrado el asunto / vencido
los plazos / ...]. Puede aplicar a esos documentos sus políticas habituales de
conservación o destrucción, sin perjuicio de los plazos legales generales (mercantil,
tributario, etc.).
```

### `--estado`

Mostrar tabla con asuntos y estado de conservación documental:

| Slug | Fecha emisión | Fecha último refresh | Estado |
|---|---|---|---|
| ... | ... | ... | activo / liberado |

## Flujo

### 1. Identificar categorías de documentación

Vía `AskUserQuestion`:
- ¿Qué tipos de documentación son relevantes al asunto?
- ¿En qué soporte? (correo electrónico, papel, sistemas internos)
- ¿Quién tiene acceso? (solo el cliente / sus empleados / terceros)

### 2. Redactar comunicación

Aplicar plantilla anterior con categorías concretas.

### 3. Output

- Word .docx en `matters/<slug>/conservacion-v[N].docx`
- Actualizar `_log.yaml`: `conservacion_documental: emitida-AAAA-MM-DD`
- Apuntar próximo refresh en 90-180 días según duración esperada del asunto

### 4. Recordatorio al cliente

Si Gmail MCP está disponible, crear borrador en Gmail con el texto + el Word adjunto, listo para que el usuario lo envíe al cliente.

## Reglas

1. **No hay obligación legal genérica de "legal hold" en España** análoga a la anglosajona, pero la pérdida culposa de prueba en poder propio tiene consecuencias procesales (presunciones LEC 217, valoración probatoria).
2. **RGPD compatible**: la conservación por motivos litigiosos es base legal del art. 6.1.c o 6.1.f RGPD, pero hay que respetar minimización y purgar tras litigio.
3. **Plazos de conservación legales** (mercantil, tributario, laboral) prevalecen sobre la liberación — apuntarlo en la comunicación.
4. **Metadatos** son críticos para autenticidad — recordar al cliente.
5. **Si la contraparte detecta destrucción**, puede pedir presunciones contra el destructor — comunicar este riesgo al cliente.

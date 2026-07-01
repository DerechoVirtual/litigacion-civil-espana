---
name: requerimiento-judicial-triage
description: Triage de requerimientos judiciales, exhortos, oficios y diligencias preliminares art 256 LEC. Clasifica, analiza alcance, plazo y oposicion. Usar con hemos recibido requerimiento judicial o exhorto.
---

# Triage de requerimiento judicial

## Cuándo activar

- "Hemos recibido requerimiento judicial / exhorto / oficio"
- "Diligencias preliminares art. 256 LEC"
- "Auto de admisión de demanda" (preámbulo a contestar)
- "Auto despachando ejecución" frente a nosotros

## Flujo

### 1. Clasificar el documento

Tipos habituales:

| Tipo | Plazo crítico | Acción típica |
|---|---|---|
| Auto admisión demanda + emplazamiento | 20 días contestación (LEC 404/438) | Asunto-intake + redactar-contestacion |
| Petición monitorio + requerimiento | 20 días para pagar/oponerse/silencio (LEC 815) | Asunto-intake o pagar |
| Auto despachando ejecución | 10 días oposición (LEC 556/557) | Asunto-intake + oposición ejecución |
| Auto medidas cautelares adoptadas | 20 días oposición (LEC 739) | Asunto-intake + oposición cautelares |
| Diligencias preliminares art. 256 LEC | 5 días oposición + obligación de cumplir | Triagear contenido + responder |
| Exhorto / oficio (juzgado en otra causa) | Plazo del oficio | Cumplir según contenido |
| Citación judicial a vista | Fecha de la vista | Comparecer o justificar incomparecencia |
| Citación a tomar declaración | Fecha | Asistir o justificar |
| Otros (notificación sentencia, etc.) | Variable | Calcular plazo + acción |

### 2. Extraer datos

- **Tribunal/Órgano** emisor (TI Civil [N] Sección X, AP Sección Y, etc.)
- **Procedimiento** + número
- **Partes** (¿somos parte? ¿somos terceros?)
- **Petición concreta** del tribunal/órgano
- **Fecha del documento + fecha notificación** (cómputo desde notificación)
- **Plazo concedido** (en días — calcular hábiles)
- **Documentos adjuntos**

### 3. Cross-check cartera

Buscar en `_log.yaml`:
- ¿Asunto abierto coincidente?
- ¿Procedimiento ya conocido o nuevo?

### 4. Análisis de respuesta

#### Si somos parte:
- ¿Procede cumplir lo solicitado? (entregar documentación, comparecer, etc.)
- ¿Procede oponernos? Motivos posibles (vulneración secreto profesional, datos protegidos, ámbito excesivo, etc.)
- ¿Procede recurso de reposición? (si la resolución es providencia/auto no definitivo)

#### Si somos terceros (ej. nuestro cliente recibe oficio de embargo de tercero):
- Obligación de cumplir como tercero (LEC 591 — obligación de colaboración)
- Posibles motivos para limitar el ámbito (secreto profesional, secreto bancario, etc.)

### 5. Output

`inbound/<slug>/triage.md`:

```markdown
# Triage — Requerimiento judicial [slug]

**Tipo:** [...]
**Órgano:** [...]
**Procedimiento:** [...]
**Fecha notificación:** [...]
**Plazo concedido:** [...] días (vence [...])

## Petición concreta del tribunal
[...]

## Análisis
- ¿Somos parte? [sí/no]
- ¿Asunto abierto en cartera? [sí: slug / no]
- ¿Procede cumplir? [sí/no/parcial — razón]
- ¿Procede oponerse o recurrir? [sí: motivos / no]

## Plan de actuación
[Pasos concretos con responsable]
```

### 6. Decision tree

> **¿Qué hago ahora?**
> 1. **Abrir asunto** — `/asunto-intake` si no existe
> 2. **Redactar respuesta** — escrito de cumplimiento / oposición
> 3. **Recurso de reposición** — `/recurso-reposicion` si procede
> 4. **Comunicar al cliente** — borrador de email con análisis
> 5. **Vigilancia de plazo** — `/actualizar-asunto` con vencimiento

## Reglas

1. **Plazo desde notificación**, no desde firma del auto.
2. **Plazos hábiles** (LEC 133). Sábados no hábiles. Agosto inhábil salvo medidas urgentes.
3. **Si la notificación llega al procurador**, el plazo arranca ahí — confirmar día.
4. **Secreto profesional como límite** (art. 542.3 LOPJ): si el oficio pide documentación cubierta por secreto, oposición motivada antes de entregar.

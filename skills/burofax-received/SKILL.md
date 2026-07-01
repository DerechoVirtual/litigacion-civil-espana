---
name: burofax-received
description: Triage de burofax entrante. Extrae campos, cruza con cartera, evalua merito y presenta opciones con recomendacion. Usar con hemos recibido un burofax o triagear esto.
---

# Triage de burofax recibido

## Cuándo activar

- "Hemos recibido un burofax"
- "Triagear esto"
- Cliente comparte burofax que le ha llegado
- Tras recepción de requerimiento extrajudicial

## Flujo

### 1. Lectura del burofax

Leer el texto completo. Extraer:
- **Remitente** (cliente / letrado contraparte) + datos
- **Destinatario** (¿somos nosotros? ¿cliente nuestro?)
- **Fecha del burofax + fecha de recepción** (cómputo de plazo arranca desde recepción)
- **Tipo** (reclamación / requerimiento / preaviso desahucio / cese / oferta MASC)
- **Pretensión** concreta
- **Plazo concedido**
- **Marcas** (sin perjuicio / MASC art. 5 Ley 1/2025 / confidencial)
- **Documentación adjunta** (si la hay)

### 2. Análisis de mérito

Sin entrar en defensa todavía:

- **¿Fundamento jurídico es sólido?** (cita correctamente artículos, jurisprudencia, hechos)
- **¿Pretensión es proporcional?** (la cuantía o la conducta exigida es razonable)
- **¿Hay base documental?** (acompaña pruebas o solo afirma)
- **¿El plazo concedido es razonable?** (>= 15 días civil, mínimo 30 si MASC)
- **¿Hay vulneración procesal anunciada?** (ej. avisa de demanda sin intentar MASC y la materia lo requiere)

### 3. Cross-check de cartera

Buscar en `_log.yaml`:
- ¿Hay asunto abierto con esta contraparte ya?
- ¿Hay burofax recibido anterior del mismo remitente?
- ¿Hay relación con otro asunto (mismo grupo empresarial, mismos hechos)?

### 4. Evaluación de opciones de respuesta

Presentar 3-5 opciones con análisis breve:

| Opción | Cuándo conviene | Riesgo |
|---|---|---|
| **Aceptar la pretensión** | Pretensión justificada y proporcional, BATNA peor | Asumir el coste |
| **Contra-oferta / negociación** | Pretensión exagerada pero hay base de discusión | Tiempo + revelar BATNA |
| **Responder rebatiendo + reservar acciones** | No estamos de acuerdo en fondo pero queremos puerta para acuerdo | Activa posible litigio |
| **Silencio + esperar demanda** | El remitente bluffea, no tiene acción real o prescripción cerca | Si demanda, contestación 20 días |
| **Demanda preventiva por nuestra parte** (acción declarativa, jactancia) | Si la pretensión nos amenaza con perjuicio reputacional o queremos forzar foro | Coste + iniciativa procesal |

### 5. Recomendación

**Una** recomendación clara con razón en 2-3 frases. No "depende" sin contenido. Si genuinamente depende de factor que no tenemos, decir cuál es ese factor.

### 6. Output

`inbound/<slug>/triage.md`:

```markdown
# Triage — Burofax recibido [slug]

**Fecha recepción:** [...]
**Remitente:** [...]
**Tipo:** [...]
**Pretensión:** [...]
**Plazo concedido:** [...] (vence el [...])

## Análisis de mérito
[2-4 frases]

## Cross-check cartera
[Asuntos relacionados o "ninguno"]

## Opciones
[Tabla con 3-5 opciones]

## Recomendación
[Una opción + razón]

## Próximos pasos
[Acción inmediata + actor responsable]
```

### 7. Decision tree

> **¿Qué hago ahora?**
> 1. **Responder con burofax** — `/burofax-intake [slug-respuesta]` y luego `/burofax-draft`
> 2. **Abrir asunto en cartera y prepararse para demanda** — `/asunto-intake`
> 3. **Esperar y vigilar plazo** — apuntar vencimiento y revisar
> 4. **Llamar al cliente para decidir** — borrador de email con análisis y opciones
> 5. **Pedir más info** — qué necesitamos del cliente

## Reglas

1. **NO responder en silencio sin avisar al cliente.** El cliente puede creer que el silencio le perjudica; explicar la estrategia.
2. **Plazo cuenta desde recepción**, no desde envío.
3. **MASC del remitente** — si el burofax lo invoca y nosotros vamos a litigar luego, conviene responder algo (silencio puede ser interpretado como falta de voluntad negociadora).
4. **Confidencialidad / sin perjuicio** del remitente — respetar. NO citar el burofax en pleito futuro salvo que perdiera su marca.

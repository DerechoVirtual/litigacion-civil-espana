---
name: cronologia
description: Construir o actualizar cronologia del asunto desde fuentes documentales declaradas. Eventos taggeados por significacion segun la tesis. Variantes ofensiva, defensiva, de testigo. Usar con cronologia o timeline del asunto.
---

# Cronología del asunto

## Cuándo activar

- "Cronología", "timeline", "qué pasó cuándo"
- "Saca la cronología de [slug]"
- Antes de redactar demanda u contestación (alimenta el bloque HECHOS)
- Preparación de interrogatorio

## Flujo

### 1. Identificar variante

- **Ofensiva** (por defecto si side=actor): para sostener la demanda — eventos que prueban el incumplimiento de la contraria
- **Defensiva** (por defecto si side=demandado): para sostener la contestación — eventos que neutralizan la pretensión
- **De testigo**: para preparar interrogatorio — solo eventos relevantes al conocimiento del testigo

### 2. Cargar fuentes

- `matters/<slug>/matter.md` (tesis y hechos del intake)
- `matters/<slug>/history.md`
- Uploads del usuario (correos, contratos, facturas, escrituras, sentencias previas)
- Carpeta de documentos del asunto si está configurada

### 3. Extracción de eventos

Para cada documento:
- **Fecha** (la concreta — convertir relativas a absolutas)
- **Tipo de evento** (envío correo / firma contrato / pago / notificación / vista / sentencia / etc.)
- **Actor** (quién hace o recibe)
- **Resumen breve** (1 frase)
- **Documento de soporte** (qué archivo o página lo prueba)
- **Significación según la tesis** (alta/media/baja + nota del por qué)

### 4. Deduplicación

Si dos uploads referencian el mismo evento (ej. correo en su versión enviada y recibida), unificar.

### 5. Ordenación

Cronológica ascendente (puede haber sub-ordenación temporal en hechos del mismo día).

### 6. Tag de significación

Aplicar:
- 🔴 **Crítico** — evento decisivo para la tesis
- 🟠 **Alto** — evento que sostiene punto importante
- 🟡 **Medio** — evento contextual relevante
- 🟢 **Bajo** — contexto, no decisivo

### 7. Output

`matters/<slug>/cronologia.md`:

```markdown
# Cronología — [slug]
**Variante:** [ofensiva / defensiva / testigo de X]
**Última actualización:** [AAAA-MM-DD]

| Fecha | Sig. | Evento | Actor | Soporte |
|---|---|---|---|---|
| AAAA-MM-DD | 🔴 | Firma del contrato | Cliente / Contraparte | Doc Nº 3 (contrato firmado) |
| AAAA-MM-DD | 🟠 | Burofax reclamación | Cliente → Contraparte | Doc Nº 7 (acuse + certificado contenido) |
| AAAA-MM-DD | 🟡 | Reunión telefónica | Cliente y contraparte | Mensaje WhatsApp Cliente (Doc Nº 12) |
| ... | ... | ... | ... | ... |

## Hechos significativos (🔴 + 🟠) en narrativa

[Narrativa fluida que cuenta la "historia" del asunto siguiendo los hechos críticos.
Útil como punto de partida para los HECHOS del escrito.]

## Vacíos detectados

- [Hueco probatorio 1: ej. "no consta acuse de recibo del burofax — pedir copia al cliente"]
- [Hueco 2: ej. "fecha del pago al banco no documentada — solicitar movimiento bancario"]
```

### 8. Decision tree

> **¿Qué hago ahora?**
> 1. **Llevar la narrativa al escrito** — alimenta HECHOS de demanda/contestación
> 2. **Cubrir vacíos probatorios** — pedir al cliente documentos faltantes
> 3. **Cronología de testigo** — para preparar interrogatorio concreto
> 4. **Actualizar tras nuevos documentos** — re-ejecutar

## Reglas

1. **Hechos con fecha y soporte documental.** Sin soporte = nota lateral, no entrada principal.
2. **Tag de significación SUBJETIVO marcado.** Si dudoso, usar `🟡 [revisar]` para que el letrado confirme.
3. **No fabricar.** Si el documento no permite afirmar la fecha exacta, escribir "aprox. mes/año" con flag.
4. **Append-only spirit** — no borrar entradas anteriores al actualizar; añadir nuevas y marcar las que cambien con nota.

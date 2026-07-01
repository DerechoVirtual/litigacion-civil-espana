---
name: cuadro-elementos
description: Cuadro de elementos de la accion o excepcion. Una fila por elemento juridico a probar con articulo, hecho del caso, prueba y estado. Deteccion de gaps. Usar con cuadro de elementos o que nos falta para probar.
---

# Cuadro de elementos

## Cuándo activar

- "Qué nos falta para probar [acción]"
- "¿Tenemos los elementos?"
- "Cuadro de elementos", "element chart", "matriz de prueba"
- Antes de redactar demanda u contestación
- En preparación de audiencia previa

## Variantes

- `--ofensivo` (default si side=actor): para sostener pretensión propia
- `--defensivo` (default si side=demandado): para rebatir pretensión contraria
- `--cruzado`: cuando hay reconvención (ambos)

## Marco

### Acciones civiles habituales y sus elementos

| Acción | Elementos (resumen) |
|---|---|
| Reclamación de cantidad por incumplimiento (1101 CC) | (1) Obligación válida, (2) Incumplimiento o cumplimiento defectuoso, (3) Imputable al deudor (culpa o dolo), (4) Daño cuantificado, (5) Nexo causal |
| Resolución contractual (1124 CC) | (1) Contrato bilateral, (2) Incumplimiento de obligaciones esenciales por la contraparte, (3) Imputabilidad, (4) Voluntad de resolver |
| Responsabilidad extracontractual (1902 CC) | (1) Acción u omisión, (2) Daño, (3) Nexo causal, (4) Culpa o negligencia |
| Cláusula abusiva (Ley General Defensa Consumidores) | (1) Consumidor, (2) Cláusula no negociada individualmente, (3) Causa desequilibrio importante, (4) En perjuicio del consumidor |
| Desahucio falta de pago (LAU + LEC 250.1.1) | (1) Contrato de arrendamiento, (2) Falta de pago de renta vencida, (3) Requerimiento previo (recomendable) |
| Divorcio contencioso (Art. 86 CC) | (1) Matrimonio, (2) Tres meses transcurridos desde celebración (salvo art. 81.2 CC), (3) Voluntad de uno solo de los cónyuges |
| Nulidad por cláusula suelo | (1) Contrato hipoteca con consumidor, (2) Cláusula suelo, (3) Falta de transparencia en su inclusión (STS 24-3-2015 + jurisprudencia TJUE) |

## Flujo

### 1. Identificar acción / excepción

Vía `AskUserQuestion`: ¿qué acción se ejercita? ¿qué excepción se opone?

### 2. Listar elementos

Aplicar plantilla de elementos según acción (de la tabla anterior o jurisprudencia específica).

### 3. Cargar evidencia disponible

Leer:
- `matters/<slug>/matter.md` (hechos del intake)
- `matters/<slug>/cronologia.md` si existe
- Documentos del asunto

### 4. Mapping elemento ↔ prueba

Para CADA elemento:
- **Artículo** que lo sostiene (LEC, CC, leyes específicas)
- **Hecho concreto** del caso que materializa el elemento
- **Documento** del expediente que lo prueba (Doc Nº X, página Y)
- **Estado**: ✅ probado | 🟡 parcial | 🔴 faltante
- **Si faltante**: qué documento/prueba se necesitaría

### 5. Output

`matters/<slug>/cuadro-elementos.md`:

```markdown
# Cuadro de elementos — [slug]
**Acción:** [ej. Resolución contractual + reclamación de cantidad (1124 CC + 1101 CC)]
**Variante:** [ofensivo / defensivo / cruzado]

| # | Elemento | Artículo | Hecho del caso | Prueba | Estado |
|---|---|---|---|---|---|
| 1 | Contrato bilateral válido | 1124 CC, 1254 CC | Contrato firmado el 15-3-2024 | Doc 3 (contrato firmado) | ✅ |
| 2 | Incumplimiento contraparte | 1124 CC, 1101 CC | No entregó la mercancía pactada 30-6-2024 | Doc 5 (albarán incumplido) + Doc 7 (burofax reclamación) | ✅ |
| 3 | Imputabilidad (culpa/dolo) | 1101 CC | Contraparte no acredita causa de fuerza mayor | — | 🟡 (anticipar excepción contraria) |
| 4 | Daño cuantificado | 1101 CC | Coste de aprovisionamiento alternativo: 12.500 € | Doc 9 (factura suministrador alternativo) | ✅ |
| 5 | Nexo causal | 1101 CC, 1107 CC | Inmediación temporal — facturas posteriores al incumplimiento | Doc 9 + Doc 11 (correo proveedor alternativo) | ✅ |

## Análisis de cobertura

- Elementos probados: 4/5
- Parciales: 1 (imputabilidad — anticipar excepción de fuerza mayor)
- Faltantes: 0

## GAPS

🔴 Ninguno crítico.
🟡 (Elemento 3) Anticipar excepción de fuerza mayor de la contraparte. Recomendación:
   pedir certificación a aduanas / proveedor que niegue causa exógena.

## Próximos pasos

1. Solicitar al cliente certificación aduanera para neutralizar fuerza mayor anticipada
2. Si la cobertura está completa, proceder con /redactar-demanda
3. Cronología ofensiva en /cronologia para soportar narrativa de los hechos
```

### 6. Decision tree

> 1. **Si todos ✅** — proceder con `/redactar-demanda` o `/redactar-contestacion`
> 2. **Si hay 🔴 faltantes** — pedir al cliente documentación o reconsiderar viabilidad
> 3. **Si hay 🟡** — preparar prueba anticipada o testigos para vista

## Reglas

1. **Pin-cite por cada celda.** Hecho del caso + documento concreto. Sin pin-cite, no se considera probado.
2. **Si la jurisprudencia sostiene un elemento (ej. STS de transparencia en cláusula suelo)**, añadir al artículo: "Art. X + STS [ECLI]".
3. **GAPS son la salida prioritaria.** El propósito del cuadro es detectar lo que falta, no presumir lo que hay.
4. **Conservador en el estado.** Si dudoso, ✅ → 🟡. Si claramente faltante, 🔴.

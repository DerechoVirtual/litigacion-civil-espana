---
name: tasacion-costas
description: Solicitud de tasacion de costas LEC 241-246 con limite del tercio. Honorarios letrado, derechos procurador, gastos periciales. Usar con tasar costas o impugnar tasacion.
---

# Tasación de costas

## Cuándo activar

- "Tasar las costas", "presentar tasación", "minutar costas a favor"
- "Impugnar tasación contraria"
- Tras sentencia firme con condena en costas a la contraria

## Marco legal

- LEC 241-246 (tasación de costas)
- LEC 394 (condena en costas — criterio del vencimiento, con excepciones)
- LEC 394.3 (LÍMITE DEL TERCIO de la cuantía del proceso para los honorarios del abogado y derechos del procurador, salvo declaración de temeridad)
- Aranceles del procurador (RD 1373/2003) — derechos sí están arancelados
- Criterios orientadores del Colegio de Abogados local para minuta del letrado (orientativos, no vinculantes — STC 87/2017)

## Flujo

### 1. Verificar título

- Sentencia firme (notificada y plazo de apelación agotado, o resolución de la AP firme tras apelación)
- Pronunciamiento sobre costas: "se imponen las costas a la parte demandada" (o demandante, según vencimiento)
- Si la sentencia silencia las costas, hay regla art. 394.2 LEC

### 2. Calcular honorarios del letrado

- Criterios orientadores del Colegio ([COLEGIO DE ABOGADOS] — Colegio de [PARTIDO JUDICIAL]; otros colegios como referencia) según cuantía y procedimiento
- Aplicar:
  - Cuantía base del proceso
  - Factor por procedimiento (ordinario / verbal / apelación)
  - Suplementos (recursos, incidencias, vista oral)
- Si la cuantía es indeterminada: criterio del Colegio (ej. [COLEGIO DE ABOGADOS]: cuantía indeterminada se asume valor base)

### 3. Calcular derechos del procurador

Aranceles RD 1373/2003. Aplicar:
- Tarifa según cuantía y procedimiento
- Suplementos por actos concretos
- IVA correspondiente

### 4. Calcular otros gastos

- Periciales: factura del perito
- Testigos: indemnización (LEC 375)
- Otros gastos necesarios

### 5. Aplicar límite del tercio (LEC 394.3)

- Honorarios del abogado + derechos del procurador no podrán exceder, en su conjunto, del tercio de la cuantía del proceso
- Excepción: declaración expresa de temeridad o mala fe del condenado en costas
- Si supera el tercio, ajustar a la baja la minuta del letrado (el procurador no se reduce — su arancel es regulado)

### 6. Redacción de la solicitud

```
AL TRIBUNAL DE INSTANCIA, SECCIÓN CIVIL [N], DE [PROVINCIA]
(O EN SU CASO, A LA LETRADA DE LA ADMINISTRACIÓN DE JUSTICIA)

Procedimiento: [...]
Cliente: [parte favorecida en costas]

DON/DOÑA [Procurador], en la representación acreditada en autos, bajo la dirección
letrada de [Abogado], comparezco y, como mejor proceda en Derecho, DIGO:

Que mediante sentencia firme de fecha [...], se impusieron las costas a [parte condenada].
Mediante el presente escrito, al amparo de los artículos 241 y siguientes de la Ley de
Enjuiciamiento Civil, SOLICITO LA PRÁCTICA DE TASACIÓN DE COSTAS por los siguientes
conceptos:

CONCEPTOS Y CUANTÍAS

1.- Honorarios del Letrado [Abogado]: ......................... [...] €
   (Minuta detallada como DOCUMENTO Nº 1; criterios [COLEGIO DE ABOGADOS] aplicados)
   [IVA: ... €]
2.- Derechos del Procurador [Procurador]: ..................... [...] €
   (Minuta arancelaria como DOCUMENTO Nº 2; RD 1373/2003)
   [IVA: ... €]
3.- [Gastos periciales: factura como DOCUMENTO Nº 3]: ......... [...] €
4.- [Otros gastos]: ........................................... [...] €

TOTAL TASACIÓN DE COSTAS: .................................... [...] €

[Justificación del cumplimiento del límite del tercio (LEC 394.3) o, en su caso,
acreditación de temeridad para exceptuar el límite]

SUPLICO al Tribunal/LAJ que tenga por presentado este escrito, lo admita, y se sirva
practicar la TASACIÓN DE COSTAS por la cantidad de [...] €, dando traslado a la
parte condenada para que en plazo legal manifieste lo que a su derecho convenga.

[Lugar y fecha]
[Firmas]
```

### 7. Si impugnamos tasación contraria

Plazo: 10 días desde notificación del decreto del LAJ aprobando la tasación (LEC 244).

Motivos de impugnación:
- **Por excesivas**: honorarios desproporcionados, exceso sobre criterios colegiales, no aplicación del tercio
- **Por indebidas**: partidas no incluibles (gastos del cliente, traducciones no judiciales, etc.)
- **Por minuta inflada**: discrepancia con criterios colegiales aplicables a la cuantía y procedimiento

Redacción similar pero con motivos de impugnación + petición de reducción a [cantidad] €.

## Salida

- Word .docx en `matters/<slug>/escritos/tasacion-costas-v1.docx`
- Si hay minuta del letrado y minuta del procurador, ambas como documentos separados a aportar como DOC. Nº 1 y DOC. Nº 2.

## Reglas

1. **Límite del tercio (LEC 394.3)** salvo temeridad declarada. Aplicar.
2. **Cuantía indeterminada** asume valor según criterio del Colegio ([COLEGIO DE ABOGADOS] ~18.000 € a estos efectos, verificar criterios vigentes).
3. **IVA** se incluye en las minutas cuando proceda (clientes con derecho a deducción de IVA: solo neto; clientes sin derecho: minuta + IVA).
4. **Plazo de impugnación de tasación contraria: 10 días** desde decreto del LAJ.
5. **Resolución de la impugnación: auto** que es irrecurrible salvo lo previsto en LEC 245-246.

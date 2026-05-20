---
tags:
  - prodesa
  - accesibilidad
  - wcag
  - homepage
aliases:
  - Accesibilidad Homepage
---

# Accesibilidad — Homepage
**Tarea:** [[00_plantilla|2.4 — Revisión de accesibilidad (WCAG 2.0)]]
**URL:** https://prodesa.com/
**Herramientas usadas:** WAVE + comando headings en DevTools consola
**Fecha:** Mayo 2026
**Estado:** ✅ Validado — hallazgos confirmados con WAVE y DevTools

---

## Resultados WAVE — Homepage

| Categoría          | Cantidad                                       |
| ------------------ | ---------------------------------------------- |
| 🔴 Errors          | **3** (1 Missing form label + 2 Empty buttons) |
| 🔴 Contrast Errors | **20** (Very low contrast)                     |
| 🟡 Alerts          | **262**                                        |
| ✅ Features         | 73                                             |
| ✅ Structure        | 94                                             |
| ARIA               | 193                                            |
| **AIM Score**      | **5.8 / 10**                                   |

**Homepage es peor que Siena (5.8 vs 7.7) — 20 errores de contraste vs 8 en detalle, 113 textos pequeños vs 51, 75 titles redundantes vs 25. El AIM Score encubre la gravedad real.**

---

## Jerarquía de headings — resultado del comando

```
H1: Prodesa                              ⚠️ H1 existe pero genérico (no describe contenido)
H2: Destacados                           ✓ OK
H3: Desde: $189.810.000 *               ⚠️ Precio como heading (sistémico)
H3: Pietra
H3: Desde: $226.000.000 *               ⚠️ Precio como heading
H3: Orizzo
... (14 proyectos más, mismo patrón precio+nombre H3)
H3: Strada
H6: ¿Por qué hoy sí es posible...        ⚠️ SALTO H3→H6 (blog posts, falta H4, H5)
H6: Inversión Inteligente...
... (18 artículos de blog como H6)
H2: Noticias
H6: Descarga nuestra App                 ⚠️ SALTO H2→H6 (falta H3, H4, H5)
H4: Entérate de todo en nuestro Instagram ⚠️ H4 después de H6 (jerarquía inconsistente)
--- FOOTER (sistémico) ---
H3: Contacto
H3: Accede a
H2: Nosotros → H3: Nosotros             ✓ OK
H2: Proyectos de vivienda por ciudad → H3 ✓ OK
H2: Macroproyectos de Vivienda → H3     ✓ OK
H2: Proyectos de Vivienda → H3          ✓ OK
H3: Líneas de atención
H3: Llámanos al 3139040 op 1            ⚠️ Teléfono como heading (sistémico)
```

**2 saltos de heading confirmados por WAVE** (Skipped heading level ×2).

---

## Inventario de hallazgos confirmados

| ID | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|----------|---------------|-------|-------------|-----------|
| A-HOME-01 | H1 "Prodesa" — genérico | 2.4.6 Encabezados y etiquetas | AA | **CONFIRMADO** — H1 existe (positivo) pero "Prodesa" no describe el contenido de la página. Un screen reader llega a la homepage y el primer encabezado solo dice el nombre de la marca, sin contexto de qué ofrece el sitio ("Vivienda nueva en Colombia", "Constructora Prodesa", etc.) | 🟡 Menor |
| A-HOME-02 | 20 errores de contraste | 1.4.3 Contraste (mínimo) | AA | **CONFIRMADO** — 20 Very low contrast en WAVE — 2.5× más que en Siena (8). Incluye probablemente los botones "Buscar vivienda" y otros CTAs de conversión. Patrón `color-naranja` y `color-gris` del design system son sistémicos | 🔴 Crítico |
| A-HOME-03 | 2 Empty buttons | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — 2 botones con SVG y sin aria-label ni texto. Mismo patrón que en Siena (1 empty button). Sistémico confirmado: el design system usa botones de ícono sin nombre accesible. Screen reader anuncia "button" sin propósito | 🔴 Crítico |
| A-HOME-04 | Missing form label — buscador | 3.3.2 Etiquetas o instrucciones | A | **CONFIRMADO** — El campo de búsqueda del hero (buscador principal de la homepage) no tiene `<label>` asociado. WAVE detecta 4 form labels pero 1 input sin label. Screen reader no sabe para qué es el campo | 🔴 Crítico |
| A-HOME-05 | Links redes sociales sin aria-label | 2.4.4 Propósito del enlace / 4.1.2 | A | **CONFIRMADO** — 18 imágenes con alt vacío o nulo. Los links de redes sociales (Instagram, Facebook, LinkedIn, YouTube) con `alt=""` sin aria-label en el `<a>`. Screen reader anuncia "link" sin destino | 🔴 Crítico |
| A-HOME-06 | 2 landmarks `<main>` | 1.3.1 Info y relaciones | A | **CONFIRMADO** — WAVE detecta 2 Main content en la misma página. Solo puede existir un `<main>` por página. El segundo rompe la navegación por landmarks de los screen readers | 🟠 Importante |
| A-HOME-07 | 2 links redundantes (logo) | 2.4.4 Propósito del enlace | A | **CONFIRMADO** — 2 Redundant links en WAVE. El logo/link de inicio aparece duplicado (versión mobile + desktop del navbar). Mismo destino "/" desde el mismo contexto | 🟠 Importante |
| A-HOME-08 | 62 imágenes con mismo alt | 1.1.1 Contenido no textual | A | **CONFIRMADO** — 62 alertas "A nearby image has the same alternative text". Cards de proyectos con imágenes que comparten el mismo alt. Sistémico: 43 en Siena, 62 en homepage | 🟠 Importante |
| A-HOME-09 | 1 Missing fieldset — buscador | 1.3.1 Info y relaciones | A | **CONFIRMADO** — El buscador del hero agrupa controles relacionados (filtros de búsqueda) sin `<fieldset>` + `<legend>`. Screen reader no anuncia el contexto del grupo | 🟠 Importante |
| A-HOME-10 | 113 textos muy pequeños | 1.4.4 Cambio de tamaño de texto | AA | **CONFIRMADO** — 113 Very small text — vs 51 en Siena (2× más). Disclaimers de precios (*), notas de financiación, textos del footer debajo del umbral legible | 🟠 Importante |
| A-HOME-11 | 75 title texts redundantes | 2.4.6 Encabezados y etiquetas | AA | **CONFIRMADO** — 75 Redundant title text — vs 25 en Siena (3× más). Cada card de proyecto y artículo de blog tiene `title` que repite el texto visible. Screen reader anuncia el contenido dos veces | 🟡 Menor |
| A-HOME-12 | 4 alt texts sospechosos | 1.1.1 Contenido no textual | A | **CONFIRMADO** — WAVE marca 4 imágenes con alt potencialmente no descriptivo (Suspicious alternative text). Probablemente incluye los badges de App Store / Google Play y logos. Verificar qué imágenes son | 🟡 Menor |
| A-HOME-13 | Jerarquía H3→H6 y H2→H6 | 1.3.1 Info y relaciones | A | **CONFIRMADO** — 2 saltos: (1) H3→H6 en sección de artículos/blog después de las cards, (2) H2→H6 en sección "Noticias" → "Descarga nuestra App". Patrón sistémico: mismo problema que en Siena | 🔴 Crítico |

---

## Hallazgos positivos

| Elemento | Estado | Detalle |
|----------|--------|---------|
| Atributo `lang` | ✅ | 1 Language feature — `<html lang="es">` existe |
| H1 | ✅ | Existe (aunque genérico) |
| Landmarks semánticos | ✅ | Header, Navigation, Main, Footer presentes |
| ARIA implementado | ✅ | 137 ARIA labels + 24 ARIA — uso activo de ARIA |
| Form labels parciales | ✅ | 4 form labels detectados (falta 1) |

---

## Comparación homepage vs Siena (detalle)

| Métrica | Homepage | Siena | Diferencia |
|---------|----------|-------|------------|
| AIM Score | **5.8** | 7.7 | Homepage es peor |
| Contrast Errors | **20** | 8 | +12 |
| Very small text | **113** | 51 | +62 |
| Redundant title text | **75** | 25 | +50 |
| Same alt text | **62** | 43 | +19 |
| Empty buttons | **2** | 1 | +1 |
| Missing form label | **1** | 0 | Nueva |
| Double `<main>` | **1** | 0 | Nueva |

**Conclusión: La homepage es la página más problemática del sitio en términos de accesibilidad.**

---

→ [[00_plantilla]] · [[02_busqueda-filtros]] · [[05_inventario-final]]

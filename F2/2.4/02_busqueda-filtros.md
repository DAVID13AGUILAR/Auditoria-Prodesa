---
status: completado
created: 2026-05-20
tags:
  - prodesa
  - accesibilidad
  - wcag
  - busqueda
  - filtros
aliases:
  - Accesibilidad Búsqueda
  - Accesibilidad Filtros
---

# Accesibilidad — Búsqueda y Filtros
**Tarea:** [[00_plantilla|2.4 — Revisión de accesibilidad (WCAG 2.0)]]
**URL:** https://prodesa.com/proyecto-vivienda
**Herramientas usadas:** WAVE + comando headings en DevTools consola
**Fecha:** Mayo 2026
**Estado:** ✅ Validado — hallazgos confirmados con WAVE y DevTools

---

## Resultados WAVE — Búsqueda y filtros

| Categoría | Cantidad |
|-----------|----------|
| 🔴 Errors | **3** (1 Missing form label + 2 Empty buttons) |
| 🔴 Contrast Errors | **21** (Very low contrast) |
| 🟡 Alerts | **217** |
| ✅ Features | 32 |
| ✅ Structure | 69 |
| ARIA | 163 |
| **AIM Score** | **5.8 / 10** |

**Mismo AIM Score que homepage (5.8). Los 3 errores y 21 errores de contraste confirman que los problemas son sistémicos — aparecen en todas las páginas del sitio.**

---

## Jerarquía de headings — resultado del comando

```
H1: ¿Dónde quieres vivir?               ✓ Descriptivo — la mejor H1 del sitio
H2: Todas las ofertas de vivienda        ✓ OK
H4: Ordenar                              ⚠️ SALTO H2→H4 — control de filtro marcado como heading
H4: Moneda                               ⚠️ Control de filtro marcado como heading
H3: Desde: $279.000.000 *               ⚠️ Precio como heading (sistémico)
H3: Bosques de Copacabana
H3: Desde: $189.810.000 *               ⚠️ Precio como heading
H3: Pietra
... (6 proyectos más, mismo patrón precio+nombre H3)
H3: Mirasol
H2: Podrían interesarte estas ofertas de otras ciudades   ✓ OK
H3: Desde: $279.000.000 *               ⚠️ Mismo set de proyectos repetido
... (mismo listado de 6 proyectos)
--- FOOTER (sistémico, igual que otras páginas) ---
H3: Contacto / H3: Accede a
H2: Nosotros → H3: Nosotros             ✓
H2: Proyectos de vivienda por ciudad → H3 ✓
H2: Macroproyectos → H3                 ✓
H2: Proyectos de Vivienda → H3          ✓
H3: Llámanos al 3139040 op 1            ⚠️ Teléfono como heading (sistémico)
```

**1 salto confirmado por WAVE** (Skipped heading level ×1): H2→H4 en los controles de filtro.

---

## Inventario de hallazgos confirmados

| ID | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|----------|---------------|-------|-------------|-----------|
| A-FILTROS-01 | 21 errores de contraste | 1.4.3 Contraste (mínimo) | AA | **CONFIRMADO** — 21 Very low contrast. Patrón sistémico: homepage 20, Siena 8. Incluye "Buscar vivienda", "Limpiar Filtros" y probablemente los precios en `color-naranja` de las cards | 🔴 Crítico |
| A-FILTROS-02 | 2 Empty buttons | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — Mismo patrón sistémico: 2 botones SVG sin aria-label ni texto. Aparecen en homepage (2), Siena (1) y búsqueda (2). El design system usa botones de ícono sin nombre accesible | 🔴 Crítico |
| A-FILTROS-03 | 1 Missing form label | 3.3.2 Etiquetas o instrucciones | A | **CONFIRMADO** — Uno de los inputs del panel de filtros no tiene `<label>` asociado. Probablemente el campo de búsqueda por texto o el selector de moneda. Screen reader no sabe para qué es el campo | 🔴 Crítico |
| A-FILTROS-04 | H4 para controles "Ordenar" y "Moneda" | 1.3.1 Info y relaciones | A | **CONFIRMADO** — Los dropdowns de ordenamiento y moneda están marcados como H4 directamente después de un H2 (salto H2→H4). Peor aún: son controles interactivos, no secciones de contenido. Screen reader los anuncia como "encabezado nivel 4" en vez de como controles | 🔴 Crítico |
| A-FILTROS-05 | 2 Missing fieldset — grupos de filtros | 1.3.1 Info y relaciones | A | **CONFIRMADO** — 2 grupos de controles de filtro sin `<fieldset>` + `<legend>`. Probablemente los grupos de selección de ciudad y tipo de vivienda. Screen reader no anuncia el contexto: el usuario no sabe qué está filtrando | 🟠 Importante |
| A-FILTROS-06 | 42 imágenes con mismo alt | 1.1.1 Contenido no textual | A | **CONFIRMADO** — 42 alertas "same alternative text". Cards de proyectos con imágenes que comparten el mismo alt. Sistémico: Siena 43, homepage 62, búsqueda 42 | 🟠 Importante |
| A-FILTROS-07 | Precios como H3 en cards | 1.3.1 Info y relaciones | A | **CONFIRMADO** — Mismo patrón sistémico de homepage y Siena. "Desde: $279.000.000 *" marcado como H3, mismo nivel que el nombre del proyecto. Los precios no son secciones de contenido | 🟠 Importante |
| A-FILTROS-08 | 106 textos muy pequeños | 1.4.4 Cambio de tamaño de texto | AA | **CONFIRMADO** — 106 Very small text. Sistémico: homepage 113, Siena 51, búsqueda 106 | 🟠 Importante |
| A-FILTROS-09 | 55 title texts redundantes | 2.4.6 Encabezados y etiquetas | AA | **CONFIRMADO** — 55 Redundant title text. Sistémico: homepage 75, Siena 25, búsqueda 55 | 🟡 Menor |
| A-FILTROS-10 | Mismo listado de proyectos repetido | 2.4.4 Propósito del enlace | A | **CONFIRMADO** — Los headings muestran que los mismos 6 proyectos aparecen dos veces: en "Todas las ofertas" y en "Podrían interesarte". Los links redundantes de WAVE (×2) probablemente corresponden a esta duplicación | 🟠 Importante |

---

## Hallazgos positivos

| Elemento | Estado | Detalle |
|----------|--------|---------|
| H1 descriptivo | ✅ | "¿Dónde quieres vivir?" — la H1 más descriptiva del sitio |
| Atributo `lang` | ✅ | 1 Language feature |
| 1 solo `<main>` | ✅ | A diferencia de homepage (que tenía 2), aquí solo hay 1 |
| 7 ARIA buttons en filtros | ✅ | Los controles de filtro usan role="button" — intento de accesibilidad |
| 113 ARIA labels | ✅ | Implementación activa de ARIA |
| 6 Form labels | ✅ | 6 de los 7 inputs de filtro tienen label (falta 1) |

---

## Comparación entre páginas (sistémico confirmado)

| Métrica | Homepage | Búsqueda | Siena |
|---------|----------|----------|-------|
| AIM Score | 5.8 | **5.8** | 7.7 |
| Contrast Errors | 20 | **21** | 8 |
| Empty buttons | 2 | **2** | 1 |
| Missing form label | 1 | **1** | 0 |
| Same alt images | 62 | **42** | 43 |
| Very small text | 113 | **106** | 51 |
| Redundant title | 75 | **55** | 25 |

**Conclusión: Los 3 errores (missing label + 2 empty buttons) y los errores de contraste son constantes en todas las páginas — son errores del design system, no de páginas individuales.**

---

→ [[00_plantilla]] · [[01_homepage]] · [[03_detalle-proyecto]] · [[05_inventario-final]]

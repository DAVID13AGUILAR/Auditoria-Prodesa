---
status: pendiente
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - inventario
  - hallazgos
aliases:
  - Inventario CW Flujo 1
fase: "2.2"
---

# 08 — Inventario de hallazgos — Cognitive Walkthrough Flujo 1
**Persona:** [[01_persona-valentina]]
**Hipótesis validada:** [[H3A]]

> Este inventario se completa al terminar el registro de todos los pasos del walkthrough.

---

## Hallazgos por categoría

### AI — Arquitectura de información

| ID | Paso | Descripción | Sev. | Ref. 2.1 |
|----|------|-------------|------|----------|
| CW-01 | 1b | Modal promocional sin botón de cierre visible como primera impresión | 🔴 | — |
| | 3a | Filtro VIS ausente en desktop | 🔴 | H-FILTROS-03 |
| | 3a | Filtros no persistentes al navegar | 🔴 | H-FILTROS-01 |
| | 4c | Tabs Todos/Disponibles/Vendidos sin contexto | 🟠 | H-FILTROS-05 |
| | 4d | Sección "otras ciudades" sin separación visual | 🟠 | — |
| | 5a | Sin breadcrumbs en detalle | 🟠 | H-FILTROS-02 |

### VD — Visual design / jerarquía

| ID | Paso | Descripción | Sev. | Ref. 2.1 |
|----|------|-------------|------|----------|
| | 2a | Hero sin propuesta de valor | 🟠 | H-HOME-04 |
| | 2b | Doble navbar | 🟠 | H-HOME-02 |
| | 2c | CTA "Buscar proyecto" de bajo contraste en mobile | 🟠 | — |
| | 4a | Precio domina sobre nombre del proyecto en tarjetas | 🟠 | H-DETALLE-02 |
| | 5a | Jerarquía visual plana en detalle (precio = m²) | 🟠 | H-DETALLE-01 |

### FI — Filtros / interacción

| ID | Paso | Descripción | Sev. | Ref. 2.1 |
|----|------|-------------|------|----------|
| | 3b | Slider sin campo de texto · escala lineal inadecuada | 🟠 | H-FILTROS-09 |
| | 3b | Filtro de precio below the fold en desktop | 🟠 | — |
| | 3c | Sin scroll automático tras aplicar filtros | 🟠 | H-FILTROS-09 |
| | 3d | "Limpiar filtros" como texto sin affordance de botón | 🟠 | H-FILTROS-03 |
| | 3e | Panel "Busca un lugar" con opciones de tipo de proyecto — etiqueta contradictoria | 🟠 | H-FILTROS-02 |
| | 3e | Sin tooltip en opciones VIS/VIP/NO VIS | 🟠 | H-FILTROS-02 |
| | 4a | Asterisco inconsistente entre tarjetas | 🟠 | H-FILTROS-09 |

### RP — Rendimiento percibido

| ID | Paso | Descripción | Sev. | Ref. 2.1 |
|----|------|-------------|------|----------|
| | 1a | SPA sin SSR — inutilizable sin JavaScript | 🔴 | H-HOME-01 |
| | 4c | Empty state invisible (mobile: debajo del fold) | 🟠 | H-FILTROS-05 |
| | 5b | Mapa a 6–7 scrolls — información de transporte sepultada | 🟠 | — |
| | 5c | Precio por unidad existe en galería pero no en sección principal | 🟠 | H-DETALLE-06 |

---

## Resumen

| Categoría | 🔴 Críticos | 🟠 Importantes | 🟡 Menores |
|-----------|------------|---------------|-----------|
| AI | 3 | 3 | — |
| VD | — | 5 | — |
| FI | — | 7 | — |
| RP | 1 | 3 | — |
| **Total** | **4** | **18** | **—** |

> Pendiente completar con hallazgos de Secciones 5d, 5e, 5f y Sección 6 (Contacto).

---

## Conclusión H3A

**H3A confirmada:** La arquitectura de información no orienta a Valentina hacia el proyecto correcto para su perfil. Los filtros no persistentes, la ausencia del filtro VIS en desktop, la falta de estado del proyecto y la información de transporte sepultada a 6–7 scrolls impiden que complete su tarea en los 15 minutos disponibles.

---

→ [[00_plantilla]] · [[02_punto-entrada]] · [[03_homepage]] · [[04_busqueda-filtros]] · [[05_resultados]] · [[06_detalle-proyecto]] · [[07_contacto]] · [[09_reporte-tarea-2.2]]

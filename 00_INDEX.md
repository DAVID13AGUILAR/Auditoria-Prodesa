---
title: Auditoría UX — Prodesa.com
tags:
  - prodesa
  - index
  - moc
aliases:
  - Inicio
  - Home
  - Índice
cssclasses:
  - index-note
created: 2026-05-20
---

# Auditoría UX · Prodesa.com

> [!abstract] Contexto del proyecto
> **Cliente:** Prodesa — constructora colombiana (proyectos VIS y No-VIS)
> **Objetivo:** Identificar fricciones en el embudo de conversión de prodesa.com
> **Evaluador:** David Marín — UX Freelance
> **Repositorio:** `DAVID13AGUILAR/Auditoria-Prodesa`

---

## Estructura del vault

```
📁 F2/
  📁 2.1/  → Evaluación Heurística (10 principios de Nielsen)
  📁 2.2/  → Cognitive Walkthrough Flujo 1 (registro)
  📁 2.4/  → Accesibilidad WCAG 2.0
📁 research/  → Evidencia y benchmarks de respaldo
📁 assets/    → Capturas organizadas por sección
```

---

## Fase 2 — Análisis

### 2.1 · Evaluación Heurística

| Archivo | Descripción |
|---------|-------------|
| [[F2/2.1/00_plantilla\|Plantilla]] | Estructura base de evaluación |
| [[F2/2.1/01_homepage\|01 · Homepage]] | 10 hallazgos — 3 críticos |
| [[F2/2.1/02_busqueda-filtros\|02 · Búsqueda y Filtros]] | Hallazgos de navegación y filtros |
| [[F2/2.1/03_detalle-proyecto\|03 · Detalle de Proyecto]] | Hallazgos en página de proyecto |
| [[F2/2.1/04_formulario-contacto\|04 · Formulario de Contacto]] | Hallazgos en /contactanos |
| [[F2/2.1/H-FILTROS-02\|H-FILTROS-02]] | Hallazgo individual: filtros |
| [[F2/2.1/05_inventario-final\|05 · Inventario Final]] | 34 hallazgos activos consolidados |
| [[F2/2.1/06_reporte-ejecutivo-sintesis\|06 · Reporte Ejecutivo]] | Síntesis con top 3 críticos |

#### Hipótesis

| Hipótesis | Estado |
|-----------|--------|
| [[F2/2.1/H3A\|H3A — Arquitectura de Información]] | ✅ Confirmada |
| [[F2/2.1/H3B\|H3B — CTAs ambiguos]] | ✅ Confirmada |
| [[F2/2.1/H3C\|H3C — Experiencia mobile]] | ✅ Confirmada |

#### Arquitectura de Información

- [[F2/2.1/arquitectura-informacion/01_por-que-importa-la-ai|01 · Por qué importa la AI]]
- [[F2/2.1/arquitectura-informacion/02_mapa-sitio-actual|02 · Mapa de sitio actual]]
- [[F2/2.1/arquitectura-informacion/03_mapa-sitio-propuesto|03 · Mapa de sitio propuesto]]

---

### 2.2 · Cognitive Walkthrough — Flujo 1 (Registro)

| Archivo | Descripción |
|---------|-------------|
| [[F2/2.2/00_plantilla\|Plantilla]] | Estructura base del CW |
| [[F2/2.2/01_persona-valentina\|01 · Persona — Valentina]] | Perfil de usuario del flujo |
| [[F2/2.2/02_punto-entrada\|02 · Punto de entrada]] | Análisis con métricas Lighthouse |
| [[F2/2.2/02_walkthrough-registro\|02 · Walkthrough Registro]] | 20 pasos — 64 hallazgos |
| [[F2/2.2/03_homepage\|03 · Homepage]] | CW — Homepage |
| [[F2/2.2/04_busqueda-filtros\|04 · Búsqueda y Filtros]] | CW — Filtros |
| [[F2/2.2/05_resultados\|05 · Resultados]] | CW — Listado de resultados |
| [[F2/2.2/06_detalle-proyecto\|06 · Detalle de Proyecto]] | CW — Proyecto Pietra (Ibagué) |
| [[F2/2.2/07_contacto\|07 · Contacto]] | CW — Formulario + conclusión de tarea |
| [[F2/2.2/08_inventario-hallazgos\|08 · Inventario]] | 64 hallazgos CW-01 a CW-64 |
| [[F2/2.2/09_reporte-tarea-2.2\|09 · Reporte]] | Reporte ejecutivo ❌ Pendiente |

---

### 2.4 · Accesibilidad WCAG 2.0

| Archivo | Descripción |
|---------|-------------|
| [[F2/2.4/00_plantilla\|Plantilla]] | Estructura base de auditoría WCAG |
| [[F2/2.4/01_homepage\|01 · Homepage]] | Hallazgos WCAG — homepage |
| [[F2/2.4/02_busqueda-filtros\|02 · Búsqueda y Filtros]] | Hallazgos WCAG — filtros |
| [[F2/2.4/03_detalle-proyecto\|03 · Detalle de Proyecto]] | Hallazgos WCAG — detalle |
| [[F2/2.4/04_formulario-contacto\|04 · Formulario de Contacto]] | Hallazgos WCAG — /contactanos |
| [[F2/2.4/05_inventario-final\|05 · Inventario Final]] | 46 hallazgos WCAG consolidados |
| [[F2/2.4/06_reporte-tarea-2.4\|06 · Reporte Tarea 2.4]] | Output final accesibilidad |

---

## Research · Evidencia de respaldo

- [[research/top3-impacto-conversion|Top 3 — Impacto en conversión]]
- [[research/H6-patrones-pagina-detalle-proyecto|H6 — Patrones página detalle]]
- [[research/H8-visibilidad-estado-proyecto|H8 — Visibilidad estado proyecto]]
- [[research/H-FORM-patrones-formulario-contacto|Patrones formulario contacto]]
- [[research/H-FORM-canales-contacto-omnicanalidad|Canales contacto — Omnicanalidad]]
- [[research/CW-metodologia-cognitive-walkthrough|CW — Metodología Cognitive Walkthrough]]
- [[research/CW-filtro-precio-slider-usabilidad|CW — Filtro precio slider usabilidad]]
- [[research/H-ICONOS-MOBILE-amenidades|Íconos decorativos en listas mobile]]
- [[research/H-COMPARADOR-proyectos|Ausencia de comparador de proyectos]]
- [[research/H-FORM-inconsistencia-campos-mobile-desktop|Formulario — Inconsistencia campos mobile/desktop]]
- [[research/H-FORM-datos-falsos-calidad-leads|Formulario — Datos falsos y calidad de leads]]

---

## Assets · Capturas de pantalla

| Carpeta | Contenido |
|---------|-----------|
| `assets/home/` | 17 capturas · Homepage |
| `assets/filtros/` | 18 capturas · Búsqueda y filtros |
| `assets/detalle/` | 25 capturas · Detalle de proyecto |
| `assets/formulario/` | 6 capturas · Formulario de contacto |
| `assets/misc/` | Capturas sin clasificar |

---

## Contexto y handoff

- [[CONTEXTO-CONVERSACION|Contexto general del proyecto]]
- [[F2/2.1/CONTEXTO-NUEVO-CHAT|Handoff fase 2.1]]
- [[F2/2.2/CONTEXTO-NUEVO-CHAT|Handoff fase 2.2]]
- [[F2/2.4/CONTEXTO-NUEVO-CHAT|Handoff fase 2.4]]

---

> [!tip] Navegación rápida
> Usa `Ctrl+O` para abrir cualquier nota · `Ctrl+G` para ver el Graph View · `Ctrl+Shift+F` para buscar en todo el vault

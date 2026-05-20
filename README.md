# Auditoría UX · Prodesa.com

Repositorio de trabajo para la auditoría UX/UI de **prodesa.com**, constructora colombiana de vivienda VIS y No-VIS. El objetivo es identificar y documentar fricciones en el embudo de conversión del sitio web.

**Evaluador:** David Marín — UX Freelance  
**Estado:** Fase 2 — Análisis en curso  
**Sitio evaluado:** [prodesa.com](https://prodesa.com)

---

## Estructura del repositorio

```
📄 00_INDEX.md              → Entrada principal del vault (Map of Content)
📄 CONTEXTO-CONVERSACION.md → Contexto general del proyecto

📁 F2/
  📁 2.1/                   → Evaluación Heurística (10 principios de Nielsen)
  │   ├── 01_homepage.md        10 hallazgos · 3 críticos
  │   ├── 02_busqueda-filtros.md
  │   ├── 03_detalle-proyecto.md
  │   ├── 04_formulario-contacto.md
  │   ├── 05_inventario-final.md    → 34 hallazgos activos consolidados
  │   ├── 06_reporte-ejecutivo-sintesis.md
  │   ├── H3A.md / H3B.md / H3C.md → Hipótesis (todas confirmadas)
  │   └── arquitectura-informacion/ → Mapas de sitio actual y propuesto
  │
  📁 2.4/                   → Auditoría de Accesibilidad WCAG 2.0
      ├── 01_homepage.md
      ├── 02_busqueda-filtros.md
      ├── 03_detalle-proyecto.md
      ├── 04_formulario-contacto.md
      ├── 05_inventario-final.md    → 46 hallazgos WCAG consolidados
      └── 06_reporte-tarea-2.4.md

📁 research/                → Evidencia y benchmarks de respaldo
📁 assets/                  → Capturas de pantalla organizadas por sección
  ├── home/                 → 17 capturas · Homepage
  ├── filtros/              → 18 capturas · Búsqueda y filtros
  ├── detalle/              → 25 capturas · Detalle de proyecto
  ├── formulario/           → 7 capturas  · Formulario de contacto
  └── misc/                 → Capturas sin clasificar
```

---

## Hallazgos clave

| Fase | Hallazgos | Críticos | Estado |
|------|-----------|----------|--------|
| 2.1 · Evaluación Heurística | 34 activos | 8 | Completado |
| 2.4 · Accesibilidad WCAG | 46 | 19 | Completado |

**Top 3 impacto en conversión:**
1. Sin CTA de contacto en la página de detalle de proyecto (mayor momento de intención)
2. SPA sin feedback de carga — pantalla en blanco en conexiones lentas
3. WhatsApp ausente en homepage y listado — solo disponible dentro del detalle

**Hipótesis confirmadas:**
- H3A — Arquitectura de información fragmenta el flujo de búsqueda
- H3B — CTAs ambiguos o insuficientemente prominentes
- H3C — Experiencia mobile inferior a desktop

---

## Cómo usar este vault

Este repositorio está diseñado para abrirse como vault en **[Obsidian](https://obsidian.md)**.

1. Clona el repositorio
2. Abre Obsidian → "Abrir carpeta como vault" → selecciona la carpeta del repo
3. Empieza por `00_INDEX.md` para navegar todo el contenido

> Los archivos `.md` usan sintaxis Obsidian (wikilinks, callouts, frontmatter YAML). Se ven mejor dentro del vault que directamente en GitHub.

---

## Ramas

| Rama | Descripción |
|------|-------------|
| `main` | Contenido validado y aprobado |
| `F2/obsidian-optimization` | Reorganización del vault para Obsidian |

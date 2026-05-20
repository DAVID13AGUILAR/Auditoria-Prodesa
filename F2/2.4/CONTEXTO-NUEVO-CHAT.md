---
tags:
  - prodesa
  - contexto
  - handoff
aliases:
  - Contexto Chat
  - Handoff 2.4
---

# Contexto para continuar — Revisión de Accesibilidad WCAG 2.0 Prodesa.com

> Copia y pega este documento completo al inicio de una nueva conversación con Claude para retomar el trabajo exactamente donde quedó.

---

## Quién soy y qué estoy haciendo

Soy **Andres**, realizando una **auditoría UX/UI completa de prodesa.com** (constructora colombiana de vivienda). El proyecto vive en la carpeta `/home/andres/Documentos/Auditoria-Prodesa/F2/2.4/` y todos los archivos están en formato `.md` para **Obsidian** (YAML frontmatter + [[wiki links]]).

Esta tarea específica es la **2.4 — Revisión de accesibilidad (WCAG 2.0)**. El objetivo es documentar todos los problemas WCAG que afectan la conversión, con foco en elementos ya identificados en el análisis preliminar (tarea 2.1).

---

## Estructura de archivos

```
F2/2.4/
│
├── 00_plantilla.md              ✅ Completo — referencia WCAG, metodología, escala
├── 01_homepage.md               ⏳ Pendiente — hallazgos homepage
├── 02_busqueda-filtros.md       ⏳ Pendiente — hallazgos búsqueda y filtros
├── 03_detalle-proyecto.md       ⏳ Pendiente — hallazgos detalle de proyecto
├── 04_formulario-contacto.md    ⏳ Pendiente — hallazgos formulario
├── 05_inventario-final.md       ⏳ Pendiente — inventario unificado (se hace al final)
└── CONTEXTO-NUEVO-CHAT.md       ✅ Este archivo
```

---

## Contexto de la tarea (de Notion)

- **Objetivo:** Documentar todos los problemas de accesibilidad que afectan la conversión, con foco en los elementos ya identificados en el análisis preliminar.
- **Alcance:** Revisión con WAVE y validación manual de contraste (color contrast ratio AA), jerarquía de headings, links duplicados y navegación por teclado en páginas del flujo principal.
- **Hipótesis:** H3B — CTAs ambiguos o insuficientemente prominentes
- **Output:** Inventario de problemas WCAG con nivel de conformidad (A / AA), capturas y recomendaciones de corrección. Sección "Accesibilidad" del informe final (tarea 3.2).
- **Fechas:** 2 jun 2026 → 5 jun 2026

---

## Problemas ya identificados en el análisis preliminar (tarea 2.1)

Estos deben confirmarse durante la revisión:

| Elemento | Problema | Criterio WCAG |
|----------|----------|---------------|
| Botón "Buscar vivienda" | Contraste insuficiente | 1.4.3 Contraste (AA) |
| Botón "Realizar Pago" | Contraste insuficiente | 1.4.3 Contraste (AA) |
| Botón "Limpiar Filtros" | Contraste insuficiente (es texto plano, no `<button>`) | 1.4.3 Contraste (AA) |
| Headings | Jerarquía de encabezados incorrecta | 1.3.1 Info y relaciones |
| Links | Links duplicados (H-FILTROS-08: Jilguero) | 2.4.4 Propósito del enlace |

---

## Metodología de trabajo

1. **Ejecutar WAVE** en cada página del flujo → documentar errores (rojo) y alertas (amarillo) relevantes
2. **Medir contraste manualmente** con Colour Contrast Analyser en los elementos críticos identificados
3. **Verificar headings** con `document.querySelectorAll('h1,h2,h3,h4,h5,h6')` en consola
4. **Verificar links duplicados** con alertas "Redundant link" en WAVE
5. **Navegar por teclado** el flujo principal (Tab / Shift+Tab / Enter)
6. **Documentar hallazgos** en el archivo de cada página → al final consolidar en `05_inventario-final.md`

El flujo de trabajo es colaborativo:
- Claude presenta el análisis del hallazgo
- Andres lo valida en el sitio real abriendo prodesa.com
- Si hay discrepancia → se corrige el documento
- Solo entonces se pasa al siguiente hallazgo

**No asumir que lo documentado como "pendiente" es correcto — siempre validar en el sitio.**

---

## Contexto técnico del sitio

- **Prodesa.com es una SPA en React.** Usar DevTools → Elements (no "Ver código fuente") para ver el DOM real.
- **81% del tráfico en Colombia es mobile (Android).** Todo hallazgo debe considerar la experiencia mobile.
- **Mercado colombiano:** VIS = Vivienda Interés Social · VIP = indexado a SMLMV · NO VIS = sin tope.

---

## Contexto del proyecto completo

Esta tarea (2.4) es parte de la **Fase 2 — Análisis** de la auditoría UX/UI de Prodesa. Las otras tareas de la fase son:

- 2.1 — Evaluación heurística (10 principios de Nielsen) → `F2/2.1/` ✅ En progreso
- 2.2 — Cognitive Walkthrough: Flujo 1 — Búsqueda y filtrado
- 2.3 — Cognitive Walkthrough: Flujo 2 — Registro y contacto
- **2.4 — Revisión de accesibilidad (WCAG 2.0)** ← aquí
- 2.5 — Análisis de rendimiento (PageSpeed + GTmetrix)

---

## Qué hacer en el nuevo chat — orden sugerido

1. Leer este archivo y `00_plantilla.md`
2. Empezar por `01_homepage.md` — ejecutar WAVE y documentar hallazgos página por página
3. Luego `02_busqueda-filtros.md`, `03_detalle-proyecto.md`, `04_formulario-contacto.md`
4. Al finalizar todas las páginas → actualizar `05_inventario-final.md`

---

## Instrucción para Claude

Eres un **especialista en accesibilidad web** que me está ayudando a revisar prodesa.com contra los criterios WCAG 2.0. Conoces todo el contexto de este documento. El trabajo es colaborativo: tú propones el análisis de cada criterio a verificar, yo lo valido en el sitio real con WAVE y DevTools, y juntos documentamos solo lo que está confirmado. **Nunca asumir que un hallazgo existe sin validación en el sitio real.**

Comenzamos con `01_homepage.md`.

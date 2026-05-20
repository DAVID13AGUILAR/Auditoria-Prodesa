---
tags:
  - prodesa
  - evaluacion-heuristica
  - hipotesis
  - arquitectura-informacion
  - confirmada
aliases:
  - Hipótesis H3A
  - H3A Arquitectura
---

# H3A — Arquitectura de Información

**Hipótesis:** Los problemas en la arquitectura de información y navegación afectan la capacidad del usuario de encontrar el proyecto correcto, reduciendo la conversión.

**Estado:** ✅ **Confirmada** — 13 hallazgos activos la respaldan (H-FILTROS-04 y H-DETALLE-04 eliminados tras validación)

---

## Hallazgos que confirman H3A

| Sección | Hallazgos |
|---------|-----------|
| [[01_homepage]] | [[01_homepage#H-HOME-02\|H-HOME-02]] (doble nav mezcla audiencias), [[01_homepage#H-HOME-03\|H-HOME-03]] ("Invertir desde el exterior" en mismo nivel), [[01_homepage#H-HOME-04\|H-HOME-04]] (VIS/VIP sin definición — el usuario no puede self-qualificarse), [[01_homepage#H-HOME-07\|H-HOME-07]] (sin breadcrumbs en ninguna página) |
| [[02_busqueda-filtros]] | [[02_busqueda-filtros#H-FILTROS-01\|H-FILTROS-01]] (sin contador de resultados — el usuario no sabe en qué estado está la búsqueda), [[02_busqueda-filtros#H-FILTROS-02\|H-FILTROS-02]] (VIS/NO VIS sin tooltip — vocabulario opaco en el punto de búsqueda activa), [[02_busqueda-filtros#H-FILTROS-03\|H-FILTROS-03]] ("Limpiar filtros" reinicia a defaults, no limpia), [[02_busqueda-filtros#H-FILTROS-05\|H-FILTROS-05]] (empty state invisible), [[02_busqueda-filtros#H-FILTROS-07\|H-FILTROS-07]] (filtro VIS/NO VIS ausente en web, defaults invisibles) |
| [[03_detalle-proyecto]] | [[03_detalle-proyecto#H-DETALLE-06\|H-DETALLE-06]] (sin plantilla estandarizada — validado en Pietra vs. Orizzo), [[03_detalle-proyecto#H-DETALLE-07\|H-DETALLE-07]] (filtros se pierden al volver al listado), [[03_detalle-proyecto#H-DETALLE-09\|H-DETALLE-09]] ("subsidio disponible" sin contexto) |
| [[04_formulario-contacto]] | [[04_formulario-contacto#H-FORM-07\|H-FORM-07]] (formulario no transmite proyecto al CRM) |

*H-FILTROS-04 y H-DETALLE-04 eliminados tras validación — las URLs son consistentes y los redirects son comportamiento correcto.*

---

## Análisis profundo de Arquitectura de Información

→ [[01_por-que-importa-la-ai]]
→ [[02_mapa-sitio-actual]]
→ [[03_mapa-sitio-propuesto]]

---

## Tres problemas estructurales clave

1. **Múltiples audiencias sin separación** — Compradores, clientes, proveedores y administradores comparten el mismo menú sin jerarquía (confirmado en [[01_homepage#H-HOME-02|H-HOME-02]] y [[01_homepage#H-HOME-03|H-HOME-03]])
2. **Taxonomía que no coincide con el modelo mental del usuario** — El usuario piensa en ciudad → presupuesto, el sitio está organizado por tipo de proyecto. Los filtros tienen defaults invisibles y "Limpiar" no limpia ([[02_busqueda-filtros#H-FILTROS-03|H-FILTROS-03]])
3. **Sin sistemas de orientación** — Sin breadcrumbs, sin estado activo en el menú, sin proyectos relacionados en todos los proyectos ([[01_homepage#H-HOME-07|H-HOME-07]], [[03_detalle-proyecto#H-DETALLE-06|H-DETALLE-06]])
4. **Pérdida de contexto al navegar** — Los filtros se pierden al volver al listado ([[03_detalle-proyecto#H-DETALLE-07|H-DETALLE-07]]) y el formulario no transmite el proyecto de origen al CRM ([[04_formulario-contacto#H-FORM-07|H-FORM-07]])

---

## Relación con otras hipótesis

- [[H3B]] — Los CTAs ambiguos son en parte consecuencia de la mala AI: el usuario no llega al CTA correcto
- [[H3C]] — La experiencia mobile sufre más los problemas de navegación y orientación

---

## Ver en contexto global

→ [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

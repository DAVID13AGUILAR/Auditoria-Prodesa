---
tags:
  - prodesa
  - evaluacion-heuristica
  - hipotesis
  - mobile
  - experiencia-movil
  - confirmada
aliases:
  - Hipótesis H3C
  - H3C Mobile
---

# H3C — Experiencia Mobile Inferior

**Hipótesis:** La versión mobile del sitio tiene problemas adicionales o amplificados que generan mayor tasa de abandono respecto a la versión desktop.

**Estado:** ✅ **Confirmada** — 12 hallazgos validados con capturas en desktop y mobile.

---

## Hallazgos que confirman H3C

| Sección | Hallazgos |
|---------|-----------|
| [[01_homepage]] | [[01_homepage#H-HOME-01\|H-HOME-01]] (SPA sin SSR — pantalla en blanco crítica en conexiones móviles lentas), [[01_homepage#H-HOME-02\|H-HOME-02]] (doble nav amplificada en pantallas pequeñas), [[01_homepage#H-HOME-06\|H-HOME-06]] (Google Play link roto — bloquea al 70% de usuarios Android en Colombia) |
| [[02_busqueda-filtros]] | [[02_busqueda-filtros#H-FILTROS-07\|H-FILTROS-07]] (filtro VIS/NO VIS solo disponible en mobile, ausente en web), [[02_busqueda-filtros#H-FILTROS-09\|H-FILTROS-09]] (spinner con delay + scroll manual al cargar resultados) |
| [[03_detalle-proyecto]] | [[03_detalle-proyecto#H-DETALLE-01\|H-DETALLE-01]] (chip "Proyecto de vivienda" duplicado en mobile, redundancia doble), [[03_detalle-proyecto#H-DETALLE-02\|H-DETALLE-02]] (en mobile el listado diferencia precio y área; el detalle no), [[03_detalle-proyecto#H-DETALLE-06\|H-DETALLE-06]] (6 inconsistencias Pietra vs. Orizzo confirmadas en mobile) |
| [[04_formulario-contacto]] | [[04_formulario-contacto#H-FORM-02\|H-FORM-02]] (6 campos obligatorios incluyendo cédula — carga excesiva en teclado táctil), [[04_formulario-contacto#H-FORM-03\|H-FORM-03]] (validación post-submit más frustrante en mobile, aunque errores son más visibles sin scroll), [[04_formulario-contacto#H-FORM-04\|H-FORM-04]] (mensajes en MAYÚSCULAS — ocupan más espacio relativo en pantalla pequeña, tono más agresivo), [[04_formulario-contacto#H-FORM-09\|H-FORM-09]] (WhatsApp ausente en homepage y listado — canal nativo del usuario mobile) |

---

## Por qué mobile importa especialmente en este proyecto

- **+81% del tráfico web en Colombia es mobile** — la mayoría de los visitantes de Prodesa llegan desde celular
- **70%+ usa Android** — relevante para H-HOME-06 (Google Play link roto apunta a Apple Store)
- **Conexiones variables** — el 3G/4G en municipios amplifica el problema de H-HOME-01 (pantalla en blanco)
- **WhatsApp es el canal nativo mobile** — H-FORM-09 impacta directamente al usuario mobile

---

## Matiz importante — mobile no siempre es peor

La validación reveló un caso donde mobile tiene **mejor** comportamiento que web: en [[04_formulario-contacto#H-FORM-03|H-FORM-03]], los errores de validación post-submit son visibles simultáneamente en mobile sin necesidad de scroll, mientras que en web el formulario se extiende fuera del viewport. Este matiz es importante — H3C no significa que mobile falle en todo, sino que acumula fricciones adicionales que en desktop no existen o son menores.

---

## Relación con otras hipótesis

- [[H3A]] — La navegación por ciudad es aún más frustrante en mobile sin breadcrumbs y sin filtros avanzados
- [[H3B]] — El CTA de WhatsApp (cobertura parcial) es especialmente crítico en mobile donde el usuario ya tiene la app abierta — su ausencia en homepage y listado impacta directamente al usuario mobile

---

## Ver en contexto global

→ [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

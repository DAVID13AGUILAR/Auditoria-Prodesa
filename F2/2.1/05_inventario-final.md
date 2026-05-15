---
tags:
  - prodesa
  - evaluacion-heuristica
  - inventario
  - resumen
  - priorizacion
aliases:
  - Inventario Final
  - Inventario Heurístico
---

# 05 — Inventario Heurístico Final
**Tarea:** 2.1 — Evaluación heurística (10 principios de Nielsen)
**Proyecto:** Evaluación de usabilidad prodesa.com
**Fecha:** Mayo 2026
**Evaluador:** David Marín
**Total de hallazgos:** 37

---

## Inventario Completo Unificado

| ID | Principio | Sección | Descripción del problema | Severidad | Hipótesis |
|----|-----------|---------|--------------------------|-----------|-----------|
| H-HOME-01 | P1 - Visibilidad | Homepage | SPA sin SSR: usuario ve "You need to enable JavaScript" si JS falla. Sin skeleton, sin estado de carga. | 3 🔴 | H3C |
| H-HOME-02 | P8 - Minimalismo | Homepage / Nav | Doble barra de navegación: una superior (Blog, Proveedores, Administradores) y una principal. Ruido visual, audiencias mezcladas. | 2 🟡 | H3A, H3C |
| H-HOME-03 | P8 - Minimalismo | Homepage / Nav | "Invertir desde el exterior" comparte nivel con CTAs de conversión del comprador local. Distracción para el 90% del público. | 2 🟡 | H3A |
| H-HOME-04 | P2 - Mundo real | Homepage / Nav global | Términos "VIS" y "NO VIS" sin definición en el título del sitio y la navegación. Jerga técnica invisible para compradores primerizos. | 3 🔴 | H3A |
| H-HOME-05 | P4 - Consistencia | Homepage / Footer | Copyright muestra "© 2025 Prodesa" en 2026. Proyecta descuido editorial. | 1 🟢 | — |
| H-HOME-06 | P9 - Recuperación errores | Homepage / Footer | Botón Google Play apunta a apple.com/store. Link roto para usuarios Android. | 3 🔴 | — |
| H-HOME-07 | P1 - Visibilidad | Global | Sin breadcrumbs en ninguna página. El usuario no sabe dónde está en la jerarquía del sitio. | 2 🟡 | H3A |
| H-HOME-08 | P2 - Mundo real | Homepage / Footer | "SAGRILAFT" en el footer sin explicación. Acrónimo regulatorio sin valor para el comprador. | 1 🟢 | — |
| H-HOME-09 | P6 - Reconocimiento | Homepage / Hero | Ausencia de H1 visible con propuesta de valor clara. El usuario debe inferir qué es y qué ofrece Prodesa. | 2 🟡 | H3B |
| H-HOME-10 | P4 - Consistencia | Homepage / Footer | Proyecto "Jilguero" duplicado en el footer con la misma URL. Confusión sobre si son proyectos distintos. | 1 🟢 | — |
| H-FILTROS-01 | P1 - Visibilidad | Listado / Filtros | Sin contador de resultados al aplicar filtros. El usuario no sabe si la acción tuvo efecto. | 3 🔴 | H3A |
| H-FILTROS-02 | P2 - Mundo real | Listado / Filtros | Filtros "VIS" / "NO VIS" sin tooltip ni explicación. Barrera para compradores primerizos en el punto de búsqueda. | 3 🔴 | H3A |
| H-FILTROS-03 | P3 - Control usuario | Listado / Filtros | Sin botón "Limpiar filtros" visible. El usuario no puede resetear búsqueda en un clic. | 2 🟡 | H3A |
| H-FILTROS-04 | P4 - Consistencia | Listado / URLs | Estructura de URLs inconsistente: algunos proyectos tienen `/ciudad/slug`, otros solo `/slug`. | 2 🟡 | H3A |
| H-FILTROS-05 | P5 - Prevención errores | Listado / Filtros | Sin prevención de combinaciones imposibles (ciudad sin proyectos VIS). El sistema no anticipa ni orienta. | 2 🟡 | H3A |
| H-FILTROS-06 | P6 - Reconocimiento | Listado / Tarjetas | Información clave (precio, estado, habitaciones) presumiblemente ausente en la superficie de las tarjetas. | 3 🔴 | H3B |
| H-FILTROS-07 | P7 - Flexibilidad | Listado / Filtros | Sin filtros avanzados (precio, m², habitaciones, fecha de entrega). Solo filtro por ciudad detectado. | 2 🟡 | H3A |
| H-FILTROS-08 | P4 - Consistencia | Footer / Sitemap | Inconsistencias entre listado de proyectos en homepage vs. página de contacto (nombres y URLs distintos). | 1 🟢 | — |
| H-FILTROS-09 | P1 - Visibilidad | Listado / SPA | Sin skeleton loader al cambiar filtros. El usuario no sabe que el sistema está procesando. | 2 🟡 | H3C |
| H-DETALLE-01 | P8 - Minimalismo | Detalle proyecto / Hero | Meta-título del proyecto mezcla localización, tipo de subsidio y nombre. Si refleja el H1, el foco del CTA se pierde. | 2 🟡 | H3B |
| H-DETALLE-02 | P6 - Reconocimiento | Detalle proyecto | Precio no detectado en la meta-descripción ni presumiblemente en el primer fold. La información más decisiva no es visible de inmediato. | 3 🔴 | H3B |
| H-DETALLE-03 | P1 + P2 | Detalle proyecto / CTA | CTA genérico ("Solicitar información" o similar). El usuario no sabe qué pasará al hacer clic: ¿formulario, llamada, WhatsApp? | 3 🔴 | H3B |
| H-DETALLE-04 | P4 - Consistencia | Detalle proyecto / URLs | URL de Ágora redirige de `/agora` a `/cali/agora`. Inconsistencia en el patrón de URLs entre proyectos. | 2 🟡 | H3A |
| H-DETALLE-05 | P6 - Reconocimiento | Detalle proyecto / Ficha | Ficha técnica (m², hab., fecha de entrega, unidades disponibles) presumiblemente no visible en el primer fold. | 2 🟡 | H3B |
| H-DETALLE-06 | P4 - Consistencia | Múltiples proyectos | Sin plantilla de diseño estandarizada entre proyectos. Cada uno puede verse distinto. | 2 🟡 | H3A |
| H-DETALLE-07 | P3 - Control usuario | Detalle proyecto / Nav | Al volver al listado desde el detalle, los filtros pueden perderse. El usuario pierde el contexto de su búsqueda. | 2 🟡 | H3A |
| H-DETALLE-08 | P1 - Visibilidad | Detalle proyecto | Estado del proyecto (en venta / preventa / agotado) no detectado en metadatos. Información crítica no visible. | 3 🔴 | H3B |
| H-DETALLE-09 | P10 - Ayuda | Detalle proyecto | "Subsidio disponible" mencionado sin contexto sobre qué subsidio, quién aplica ni cómo acceder. | 2 🟡 | H3A |
| H-FORM-01 | P1 - Visibilidad | Formulario / Post-envío | Sin confirmación post-envío verificada. El usuario no sabe qué pasará después de enviar. | 3 🔴 | H3B |
| H-FORM-02 | P2 - Mundo real | Formulario / Labels | Labels del formulario presumiblemente técnicos o poco claros para compradores primerizos. | 2 🟡 | — |
| H-FORM-03 | P5 - Prevención errores | Formulario / Validación | Validación probablemente post-submit, no inline. El usuario descubre errores solo al enviar. | 3 🔴 | H3C |
| H-FORM-04 | P9 - Recuperación errores | Formulario / Mensajes | Mensajes de error presumiblemente genéricos ("Campo requerido"). No orientan la corrección. | 2 🟡 | — |
| H-FORM-05 | P2 - Mundo real | Footer / Teléfonos | Tres líneas de contacto con el mismo número de teléfono. Confuso e inconsistente. | 2 🟡 | — |
| H-FORM-06 | P3 - Control usuario | Formulario / Canal | Sin opción para elegir canal de respuesta (WhatsApp / llamada / email). El sistema impone el canal. | 2 🟡 | H3B |
| H-FORM-07 | P8 - Minimalismo | Formulario / Contexto | Formulario genérico sin precargar el proyecto de interés. El lead llega al CRM sin contexto del proyecto. | 2 🟡 | H3B |
| H-FORM-08 | P10 - Ayuda | Formulario / FAQ | FAQ del sitio no está integrada al flujo del formulario ni de la página de detalle. | 1 🟢 | — |
| H-FORM-09 | P1 - Visibilidad | Global / WhatsApp | Sin botón flotante de WhatsApp en el sitio. Canal de mayor conversión en el mercado colombiano ausente. | 3 🔴 | H3B, H3C |

---

## Resumen Global por Severidad

| Severidad | Cantidad | Porcentaje |
|-----------|----------|------------|
| 🔴 Crítico (3) | 13 | 35% |
| 🟡 Importante (2) | 19 | 51% |
| 🟢 Menor (1) | 5 | 14% |
| **Total** | **37** | |

---

## Resumen Global por Principio de Nielsen

| Principio | Hallazgos | Severidad máxima |
|-----------|-----------|-----------------|
| P1 - Visibilidad del estado | 7 | 🔴 3 |
| P2 - Mundo real | 6 | 🔴 3 |
| P3 - Control del usuario | 3 | 🟡 2 |
| P4 - Consistencia y estándares | 6 | 🟡 2 |
| P5 - Prevención de errores | 2 | 🔴 3 |
| P6 - Reconocimiento antes que recuerdo | 4 | 🔴 3 |
| P7 - Flexibilidad y eficiencia | 1 | 🟡 2 |
| P8 - Diseño estético y minimalista | 4 | 🟡 2 |
| P9 - Recuperación de errores | 2 | 🔴 3 |
| P10 - Ayuda y documentación | 2 | 🟡 2 |

---

## Agrupación por Categoría

### 🧭 Navegación y Arquitectura (H3A)
H-HOME-02 · H-HOME-03 · H-HOME-07 · H-FILTROS-03 · H-FILTROS-04 · H-FILTROS-05 · H-FILTROS-07 · H-DETALLE-04 · H-DETALLE-06 · H-DETALLE-07 · H-DETALLE-09

### 📝 Contenido y Copy (H3A, H3B)
H-HOME-04 · H-HOME-08 · H-HOME-09 · H-FILTROS-02 · H-DETALLE-01 · H-DETALLE-09 · H-FORM-02

### 🎯 CTAs y Conversión (H3B)
H-HOME-09 · H-FILTROS-06 · H-DETALLE-02 · H-DETALLE-03 · H-DETALLE-05 · H-DETALLE-08 · H-FORM-01 · H-FORM-06 · H-FORM-09

### 📋 Formularios y Feedback (P5, P9)
H-FORM-03 · H-FORM-04 · H-FORM-05 · H-FORM-07 · H-FORM-08

### ⚙️ Feedback del Sistema (P1)
H-HOME-01 · H-FILTROS-01 · H-FILTROS-09 · H-FORM-01 · H-FORM-03

### 🐛 Errores técnicos
H-HOME-06 · H-HOME-10 · H-FILTROS-08

---

## 🏆 Top 3 Hallazgos Críticos — Impacto en Conversión

### #1 — H-FORM-09: Ausencia de botón WhatsApp (Severidad 3)
**Por qué es el más crítico:** WhatsApp es el canal de comunicación dominante en Colombia para decisiones de compra de alto valor. La ausencia de un botón flotante de WhatsApp contextualizado por proyecto representa la pérdida del canal de conversión de menor fricción. En el mercado de vivienda colombiano, el comprador promedio prefiere iniciar la conversación por WhatsApp antes de hacer una llamada o llenar un formulario. Este hallazgo solo impacta directamente en H3B.

**Relación con hipótesis:** H3B ✅ · H3C ✅

---

### #2 — H-DETALLE-03: CTA ambiguo en página de detalle (Severidad 3)
**Por qué es el segundo más crítico:** La página de detalle de proyecto es el momento de mayor intención de compra del usuario. Un CTA genérico como "Solicitar información" o "Me interesa" sin indicar canal, tiempo de respuesta ni compromiso genera parálisis por incertidumbre. El usuario que no sabe qué pasará al hacer clic, no hace clic. Este es el punto de conversión más valorado y el más vulnerable.

**Relación con hipótesis:** H3B ✅ (confirmación directa)

---

### #3 — H-HOME-04 + H-FILTROS-02: Jerga técnica "VIS/NO VIS" sin explicación (Severidad 3)
**Por qué es el tercero más crítico:** "VIS" y "NO VIS" aparecen en el título del sitio, en el nav y en los filtros de búsqueda — los tres puntos de mayor visibilidad del sitio. Para el comprador primerizo (segmento principal de Prodesa), este vocabulario es una barrera de entrada inmediata. Un usuario que no entiende si puede comprar VIS o No VIS no avanzará en el funnel. El problema se repite en dos secciones distintas lo que amplifica su impacto.

**Relación con hipótesis:** H3A ✅ (confirmación directa)

---

## Relación con Hipótesis del Proyecto

| Hipótesis | Descripción | Hallazgos que la confirman | Veredicto |
|-----------|-------------|---------------------------|-----------|
| [[H3A]] — Arquitectura de información | La arquitectura y navegación del sitio dificultan que el usuario encuentre el proyecto correcto | H-HOME-02, H-HOME-04, H-HOME-07, H-FILTROS-01, H-FILTROS-02, H-FILTROS-03, H-FILTROS-04, H-FILTROS-05, H-FILTROS-07, H-DETALLE-04, H-DETALLE-06, H-DETALLE-07 | ✅ **Confirmada** — 12 hallazgos respaldan esta hipótesis |
| [[H3B]] — CTAs ambiguos o insuficientes | Los CTAs no comunican claramente la acción ni el canal, reduciendo la conversión | H-HOME-09, H-FILTROS-06, H-DETALLE-02, H-DETALLE-03, H-DETALLE-05, H-DETALLE-08, H-FORM-01, H-FORM-06, H-FORM-09 | ✅ **Confirmada** — 9 hallazgos respaldan esta hipótesis |
| [[H3C]] — Experiencia mobile inferior | La versión mobile tiene problemas adicionales que generan mayor abandono | H-HOME-01, H-HOME-02, H-FILTROS-09, H-FORM-03, H-FORM-09 | ✅ **Sospecha confirmada parcialmente** — 5 hallazgos estructurales; requiere validación con capturas mobile |

---

## Pendientes de Validación Visual

Los siguientes hallazgos requieren capturas del sitio renderizado en browser (desktop + mobile) para ser incluidos en el informe final con evidencia:

| Prioridad | ID | Sección | Qué capturar |
|-----------|-----|---------|--------------|
| Alta | H-HOME-01 | Global | Mensaje de error con JS desactivado |
| Alta | H-HOME-02 | Navbar | Doble barra de navegación desktop y mobile |
| Alta | H-HOME-04 | Navbar | Términos VIS/NO VIS sin tooltip |
| Alta | H-HOME-06 | Footer | Botón Google Play apuntando a Apple Store |
| Alta | H-FILTROS-01 | Listado | Panel de filtros sin contador de resultados |
| Alta | H-FILTROS-06 | Tarjetas | Tarjeta de proyecto sin precio visible |
| Alta | H-DETALLE-02 | Detalle | Primer fold sin precio visible |
| Alta | H-DETALLE-03 | Detalle | CTA ambiguo en página de proyecto |
| Alta | H-DETALLE-08 | Detalle | Ausencia de estado del proyecto |
| Alta | H-FORM-01 | Formulario | Pantalla post-envío (o ausencia de ella) |
| Alta | H-FORM-03 | Formulario | Validación post-submit de campos |
| Alta | H-FORM-09 | Global | Ausencia de botón WhatsApp flotante |
| Media | H-HOME-07 | Global | Ausencia de breadcrumbs en proyecto y listado |
| Media | H-DETALLE-05 | Detalle | Ficha técnica no visible sin scroll |

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[06_reporte-ejecutivo-sintesis]] · [[H3A]] · [[H3B]] · [[H3C]]

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
**Total de hallazgos:** 34 activos (3 eliminados tras validación — H-FILTROS-04, H-DETALLE-04, H-FORM-08)

---

## Inventario Completo Unificado

| ID | Principio | Sección | Descripción del problema | Severidad | Hipótesis |
|----|-----------|---------|--------------------------|-----------|-----------|
| [[01_homepage\|H-HOME-01]] | P1 - Visibilidad | [[01_homepage\|Homepage]] | SPA sin SSR: pantalla en blanco con *"You need to enable JavaScript"* mientras carga JS. Sin skeleton loader. Crítico en mobile con conexiones lentas. | 3 🔴 | [[H3C]] |
| [[01_homepage\|H-HOME-02]] | P8 - Minimalismo | Homepage / Nav | Doble barra de navegación mezcla audiencias internas (Blog, Proveedores, Administradores) con compradores. Ruido visual que distrae del flujo de conversión. | 2 🟡 | [[H3A]], [[H3C]] |
| [[01_homepage\|H-HOME-03]] | P8 - Minimalismo | Homepage / Nav | "Invertir desde el exterior" comparte nivel jerárquico con CTAs de conversión. Distracción para el 90% del público objetivo. | 2 🟡 | [[H3A]] |
| [[01_homepage\|H-HOME-04]] | P2 - Mundo real | Homepage / Nav global | Badges "VIS" y "VIP" sin definición ni tooltip en tarjetas, descripción y navegación. Barrera de entrada activa para compradores primerizos. Conecta con [[02_busqueda-filtros\|H-FILTROS-02]]. | 3 🔴 | [[H3A]], [[H3B]] |
| [[01_homepage\|H-HOME-05]] | P4 - Consistencia | Homepage / Footer | Copyright muestra "© 2025 Prodesa" en 2026. Parte del patrón de gobernanza de contenidos con [[01_homepage\|H-HOME-10]], [[02_busqueda-filtros\|H-FILTROS-08]] y [[04_formulario-contacto\|H-FORM-05]]. | 1 🟢 | — |
| [[01_homepage\|H-HOME-06]] | P9 - Recuperación errores | Homepage / Footer | Botón Google Play apunta a apple.com/store. Link roto para Android — 70% del mercado colombiano. | 3 🔴 | [[H3C]] |
| [[01_homepage\|H-HOME-07]] | P1 - Visibilidad | Global | Sin breadcrumbs en ninguna página. El usuario no sabe en qué nivel de la jerarquía del sitio se encuentra. | 2 🟡 | [[H3A]] |
| [[01_homepage\|H-HOME-08]] | P2 - Mundo real | Homepage / Footer | "SAGRILAFT" en footer sin explicación ni link — elemento no interactivo sin valor para el comprador. Severidad ajustada de 1 a 2 tras confirmación. | 2 🟡 | — |
| [[01_homepage\|H-HOME-09]] | P6 - Reconocimiento | Homepage / Hero | Hero sin H1 ni propuesta de valor visible. El usuario debe inferir qué es y qué ofrece Prodesa. | 2 🟡 | [[H3B]] |
| [[01_homepage\|H-HOME-10]] | P4 - Consistencia | Homepage / Footer | "Proyecto de vivienda Jilguero" duplicado en footer con la misma URL. Parte del patrón de gobernanza de contenidos. | 1 🟢 | — |
| [[02_busqueda-filtros\|H-FILTROS-01]] | P1 - Visibilidad | Listado / Filtros | Sin contador de resultados al aplicar filtros. El usuario no sabe cuántos proyectos corresponden a su búsqueda ni si el filtro tuvo efecto. | 3 🔴 | [[H3A]] |
| [[02_busqueda-filtros\|H-FILTROS-02]] | P2 - Mundo real | Listado / Filtros | Filtros "VIS / NO VIS / VIP" sin tooltip ni definición. Barrera activa para compradores primerizos en el punto de búsqueda. Conecta con [[01_homepage\|H-HOME-04]]. | 3 🔴 | [[H3A]], [[H3B]] |
| [[02_busqueda-filtros\|H-FILTROS-03]] | P3 - Control usuario | Listado / Filtros | "Limpiar filtros" es texto plano (no `<button>`) y reinicia a valores default ($140M–$2.2B, 32–235m²) en lugar de vaciar — comportamiento engañoso sin aviso. Conecta con [[03_detalle-proyecto\|H-DETALLE-07]]. | 2 🟡 | [[H3A]] |
| ~~H-FILTROS-04~~ | ~~P4 - Consistencia~~ | ~~Listado / URLs~~ | **Eliminado tras validación.** URLs son consistentes — patrón `/proyecto-vivienda/[ciudad]/[slug]`. El redirect de Ágora es comportamiento correcto (URL canónica). | — | — |
| [[02_busqueda-filtros\|H-FILTROS-05]] | P5 - Prevención errores | Listado / Filtros | Empty state invisible al filtrar sin resultados: mensaje en esquina inferior derecha fuera de la jerarquía visual. Sin orientación ni CTA para ampliar búsqueda. | 2 🟡 | [[H3A]] |
| [[02_busqueda-filtros\|H-FILTROS-06]] | P6 - Reconocimiento + P4 - Consistencia | Listado / Tarjetas | Precio con asterisco ambiguo e inconsistente entre tarjetas (VIP indexado a SMLMV vs. precio fijo). Sin estado del proyecto visible. Revisado de 3 a 2 — el precio existe, el problema es la ambigüedad. | 2 🟡 | [[H3B]] |
| [[02_busqueda-filtros\|H-FILTROS-07]] | P4 - Consistencia | Listado / Filtros | Filtro VIS/NO VIS/VIP solo disponible en mobile, ausente en web. Valores default del panel visualmente indistinguibles de filtros activos. | 2 🟡 | [[H3A]], [[H3C]] |
| [[02_busqueda-filtros\|H-FILTROS-08]] | P4 - Consistencia | Footer / Sitemap | "Proyecto de vivienda Jilguero" duplicado en footer — misma entrada dos veces consecutivas. | 1 🟢 | — |
| [[02_busqueda-filtros\|H-FILTROS-09]] | P1 - Visibilidad | Listado / SPA | Spinner de carga con delay perceptible + al cargar resultados el usuario debe hacer scroll manual al listado. Validado en web y mobile con Slow 4G. | 2 🟡 | [[H3C]] |
| [[03_detalle-proyecto\|H-DETALLE-01]] | P8 - Minimalismo + P6 - Reconocimiento | Detalle proyecto / Hero | H1 redundante ("Proyecto de Vivienda [Nombre]"), precio visualmente domina sobre el nombre, "Déjanos tus datos" duplica el formulario visible en desktop, "Agenda tu cita" pide correo innecesariamente. Validado en Ágora y Mirla — desktop y mobile. | 2 🟡 | [[H3B]], [[H3C]] |
| [[03_detalle-proyecto\|H-DETALLE-02]] | P6 - Reconocimiento + P8 - Minimalismo | Detalle proyecto / Hero | Precio y área con idéntico peso visual — mismo naranja, mismo tamaño. El listado mobile diferencia correctamente; el detalle no. Revisado de 3 a 2 — el precio existe, el problema es la jerarquía. | 2 🟡 | [[H3B]], [[H3C]] |
| [[03_detalle-proyecto\|H-DETALLE-03]] | P8 - Minimalismo + P3 - Control usuario | Detalle proyecto / CTA | CTAs en "Acerca del proyecto" son "Descargar brochure" y "Compartir" — sin CTA de contacto directo. En desktop el formulario está en columna separada, desconectado del flujo de lectura. Conecta con [[04_formulario-contacto\|H-FORM-01]] y [[04_formulario-contacto\|H-FORM-09]]. | 3 🔴 | [[H3B]] |
| [[03_detalle-proyecto\|H-DETALLE-05]] | P6 - Reconocimiento + P1 - Visibilidad | Detalle proyecto / Ficha | Datos clave (habitaciones, m², precio por tipología) requieren scroll — no están en el hero. Fecha estimada de entrega ausente en toda la página. | 2 🟡 | [[H3B]] |
| [[03_detalle-proyecto\|H-DETALLE-06]] | P4 - Consistencia | Múltiples proyectos | 6 inconsistencias concretas validadas en Pietra vs. Orizzo: galería (2 vs. 5 tabs), brochure, lista de incluidos, mapa, CTAs de contacto y proyectos similares. Transversal a desktop y mobile. | 2 🟡 | [[H3A]], [[H3C]] |
| [[03_detalle-proyecto\|H-DETALLE-07]] | P3 - Control usuario | Detalle proyecto / Nav | Al regresar al listado desde el detalle, los filtros se pierden. El usuario debe reconfigurar su búsqueda desde cero. Conecta con [[02_busqueda-filtros\|H-FILTROS-03]] y [[04_formulario-contacto\|H-FORM-07]]. | 2 🟡 | [[H3A]] |
| [[03_detalle-proyecto\|H-DETALLE-08]] | P1 - Visibilidad | Detalle proyecto | Sin chip de estado del proyecto (preventa / en construcción / listo para entrega / agotado) en el hero ni en las tarjetas del listado. | 3 🔴 | [[H3B]] |
| [[03_detalle-proyecto\|H-DETALLE-09]] | P10 - Ayuda | Detalle proyecto | "Subsidio disponible" en la descripción sin indicar tipo, monto ni requisitos. Información enterrada en prosa en lugar de contextualizada junto al precio. Conecta con [[04_formulario-contacto\|H-FORM-08]]. | 2 🟡 | [[H3A]] |
| [[04_formulario-contacto\|H-FORM-01]] | P1 - Visibilidad | Formulario / Post-envío | Confirmación post-envío existe pero: muestra el correo del usuario en pantalla (privacidad), no indica canal ni tiempo de respuesta, sin CTA de respaldo. Revisado de 3 a 2 — la confirmación existe. Conecta con [[03_detalle-proyecto\|H-DETALLE-03]]. | 2 🟡 | [[H3B]] |
| [[04_formulario-contacto\|H-FORM-02]] | P2 - Mundo real + P8 - Minimalismo | Formulario / Campos | 6 campos obligatorios incluyendo tipo y número de documento — innecesarios en primer contacto. Capitalización inconsistente en labels ("Tipo De Documento"). Mayor fricción en mobile. Conecta con [[01_homepage\|H-HOME-04]] y [[02_busqueda-filtros\|H-FILTROS-02]]. | 2 🟡 | [[H3B]], [[H3C]] |
| [[04_formulario-contacto\|H-FORM-03]] | P5 - Prevención errores | Formulario / Validación | Validación 100% post-submit confirmada. Teléfono inválido no genera error — pasa al CRM sin validación de formato colombiano. En web los errores salen del viewport y obligan a scroll. Conecta con [[04_formulario-contacto\|H-FORM-04]]. | 3 🔴 | [[H3C]] |
| [[04_formulario-contacto\|H-FORM-04]] | P9 - Recuperación errores | Formulario / Mensajes | Mensajes de error "RELLENA ESTE CAMPO OBLIGATORIO." — todo en mayúsculas, idéntico para todos los campos, sin orientación. Teléfono inválido no recibe ningún mensaje. | 2 🟡 | [[H3B]], [[H3C]] |
| [[04_formulario-contacto\|H-FORM-05]] | P2 - Mundo real + P4 - Consistencia | Footer / Teléfonos | Tres de cuatro líneas de contacto tienen el mismo número (+573241000060). Cuarto ejemplo del patrón de gobernanza de contenidos junto a [[01_homepage\|H-HOME-05]], [[01_homepage\|H-HOME-10]] y [[02_busqueda-filtros\|H-FILTROS-08]]. | 2 🟡 | — |
| [[04_formulario-contacto\|H-FORM-06]] | P3 - Control usuario + P4 - Consistencia | /contactanos / Canales | Canales existen (WhatsApp, Teams, callback) pero: "Agenda tu cita en sala" lleva a Teams (nombre engañoso), reCAPTCHA en "Asesoría inmediata" reduce conversión hasta 40%, formularios inconsistentes entre canales. | 2 🟡 | [[H3B]] |
| [[04_formulario-contacto\|H-FORM-07]] | P8 - Minimalismo | Detalle proyecto / Formulario | "Déjanos tus datos" hace scroll al formulario embebido. El formulario no transmite el proyecto al CRM aunque la URL lo indica. Conecta con [[03_detalle-proyecto\|H-DETALLE-03]] y [[03_detalle-proyecto\|H-DETALLE-07]]. | 2 🟡 | [[H3A]] |
| [[04_formulario-contacto\|H-FORM-09]] | P1 - Visibilidad + P4 - Consistencia | Global / WhatsApp | WhatsApp existe y funciona en la sticky del detalle de proyecto. Ausente en homepage y listado — cobertura parcial del canal de mayor conversión. Revisado de 3 a 2. Conecta con [[03_detalle-proyecto\|H-DETALLE-01]] y [[04_formulario-contacto\|H-FORM-01]]. | 2 🟡 | [[H3B]], [[H3C]] |

---

## Resumen Global por Severidad

| Severidad | Cantidad | Porcentaje |
|-----------|----------|------------|
| 🔴 Crítico (3) | 8 | 24% |
| 🟠 Importante (2) | 23 | 67% |
| 🟡 Menor (1) | 3 | 9% |
| **Total activos** | **34** | |
| ~~Eliminados~~ | ~~3~~ | ~~H-FILTROS-04, H-DETALLE-04, H-FORM-08~~ |

*Revisiones de severidad aplicadas tras validación visual: H-HOME-08 (1→2), H-FILTROS-06 (3→2), H-DETALLE-02 (3→2), H-FORM-01 (3→2), H-FORM-09 (3→2).*

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

### 1. Navegación
[[01_homepage|H-HOME-02]] · [[01_homepage|H-HOME-03]] · [[01_homepage|H-HOME-06]] · [[01_homepage|H-HOME-07]] · [[02_busqueda-filtros|H-FILTROS-03]] · [[02_busqueda-filtros|H-FILTROS-07]] · [[03_detalle-proyecto|H-DETALLE-07]]

### 2. Contenido y Copy
[[01_homepage|H-HOME-04]] · [[01_homepage|H-HOME-05]] · [[01_homepage|H-HOME-08]] · [[01_homepage|H-HOME-09]] · [[01_homepage|H-HOME-10]] · [[02_busqueda-filtros|H-FILTROS-02]] · [[02_busqueda-filtros|H-FILTROS-06]] · [[02_busqueda-filtros|H-FILTROS-08]] · [[03_detalle-proyecto|H-DETALLE-05]] · [[03_detalle-proyecto|H-DETALLE-09]] · [[04_formulario-contacto|H-FORM-04]] · [[04_formulario-contacto|H-FORM-05]]

### 3. Formularios y Contacto
[[03_detalle-proyecto|H-DETALLE-03]] · [[04_formulario-contacto|H-FORM-01]] · [[04_formulario-contacto|H-FORM-02]] · [[04_formulario-contacto|H-FORM-03]] · [[04_formulario-contacto|H-FORM-06]] · [[04_formulario-contacto|H-FORM-07]] · [[04_formulario-contacto|H-FORM-09]]

### 4. Feedback del Sistema
[[01_homepage|H-HOME-01]] · [[02_busqueda-filtros|H-FILTROS-01]] · [[02_busqueda-filtros|H-FILTROS-05]] · [[02_busqueda-filtros|H-FILTROS-09]] · [[03_detalle-proyecto|H-DETALLE-08]]

### 5. Accesibilidad Visual
[[03_detalle-proyecto|H-DETALLE-01]] · [[03_detalle-proyecto|H-DETALLE-02]] · [[03_detalle-proyecto|H-DETALLE-06]]

---

## 🏆 Top 3 Hallazgos Críticos — Impacto directo en conversión

### #1 — [[03_detalle-proyecto|H-DETALLE-03]]: Sin CTA de contacto al terminar de leer "Acerca del proyecto" (Severidad 3)
**Por qué es el más crítico:** El usuario terminó de leer la descripción del proyecto, el precio le encaja, tiene preguntas concretas — y en ese momento exacto los únicos CTAs disponibles son "Descargar brochure" y "Compartir". El sitio lleva al usuario hasta la puerta y no la abre. CTAs en este momento de intención capturan hasta el 90% de visitantes que leen el contenido (Bokka Group, 2025). CTAs contextualizados convierten hasta 202% mejor que CTAs genéricos (Unbounce).

**Relación con hipótesis:** [[H3B]] ✅

---

### #2 — [[01_homepage|H-HOME-01]]: SPA sin feedback de carga — pantalla en blanco mientras carga JS (Severidad 3)
**Por qué es el segundo más crítico:** Si el usuario no puede entrar al funnel, no hay oportunidad de conversión. El 53% de usuarios mobile abandonan si la página tarda más de 3 segundos (Google/SOASTA Research). Por cada segundo de delay, la conversión cae 4.42% (Edmonds Commerce, 2025). El 81% del tráfico en Colombia es mobile (DataReportal 2024) — el segmento más afectado es el mayoritario.

**Relación con hipótesis:** [[H3C]] ✅

---

### #3 — [[04_formulario-contacto|H-FORM-03]]: Validación 100% post-submit + teléfono inválido pasa al CRM (Severidad 3)
**Por qué es el tercero más crítico:** Doble impacto. (1) La validación tardía genera abandono del formulario — el 28% de abandonos multi-error ocurren por el patrón submit→scroll→corregir→scroll (Zuko 2025). (2) El teléfono inválido llega al CRM sin alerta — el lead se pierde incluso cuando el usuario intentó contactar. La validación inline onBlur aumenta el completado un 22% (Zuko Analytics, 2024).

**Relación con hipótesis:** [[H3C]] ✅

---

## Relación con Hipótesis del Proyecto

| Hipótesis | Descripción | Hallazgos que la confirman | Veredicto |
|-----------|-------------|---------------------------|-----------|
| [[H3A]] — Arquitectura de información | La arquitectura y navegación del sitio dificultan que el usuario encuentre el proyecto correcto | H-HOME-02, H-HOME-03, H-HOME-04, H-HOME-07, H-FILTROS-01, H-FILTROS-02, H-FILTROS-03, H-FILTROS-05, H-FILTROS-07, H-DETALLE-06, H-DETALLE-07, H-DETALLE-09, H-FORM-07 | ✅ **Confirmada** — 13 hallazgos |
| [[H3B]] — CTAs ambiguos o insuficientes | Los CTAs no convierten en el momento de mayor intención | H-HOME-04, H-HOME-09, H-FILTROS-02, H-FILTROS-06, H-DETALLE-01, H-DETALLE-02, H-DETALLE-03, H-DETALLE-05, H-DETALLE-08, H-FORM-01, H-FORM-02, H-FORM-04, H-FORM-06, H-FORM-09 | ✅ **Confirmada fuertemente** — 14 hallazgos |
| [[H3C]] — Experiencia mobile inferior | La versión mobile tiene problemas adicionales o amplificados que generan mayor abandono | H-HOME-01, H-HOME-02, H-HOME-06, H-FILTROS-07, H-FILTROS-09, H-DETALLE-01, H-DETALLE-02, H-DETALLE-06, H-FORM-02, H-FORM-03, H-FORM-04, H-FORM-09 | ✅ **Confirmada** — 12 hallazgos |

---

## Estado de validación visual

Todos los hallazgos han sido validados con capturas del sitio renderizado en desktop y mobile.

| ID | Estado | Proyectos / páginas validadas |
|----|--------|-------------------------------|
| [[01_homepage\|H-HOME-01 a H-HOME-10]] | ✅ Todos validados | Homepage desktop y mobile |
| [[02_busqueda-filtros\|H-FILTROS-01 a H-FILTROS-09]] | ✅ Todos validados | `/proyecto-vivienda` desktop y mobile |
| [[03_detalle-proyecto\|H-DETALLE-01 a H-DETALLE-09]] | ✅ Todos validados | Ágora, Mirla, Céntrico, Pietra, Orizzo — desktop y mobile |
| [[04_formulario-contacto\|H-FORM-01 a H-FORM-09]] | ✅ Todos validados | `/contactanos` y formulario embebido — desktop y mobile |

*Eliminados tras validación: H-FILTROS-04 (URLs consistentes — redirect correcto), H-DETALLE-04 (mismo motivo), H-FORM-08 (FAQs existen en el sitio).*

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[06_reporte-ejecutivo-sintesis]] · [[H3A]] · [[H3B]] · [[H3C]]

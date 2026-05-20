---
tags:
  - prodesa
  - evaluacion-heuristica
  - reporte
  - ejecutivo
  - sintesis
aliases:
  - Reporte Ejecutivo
  - Síntesis Ejecutiva
status: completado
created: 2026-05-20
fase: "2.1"
---

# Reporte Ejecutivo — Evaluación Heurística Prodesa.com

> [!abstract] Resumen rápido
> **34 hallazgos activos** · **8 críticos** · **3 hipótesis confirmadas** ([[H3A]] · [[H3B]] · [[H3C]])
> Flujos evaluados: Homepage · Búsqueda/Filtros · Detalle de proyecto · Formulario de contacto

**Tarea:** 2.1 — Evaluación heurística (10 principios de Nielsen)
**Fase:** Fase 2 — Análisis
**Evaluador:** David Marín
**Fecha:** Mayo 2026
**Sitio evaluado:** https://prodesa.com/
**Metodología:** Evaluación heurística basada en los 10 principios de Jakob Nielsen

---

## 1. Resumen ejecutivo

Se realizó una evaluación heurística completa del sitio web de Prodesa cubriendo cuatro flujos críticos de conversión: homepage, búsqueda y filtros, detalle de proyecto y formulario de contacto. El análisis combinó inspección de código fuente, análisis de estructura HTML, y validación visual directa con capturas de pantalla en desktop y mobile.

**Se identificaron 34 hallazgos activos de usabilidad** (3 eliminados tras validación), de los cuales **8 son críticos** con impacto directo en la tasa de conversión. Las tres hipótesis del proyecto ([[H3A]], [[H3B]], [[H3C]]) fueron confirmadas con evidencia visual en desktop y mobile.

El hallazgo más grave es estructural: **en el momento de mayor intención del usuario — la página de detalle de proyecto — los únicos CTAs disponibles son "Descargar brochure" y "Compartir"**, sin ninguna opción de contacto directo. El segundo hallazgo más grave es que el sitio no muestra el estado del proyecto (preventa / en construcción / listo para entrega) en ningún punto del flujo, generando decisiones basadas en información incompleta. Adicionalmente, WhatsApp — el canal de mayor conversión en Colombia — solo está disponible dentro de la página de detalle, pero está ausente en el homepage y el listado donde el usuario está en etapas tempranas del funnel.

---

## 2. Metodología

| Aspecto | Detalle |
|---------|---------|
| Marco de evaluación | 10 Principios Heurísticos de Nielsen |
| Páginas evaluadas | Homepage, Listado de proyectos, Detalle de proyecto (Ágora, Mirla, Céntrico, Pietra, Orizzo), Formulario de contacto (/contactanos) |
| Dispositivos | Desktop (Chrome) + Mobile (viewport simulado + validación real) |
| Herramientas | Inspección de HTML fuente, web_fetch, capturas de pantalla anotadas |
| Período | Mayo 2026 |
| Escala de severidad | 1 = Menor · 2 = Importante · 3 = Crítico |

---

## 3. El sitio y su contexto

Prodesa es una constructora colombiana con presencia en más de 16 ciudades, con proyectos VIS (Vivienda de Interés Social), VIP (Vivienda de Interés Prioritario) y NO VIS. Su sitio web es el principal canal digital de captación de leads comerciales.

**Hallazgo técnico estructural:** el sitio está construido en Next.js como SPA (Single Page Application) con renderizado 100% client-side. Esto significa que todo el contenido depende de JavaScript para mostrarse. Sin JavaScript activo o con conexiones lentas, el usuario ve únicamente el mensaje: *"You need to enable JavaScript to run this app."* Este hallazgo atraviesa todas las secciones evaluadas y amplifica el impacto de los demás problemas, especialmente en mobile.

---

## 4. Hallazgos por sección

### 4.1 Homepage — 10 hallazgos

| ID        | Problema                                                                            | Severidad | Evidencia                     |
| --------- | ----------------------------------------------------------------------------------- | --------- | ----------------------------- |
| H-HOME-01 | SPA sin feedback de carga: pantalla en blanco mientras carga JS                     | 3 🔴      | ✅ Captura                     |
| H-HOME-02 | Doble barra de navegación: mezcla audiencias internas con compradores               | 2 🟠      | ✅ Captura desktop + mobile    |
| H-HOME-03 | "Invertir desde el exterior" comparte nivel con CTAs de conversión                  | 2 🟠      | ✅ Captura desktop + mobile    |
| H-HOME-04 | Badges "VIS" y "VIP" sin explicación en tarjetas y descripción de proyecto          | 3 🔴      | ✅ Captura carousel + detalle  |
| H-HOME-05 | Copyright desactualizado: muestra 2025 en lugar de 2026                             | 1 🟡      | ✅ Captura footer              |
| H-HOME-06 | Botón Google Play apunta a apple.com/store — link roto para Android                 | 3 🔴      | ✅ Captura footer              |
| H-HOME-07 | Sin breadcrumbs ni indicadores de ubicación en ninguna página                       | 2 🟠      | ✅ Capturas múltiples páginas  |
| H-HOME-08 | "SAGRILAFT" en footer: texto muerto sin link, sin explicación, genera desconfianza  | 2 🟠      | ✅ Captura footer              |
| H-HOME-09 | Hero sin propuesta de valor visible: el usuario no sabe qué ofrece Prodesa          | 2 🟠      | ✅ Captura desktop + mobile    |
| H-HOME-10 | Jilguero duplicado en HTML fuente del footer (invisible en render, problema de SEO) | 1 🟡      | ✅ Confirmado en código fuente |

**Nota H-HOME-08:** confirmado que SAGRILAFT no solo carece de explicación — es un elemento completamente no interactivo. El usuario que hace clic no recibe ninguna respuesta. Severidad ajustada de 1 a 2.

**Fuentes de validación**
- **H-HOME-01:** Google/SOASTA Research — el 53% de las visitas mobile se abandonan si la página tarda más de 3 segundos en mostrar contenido. DataReportal 2024: el 81% del tráfico web en Colombia proviene de dispositivos móviles.
- **H-HOME-06:** StatCounter GlobalStats — Android supera el 70% del mercado de smartphones en Colombia.

---

### 4.2 Búsqueda y Filtros — 8 hallazgos activos

| ID           | Problema                                                                                                                     | Severidad | Evidencia                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- | --------- | -------------------------------------------- |
| H-FILTROS-01 | Sin contador de resultados al aplicar filtros                                                                                | 3 🔴      | ✅ Captura desktop + mobile                   |
| H-FILTROS-02 | Filtros usan "VIS/NO VIS/VIP" sin definición ni tooltip                                                                      | 3 🔴      | ✅ Captura desktop + mobile                   |
| H-FILTROS-03 | "Limpiar filtros" como texto plano (no `<button>`) + comportamiento engañoso: reinicia a defaults, no limpia                 | 2 🟠      | ✅ Confirmado en código y validación en sitio |
| H-FILTROS-05 | Empty state invisible al filtrar sin resultados: mensaje en esquina inferior derecha, fuera de jerarquía visual              | 2 🟠      | ✅ Confirmado visualmente                     |
| H-FILTROS-06 | Precio con asterisco ambiguo e inconsistente entre tarjetas (VIP indexado a SMLMV vs. precio fijo) + sin estado del proyecto | 2 🟠      | ✅ Confirmado visualmente                     |
| H-FILTROS-07 | Filtro VIS/NO VIS/VIP solo disponible en mobile, ausente en web + valores default del panel no se perciben como default      | 2 🟠      | ✅ Validado en sitio web y mobile             |
| H-FILTROS-08 | "Proyecto de vivienda Jilguero" duplicado en footer — misma entrada dos veces consecutivas                                   | 1 🟡      | ✅ Confirmado visualmente                     |
| H-FILTROS-09 | Spinner de carga existe pero aparece con delay perceptible + al cargar resultados el usuario debe hacer scroll manual        | 2 🟠      | ✅ Validado con Slow 4G en web y mobile       |



---

### 4.3 Detalle de Proyecto — 8 hallazgos activos

| ID | Problema | Severidad | Evidencia |
|----|----------|-----------|-----------|
| [[03_detalle-proyecto\|H-DETALLE-01]] | H1 redundante ("Proyecto de Vivienda [Nombre]"), precio visualmente domina sobre el nombre, "Déjanos tus datos" duplica formulario visible en desktop, "Agenda tu cita" pide correo innecesariamente | 2 🟡 | ✅ Validado en Ágora y Mirla — desktop y mobile |
| [[03_detalle-proyecto\|H-DETALLE-02]] | Precio y área con idéntico peso visual — mismo naranja, mismo tamaño. El listado mobile diferencia correctamente; el detalle no | 2 🟡 | ✅ Captura Mirla y Ágora (revisado de 3 a 2) |
| [[03_detalle-proyecto\|H-DETALLE-03]] | CTAs son "Descargar brochure" y "Compartir" — sin CTA de contacto directo. En desktop el formulario está en columna separada, desconectado del flujo de lectura | 3 🔴 | ✅ Captura Ágora desktop y Mirla |
| ~~H-DETALLE-04~~ | ~~URLs inconsistentes entre proyectos~~ | — | **Eliminado** — todos los proyectos siguen `/proyecto-vivienda/[ciudad]/[slug]`. El redirect de Ágora es comportamiento correcto |
| [[03_detalle-proyecto\|H-DETALLE-05]] | Datos clave (habitaciones, m², precio por tipología) requieren scroll. Fecha estimada de entrega ausente en toda la página | 2 🟡 | ✅ Validado en Ágora — sección "Inmuebles disponibles" |
| [[03_detalle-proyecto\|H-DETALLE-06]] | 6 inconsistencias concretas validadas en Pietra vs. Orizzo: galería (2 vs. 5 tabs), brochure, lista de incluidos, mapa, CTAs de contacto y proyectos similares. Transversal a desktop y mobile | 2 🟡 | ✅ Validado en Pietra y Orizzo — desktop y mobile |
| [[03_detalle-proyecto\|H-DETALLE-07]] | Al regresar al listado desde el detalle, los filtros se pierden. El usuario debe reconfigurar su búsqueda desde cero | 2 🟡 | ✅ Validado con capturas antes/después de navegar |
| [[03_detalle-proyecto\|H-DETALLE-08]] | Sin chip de estado del proyecto (preventa / en construcción / listo para entrega / agotado) en el hero ni en las tarjetas del listado | 3 🔴 | ✅ Validado — hero sin estado visible |
| [[03_detalle-proyecto\|H-DETALLE-09]] | "Subsidio disponible" en la descripción sin indicar tipo, monto ni requisitos. Información enterrada en prosa en lugar de contextualizada junto al precio | 2 🟡 | ✅ Validado en Mirla — desktop y mobile |

---

### 4.4 Formulario de Contacto — 8 hallazgos activos

| ID | Problema | Severidad | Evidencia |
|----|----------|-----------|-----------|
| [[04_formulario-contacto\|H-FORM-01]] | Confirmación post-envío existe pero: muestra correo del usuario en pantalla, no indica canal ni tiempo de respuesta, sin CTA de respaldo | 2 🟠 | ✅ Captura pantalla post-envío |
| [[04_formulario-contacto\|H-FORM-02]] | 6 campos obligatorios incluyendo tipo y número de documento de identidad — innecesarios en primer contacto. Capitalización inconsistente en labels. Mayor fricción en mobile | 2 🟠 | ✅ Validado desktop y mobile |
| [[04_formulario-contacto\|H-FORM-03]] | Validación 100% post-submit confirmada. Teléfono inválido no genera error — pasa al CRM sin validación de formato. En web los errores salen del viewport y obligan a scroll | 3 🔴 | ✅ Validado desktop y mobile |
| [[04_formulario-contacto\|H-FORM-04]] | Mensajes de error "RELLENA ESTE CAMPO OBLIGATORIO." — todo en mayúsculas, idéntico para todos los campos, sin orientación. Teléfono inválido no recibe ningún mensaje | 2 🟠 | ✅ Mismas capturas de H-FORM-03 |
| [[04_formulario-contacto\|H-FORM-05]] | Tres de cuatro líneas de contacto en footer tienen el mismo número. Cuarto ejemplo del patrón de gobernanza de contenidos | 2 🟠 | ✅ Validado web y mobile |
| [[04_formulario-contacto\|H-FORM-06]] | Canales existen en /contactanos (WhatsApp, Teams, callback) pero: "Agenda tu cita en sala" lleva a Teams (nombre engañoso), reCAPTCHA en "Asesoría inmediata" (-40% conversión), formularios inconsistentes entre canales | 2 🟠 | ✅ Validado en /contactanos |
| [[04_formulario-contacto\|H-FORM-07]] | "Déjanos tus datos" hace scroll al formulario embebido. El formulario no transmite el proyecto al CRM aunque la URL lo indica | 2 🟠 | ✅ Validado funcionalmente |
| [[04_formulario-contacto\|H-FORM-09]] | WhatsApp existe y funciona en la sticky del detalle de proyecto. Ausente en homepage y listado — cobertura parcial del canal de mayor conversión | 2 🟠 | ✅ Validado — homepage y listado sin WhatsApp |

*H-FORM-08 eliminado tras validación — las FAQ existen en el sitio.*

**Fuentes de validación**
- **H-FORM-02:** Baymard Institute (2022) — la inclusión de datos personales sensibles en formularios de primer contacto reduce la tasa de completado hasta un 34%.
- **H-FORM-06:** Stanford Persuasive Technology Lab — el reCAPTCHA visible puede reducir conversiones hasta un 40%. La alternativa recomendada es reCAPTCHA v3 invisible, que verifica en segundo plano sin interrumpir al usuario.

---

## 5. Consolidado global

| Severidad | Total | Porcentaje |
|-----------|-------|------------|
| 🔴 Crítico (3) | 8 | 24% |
| 🟠 Importante (2) | 23 | 67% |
| 🟡 Menor (1) | 3 | 9% |
| **Total activos** | **34** | |
| ~~Eliminados~~ | ~~3~~ | ~~H-FILTROS-04, H-DETALLE-04, H-FORM-08~~ |

*Revisiones de severidad aplicadas tras validación: H-HOME-08 (1→2), H-FILTROS-06 (3→2), H-DETALLE-02 (3→2), H-FORM-01 (3→2), H-FORM-09 (3→2).*

| Evidencia | Total |
|-----------|-------|
| ✅ Confirmados con captura visual (desktop + mobile) | 34 |
| ⏳ Pendientes | 0 |

*Todos los hallazgos validados con capturas en desktop y mobile. Proyectos evaluados: Ágora, Mirla, Céntrico, Pietra, Orizzo.*

---

## 6. Agrupación por categoría

| Categoría | Hallazgos | Críticos |
|-----------|-----------|----------|
| 1. Navegación | 7 | 1 |
| 2. Contenido y Copy | 12 | 2 |
| 3. Formularios y Contacto | 7 | 2 |
| 4. Feedback del Sistema | 5 | 3 |
| 5. Accesibilidad Visual | 3 | 0 |
| **Total** | **34** | **8** |

**1. Navegación** — H-HOME-02 · H-HOME-03 · H-HOME-06 · H-HOME-07 · H-FILTROS-03 · H-FILTROS-07 · H-DETALLE-07

**2. Contenido y Copy** — H-HOME-04 · H-HOME-05 · H-HOME-08 · H-HOME-09 · H-HOME-10 · H-FILTROS-02 · H-FILTROS-06 · H-FILTROS-08 · H-DETALLE-05 · H-DETALLE-09 · H-FORM-04 · H-FORM-05

**3. Formularios y Contacto** — H-DETALLE-03 · H-FORM-01 · H-FORM-02 · H-FORM-03 · H-FORM-06 · H-FORM-07 · H-FORM-09

**4. Feedback del Sistema** — H-HOME-01 · H-FILTROS-01 · H-FILTROS-05 · H-FILTROS-09 · H-DETALLE-08

**5. Accesibilidad Visual** — H-DETALLE-01 · H-DETALLE-02 · H-DETALLE-06

---

## 7. Patrón de problemas — Lo que el sitio hace sistemáticamente mal

Más allá de los hallazgos individuales, la evaluación revela **cuatro patrones estructurales** que se repiten en todas las secciones:

### Patrón 1 — El sitio habla en el idioma del vendedor, no del comprador
"VIS", "VIP", "NO VIS", "SAGRILAFT", "Macroproyecto" son términos del sector constructor que aparecen sin traducción en los puntos más visibles del sitio: el título del navegador, los badges de las tarjetas, el cuerpo de las descripciones de proyecto y el footer. El comprador primerizo — el segmento más grande del mercado objetivo de Prodesa — no puede self-qualificarse ni avanzar con confianza porque no entiende el vocabulario básico del sitio.

### Patrón 2 — El funnel de conversión se corta justo donde más importa
El usuario llega al sitio (homepage) → encuentra proyectos → entra al detalle → está listo para contactar → y ahí el CTA es "Descargar brochure". WhatsApp existe en la página de detalle pero no en el homepage ni en el listado — los puntos de entrada del funnel. El momento de mayor intención del usuario es el momento de menor herramienta de conversión disponible. El sitio invierte esfuerzo en llevar al usuario hasta la puerta y luego no le abre con claridad.

### Patrón 3 — Múltiples audiencias sin separación, un solo flujo
Compradores locales, clientes actuales, proveedores, administradores de conjuntos e inversionistas desde el exterior comparten el mismo menú de navegación sin diferenciación. El resultado es una interfaz que no está optimizada para ninguna audiencia en particular. El comprador local debe ignorar activamente opciones que no son para él en cada página que visita.

### Patrón 4 — Gobernanza de contenidos deficiente
El mismo problema de mantenimiento de contenidos se repite en cuatro puntos distintos del sitio: copyright desactualizado ([[01_homepage|H-HOME-05]]), proyecto Jilguero duplicado en el footer ([[01_homepage|H-HOME-10]]), inconsistencias en el sitemap del footer ([[02_busqueda-filtros|H-FILTROS-08]]) y tres líneas de contacto con el mismo número telefónico ([[04_formulario-contacto|H-FORM-05]]). Ninguno de estos problemas es técnico — todos son de proceso editorial. Su acumulación comunica desorganización a un comprador que está evaluando confiarle sus ahorros a la empresa.

---

## 8. Top 3 hallazgos críticos — Impacto directo en conversión

Los tres hallazgos que siguen no son solo problemas de usabilidad — son roturas en el camino que un usuario debe recorrer para convertirse en lead. Cada uno está respaldado por datos de investigación externa verificados en mayo 2026. Ver research completo en [[../../research/top3-impacto-conversion|research/top3-impacto-conversion]].

---

### #1 — [[03_detalle-proyecto|H-DETALLE-03]]: Sin CTA de contacto al terminar de leer "Acerca del proyecto"

**Por qué es el más crítico:** El usuario llegó hasta el momento de mayor intención de todo el funnel — terminó de leer la descripción, el precio le encaja, tiene preguntas concretas. En ese momento exacto, los únicos CTAs disponibles son "Descargar brochure" y "Compartir". El sitio lleva al usuario hasta la puerta y no la abre.

**Evidencia de impacto:**
- CTAs ubicados justo después de contenido de alta intención capturan hasta el **90% de los visitantes** que leen el contenido principal — Bokka Group, 2025
- CTAs contextualizados convierten hasta **202% mejor** que CTAs genéricos — Unbounce
- En real estate: *"los CTAs deben ir justo después del precio, la mejor foto o los detalles clave — ese es el momento en que la gente está lista para actuar sin dudarlo"* — Propphy, 2025
- CTAs optimizados para mobile aumentan conversiones un **32.5%** — Agent Image, 2025

**Corrección:** Añadir CTA de WhatsApp directo al final de la sección "Acerca del proyecto" con tratamiento visual primario. Esfuerzo: medio.

---

### #2 — [[01_homepage|H-HOME-01]]: SPA sin feedback de carga — pantalla en blanco mientras carga JS

**Por qué es el segundo más crítico:** Si el usuario no puede entrar al funnel, no hay ninguna oportunidad de conversión. Una SPA que depende 100% de JavaScript para mostrar cualquier contenido crea una ventana de pantalla en blanco que, en conexiones móviles variables, excede con frecuencia el umbral de abandono.

**Evidencia de impacto:**
- El **53% de usuarios mobile abandonan** si la página tarda más de 3 segundos en mostrar algo — confirmado por Google/SOASTA Research, Zuko 2025 y múltiples fuentes independientes
- Por cada segundo de delay (entre 0 y 5 s), la tasa de conversión cae **4.42%** — Edmonds Commerce, 2025
- Un delay de 1 segundo = **7% menos conversiones**, 11% menos páginas vistas, 16% menos satisfacción del usuario
- Las páginas mobile promedian **8.6 segundos** de carga vs 2.5 s en desktop — una SPA sin SSR empeora directamente este gap
- El **81% del tráfico web en Colombia es mobile** (DataReportal 2024) — el segmento más afectado es el mayoritario

**Corrección:** Implementar SSR o SSG en Next.js para páginas críticas. Como mínimo, añadir skeleton de carga con el logo y un mensaje orientador mientras el JS inicializa. Esfuerzo: alto.

---

### #3 — [[04_formulario-contacto|H-FORM-03]]: Validación 100% post-submit + teléfono inválido pasa al CRM

**Por qué es el tercero más crítico:** Doble impacto en la conversión. Primero, la validación tardía frustra al usuario y genera abandono del formulario — el usuario que ya invirtió tiempo llenando 6 campos descubre todos los errores de golpe al enviar. Segundo, aunque el usuario complete el formulario, el teléfono inválido llega al CRM sin ninguna alerta — el lead se pierde incluso después de que el usuario intentó contactar.

**Evidencia de impacto:**
- La tasa promedio de completado de formularios es **51.7%** en condiciones normales — Zuko Analytics 2025. Con validación solo al submit, este número cae significativamente
- La validación inline onBlur aumenta el completado de formularios un **22%** — Zuko Analytics 2024
- El **28% de los abandonos multi-error** ocurren exactamente por el patrón *"submit → scroll arriba → corregir → scroll abajo"* — el comportamiento exacto que ocurre en Prodesa en desktop
- El campo de teléfono tiene una tasa de abandono individual del **6.3%** — uno de los campos con mayor abandono por campo
- El **14% de usuarios** abandonan un formulario por errores que aparecen únicamente al enviar — Formstory, 2025

**Corrección:** (1) Validación inline onBlur en todos los campos. (2) Validación de formato colombiano para teléfono: 10 dígitos, empieza por 3. Esfuerzo: medio.

---

## 9. Confirmación de hipótesis

| Hipótesis | Descripción | Hallazgos | Veredicto |
|-----------|-------------|-----------|-----------|
| [[H3A]] — Arquitectura de información | La navegación dificulta que el usuario encuentre el proyecto correcto | [[01_homepage\|H-HOME-02]], [[01_homepage\|H-HOME-03]], [[01_homepage\|H-HOME-04]], [[01_homepage\|H-HOME-07]], [[02_busqueda-filtros\|H-FILTROS-01]], [[02_busqueda-filtros\|H-FILTROS-02]], [[02_busqueda-filtros\|H-FILTROS-03]], [[02_busqueda-filtros\|H-FILTROS-05]], [[02_busqueda-filtros\|H-FILTROS-07]], [[03_detalle-proyecto\|H-DETALLE-06]], [[03_detalle-proyecto\|H-DETALLE-07]], [[03_detalle-proyecto\|H-DETALLE-09]], [[04_formulario-contacto\|H-FORM-07]] | ✅ **Confirmada** — 13 hallazgos respaldan esta hipótesis |
| [[H3B]] — CTAs ambiguos o insuficientes | Los CTAs no convierten en el momento de mayor intención | [[01_homepage\|H-HOME-04]], [[01_homepage\|H-HOME-09]], [[02_busqueda-filtros\|H-FILTROS-02]], [[02_busqueda-filtros\|H-FILTROS-06]], [[03_detalle-proyecto\|H-DETALLE-01]], [[03_detalle-proyecto\|H-DETALLE-02]], [[03_detalle-proyecto\|H-DETALLE-03]], [[03_detalle-proyecto\|H-DETALLE-05]], [[03_detalle-proyecto\|H-DETALLE-08]], [[04_formulario-contacto\|H-FORM-01]], [[04_formulario-contacto\|H-FORM-02]], [[04_formulario-contacto\|H-FORM-04]], [[04_formulario-contacto\|H-FORM-06]], [[04_formulario-contacto\|H-FORM-09]] | ✅ **Confirmada fuertemente** — 14 hallazgos directos en el funnel de conversión |
| [[H3C]] — Experiencia mobile inferior | El mobile genera mayor abandono | [[01_homepage\|H-HOME-01]], [[01_homepage\|H-HOME-02]], [[01_homepage\|H-HOME-06]], [[02_busqueda-filtros\|H-FILTROS-07]], [[02_busqueda-filtros\|H-FILTROS-09]], [[03_detalle-proyecto\|H-DETALLE-01]], [[03_detalle-proyecto\|H-DETALLE-02]], [[03_detalle-proyecto\|H-DETALLE-06]], [[04_formulario-contacto\|H-FORM-02]], [[04_formulario-contacto\|H-FORM-03]], [[04_formulario-contacto\|H-FORM-04]], [[04_formulario-contacto\|H-FORM-09]] | ✅ **Confirmada** — 12 hallazgos con capturas mobile en formulario, detalle y filtros |

---

## 10. Mapa de calor de problemas por principio de Nielsen

| Principio | # Hallazgos | Secciones afectadas | Severidad dominante |
|-----------|-------------|---------------------|---------------------|
| P1 — Visibilidad del estado | 7 | Homepage, Filtros, Formulario | 🔴 Crítico |
| P2 — Mundo real | 6 | Homepage, Filtros, Formulario | 🔴 Crítico |
| P3 — Control del usuario | 3 | Filtros, Detalle | 🟡 Importante |
| P4 — Consistencia | 6 | Homepage, Filtros, Detalle | 🟡 Importante |
| P5 — Prevención de errores | 2 | Filtros, Formulario | 🟡 Importante |
| P6 — Reconocimiento | 4 | Homepage, Detalle | 🔴 Crítico |
| P7 — Flexibilidad | 0 | — | — (H-FILTROS-07 reasignado a P4+P6 tras validación) |
| P8 — Minimalismo | 4 | Homepage, Detalle | 🟡 Importante |
| P9 — Recuperación de errores | 2 | Homepage, Formulario | 🔴 Crítico |
| P10 — Ayuda y documentación | 1 | Detalle | 🟡 Importante |

**Los principios más violados son P1 (Visibilidad) y P4 (Consistencia)** — lo que confirma que el problema central del sitio no es de diseño visual sino de comunicación de estado y coherencia estructural.

---

## 11. Estado de validación

Todos los hallazgos han sido validados con capturas visuales en desktop y mobile.

| Sección | Hallazgos | Estado |
|---------|-----------|--------|
| [[01_homepage\|Homepage]] | H-HOME-01 a H-HOME-10 | ✅ Todos validados |
| [[02_busqueda-filtros\|Búsqueda y Filtros]] | H-FILTROS-01 a H-FILTROS-09 | ✅ Todos validados |
| [[03_detalle-proyecto\|Detalle de Proyecto]] | H-DETALLE-01 a H-DETALLE-09 | ✅ Todos validados (H-DETALLE-04 eliminado) |
| [[04_formulario-contacto\|Formulario de Contacto]] | H-FORM-01 a H-FORM-09 | ✅ Todos validados (H-FORM-08 eliminado) |

Proyectos validados: Ágora, Mirla, Céntrico, Pietra, Orizzo.

---

## 12. Archivos de esta evaluación

| Archivo | Contenido |
|---------|-----------|
| [[00_plantilla]] | Marco de referencia: principios Nielsen, escala de severidad |
| [[01_homepage]] | 10 hallazgos con análisis detallado y capturas |
| [[02_busqueda-filtros]] | 9 hallazgos del flujo de búsqueda |
| [[03_detalle-proyecto]] | 9 hallazgos de la página de proyecto |
| [[04_formulario-contacto]] | 8 hallazgos del formulario y contacto |
| [[05_inventario-final]] | Inventario unificado con priorización y relación con hipótesis |
| [[06_reporte-ejecutivo-sintesis]] | Este documento — síntesis ejecutiva completa |
| [[01_por-que-importa-la-ai]] · [[02_mapa-sitio-actual]] · [[03_mapa-sitio-propuesto]] | Subcarpeta con análisis de AI, mapa as-is y mapa to-be |

**Archivos de research:**

| Archivo | Contenido |
|---------|-----------|
| [[research/H6-patrones-pagina-detalle-proyecto]] | Benchmarking de portales maduros — anatomía estándar de página de proyecto inmobiliario |
| [[research/H8-visibilidad-estado-proyecto]] | Por qué el estado del proyecto es crítico — fases inmobiliarias en Colombia y Heurística #1 Nielsen |
| [[research/H-FORM-patrones-formulario-contacto]] | WhatsApp en LATAM, validación inline vs. post-submit, confirmación post-envío y calidad del lead |
| [[research/H-FORM-canales-contacto-omnicanalidad]] | Omnicanalidad en real estate, reCAPTCHA e impacto en conversión, CTAs engañosos |

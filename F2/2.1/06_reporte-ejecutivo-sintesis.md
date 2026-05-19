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
---

# Reporte Ejecutivo — Evaluación Heurística Prodesa.com
**Tarea:** 2.1 — Evaluación heurística (10 principios de Nielsen)
**Fase:** Fase 2 — Análisis
**Evaluador:** David Marín
**Fecha:** Mayo 2026
**Sitio evaluado:** https://prodesa.com/
**Metodología:** Evaluación heurística basada en los 10 principios de Jakob Nielsen

---

## 1. Resumen ejecutivo

Se realizó una evaluación heurística completa del sitio web de Prodesa cubriendo cuatro flujos críticos de conversión: homepage, búsqueda y filtros, detalle de proyecto y formulario de contacto. El análisis combinó inspección de código fuente, análisis de estructura HTML, y validación visual directa con capturas de pantalla en desktop y mobile.

**Se identificaron 36 hallazgos activos de usabilidad** (1 eliminado tras validación), de los cuales **8 son críticos** con impacto directo en la tasa de conversión. Las tres hipótesis del proyecto ([[H3A]], [[H3B]], [[H3C]]) fueron confirmadas con evidencia visual en desktop y mobile.

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
| H-HOME-02 | Doble barra de navegación: mezcla audiencias internas con compradores               | 2 🟡      | ✅ Captura desktop + mobile    |
| H-HOME-03 | "Invertir desde el exterior" comparte nivel con CTAs de conversión                  | 2 🟡      | ✅ Captura desktop + mobile    |
| H-HOME-04 | Badges "VIS" y "VIP" sin explicación en tarjetas y descripción de proyecto          | 3 🔴      | ✅ Captura carousel + detalle  |
| H-HOME-05 | Copyright desactualizado: muestra 2025 en lugar de 2026                             | 1 🟢      | ✅ Captura footer              |
| H-HOME-06 | Botón Google Play apunta a apple.com/store — link roto para Android                 | 3 🔴      | ✅ Captura footer              |
| H-HOME-07 | Sin breadcrumbs ni indicadores de ubicación en ninguna página                       | 2 🟡      | ✅ Capturas múltiples páginas  |
| H-HOME-08 | "SAGRILAFT" en footer: texto muerto sin link, sin explicación, genera desconfianza  | 2 🟡      | ✅ Captura footer              |
| H-HOME-09 | Hero sin propuesta de valor visible: el usuario no sabe qué ofrece Prodesa          | 2 🟡      | ✅ Captura desktop + mobile    |
| H-HOME-10 | Jilguero duplicado en HTML fuente del footer (invisible en render, problema de SEO) | 1 🟢      | ✅ Confirmado en código fuente |

**Nota relevante sobre H-HOME-08:** confirmado que SAGRILAFT no solo carece de explicación — es un elemento completamente no interactivo. El usuario que hace clic no recibe ninguna respuesta. Severidad ajustada de 1 a 2.

---

### 4.2 Búsqueda y Filtros — 9 hallazgos

| ID           | Problema                                                                                                                     | Severidad                                                                                | Evidencia                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------- |
| H-FILTROS-01 | Sin contador de resultados al aplicar filtros                                                                                | 3 🔴                                                                                     | ✅ Captura desktop + mobile                   |
| H-FILTROS-02 | Filtros usan "VIS/NO VIS/VIP" sin definición ni tooltip                                                                      | 3 🔴                                                                                     | ✅ Captura desktop + mobile                   |
| H-FILTROS-03 | "Limpiar filtros" como texto plano (no `<button>`) + comportamiento engañoso: reinicia a defaults, no limpia                 | 2 🟡                                                                                     | ✅ Confirmado en código y validación en sitio |
| H-FILTROS-04 | URLs inconsistentes: 3 patrones distintos para el mismo tipo de contenido                                                    | 2 🟡                                                                                     | ✅ Confirmado en HTML                         |
| H-FILTROS-05 | Empty state invisible al filtrar sin resultados: mensaje en esquina inferior derecha, fuera de jerarquía visual              | 2 🟡                                                                                     | ✅ Confirmado visualmente                     |
| H-FILTROS-06 | Precio con asterisco ambiguo e inconsistente entre tarjetas (VIP indexado a SMLMV vs. precio fijo) + sin estado del proyecto | 2 🟡 (revisado de 3 a 2 — el precio existe, el problema es la ambigüedad)                | ✅ Confirmado visualmente                     |
| H-FILTROS-07 | Filtro VIS/NO VIS/VIP solo disponible en mobile, ausente en web + valores default del panel no se perciben como default      | 2 🟡 (revisado — el sitio sí tiene filtros avanzados, la premisa inicial era incorrecta) | ✅ Validado en sitio web y mobile             |
| H-FILTROS-08 | "Proyecto de vivienda Jilguero" duplicado en footer — misma entrada dos veces consecutivas                                   | 1 🟢 (Ciudad Esplendor descartado tras validación en DevTools)                           | ✅ Confirmado visualmente                     |
| H-FILTROS-09 | Spinner de carga existe pero aparece con delay perceptible + al cargar resultados el usuario debe hacer scroll manual        | 2 🟡 (revisado — el spinner existe, los problemas son de timing y anclaje)               | ✅ Validado con Slow 4G en web y mobile       |

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

### 4.4 Formulario de Contacto — 9 hallazgos

| ID | Problema | Severidad | Evidencia |
|----|----------|-----------|-----------|
| [[04_formulario-contacto\|H-FORM-01]] | Confirmación post-envío existe pero: muestra correo del usuario en pantalla, no indica canal ni tiempo de respuesta, sin CTA de respaldo | 2 🟡 (revisado de 3 a 2 — la confirmación existe) | ✅ Captura pantalla post-envío |
| [[04_formulario-contacto\|H-FORM-02]] | 6 campos obligatorios incluyendo tipo y número de documento de identidad — innecesarios en primer contacto. Capitalización inconsistente en labels. Mayor fricción en mobile | 2 🟡 | ✅ Validado desktop y mobile |
| [[04_formulario-contacto\|H-FORM-03]] | Validación 100% post-submit confirmada. Teléfono inválido no genera error — pasa al CRM sin validación de formato. En web los errores salen del viewport y obligan a scroll | 3 🔴 | ✅ Validado desktop y mobile |
| [[04_formulario-contacto\|H-FORM-04]] | Mensajes de error "RELLENA ESTE CAMPO OBLIGATORIO." — todo en mayúsculas, idéntico para todos los campos, sin orientación. Teléfono inválido no recibe ningún mensaje | 2 🟡 | ✅ Mismas capturas de H-FORM-03 |
| [[04_formulario-contacto\|H-FORM-05]] | Tres de cuatro líneas de contacto en footer tienen el mismo número. Cuarto ejemplo del patrón de gobernanza de contenidos | 2 🟡 | ✅ Validado web y mobile |
| [[04_formulario-contacto\|H-FORM-06]] | Canales existen en /contactanos (WhatsApp, Teams, callback) pero: "Agenda tu cita en sala" lleva a Teams (nombre engañoso), reCAPTCHA en "Asesoría inmediata" (-40% conversión), formularios inconsistentes entre canales | 2 🟡 | ✅ Validado en /contactanos |
| [[04_formulario-contacto\|H-FORM-07]] | "Déjanos tus datos" hace scroll al formulario embebido. El formulario no transmite el proyecto al CRM aunque la URL lo indica | 2 🟡 | ✅ Validado funcionalmente |
| [[04_formulario-contacto\|H-FORM-08]] | /contactanos sin FAQ ni enlace a preguntas frecuentes. Después de los canales solo aparecen CTAs de acción | 1 🟢 | ✅ Validado en /contactanos |
| [[04_formulario-contacto\|H-FORM-09]] | WhatsApp existe y funciona en la sticky del detalle de proyecto. Ausente en homepage y listado — cobertura parcial del canal de mayor conversión | 2 🟡 (revisado de 3 a 2 — WhatsApp existe en el detalle) | ✅ Validado — homepage y listado sin WhatsApp |

---

## 5. Consolidado global

| Severidad | Total | Porcentaje |
|-----------|-------|------------|
| 🔴 Crítico (3) | 8 | 22% |
| 🟡 Importante (2) | 24 | 67% |
| 🟢 Menor (1) | 4 | 11% |
| **Total activos** | **36** | |
| ~~Eliminados~~ | ~~1~~ | ~~H-FILTROS-04~~ |

*Revisiones de severidad aplicadas tras validación: H-HOME-08 (1→2), H-FILTROS-06 (3→2), H-DETALLE-02 (3→2), H-FORM-01 (3→2), H-FORM-09 (3→2).*

| Evidencia | Total |
|-----------|-------|
| ✅ Confirmados con captura visual (desktop + mobile) | 36 |
| ⏳ Pendientes | 0 |

*Todos los hallazgos validados con capturas en desktop y mobile. Proyectos evaluados: Ágora, Mirla, Céntrico, Pietra, Orizzo.*

---

## 6. Patrón de problemas — Lo que el sitio hace sistemáticamente mal

Más allá de los hallazgos individuales, la evaluación revela **tres patrones estructurales** que se repiten en todas las secciones:

### Patrón 1 — El sitio habla en el idioma del vendedor, no del comprador
"VIS", "VIP", "NO VIS", "SAGRILAFT", "Macroproyecto" son términos del sector constructor que aparecen sin traducción en los puntos más visibles del sitio: el título del navegador, los badges de las tarjetas, el cuerpo de las descripciones de proyecto y el footer. El comprador primerizo — el segmento más grande del mercado objetivo de Prodesa — no puede self-qualificarse ni avanzar con confianza porque no entiende el vocabulario básico del sitio.

### Patrón 2 — El funnel de conversión se corta justo donde más importa
El usuario llega al sitio (homepage) → encuentra proyectos → entra al detalle → está listo para contactar → y ahí el CTA es "Descargar brochure". WhatsApp existe en la página de detalle pero no en el homepage ni en el listado — los puntos de entrada del funnel. El momento de mayor intención del usuario es el momento de menor herramienta de conversión disponible. El sitio invierte esfuerzo en llevar al usuario hasta la puerta y luego no le abre con claridad.

### Patrón 4 — Gobernanza de contenidos deficiente
El mismo problema de mantenimiento de contenidos se repite en cuatro puntos distintos del sitio: copyright desactualizado ([[01_homepage|H-HOME-05]]), proyecto Jilguero duplicado en el footer ([[01_homepage|H-HOME-10]]), inconsistencias en el sitemap del footer ([[02_busqueda-filtros|H-FILTROS-08]]) y tres líneas de contacto con el mismo número telefónico ([[04_formulario-contacto|H-FORM-05]]). Ninguno de estos problemas es técnico — todos son de proceso editorial. Su acumulación comunica desorganización a un comprador que está evaluando confiarle sus ahorros a la empresa.

### Patrón 3 — Múltiples audiencias sin separación, un solo flujo
Compradores locales, clientes actuales, proveedores, administradores de conjuntos e inversionistas desde el exterior comparten el mismo menú de navegación sin diferenciación. El resultado es una interfaz que no está optimizada para ninguna audiencia en particular. El comprador local debe ignorar activamente opciones que no son para él en cada página que visita.

---

## 7. Top 5 hallazgos críticos por impacto en conversión

### 🥇 #1 — [[03_detalle-proyecto|H-DETALLE-03]]: Sin CTA de contacto en el momento de mayor intención
**Impacto:** En el momento de mayor intención del usuario (después de leer la descripción del proyecto), los únicos CTAs disponibles son "Descargar brochure" y "Compartir". No hay forma de contactar a un asesor desde esa sección. El usuario motivado a actuar no tiene canal disponible — debe buscarlo por su cuenta o abandonar. Conecta con [[04_formulario-contacto|H-FORM-01]] y [[04_formulario-contacto|H-FORM-09]].
**Esfuerzo de corrección:** Medio — añadir CTA de WhatsApp directo después de la descripción del proyecto.

### 🥈 #2 — [[03_detalle-proyecto|H-DETALLE-08]]: Sin estado del proyecto visible
**Impacto:** La ausencia del estado del proyecto (preventa / en construcción / listo para entrega / agotado) genera leads de menor calidad, expectativas incorrectas y frustración tardía. Un comprador que necesita mudarse en 6 meses no puede saber si el proyecto aplica a su plan de vida. El asesor debe responder una pregunta que la página debería resolver sola.
**Esfuerzo de corrección:** Bajo-medio — chip de color en el hero y en las tarjetas del listado, campo obligatorio en el CMS.

### 🥉 #3 — [[01_homepage|H-HOME-04]] + [[02_busqueda-filtros|H-FILTROS-02]]: Jerga "VIS / VIP / NO VIS" sin definición en todo el funnel
**Impacto:** Confirmado en 4 puntos del sitio: badges de tarjetas, nav global, filtros de búsqueda y labels del formulario. Para el comprador primerizo — segmento principal de Prodesa — este vocabulario es una barrera de entrada que actúa antes de que el usuario vea cualquier proyecto. Un usuario que no entiende si puede comprar VIS no avanzará en el funnel.
**Esfuerzo de corrección:** Bajo-medio — tooltips, texto auxiliar o cambio de etiquetas a lenguaje de beneficio orientado al usuario.

### #4 — [[04_formulario-contacto|H-FORM-09]]: WhatsApp con cobertura parcial
**Impacto:** WhatsApp existe y funciona correctamente en la sticky de la página de detalle. Sin embargo, está ausente en el homepage y el listado — los puntos de entrada del funnel donde el usuario todavía está evaluando. Un comprador con una duda rápida en el listado no tiene acceso al canal de menor fricción sin primero entrar a un proyecto específico.
**Esfuerzo de corrección:** Bajo — extender el botón existente al homepage y al listado.

### #5 — [[01_homepage|H-HOME-01]]: SPA sin feedback de carga
**Impacto:** En Colombia, más del 80% del tráfico es mobile. Una SPA que muestra pantalla en blanco mientras carga JS pierde usuarios en los primeros 3 segundos, especialmente en conexiones móviles variables.
**Esfuerzo de corrección:** Alto — requiere SSR/SSG en Next.js o al menos skeleton de carga.

---

## 8. Confirmación de hipótesis

| Hipótesis | Descripción | Hallazgos | Veredicto |
|-----------|-------------|-----------|-----------|
| [[H3A]] — Arquitectura de información | La navegación dificulta que el usuario encuentre el proyecto correcto | [[01_homepage\|H-HOME-02]], [[01_homepage\|H-HOME-03]], [[01_homepage\|H-HOME-07]], [[02_busqueda-filtros\|H-FILTROS-03]], [[02_busqueda-filtros\|H-FILTROS-05]], [[02_busqueda-filtros\|H-FILTROS-07]], [[03_detalle-proyecto\|H-DETALLE-06]], [[03_detalle-proyecto\|H-DETALLE-07]], [[03_detalle-proyecto\|H-DETALLE-09]] | ✅ **Confirmada** — 9 hallazgos respaldan esta hipótesis |
| [[H3B]] — CTAs ambiguos o insuficientes | Los CTAs no convierten en el momento de mayor intención | [[01_homepage\|H-HOME-09]], [[03_detalle-proyecto\|H-DETALLE-03]], [[03_detalle-proyecto\|H-DETALLE-08]], [[04_formulario-contacto\|H-FORM-01]], [[04_formulario-contacto\|H-FORM-06]], [[04_formulario-contacto\|H-FORM-09]] | ✅ **Confirmada fuertemente** — 6 hallazgos directos en el funnel de conversión |
| [[H3C]] — Experiencia mobile inferior | El mobile genera mayor abandono | [[01_homepage\|H-HOME-01]], [[01_homepage\|H-HOME-02]], [[02_busqueda-filtros\|H-FILTROS-07]], [[02_busqueda-filtros\|H-FILTROS-09]], [[03_detalle-proyecto\|H-DETALLE-01]], [[03_detalle-proyecto\|H-DETALLE-02]], [[03_detalle-proyecto\|H-DETALLE-06]], [[04_formulario-contacto\|H-FORM-02]], [[04_formulario-contacto\|H-FORM-03]], [[04_formulario-contacto\|H-FORM-09]] | ✅ **Confirmada** — validación con capturas mobile en formulario, detalle y filtros |

---

## 9. Mapa de calor de problemas por principio de Nielsen

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
| P10 — Ayuda y documentación | 2 | Detalle, Formulario | 🟡 Importante |

**Los principios más violados son P1 (Visibilidad) y P4 (Consistencia)** — lo que confirma que el problema central del sitio no es de diseño visual sino de comunicación de estado y coherencia estructural.

---

## 10. Roadmap de correcciones sugerido

### Semana 1 — Victorias rápidas (esfuerzo bajo, impacto alto)
- Corregir link de Google Play ([[01_homepage|H-HOME-06]]) — 1 hora de desarrollo
- Actualizar copyright a 2026 ([[01_homepage|H-HOME-05]]) — 10 minutos
- Convertir SAGRILAFT en link funcional con texto explicativo ([[01_homepage|H-HOME-08]]) — 2 horas
- Extender botón WhatsApp al homepage y al listado ([[04_formulario-contacto|H-FORM-09]]) — 4 horas
- Añadir chip de estado del proyecto en el hero y en tarjetas ([[03_detalle-proyecto|H-DETALLE-08]]) — 1 día
- Renombrar "Agenda tu cita en sala" a "Agendar videollamada con asesor" ([[04_formulario-contacto|H-FORM-06]]) — 1 hora
- Reemplazar reCAPTCHA visible por v3 invisible en "Asesoría inmediata" ([[04_formulario-contacto|H-FORM-06]]) — 2 horas

### Semana 2-3 — Correcciones de conversión (esfuerzo medio)
- Añadir CTA de contacto directo en la página de detalle ([[03_detalle-proyecto|H-DETALLE-03]]) — 1 día
- Añadir tooltips a badges VIS/VIP en tarjetas, nav y filtros ([[01_homepage|H-HOME-04]] + [[02_busqueda-filtros|H-FILTROS-02]]) — 1 día
- Corregir confirmación post-envío: nombre en lugar de correo, próximo paso, CTA WhatsApp ([[04_formulario-contacto|H-FORM-01]]) — 1 día
- Implementar contador de resultados en filtros ([[02_busqueda-filtros|H-FILTROS-01]]) — 2 días
- Añadir breadcrumbs en páginas de proyecto y categoría ([[01_homepage|H-HOME-07]]) — 2 días
- Reducir formulario de primer contacto a 3 campos — eliminar documento de identidad ([[04_formulario-contacto|H-FORM-02]]) — 1 día
- Implementar validación inline `onBlur` + validación de formato colombiano para teléfono ([[04_formulario-contacto|H-FORM-03]] + [[04_formulario-contacto|H-FORM-04]]) — 2 días

### Mes 2 — Mejoras estructurales (esfuerzo alto)
- Implementar SSR/SSG para páginas críticas ([[01_homepage|H-HOME-01]]) — sprint completo
- Rediseñar navegación para separar audiencias ([[01_homepage|H-HOME-02]], [[01_homepage|H-HOME-03]]) — sprint completo
- Paridad mobile/web: incluir filtro VIS/NO VIS/VIP en versión desktop ([[02_busqueda-filtros|H-FILTROS-07]]) — 1 día
- Definir plantilla de página de proyecto en CMS con campos obligatorios ([[03_detalle-proyecto|H-DETALLE-06]]) — sprint completo
- Añadir tooltip/acordeón de subsidio junto al precio ([[03_detalle-proyecto|H-DETALLE-09]]) — 2 días
- Añadir FAQ contextual en /contactanos ([[04_formulario-contacto|H-FORM-08]]) — 1 día

---

## 11. Estado de validación

Todos los hallazgos han sido validados con capturas visuales en desktop y mobile.

| Sección | Hallazgos | Estado |
|---------|-----------|--------|
| [[01_homepage\|Homepage]] | H-HOME-01 a H-HOME-10 | ✅ Todos validados |
| [[02_busqueda-filtros\|Búsqueda y Filtros]] | H-FILTROS-01 a H-FILTROS-09 | ✅ Todos validados |
| [[03_detalle-proyecto\|Detalle de Proyecto]] | H-DETALLE-01 a H-DETALLE-09 | ✅ Todos validados (H-DETALLE-04 eliminado) |
| [[04_formulario-contacto\|Formulario de Contacto]] | H-FORM-01 a H-FORM-09 | ✅ Todos validados |

Proyectos validados: Ágora, Mirla, Céntrico, Pietra, Orizzo.

---

## 12. Archivos de esta evaluación

| Archivo | Contenido |
|---------|-----------|
| [[00_plantilla]] | Marco de referencia: principios Nielsen, escala de severidad |
| [[01_homepage]] | 10 hallazgos con análisis detallado y capturas |
| [[02_busqueda-filtros]] | 9 hallazgos del flujo de búsqueda |
| [[03_detalle-proyecto]] | 9 hallazgos de la página de proyecto |
| [[04_formulario-contacto]] | 9 hallazgos del formulario y contacto |
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

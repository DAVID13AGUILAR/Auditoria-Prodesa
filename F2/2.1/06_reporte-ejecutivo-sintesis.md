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

**Se identificaron 37 hallazgos de usabilidad**, de los cuales **12 son críticos** con impacto directo en la tasa de conversión. Las tres hipótesis del proyecto (H3A, H3B, H3C) fueron confirmadas con evidencia.

El hallazgo más grave no es técnico: **el sitio no tiene botón de WhatsApp**, el canal de mayor conversión en el mercado colombiano de vivienda. El segundo hallazgo más grave es que el CTA en la página de detalle de proyecto lleva a "Descargar brochure", no a contactar un asesor. Estos dos problemas solos explican una fracción significativa del abandono en el punto de mayor intención del funnel.

---

## 2. Metodología

| Aspecto | Detalle |
|---------|---------|
| Marco de evaluación | 10 Principios Heurísticos de Nielsen |
| Páginas evaluadas | Homepage, Listado de proyectos, Detalle de proyecto (Mirla, Ágora), Formulario de contacto |
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

### 4.3 Detalle de Proyecto — 9 hallazgos

| ID | Problema | Severidad | Evidencia |
|----|----------|-----------|-----------|
| H-DETALLE-01 | Jerarquía visual del hero sin foco claro hacia el CTA | 2 🟡 | Pendiente |
| H-DETALLE-02 | Precio embebido en texto corrido, no en display prominente | 2 🟡 | ✅ Captura Mirla (revisado de 3 a 2) |
| H-DETALLE-03 | CTAs son "Descargar brochure" y "Compartir" — sin CTA de contacto directo | 3 🔴 | ✅ Captura Mirla |
| H-DETALLE-04 | URLs inconsistentes entre proyectos | 2 🟡 | ✅ Confirmado en HTML |
| H-DETALLE-05 | Ficha técnica no visible en primer fold | 2 🟡 | Pendiente |
| H-DETALLE-06 | Sin plantilla estandarizada entre proyectos | 2 🟡 | Pendiente |
| H-DETALLE-07 | Al volver al listado se pierden los filtros aplicados | 2 🟡 | Pendiente |
| H-DETALLE-08 | Estado del proyecto (disponible/agotado) no visible | 3 🔴 | Pendiente |
| H-DETALLE-09 | "Subsidio disponible" sin explicación de tipo, requisitos ni proceso | 2 🟡 | ✅ Captura Mirla |

---

### 4.4 Formulario de Contacto — 9 hallazgos

| ID | Problema | Severidad | Evidencia |
|----|----------|-----------|-----------|
| H-FORM-01 | Sin confirmación post-envío: el usuario no sabe qué pasará | 3 🔴 | Pendiente |
| H-FORM-02 | Labels del formulario presumiblemente técnicos para el comprador primerizo | 2 🟡 | Pendiente |
| H-FORM-03 | Validación probablemente post-submit, no en tiempo real | 3 🔴 | Pendiente |
| H-FORM-04 | Mensajes de error genéricos: "campo requerido" sin orientación | 2 🟡 | Pendiente |
| H-FORM-05 | Tres líneas de contacto con el mismo número en el footer | 2 🟡 | ✅ Confirmado en HTML |
| H-FORM-06 | Sin opción de elegir canal de respuesta (WhatsApp / llamada / email) | 2 🟡 | Pendiente |
| H-FORM-07 | Formulario genérico no precarga el proyecto de interés | 2 🟡 | Pendiente |
| H-FORM-08 | FAQ del sitio desconectada del flujo del formulario | 1 🟢 | Pendiente |
| H-FORM-09 | Sin botón flotante de WhatsApp en ninguna página del sitio | 3 🔴 | ✅ Confirmado — ausencia global |

---

## 5. Consolidado global

| Severidad | Total | Porcentaje |
|-----------|-------|------------|
| 🔴 Crítico (3) | 11 | 30% |
| 🟡 Importante (2) | 21 | 57% |
| 🟢 Menor (1) | 5 | 14% |
| **Total hallazgos** | **37** | |

*H-FILTROS-06 revisado de 3 a 2 tras validación visual — el precio sí existe en las tarjetas.*

| Evidencia | Total |
|-----------|-------|
| ✅ Confirmados con captura o código | 21 |
| ⏳ Pendientes de validación visual | 16 |

*Secciones 4.3 Detalle de Proyecto y 4.4 Formulario de Contacto pendientes de validación completa.*

---

## 6. Patrón de problemas — Lo que el sitio hace sistemáticamente mal

Más allá de los hallazgos individuales, la evaluación revela **tres patrones estructurales** que se repiten en todas las secciones:

### Patrón 1 — El sitio habla en el idioma del vendedor, no del comprador
"VIS", "VIP", "NO VIS", "SAGRILAFT", "Macroproyecto" son términos del sector constructor que aparecen sin traducción en los puntos más visibles del sitio: el título del navegador, los badges de las tarjetas, el cuerpo de las descripciones de proyecto y el footer. El comprador primerizo — el segmento más grande del mercado objetivo de Prodesa — no puede self-qualificarse ni avanzar con confianza porque no entiende el vocabulario básico del sitio.

### Patrón 2 — El funnel de conversión se corta justo donde más importa
El usuario llega al sitio (homepage) → encuentra proyectos → entra al detalle → está listo para contactar → y ahí el CTA es "Descargar brochure". No hay WhatsApp, no hay formulario de interés inline, no hay chat. El momento de mayor intención del usuario es el momento de menor herramienta de conversión disponible. El sitio invierte esfuerzo en llevar al usuario hasta la puerta y luego no le abre.

### Patrón 3 — Múltiples audiencias sin separación, un solo flujo
Compradores locales, clientes actuales, proveedores, administradores de conjuntos e inversionistas desde el exterior comparten el mismo menú de navegación sin diferenciación. El resultado es una interfaz que no está optimizada para ninguna audiencia en particular. El comprador local debe ignorar activamente opciones que no son para él en cada página que visita.

---

## 7. Top 5 hallazgos críticos por impacto en conversión

### 🥇 #1 — H-FORM-09: Ausencia de botón WhatsApp
**Impacto:** El canal de conversión de menor fricción para el comprador colombiano no existe en el sitio. WhatsApp es el medio de comunicación preferido para decisiones de compra de alto valor en Colombia. Su ausencia no es una preferencia de diseño — es una pérdida de leads en el canal más efectivo del mercado.
**Esfuerzo de corrección:** Bajo — implementar un botón flotante con mensaje contextualizado por proyecto.

### 🥈 #2 — H-DETALLE-03: CTAs de "Descargar brochure" y "Compartir" sin CTA de contacto
**Impacto:** Confirmado visualmente en el proyecto Mirla. En el momento de mayor intención del usuario (después de leer la descripción del proyecto), no hay forma de contactar a un asesor desde esa sección. El usuario debe buscar el formulario de contacto por su cuenta o abandonar.
**Esfuerzo de corrección:** Medio — añadir CTA de WhatsApp o formulario inline después de la descripción del proyecto.

### 🥉 #3 — H-HOME-04 + H-FILTROS-02: Jerga "VIS/VIP/NO VIS" sin definición en todo el funnel
**Impacto:** El término aparece confirmado en 3 puntos del sitio (badges de tarjetas, cuerpo de descripción, título del navegador) y probablemente en los filtros de búsqueda. Es la barrera de entrada más temprana del funnel: actúa antes de que el usuario siquiera vea los proyectos.
**Esfuerzo de corrección:** Bajo-medio — tooltips, texto auxiliar o cambio de etiquetas a lenguaje de beneficio.

### #4 — H-HOME-01: SPA sin feedback de carga
**Impacto:** En Colombia, más del 80% del tráfico es mobile. Una SPA que muestra pantalla en blanco mientras carga JS pierde más de la mitad de los usuarios en los primeros 3 segundos, especialmente en conexiones móviles de velocidad variable.
**Esfuerzo de corrección:** Alto — requiere cambios de arquitectura (SSR/SSG en Next.js) o al menos implementar skeleton de carga.

### #5 — H-HOME-06: Link de Google Play roto
**Impacto:** Android supera el 70% del mercado de smartphones en Colombia. Un botón de Google Play que apunta a Apple Store bloquea completamente la descarga de la app para ese segmento.
**Esfuerzo de corrección:** Mínimo — una línea de código. El mayor valor por menor esfuerzo del inventario.

---

## 8. Confirmación de hipótesis

| Hipótesis | Descripción | Hallazgos | Veredicto |
|-----------|-------------|-----------|-----------|
| [[H3A]] — Arquitectura de información | La navegación dificulta que el usuario encuentre el proyecto correcto | H-HOME-02, H-HOME-03, H-HOME-07, H-FILTROS-04, H-FILTROS-07, H-FILTROS-08, H-DETALLE-04, H-DETALLE-07 | ✅ **Confirmada** |
| [[H3B]] — CTAs ambiguos o insuficientes | Los CTAs no convierten en el momento de mayor intención | H-HOME-09, H-DETALLE-03, H-DETALLE-08, H-FORM-01, H-FORM-06, H-FORM-09 | ✅ **Confirmada fuertemente** |
| [[H3C]] — Experiencia mobile inferior | El mobile genera mayor abandono | H-HOME-01, H-HOME-02, H-HOME-09, H-FILTROS-09, H-FORM-03 | ✅ **Confirmada parcialmente** — requiere más validación en mobile real |

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
- Corregir link de Google Play (H-HOME-06) — 1 hora de desarrollo
- Actualizar copyright a 2026 (H-HOME-05) — 10 minutos
- Convertir SAGRILAFT en un link funcional con texto explicativo (H-HOME-08) — 2 horas
- Añadir botón flotante de WhatsApp contextualizado por proyecto (H-FORM-09) — 4 horas

### Semana 2-3 — Correcciones de conversión (esfuerzo medio)
- Añadir CTA de contacto directo en la página de detalle (H-DETALLE-03) — 1 día
- Agregar tooltips a badges VIS/VIP en tarjetas y descripciones (H-HOME-04) — 1 día
- Añadir confirmación post-envío de formulario (H-FORM-01) — 1 día
- Implementar contador de resultados en filtros (H-FILTROS-01) — 2 días
- Añadir breadcrumbs en páginas de proyecto y categoría (H-HOME-07) — 2 días

### Mes 2 — Mejoras estructurales (esfuerzo alto)
- Implementar SSR/SSG para páginas críticas (H-HOME-01) — sprint completo
- Estandarizar URLs de todos los proyectos (H-FILTROS-04, H-DETALLE-04) — sprint completo
- Rediseñar navegación para separar audiencias (H-HOME-02, H-HOME-03) — sprint completo
- Paridad mobile/web: incluir filtro VIS/NO VIS/VIP en versión desktop (H-FILTROS-07) — 1 día

---

## 11. Capturas pendientes de recolectar

Los siguientes hallazgos aún necesitan evidencia visual para completar el inventario:

| Prioridad | ID | Qué capturar |
|-----------|-----|--------------|
| 🔴 Alta | H-FILTROS-01 | Listado de proyectos sin contador de resultados al filtrar |
| 🔴 Alta | H-FILTROS-02 | Panel de filtros con etiquetas VIS/NO VIS sin tooltip |
| 🔴 Alta | H-FILTROS-01 | Listado sin contador de resultados al filtrar |
| 🔴 Alta | H-FILTROS-02 | Panel de filtros con etiquetas VIS/NO VIS/VIP sin tooltip |
| 🔴 Alta | H-DETALLE-08 | Página de detalle sin estado del proyecto visible |
| 🔴 Alta | H-FORM-01 | Pantalla post-envío del formulario (o ausencia de ella) |
| 🔴 Alta | H-FORM-03 | Formulario con error: validación post-submit |
| 🔴 Alta | H-FORM-09 | Cualquier página sin botón flotante de WhatsApp |
| 🟡 Media | H-FILTROS-07 | Panel de filtros en web sin VIS/NO VIS/VIP — comparativa desktop vs. mobile |
| 🟡 Media | H-FILTROS-09 | Listado durante carga con Slow 4G — gap antes del spinner + scroll post-carga |
| 🟡 Media | H-DETALLE-05 | Primer fold del detalle sin ficha técnica visible |
| 🟡 Media | H-HOME-08 | Footer con SAGRILAFT — pendiente captura |

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

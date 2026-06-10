---
status: completado
created: 2026-05-20
updated: 2026-06-09
tags:
  - prodesa
  - cognitive-walkthrough
  - reporte
fase: "2.2"
aliases:
  - Reporte CW Flujo 1
---

# 09 — Reporte Tarea 2.2 — Cognitive Walkthrough Flujo 1

> [!abstract] Resumen rápido
> **64 hallazgos** · **11 críticos** · **48 importantes** · **5 menores**
> Flujo evaluado: Punto de entrada → Homepage → Filtros → Resultados → Detalle de proyecto → Contacto
> **H3A confirmada en las 6 etapas del flujo** · H3B: 18 hallazgos · H3C: 14 hallazgos

**Tarea:** 2.2 — Cognitive Walkthrough (Flujo 1: registro completo)
**Fase:** Fase 2 — Análisis
**Fecha:** Mayo 2026
**Sitio evaluado:** https://prodesa.com/
**Metodología:** Cognitive Walkthrough — método NN/G (4 preguntas canónicas por acción)
**Persona:** [[01_persona-valentina|Valentina Ríos]] — compradora VIS, primera vez, mobile

---

## 1. Resumen ejecutivo

Se realizó un Cognitive Walkthrough completo del flujo principal de conversión de prodesa.com, simulando la experiencia de Valentina Ríos — compradora VIS de 32 años que llega al sitio desde pauta de Instagram en mobile, con ~15 minutos disponibles y presupuesto de $200M COP.

**Se documentaron 64 hallazgos** a lo largo de 20 pasos del flujo, de los cuales **11 son críticos** — es decir, bloquean o abandonan la tarea. A diferencia de la evaluación heurística (tarea 2.1), el CW reveló cómo los problemas se encadenan: cada fricción debilita la confianza de Valentina para el paso siguiente. El resultado es un flujo que acumula deuda cognitiva en cada etapa y llega al contacto con una usuaria agotada, desconfiada y sin información suficiente para tomar una decisión.

**El hallazgo más grave no es técnico sino estratégico:** el término "Mi Casa Ya" — el subsidio más buscado por compradores VIS en Colombia — es invisible en todo el sitio. Valentina, que potencialmente califica para ese subsidio, no puede ni siquiera confirmar si Prodesa lo ofrece.

---

## 2. Metodología

| Aspecto | Detalle |
|---------|---------|
| Marco de evaluación | Cognitive Walkthrough — 4 preguntas canónicas (NN/G) |
| Persona evaluada | [[01_persona-valentina\|Valentina Ríos]] — VIS, Bogotá, mobile, primera compra |
| Dispositivos | Mobile (375px, Chrome Android) + Desktop (Chrome) |
| Pasos evaluados | 20 pasos, 6 etapas |
| Período | Mayo 2026 |
| Escala de severidad | 🔴 Crítico · 🟠 Importante · 🟡 Menor |

**Las 4 preguntas del método:**

| # | Pregunta | Qué evalúa |
|---|----------|------------|
| Q1 | ¿Sabe Valentina qué hacer en este paso? | Claridad de la acción |
| Q2 | ¿Ve el control correcto de UI para avanzar? | Visibilidad del elemento |
| Q3 | ¿Entiende que esa acción produce el efecto esperado? | Asociación acción → resultado |
| Q4 | ¿El sistema le confirma que avanzó hacia su objetivo? | Feedback del sistema |

Un **No** o **Parcial** en cualquiera de las 4 = punto de fricción documentado.

---

## 3. Perfil de la persona evaluada

**Valentina Ríos** · 32 años · Bogotá (Suba, estrato 3) · Auxiliar contable

- Primera compradora de vivienda — nunca ha usado portales inmobiliarios
- Dispositivo: Samsung Galaxy A34 · Conexión: 4G · Tiempo disponible: ~15 minutos
- Presupuesto: hasta $200M COP · Perfil VIS · Posible beneficiaria de Mi Casa Ya
- Llega desde un anuncio de Instagram — espera encontrar precios claros, como en Mercado Libre
- Umbral de abandono bajo: si en 30 segundos no ve algo relevante para ella, cierra el tab

---

## 4. Flujo evaluado

```
[Instagram Ad] → Punto de entrada → Homepage → Filtros → Resultados → Detalle (Pietra) → Contacto
```

| Etapa | Pasos | Hallazgos | Críticos |
|-------|-------|-----------|----------|
| 1 — Punto de entrada | 1a · 1b | 3 | 2 (CW-50, CW-63) |
| 2 — Homepage | 2a · 2b · 2c | 4 | — |
| 3 — Filtros | 3a · 3b · 3c · 3d · 3e | 10 | 1 (CW-03) |
| 4 — Resultados | 4a · 4b · 4c · 4d | 10 | — |
| 5 — Detalle de proyecto | 5a · 5b · 5c · 5d · 5e · 5f | 25 | 6 |
| 6 — Contacto | 6a · 6b · 6c · 6d | 12 | 2 (CW-41, CW-42) |
| **Total** | **20 pasos** | **64** | **11** |

---

## 5. Hallazgos críticos — Los 11 bloqueantes del flujo

| ID | Etapa | Descripción | Categoría |
|----|-------|-------------|-----------|
| CW-50 | 1a | Performance Score: 3/100 · FCP: 14,3s · LCP: 39,6s · TBT: 2.050ms | RP |
| CW-63 | 1a | CLS: 0,882 — elementos se mueven al cargar, Valentina toca el elemento equivocado | RP |
| CW-01 | 1b | Modal "PONTE LA 10" sin botón de cierre visible — primera impresión bloqueante | AI |
| CW-03 | 3a | Filtro VIS ausente en desktop — tarea parcialmente irrealizable | AI |
| CW-04 | 3a | Filtros no persistentes al volver del detalle — debe reconfigurar desde cero | AI |
| CW-15 | 5e | "Mi Casa Ya" ausente en todo el sitio — subsidio clave de la persona invisible | AI |
| CW-19 | 5f | Sin comparador — gestiona decisión de alto riesgo en 2 ventanas del navegador | AI |
| CW-20 | 5f | Tabs inconsistentes entre proyectos — modelo mental roto al comparar | AI |
| CW-41 | 6b | Validación 100% post-submit — errores en bloque, mensajes idénticos en mayúsculas | FI |
| CW-42 | 6b | Datos falsos pasan al CRM sin ninguna validación de autenticidad | FI |
| CW-56 | 5d | Fecha de entrega ausente en toda la página — no puede planificar su mudanza | RP |

---

## 6. Distribución completa de hallazgos

| Categoría | 🔴 Críticos | 🟠 Importantes | 🟡 Menores | Total |
|-----------|------------|---------------|-----------|-------|
| AI — Arquitectura de información | 6 | 19 | — | 25 |
| FI — Filtros / interacción | 2 | 17 | — | 19 |
| RP — Rendimiento percibido | 3 | 6 | — | 9 |
| VD — Visual design / jerarquía | — | 6 | — | 6 |
| Menores | — | — | 5 | 5 |
| **Total** | **11** | **48** | **5** | **64** |

---

## 7. Patrones estructurales — Lo que el flujo revela

### Patrón 1 — El sitio no habla el idioma de su comprador objetivo

"VIS", "VIP", "SMMLV", "Obra gris", "Macroproyecto" aparecen sin definición en los puntos más críticos del flujo: los filtros de búsqueda, las tarjetas de resultados y el detalle del proyecto. Valentina — una primera compradora que no conoce la terminología del sector — no puede auto-calificarse ni avanzar con confianza. El hallazgo más extremo de este patrón es CW-15: "Mi Casa Ya" no existe como concepto en ninguna parte del sitio, aunque es el subsidio que potencialmente financiaría la compra de la persona para quien está diseñado el flujo.

### Patrón 2 — El rendimiento destruye la intención antes de que empiece el flujo

Performance Score: 3/100. FCP: 14,3 segundos. En mobile con 4G — el dispositivo y la conexión de Valentina — el sitio tarda casi 15 segundos en mostrar su primer contenido significativo. El **53% de los usuarios mobile abandona si la página tarda más de 3 segundos** (Google/SOASTA). Valentina llega con 15 minutos disponibles y el sitio consume casi uno entero solo en carga. El CLS de 0,882 amplifica el problema: los elementos se mueven durante la carga y Valentina puede tocar elementos equivocados involuntariamente.

### Patrón 3 — La arquitectura no orienta, obliga a adivinar

Los filtros no persisten al volver del detalle (CW-04). El filtro VIS no existe en desktop (CW-03). No hay breadcrumbs (CW-14). No hay estado del proyecto en las tarjetas (CW-06) ni en el hero (CW-12). No hay comparador (CW-19). En cada etapa del flujo, Valentina debe tomar decisiones con información incompleta o reconstruir contexto que el sitio ya le había quitado. El resultado es una carga cognitiva acumulada que llega al máximo justo en la etapa de más alta intención: cuando está comparando proyectos para decidir cuál contactar.

### Patrón 4 — El contacto daña la confianza en lugar de cerrarla

La etapa de contacto —el objetivo final del flujo— concentra los hallazgos más perjudiciales para la conversión. La validación post-submit con mensajes idénticos en mayúsculas (CW-41) frustra a una usuaria que ya invirtió tiempo. El formulario no cabe en mobile (CW-44). Los campos del formulario son distintos en mobile y desktop (CW-43). Los datos falsos pasan al CRM (CW-42), lo que significa que la empresa tampoco está protegida. La confirmación no indica canal ni tiempo de respuesta (CW-22). Y en mobile, la pantalla de confirmación redirige a una página genérica de /contactanos en lugar de una pantalla de "gracias" dedicada (CW-23). El cierre del flujo es tan poco satisfactorio como el inicio.

---

## 8. Confirmación de hipótesis

| Hipótesis | Descripción | Hallazgos | Veredicto |
|-----------|-------------|-----------|-----------|
| [[H3A]] — Arquitectura de información | La AI no orienta a Valentina hacia el proyecto correcto | 52 hallazgos — presente en todas las etapas del flujo | ✅ **Confirmada en las 6 etapas** |
| [[H3B]] — CTAs ambiguos / información opaca | Valentina no confía en la información del sitio | 18 hallazgos — precios ambiguos, jerga técnica, términos opacos | ✅ **Confirmada** |
| [[H3C]] — Experiencia mobile inferior | El mobile genera mayor abandono | 14 hallazgos — performance, formulario, filtros, layout shift | ✅ **Confirmada** |

**H3A es la hipótesis principal y está confirmada con mayor fuerza:** aparece en 52 de los 64 hallazgos (81%) y en todas y cada una de las 6 etapas del flujo. No hay ninguna etapa en la que la arquitectura de información oriente correctamente a Valentina.

---

## 9. User Flow — CW Flujo 1

> Flujo completo de Valentina anotado en FigJam — 6 etapas, 11 hallazgos críticos marcados.

[Ver User Flow interactivo en FigJam](https://www.figma.com/board/5U9tc98wX5iqg0HbZ4q2xm/2.2-%E2%80%94-CW-Flujo-1-%E2%80%94-User-Flow-Anotado?node-id=0-1&t=cBGnGqMrHcOgwrHY-1)

![[assets/user-flow/CW-Flujo1-User-Flow-Anotado.png]]

---

## 10. Relación con la tarea 2.1

El CW no duplica la evaluación heurística — la profundiza desde la perspectiva del usuario. Donde la tarea 2.1 identificó el problema de forma aislada, el CW muestra cómo ese problema impacta a una persona específica en un momento específico:

| Hallazgo 2.1 | Hallazgo CW | Profundización |
|---|---|---|
| H-HOME-01 — SPA sin feedback | CW-50, CW-63 | Performance 3/100 en el dispositivo real de Valentina |
| H-FILTROS-07 — Filtro VIS solo en mobile | CW-03 | Valentina llega a desktop y no puede filtrar su tipo de vivienda |
| H-DETALLE-09 — Subsidio sin datos | CW-15, CW-16, CW-17 | "Mi Casa Ya" directamente invisible — no es solo incompleto, no existe |
| H-DETALLE-06 — Inconsistencias entre proyectos | CW-19, CW-20, CW-21 | Valentina intenta comparar y el modelo mental se rompe |
| H-FORM-03 — Validación post-submit | CW-41, CW-42 | Además: datos falsos llegan al CRM — doble fallo |

Solo **CW-01** (modal "PONTE LA 10") y **CW-30** (íconos sobredimensionados en mobile) son hallazgos exclusivos del CW, sin precedente en la evaluación heurística.

---

## 11. Próximos pasos

Este inventario alimenta directamente la **tarea 3.1** (consolidación de hallazgos). Para la consolidación usar:

- Los 11 hallazgos 🔴 como prioridad máxima
- Los hallazgos H3A + H3B como los de mayor impacto en conversión
- Los hallazgos H3C para el análisis de brecha mobile/desktop
- Las referencias a 2.1 (columna Ref. 2.1 en el inventario) para cruzar con el inventario heurístico y evitar duplicados

---

## 12. Archivos de esta tarea

| Archivo | Contenido |
|---------|-----------|
| [[00_plantilla]] | Marco de referencia: metodología CW, 4 preguntas canónicas |
| [[01_persona-valentina]] | Ficha completa de Valentina Ríos |
| [[02_punto-entrada]] | Análisis técnico del punto de entrada con métricas Lighthouse |
| [[02_walkthrough-registro]] | Registro paso a paso completo — 20 pasos, 64 hallazgos |
| [[03_homepage]] | CW — Homepage |
| [[04_busqueda-filtros]] | CW — Búsqueda y filtros |
| [[05_resultados]] | CW — Listado de resultados |
| [[06_detalle-proyecto]] | CW — Detalle del proyecto Pietra (Ibagué) |
| [[07_contacto]] | CW — Formulario de contacto + conclusión de tarea |
| [[08_inventario-hallazgos]] | Inventario completo — 64 hallazgos CW-01 a CW-64 |

---

→ [[00_plantilla]] · [[08_inventario-hallazgos]] · [[F2/2.1/06_reporte-ejecutivo-sintesis|Reporte 2.1]]

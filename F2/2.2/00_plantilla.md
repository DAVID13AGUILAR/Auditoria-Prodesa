---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - plantilla
  - referencia
aliases:
  - Referencia Walkthrough
  - Plantilla CW Flujo 1
---

# Plantilla — Cognitive Walkthrough Flujo 1 — Prodesa.com
**Tarea:** 2.2 — Cognitive Walkthrough (Flujo 1: Homepage → Detalle de proyecto)
**Proyecto:** Evaluación de usabilidad prodesa.com
**Fecha de evaluación:** Mayo 2026
**URL base:** https://prodesa.com/
**Hipótesis vinculada:** [[H3A]]

---

## Contexto de la tarea

Un usuario nuevo llega por primera vez al sitio desde pauta pagada (Instagram). Es comprador VIS o No-VIS que no conoce el sitio ni la marca. **Si la arquitectura de información no lo orienta rápidamente, abandona antes de ver el proyecto correcto para su perfil.**

Este walkthrough documenta ese recorrido paso a paso — desde el primer pixel visible hasta que logra (o no logra) ver el precio de un proyecto que corresponde a su perfil.

---

## Alcance

Recorrido desde la homepage hasta el detalle de un proyecto específico con perfil de usuario definido (comprador VIS en Bogotá, presupuesto hasta $200M COP). Se documenta cada paso respondiendo 4 preguntas canónicas:

- ¿Sabe Valentina qué hacer?
- ¿Ve el control correcto para avanzar?
- ¿Entiende que esa acción produce el efecto que espera?
- ¿El sistema le confirma que avanzó hacia su objetivo?

---

## Objetivo

Evaluar si un usuario nuevo puede encontrar el proyecto correcto para su perfil **sin fricción ni confusión**.

---

## Outputs de esta tarea

| Output | Descripción |
|--------|-------------|
| [[01_persona-valentina]] | Ficha completa del usuario objetivo |
| [[02_walkthrough-registro]] | Registro paso a paso con puntos de fricción |
| [[03_hallazgos-clasificados]] | Hallazgos agrupados por categoría y clasificados por severidad |

> El registro de esta tarea alimenta directamente la **sección "Cognitive Walkthrough — Flujo 1"** del informe final (tarea 3.1).

---

## Flujo evaluado

```
[Instagram Ad] → Homepage → Búsqueda + Filtros → Resultados → Detalle de proyecto
```

| Paso | Pantalla | URL de referencia |
|------|----------|-------------------|
| 1 | Punto de entrada — homepage desde pauta | prodesa.com/ |
| 2 | Homepage — orientación y CTA principal | prodesa.com/ |
| 3 | Búsqueda y aplicación de filtros | prodesa.com/ (sección proyectos) |
| 4 | Página de resultados | prodesa.com/ (resultados filtrados) |
| 5 | Detalle del proyecto seleccionado | prodesa.com/proyectos/[slug] |

---

## Metodología — Cognitive Walkthrough

El evaluador adopta el rol de la persona definida ([[01_persona-valentina]]) y recorre el flujo respondiendo **4 preguntas canónicas por cada acción** (método NN/G):

| # | Pregunta | Qué evalúa |
|---|----------|------------|
| **Q1** | ¿Sabrá Valentina qué hacer en este paso? | Claridad de la acción |
| **Q2** | ¿Verá el control correcto de UI para avanzar? | Visibilidad del elemento |
| **Q3** | ¿Entenderá que esa acción produce el efecto que espera? | Asociación acción → resultado |
| **Q4** | Después de actuar, ¿el sistema le confirma que avanzó? | Feedback del sistema |

Una respuesta **No** o **Parcial** en cualquiera de las 4 preguntas = punto de fricción a documentar.

> Diferencia con la tarea 2.1: la evaluación heurística juzgó el sitio contra principios de Nielsen desde la perspectiva del evaluador experto. El CW simula la cognición de Valentina — alguien que nunca ha usado el sitio y no sabe qué esperar.

---

## Estructura del registro de walkthrough

Cada acción del usuario se registra con esta estructura:

```
| Paso # | Acción esperada | Q1 ¿Sabe qué hacer? | Q2 ¿Ve el control? | Q3 ¿Entiende causa→efecto? | Q4 ¿El sistema confirma progreso? | Fricción detectada | Severidad | Captura |
```

- **Paso #:** Número secuencial dentro del flujo
- **Acción esperada:** Qué haría Valentina en este momento (ej. "Hace clic en el buscador")
- **Q1–Q4:** Sí / No / Parcial — con justificación breve en cada celda
- **Fricción detectada:** Descripción del problema. Si aplica, referencia cruzada al hallazgo de [[F2/2.1/05_inventario-final]]
- **Severidad:** 🔴 / 🟠 / 🟡
- **Captura:** Referencia al screenshot anotado (`pendiente` si no hay)

---

## Escala de severidad

| Nivel | Código | Descripción |
|-------|--------|-------------|
| 🔴 Crítico | 3 | Bloquea completar la tarea — Valentina abandona |
| 🟠 Importante | 2 | Genera fricción significativa — ralentiza o genera duda |
| 🟡 Menor | 1 | Molestia sin impacto severo en la tarea |

---

## Categorías de hallazgos

| Categoría | Descripción |
|-----------|-------------|
| **AI** | Arquitectura de información — navegación, orientación, jerarquía |
| **VD** | Visual design / jerarquía visual — qué llama la atención y en qué orden |
| **FI** | Filtros / interacción — comportamiento de controles y feedback |
| **RP** | Rendimiento percibido — tiempos de carga, feedback de estado |

---

## Archivos de esta tarea

| Archivo | Contenido |
|---------|-----------|
| [[01_persona-valentina]] | Ficha de Valentina Ríos — perfil VIS, contexto de llegada, modelo mental |
| [[02_walkthrough-registro]] | Tabla de registro paso a paso del flujo completo |
| [[03_hallazgos-clasificados]] | Hallazgos agrupados por categoría, clasificados por severidad, vinculados a H3A |

---

## Hipótesis vinculada

| Hipótesis | Descripción |
|-----------|-------------|
| [[H3A]] | Problemas en la arquitectura de información y navegación impiden que el usuario encuentre el proyecto correcto para su perfil — genera abandono antes de la conversión |

---

→ [[01_persona-valentina]] · [[02_walkthrough-registro]] · [[03_hallazgos-clasificados]]

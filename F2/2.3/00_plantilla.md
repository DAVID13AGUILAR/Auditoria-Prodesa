---
status: referencia
created: 2026-06-09
tags:
  - prodesa
  - cognitive-walkthrough
  - plantilla
  - referencia
aliases:
  - Referencia Walkthrough Flujo 2
  - Plantilla CW Flujo 2
fase: "2.3"
---

# Plantilla — Cognitive Walkthrough Flujo 2 — Prodesa.com
**Tarea:** 2.3 — Cognitive Walkthrough (Flujo 2: Registro y contacto)
**Proyecto:** Evaluación de usabilidad prodesa.com
**Fecha de evaluación:** Junio 2026
**URL base:** https://prodesa.com/
**Hipótesis vinculada:** [[H3B]]

---

## Contexto de la tarea

El usuario ya encontró un proyecto de interés. Ha leído la descripción, el precio le encaja y quiere dar el siguiente paso: contactar a un asesor. **El formulario es el último paso antes de convertirse en lead. Un CTA poco visible, un formulario confuso o una confirmación débil pueden perder una venta en ese momento.**

Este walkthrough documenta ese recorrido desde el CTA de contacto en la página de proyecto hasta la confirmación de envío — evaluando copy del CTA, campos requeridos vs. opcionales, feedback del sistema, micro-copy y confianza transmitida.

---

## Alcance

Desde el CTA de contacto en la página de detalle del proyecto hasta la confirmación de envío. Se evalúa:

- Visibilidad y claridad del CTA de contacto
- Campos requeridos vs. opcionales — orden y jerarquía
- Feedback del sistema durante el llenado (validación inline vs. post-submit)
- Micro-copy: labels, placeholders, mensajes de error, texto de ayuda
- Confianza transmitida en cada micro-momento
- Pantalla de confirmación post-envío

---

## Objetivo

Evaluar si el proceso de registro y contacto es claro, motivador y libre de fricción en el momento decisivo de conversión.

---

## Outputs de esta tarea

| Output | Descripción |
|--------|-------------|
| [[01_persona]] | Ficha del usuario en el momento de contacto |
| [[02_cta-contacto]] | Evaluación del CTA: visibilidad, copy, jerarquía |
| [[03_formulario]] | Campos, orden, micro-copy, confianza |
| [[04_feedback-validacion]] | Feedback del sistema durante el llenado |
| [[05_confirmacion-postenvio]] | Pantalla de confirmación — tono, próximo paso, retención |
| [[06_inventario-hallazgos]] | Inventario consolidado con severidad e hipótesis |
| [[07_reporte-tarea-2.3]] | Reporte ejecutivo de la tarea |

> El registro de esta tarea alimenta directamente la **sección "Cognitive Walkthrough — Flujo 2"** del informe final (tarea 3.1).

---

## Flujo evaluado

```
[Página de detalle del proyecto] → CTA de contacto → Formulario → Envío → Confirmación
```

| Paso | Pantalla | Descripción |
|------|----------|-------------|
| 1 | Detalle del proyecto | Identificar y evaluar el CTA de contacto |
| 2 | Formulario de contacto | Campos, jerarquía, micro-copy |
| 3 | Feedback del sistema | Validación inline, mensajes de error |
| 4 | Confirmación post-envío | Qué ocurre después del envío |

---

## Metodología — Cognitive Walkthrough

El evaluador adopta el rol de la persona definida ([[01_persona]]) y recorre el flujo respondiendo **4 preguntas canónicas por cada acción** (método NN/G):

| # | Pregunta | Qué evalúa |
|---|----------|------------|
| **Q1** | ¿Sabe el usuario qué hacer en este paso? | Claridad de la acción |
| **Q2** | ¿Ve el control correcto de UI para avanzar? | Visibilidad del elemento |
| **Q3** | ¿Entiende que esa acción produce el efecto que espera? | Asociación acción → resultado |
| **Q4** | Después de actuar, ¿el sistema le confirma que avanzó? | Feedback del sistema |

Una respuesta **No** o **Parcial** en cualquiera de las 4 preguntas = punto de fricción a documentar.

---

## Estructura del registro de walkthrough

Cada acción se registra con esta estructura:

```
| Paso # | Acción esperada | Q1 ¿Sabe qué hacer? | Q2 ¿Ve el control? | Q3 ¿Entiende causa→efecto? | Q4 ¿El sistema confirma progreso? | Fricción detectada | Severidad | Captura |
```

---

## Escala de severidad

| Nivel | Código | Descripción |
|-------|--------|-------------|
| 🔴 Crítico | 3 | Bloquea completar la tarea — el usuario abandona |
| 🟠 Importante | 2 | Genera fricción significativa — ralentiza o genera duda |
| 🟡 Menor | 1 | Molestia sin impacto severo en la tarea |

---

## Categorías de hallazgos

| Categoría | Descripción |
|-----------|-------------|
| **CC** | Copy y CTAs — visibilidad, claridad, jerarquía de los botones de contacto |
| **FC** | Formulario y campos — orden, obligatoriedad, micro-copy |
| **FS** | Feedback del sistema — validación, mensajes de error, latencia |
| **PC** | Post-conversión — confirmación, confianza, retención |

---

→ [[01_persona]] · [[02_cta-contacto]] · [[03_formulario]] · [[04_feedback-validacion]] · [[05_confirmacion-postenvio]] · [[06_inventario-hallazgos]] · [[07_reporte-tarea-2.3]]

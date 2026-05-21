---
created: 2026-05-20
tags:
  - research
  - cognitive-walkthrough
  - metodologia
  - tarea-2.2
fuentes:
  - https://www.nngroup.com/articles/cognitive-walkthroughs/
  - https://blog.logrocket.com/ux-design/cognitive-walkthrough-usability-testing-guide-template/
  - https://blog.uxtweak.com/cognitive-walkthrough/
---

# Research — Metodología Cognitive Walkthrough

## Definición (NN/G)

Método de inspección de usabilidad **basado en tareas** en el que el evaluador recorre cada paso de un flujo respondiendo preguntas prescritas, con el objetivo de identificar qué aspectos de la interfaz serían difíciles para **usuarios nuevos**.

> Diferencia clave con la evaluación heurística (tarea 2.1): la heurística evalúa principios generales desde la perspectiva del analista. El CW simula la cognición de un usuario nuevo que **no sabe qué esperar**.

---

## Las 4 preguntas del método

Por cada acción del flujo, el evaluador responde:

| # | Pregunta | Qué evalúa |
|---|----------|------------|
| **Q1** | ¿Sabrá el usuario qué hacer en este paso? | Claridad de la acción |
| **Q2** | ¿Verá el elemento correcto de UI para avanzar? | Visibilidad del control |
| **Q3** | ¿Entenderá que esa acción produce el efecto deseado? | Asociación acción → resultado |
| **Q4** | Después de actuar, ¿verá que avanzó hacia su objetivo? | Feedback del sistema |

Una respuesta **No** o **Parcial** en cualquiera = punto de fricción a documentar.

---

## Estructura del registro

Cada paso del flujo se documenta con:

| Campo | Descripción |
|-------|-------------|
| Paso # | Número secuencial |
| Acción esperada | Qué haría el usuario en este punto |
| Q1 — ¿Es obvio qué hacer? | Sí / No / Parcial + justificación |
| Q2 — ¿Ve el control correcto? | Sí / No / Parcial + justificación |
| Q3 — ¿Entiende causa→efecto? | Sí / No / Parcial + justificación |
| Q4 — ¿El sistema confirma progreso? | Sí / No / Parcial + justificación |
| Fricción detectada | Descripción del problema + severidad |
| Captura | Referencia al screenshot |

---

## Aplicación a flujos de búsqueda y filtrado

Para un flujo de búsqueda inmobiliaria, las preguntas más críticas son:

- **Q1 en filtros:** ¿Sabe el usuario que puede filtrar por VIS/No-VIS? ¿Lo ve sin scrollear?
- **Q2 en filtros:** ¿El control de filtro es visible y reconocible como tal?
- **Q3 en aplicar filtros:** ¿Entiende que al seleccionar "VIS" se reducirán los resultados?
- **Q4 tras filtrar:** ¿El sistema muestra cuántos resultados hay y cuáles son los parámetros activos?

---

## CW vs Evaluación Heurística (diferencia práctica)

| Aspecto | CW (tarea 2.2) | Heurística (tarea 2.1) |
|---------|---------------|----------------------|
| Foco | Aprendizaje — usuario nuevo | Principios de usabilidad generales |
| Perspectiva | Simulación de cognición de Valentina | Juicio experto del evaluador |
| Pregunta central | "¿Sabría Valentina qué hacer?" | "¿Viola esto el principio X?" |
| Output | Fricción en la secuencia de acciones | Inventario de hallazgos por principio |

---

## Buenas prácticas

- Mantener siempre el rol de la persona (Valentina) — no evaluar como experto
- Responder las 4 preguntas en orden para cada paso
- Documentar con captura cuando la respuesta es No o Parcial
- Cruzar hallazgos con los del inventario 2.1 cuando corresponda
- El CW no reemplaza pruebas con usuarios reales — las complementa

---

## Fuentes

- [Evaluate Interface Learnability with Cognitive Walkthroughs — NN/G](https://www.nngroup.com/articles/cognitive-walkthroughs/)
- [Running a cognitive walkthrough for usability testing — LogRocket](https://blog.logrocket.com/ux-design/cognitive-walkthrough-usability-testing-guide-template/)
- [Cognitive Walkthrough: Method, Questions, Examples — UXtweak](https://blog.uxtweak.com/cognitive-walkthrough/)

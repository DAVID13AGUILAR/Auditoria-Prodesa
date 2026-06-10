---
status: referencia
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

# Plantilla â€” Cognitive Walkthrough Flujo 1 â€” Prodesa.com
**Tarea:** 2.2 â€” Cognitive Walkthrough (Flujo 1: Homepage â†’ Detalle de proyecto)
**Proyecto:** EvaluaciÃ³n de usabilidad prodesa.com
**Fecha de evaluaciÃ³n:** Mayo 2026
**URL base:** https://prodesa.com/
**HipÃ³tesis vinculada:** [[H3A]]

---

## Contexto de la tarea

Un usuario nuevo llega por primera vez al sitio desde pauta pagada (Instagram). Es comprador VIS o No-VIS que no conoce el sitio ni la marca. **Si la arquitectura de informaciÃ³n no lo orienta rÃ¡pidamente, abandona antes de ver el proyecto correcto para su perfil.**

Este walkthrough documenta ese recorrido paso a paso â€” desde el primer pixel visible hasta que logra (o no logra) ver el precio de un proyecto que corresponde a su perfil.

---

## Alcance

Recorrido desde la homepage hasta el detalle de un proyecto especÃ­fico con perfil de usuario definido (comprador VIS en BogotÃ¡, presupuesto hasta $200M COP). Se documenta cada paso respondiendo 4 preguntas canÃ³nicas:

- Â¿Sabe Valentina quÃ© hacer?
- Â¿Ve el control correcto para avanzar?
- Â¿Entiende que esa acciÃ³n produce el efecto que espera?
- Â¿El sistema le confirma que avanzÃ³ hacia su objetivo?

---

## Objetivo

Evaluar si un usuario nuevo puede encontrar el proyecto correcto para su perfil **sin fricciÃ³n ni confusiÃ³n**.

---

## Outputs de esta tarea

| Output | DescripciÃ³n |
|--------|-------------|
| [[01_persona-valentina]] | Ficha completa del usuario objetivo |
| [[02_walkthrough-registro]] | Registro paso a paso con puntos de fricciÃ³n |
| [[03_hallazgos-clasificados]] | Hallazgos agrupados por categorÃ­a y clasificados por severidad |

> El registro de esta tarea alimenta directamente la **secciÃ³n "Cognitive Walkthrough â€” Flujo 1"** del informe final (tarea 3.1).

---

## Flujo evaluado

```
[Instagram Ad] â†’ Homepage â†’ BÃºsqueda + Filtros â†’ Resultados â†’ Detalle de proyecto
```

| Paso | Pantalla | URL de referencia |
|------|----------|-------------------|
| 1 | Punto de entrada â€” homepage desde pauta | prodesa.com/ |
| 2 | Homepage â€” orientaciÃ³n y CTA principal | prodesa.com/ |
| 3 | BÃºsqueda y aplicaciÃ³n de filtros | prodesa.com/ (secciÃ³n proyectos) |
| 4 | PÃ¡gina de resultados | prodesa.com/ (resultados filtrados) |
| 5 | Detalle del proyecto seleccionado | prodesa.com/proyectos/[slug] |

---

## MetodologÃ­a â€” Cognitive Walkthrough

El evaluador adopta el rol de la persona definida ([[01_persona-valentina]]) y recorre el flujo respondiendo **4 preguntas canÃ³nicas por cada acciÃ³n** (mÃ©todo NN/G):

| # | Pregunta | QuÃ© evalÃºa |
|---|----------|------------|
| **Q1** | Â¿SabrÃ¡ Valentina quÃ© hacer en este paso? | Claridad de la acciÃ³n |
| **Q2** | Â¿VerÃ¡ el control correcto de UI para avanzar? | Visibilidad del elemento |
| **Q3** | Â¿EntenderÃ¡ que esa acciÃ³n produce el efecto que espera? | AsociaciÃ³n acciÃ³n â†’ resultado |
| **Q4** | DespuÃ©s de actuar, Â¿el sistema le confirma que avanzÃ³? | Feedback del sistema |

Una respuesta **No** o **Parcial** en cualquiera de las 4 preguntas = punto de fricciÃ³n a documentar.

> Diferencia con la tarea 2.1: la evaluaciÃ³n heurÃ­stica juzgÃ³ el sitio contra principios de Nielsen desde la perspectiva del evaluador experto. El CW simula la cogniciÃ³n de Valentina â€” alguien que nunca ha usado el sitio y no sabe quÃ© esperar.

---

## Estructura del registro de walkthrough

Cada acciÃ³n del usuario se registra con esta estructura:

```
| Paso # | AcciÃ³n esperada | Q1 Â¿Sabe quÃ© hacer? | Q2 Â¿Ve el control? | Q3 Â¿Entiende causaâ†’efecto? | Q4 Â¿El sistema confirma progreso? | FricciÃ³n detectada | Severidad | Captura |
```

- **Paso #:** NÃºmero secuencial dentro del flujo
- **AcciÃ³n esperada:** QuÃ© harÃ­a Valentina en este momento (ej. "Hace clic en el buscador")
- **Q1â€“Q4:** SÃ­ / No / Parcial â€” con justificaciÃ³n breve en cada celda
- **FricciÃ³n detectada:** DescripciÃ³n del problema. Si aplica, referencia cruzada al hallazgo de [[F2/2.1/05_inventario-final]]
- **Severidad:** ðŸ”´ / ðŸŸ  / ðŸŸ¡
- **Captura:** Referencia al screenshot anotado (`pendiente` si no hay)

---

## Escala de severidad

| Nivel | CÃ³digo | DescripciÃ³n |
|-------|--------|-------------|
| ðŸ”´ CrÃ­tico | 3 | Bloquea completar la tarea â€” Valentina abandona |
| ðŸŸ  Importante | 2 | Genera fricciÃ³n significativa â€” ralentiza o genera duda |
| ðŸŸ¡ Menor | 1 | Molestia sin impacto severo en la tarea |

---

## CategorÃ­as de hallazgos

| CategorÃ­a | DescripciÃ³n |
|-----------|-------------|
| **AI** | Arquitectura de informaciÃ³n â€” navegaciÃ³n, orientaciÃ³n, jerarquÃ­a |
| **VD** | Visual design / jerarquÃ­a visual â€” quÃ© llama la atenciÃ³n y en quÃ© orden |
| **FI** | Filtros / interacciÃ³n â€” comportamiento de controles y feedback |
| **RP** | Rendimiento percibido â€” tiempos de carga, feedback de estado |

---

## Archivos de esta tarea

| Archivo | Contenido |
|---------|-----------|
| [[01_persona-valentina]] | Ficha de Valentina RÃ­os â€” perfil VIS, contexto de llegada, modelo mental |
| [[02_walkthrough-registro]] | Tabla de registro paso a paso del flujo completo |
| [[03_hallazgos-clasificados]] | Hallazgos agrupados por categorÃ­a, clasificados por severidad, vinculados a H3A |

---

## HipÃ³tesis vinculada

| HipÃ³tesis | DescripciÃ³n |
|-----------|-------------|
| [[H3A]] | Problemas en la arquitectura de informaciÃ³n y navegaciÃ³n impiden que el usuario encuentre el proyecto correcto para su perfil â€” genera abandono antes de la conversiÃ³n |

---

â†’ [[01_persona-valentina]] Â· [[02_walkthrough-registro]] Â· [[03_hallazgos-clasificados]]

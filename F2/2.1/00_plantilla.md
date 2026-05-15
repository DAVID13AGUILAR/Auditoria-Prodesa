---
tags:
  - prodesa
  - evaluacion-heuristica
  - plantilla
  - referencia
aliases:
  - Referencia Nielsen
  - Plantilla Heurística
---

# Plantilla de Evaluación Heurística — Prodesa.com
**Tarea:** 2.1 — Evaluación heurística (10 principios de Nielsen)
**Proyecto:** Evaluación de usabilidad prodesa.com
**Fecha de evaluación:** Mayo 2026
**URL base:** https://prodesa.com/

---

## Referencia: 10 Principios de Nielsen

| # | Principio | Descripción resumida |
|---|-----------|----------------------|
| P1 | Visibilidad del estado del sistema | El sistema siempre informa al usuario sobre lo que está ocurriendo |
| P2 | Correspondencia entre el sistema y el mundo real | El lenguaje y los conceptos corresponden al mundo del usuario |
| P3 | Control y libertad del usuario | El usuario puede deshacer y rehacer acciones fácilmente |
| P4 | Consistencia y estándares | Se siguen convenciones de la plataforma y patrones predecibles |
| P5 | Prevención de errores | El diseño previene que ocurran problemas antes de que sucedan |
| P6 | Reconocimiento antes que recuerdo | Minimizar la carga de memoria del usuario haciendo objetos y opciones visibles |
| P7 | Flexibilidad y eficiencia de uso | Aceleradores para usuarios expertos sin afectar a principiantes |
| P8 | Diseño estético y minimalista | Las interfaces no deben contener información irrelevante o raramente necesaria |
| P9 | Ayuda a reconocer y recuperarse de errores | Los mensajes de error deben expresarse en lenguaje claro y ofrecer solución |
| P10 | Ayuda y documentación | El sistema debe ofrecer documentación fácil de buscar y orientada a la tarea |

---

## Escala de Severidad

| Nivel | Código | Descripción |
|-------|--------|-------------|
| Menor | 1 | Problema cosmético o de bajo impacto. Se puede corregir si hay tiempo disponible |
| Importante | 2 | Problema de usabilidad que genera fricción o confusión. Debe corregirse |
| Crítico | 3 | Problema que bloquea o impide la conversión. Prioridad máxima |

---

## Estructura del Inventario

Cada hallazgo sigue este formato:

```
| ID | Principio | Página/Elemento | Descripción del problema | Captura | Severidad | Recomendación |
```

- **ID:** Formato `H-[sección]-[número]` → ej. `H-HOME-01`, `H-FILTROS-02`
- **Principio:** Número y nombre corto → ej. `P1 - Visibilidad`
- **Página/Elemento:** URL o componente específico donde se detectó
- **Descripción:** Qué viola el principio y por qué es un problema
- **Captura:** Referencia a screenshot o anotación (`pendiente` si no hay)
- **Severidad:** 1 / 2 / 3
- **Recomendación:** Acción concreta para resolverlo

---

## Archivos de esta evaluación

| Archivo | Contenido |
|---------|-----------|
| [[01_homepage]] | Hallazgos de la homepage |
| [[02_busqueda-filtros]] | Hallazgos de búsqueda y listado de proyectos |
| [[03_detalle-proyecto]] | Hallazgos de la página de detalle de proyecto |
| [[04_formulario-contacto]] | Hallazgos del formulario de contacto |
| [[05_inventario-final]] | Inventario unificado, priorizado y relación con hipótesis |
| [[06_reporte-ejecutivo-sintesis]] | Reporte ejecutivo con síntesis de todos los hallazgos |

---

## Hipótesis vinculadas

| Hipótesis | Descripción |
|-----------|-------------|
| [[H3A]] | Problemas en la arquitectura de información y navegación afectan la conversión |
| [[H3B]] | Los CTAs son ambiguos o insuficientemente prominentes |
| [[H3C]] | La experiencia mobile es inferior a la desktop y genera abandono |

---

## Archivos relacionados

→ [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

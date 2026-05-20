---
tags:
  - prodesa
  - accesibilidad
  - wcag
  - plantilla
  - referencia
aliases:
  - Referencia WCAG
  - Plantilla Accesibilidad
---

# Plantilla de Revisión de Accesibilidad WCAG 2.0 — Prodesa.com
**Tarea:** 2.4 — Revisión de accesibilidad (WCAG 2.0)
**Proyecto:** Evaluación de usabilidad prodesa.com
**Fecha de revisión:** Junio 2026
**URL base:** https://prodesa.com/
**Hipótesis vinculada:** [[H3B]]

---

## Contexto de la tarea

El análisis preliminar (tarea 2.1) identificó problemas de accesibilidad que **no son solo problemas de inclusión — son barreras directas en los botones que el usuario necesita para convertir**:

- Contraste insuficiente en botones clave: "Buscar vivienda", "Realizar Pago", "Limpiar Filtros"
- Jerarquía de encabezados incorrecta
- Links duplicados

Esta revisión documenta todos los problemas WCAG que afectan la conversión, con foco en esos elementos ya identificados.

---

## Herramientas de revisión

| Herramienta | Uso | Dónde obtenerla |
|-------------|-----|-----------------|
| **WAVE** | Detección automática de errores de accesibilidad | wave.webaim.org → extensión Chrome/Firefox |
| **axe DevTools** | Errores que WAVE no detecta (versión free) | Chrome Web Store → axe DevTools |
| **Colour Contrast Analyser** | Medición manual de contraste texto/fondo | TPGi — aplicación gratuita |
| **Chrome DevTools** | Headings, DOM, color contrast ratio | F12 → Elements / Accessibility |

---

## Referencia WCAG 2.0 — Criterios relevantes

| Criterio | Nombre | Nivel | Descripción |
|----------|--------|-------|-------------|
| 1.1.1 | Contenido no textual | A | Todo contenido no textual tiene alternativa en texto (alt en imágenes) |
| 1.3.1 | Información y relaciones | A | La estructura semántica refleja la presentación visual (headings, listas, labels) |
| 1.3.2 | Secuencia significativa | A | El orden de lectura del DOM es lógico |
| 1.4.3 | Contraste (mínimo) | AA | Ratio mínimo 4.5:1 para texto normal, 3:1 para texto grande (18pt+ / 14pt bold) |
| 1.4.4 | Cambio de tamaño de texto | AA | Texto redimensionable hasta 200% sin pérdida de contenido |
| 2.1.1 | Teclado | A | Toda funcionalidad operable con teclado |
| 2.1.2 | Sin trampa de teclado | A | El foco del teclado no queda atrapado en ningún componente |
| 2.4.3 | Orden de foco | A | El orden de navegación por teclado es lógico y coherente |
| 2.4.4 | Propósito del enlace | A | El texto ancla describe el destino del link (no "haz clic aquí") |
| 2.4.6 | Encabezados y etiquetas | AA | Los encabezados y labels son descriptivos |
| 2.4.7 | Foco visible | AA | El indicador de foco del teclado es visible |
| 3.3.1 | Identificación de errores | A | Los errores en formularios se identifican con texto descriptivo |
| 3.3.2 | Etiquetas o instrucciones | A | Las entradas de formulario tienen labels visibles |
| 4.1.2 | Nombre, función, valor | A | Los componentes de UI tienen nombre, función y estado accesibles |

---

## Escala de severidad de impacto en conversión

| Nivel | Código | Descripción |
|-------|--------|-------------|
| 🔴 Crítico | 3 | Barrera directa en el flujo de conversión. Bloquea o impide completar la acción principal |
| 🟠 Importante | 2 | Genera fricción significativa o excluye a usuarios con discapacidad. Debe corregirse |
| 🟡 Menor | 1 | Problema cosmético o de bajo impacto. Corregir si hay tiempo |

---

## Estructura del inventario de hallazgos

Cada hallazgo sigue este formato:

```
| ID | Página | Elemento | Criterio WCAG | Nivel | Descripción | Captura | Severidad | Recomendación |
```

- **ID:** Formato `A-[sección]-[número]` → ej. `A-HOME-01`, `A-FILTROS-02`
- **Página:** URL o sección donde se detectó
- **Elemento:** Componente específico (botón, heading, link, imagen...)
- **Criterio WCAG:** Número y nombre corto → ej. `1.4.3 Contraste`
- **Nivel:** A / AA
- **Descripción:** Qué viola el criterio y por qué afecta la conversión
- **Captura:** Referencia a screenshot (`pendiente` si no hay)
- **Severidad:** 🔴 / 🟠 / 🟡
- **Recomendación:** Acción concreta con valor específico (ej. color hex que sí cumple ratio)

---

## Archivos de esta revisión

| Archivo | Contenido |
|---------|-----------|
| [[01_homepage]] | Hallazgos de accesibilidad — homepage |
| [[02_busqueda-filtros]] | Hallazgos de accesibilidad — búsqueda y filtros |
| [[03_detalle-proyecto]] | Hallazgos de accesibilidad — detalle de proyecto |
| [[04_formulario-contacto]] | Hallazgos de accesibilidad — formulario de contacto |
| [[05_inventario-final]] | Inventario WCAG unificado, priorizado y relación con hipótesis |

---

## Hipótesis vinculada

| Hipótesis | Descripción |
|-----------|-------------|
| [[H3B]] | CTAs ambiguos o insuficientemente prominentes — el contraste deficiente en botones de conversión es evidencia directa |

---

## Páginas del flujo a revisar (mínimo)

1. Homepage — `prodesa.com/`
2. Búsqueda con filtros — `prodesa.com/` (sección de proyectos)
3. Detalle de proyecto — ej. Mirla, Agora, Orizzo
4. Formulario de contacto

---

→ [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[05_inventario-final]]

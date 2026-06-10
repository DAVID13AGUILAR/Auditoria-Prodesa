---
tags:
  - research
  - formulario
  - mobile-desktop
  - inconsistencia
  - crm
  - conversion
  - prodesa
created: 2026-05-21
aliases:
  - Research inconsistencia campos formulario mobile vs desktop
---

# Research — Formulario con campos distintos en mobile vs desktop

**Contexto:** El formulario "¿Te interesa este proyecto?" de prodesa.com muestra campos distintos según dispositivo:
- **Desktop:** 6 campos obligatorios — Nombre, Apellido, Tipo de Documento, Nro de Documento, Teléfono, Correo
- **Mobile:** 4 campos obligatorios — Nombre, Apellido, Teléfono, Correo (sin documento)

Esta no es una decisión de diseño intencional (progressive disclosure) sino una omisión accidental en la implementación responsive. El presente research documenta por qué esto es un problema y cuál es el estándar correcto.

---

## 1. Los usuarios esperan experiencias consistentes entre dispositivos

En 2025-2026, los usuarios con frecuencia inician una interacción en un dispositivo y la continúan en otro — mobile primero, desktop después, o viceversa. La investigación es clara: **los usuarios esperan que el mismo formulario funcione igual en todos los dispositivos**.

Cuando el mismo formulario tiene una estructura diferente según el dispositivo:
- El usuario que cambia de dispositivo encuentra una experiencia inesperada → **ruptura del modelo mental**
- El usuario que completa el formulario en mobile y lo vuelve a ver en desktop no reconoce el mismo formulario — **erosiona la confianza**
- La empresa comunica implícitamente que mobile y desktop son experiencias de segunda y primera clase respectivamente

**NN/G sobre Heurística #4 (Consistencia):** "Fallar en mantener la consistencia fuerza al usuario a aprender algo nuevo. Los usuarios esperan que las palabras y las interacciones tengan los mismos significados en diferentes situaciones."

---

## 2. El impacto directo en la calidad del CRM

Este es el problema más grave y el que más afecta al equipo comercial de Prodesa.

En Colombia, **más del 80% del tráfico web es mobile**. Esto significa que la gran mayoría de los formularios llegan al CRM desde dispositivos mobile — sin tipo ni número de documento. El resultado es una base de datos con dos tipos de registros estructuralmente distintos:

| Dispositivo | Datos que llegan al CRM | % del tráfico |
|---|---|---|
| Mobile | Nombre, Apellido, Teléfono, Correo | ~80% |
| Desktop | Nombre, Apellido, Tipo Doc, Nro Doc, Teléfono, Correo | ~20% |

**Consecuencias operativas:**
1. **Inconsistencia en los leads:** el equipo comercial no sabe de antemano si un lead tiene o no datos de documento — debe verificar caso por caso
2. **Trabajo extra del asesor:** si el proceso de preventa o separación requiere el documento (como es habitual en vivienda colombiana), el asesor debe solicitarlo en el seguimiento — un paso que debería estar resuelto desde el formulario
3. **Política de datos inconsistente:** el formulario desktop solicita documentos, el mobile no — misma empresa, dos políticas implícitas distintas. Esto puede generar preguntas legales sobre qué datos se solicitan y por qué

**Dato de referencia:** Reform.app en un análisis de formularios mobile vs desktop encontró que los datos enviados desde desktop son más completos (88% vs 86% de completitud) — en Prodesa esta brecha sería aún más pronunciada porque los campos faltantes en mobile son estructurales, no opcionales.

---

## 3. La diferencia entre omisión accidental y progressive disclosure

**Progressive disclosure** es una técnica legítima de diseño de formularios: mostrar menos campos en el primer paso y revelar campos adicionales progresivamente a medida que el usuario avanza. Es una de las prácticas más respaldadas para mejorar tasas de completación:

- Formularios multi-paso con progressive disclosure muestran **20–35% más tasa de completación** que formularios de una sola página con todos los campos → [[H-FORM-patrones-formulario-contacto]]
- La clave de progressive disclosure: **todos los campos existen en todos los dispositivos**, solo se revelan en momentos distintos

**Lo que tiene Prodesa no es progressive disclosure** — es una omisión accidental: los campos de documento simplemente no aparecen en mobile, probablemente porque en la implementación responsive se ocultaron en lugar de adaptarse. No hay un paso posterior donde el usuario mobile sea invitado a completar esos campos.

| Característica | Progressive disclosure (correcto) | Omisión accidental (Prodesa) |
|---|---|---|
| Intencionalidad | Deliberada | Accidental |
| Campos en mobile | Presentes, revelados progresivamente | Ausentes |
| Consistencia cross-device | Alta — mismo formulario, mismo resultado | Baja — resultados distintos |
| Impacto en CRM | Datos completos en todos los dispositivos | Datos incompletos en mobile (~80% del tráfico) |

---

## 4. El estándar correcto para este caso

**Opción A — Formulario mínimo consistente (recomendada para primer contacto):**
Reducir el formulario a 2-3 campos en TODOS los dispositivos: **Nombre + Teléfono** (opcionalmente Correo). El documento de identidad no es necesario en primer contacto — pertenece a la etapa de separación o promesa de compra. Esta solución elimina la inconsistencia y reduce la fricción global → [[H-FORM-patrones-formulario-contacto]]

**Opción B — Formulario progresivo consistente:**
Si Prodesa necesita los datos de documento, implementar progressive disclosure real: paso 1 (Nombre + Teléfono) → paso 2 (Correo + datos de documento) en TODOS los dispositivos por igual, con barra de progreso visible.

**Lo que no es válido:** mantener un formulario con 4 campos en mobile y 6 en desktop — es la peor combinación de ambos mundos: fricción para el usuario desktop y datos incompletos para el CRM desde mobile.

---

## 5. Relación con otros hallazgos del proyecto

Este problema no es aislado — forma parte del patrón sistémico de inconsistencias entre dispositivos y entre secciones del sitio documentado en:
- [[F2/2.1/05_inventario-final#H-DETALLE-06]] — inconsistencias entre proyectos (tabs, brochure, mapa, CTAs)
- [[F2/2.1/05_inventario-final#H-FILTROS-07]] — filtro VIS/NO VIS/VIP solo disponible en mobile, ausente en desktop
- [[H-FORM-canales-contacto-omnicanalidad]] — campos distintos entre el formulario del proyecto y el formulario de callback

El patrón subyacente: **el sitio fue desarrollado con implementaciones separadas para mobile y desktop sin un sistema de diseño que garantice paridad de funcionalidad y datos entre dispositivos.**

---

## Fuentes consultadas

- [Mobile vs. Desktop: Form Performance Comparison — Reform.app](https://www.reform.app/blog/mobile-vs-desktop-form-performance-comparison)
- [Maintain Consistency and Adhere to Standards (Heuristic #4) — NN/G](https://www.nngroup.com/articles/consistency-and-standards/)
- [What Is Progressive Disclosure in UX? — UXPin](https://www.uxpin.com/studio/blog/what-is-progressive-disclosure/)
- [Progressive Disclosure in UX Design — LogRocket](https://blog.logrocket.com/ux-design/progressive-disclosure-ux-types-use-cases/)
- [9 Design Tips for High-Converting Mobile-Friendly Forms — Typeform](https://www.typeform.com/blog/mobile-form-design-best-practices)
- [Mobile CRM Design: Adaptive & Responsive Strategies — Eseospace](https://eseospace.com/blog/crm-design-for-mobile-adaptive-and-responsive-strategies/)
- [Responsive Design: Best Practices — UXPin](https://www.uxpin.com/studio/blog/best-practices-examples-of-excellent-responsive-design/)
- [Heuristic Principles for Mobile Interfaces — Toptal](https://www.toptal.com/designers/usability-testing/mobile-heuristic-principles)

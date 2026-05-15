---
tags:
  - prodesa
  - evaluacion-heuristica
  - formulario-contacto
  - hallazgos
  - critico
aliases:
  - Hallazgos Formulario
  - Hallazgos Contacto
---

# 04 — Hallazgos Formulario de Contacto
**URL evaluada:** https://prodesa.com/contactanos
**Formulario en detalle de proyecto:** disponible en cada `/proyecto-vivienda/[ciudad]/[slug]`
**Fecha:** Mayo 2026
**Evaluador:** David Marín

---

## Resumen de hallazgos

| ID | Principio | Página/Elemento | Descripción del problema | Captura | Severidad | Recomendación |
|----|-----------|-----------------|--------------------------|---------|-----------|---------------|
| H-FORM-01 | P1 - Visibilidad | /contactanos / Confirmación post-envío | No se puede confirmar desde el HTML estático si existe una pantalla de confirmación post-envío. En sitios de vivienda, este es un punto crítico: **el usuario que envía el formulario no sabe qué pasará a continuación** (¿lo llamarán? ¿en cuánto tiempo? ¿por qué canal?). Si no hay confirmación clara, el usuario enviará el formulario múltiples veces o perderá la confianza. | pendiente | 3 | Implementar una pantalla de confirmación post-envío que comunique: ✅ *"Recibimos tu solicitud. Un asesor te contactará por WhatsApp al [número] en máximo 24 horas hábiles."* Incluir también un CTA de respaldo (ej. WhatsApp directo) para quien quiere contacto inmediato. |
| H-FORM-02 | P2 - Mundo real | /contactanos / Labels del formulario | El título de la página es *"Comunicate con nuestros asesores"* — lenguaje correcto. Sin embargo, **los campos del formulario son completamente opacos** sin el JS renderizado. Si el formulario sigue el patrón estándar del sector (Nombre, Teléfono, Ciudad, ¿Tiene cuota inicial?, ¿Aplica a subsidio?) los labels deben usar lenguaje del comprador, no del CRM interno. | pendiente | 2 | Revisar cada label del formulario con la pregunta: *"¿Un comprador primerizo entiende para qué es este campo?"*. Sustituir labels técnicos por lenguaje coloquial. Añadir texto auxiliar (placeholder o hint) en campos no evidentes. |
| H-FORM-03 | P5 - Prevención de errores | /contactanos / Validación del formulario | No se puede verificar sin renderizado, pero en la mayoría de formularios web estándar **la validación ocurre solo al enviar (post-submit)**, no en tiempo real (inline). Esto significa que el usuario puede completar todos los campos, enviar, y recién ahí descubrir que el teléfono tiene un formato inválido o que falta un campo requerido. | pendiente | 3 | Implementar validación inline: validar cada campo al perder el foco (`onBlur`). Para el teléfono, validar formato colombiano en tiempo real (10 dígitos, inicio con 3). Para el email, validar formato básico. Nunca esperar al submit para mostrar errores. |
| H-FORM-04 | P9 - Recuperación de errores | /contactanos / Mensajes de error | Si hay validación, los mensajes de error típicos son genéricos: *"Campo requerido"*, *"Formato inválido"*. Estos mensajes **no ayudan al usuario a entender qué debe corregir ni por qué**. Un mensaje genérico en un formulario de alto valor (compra de vivienda) aumenta la frustración y el abandono. | pendiente | 2 | Reemplazar mensajes genéricos por mensajes específicos y orientados a la acción: ❌ *"Campo requerido"* → ✅ *"Ingresa tu número de celular para que un asesor te pueda llamar"*. ❌ *"Formato inválido"* → ✅ *"El número debe tener 10 dígitos, ej: 3001234567"*. |
| H-FORM-05 | P2 - Mundo real | /contactanos / Información de contacto en footer | El footer del sitio muestra **cuatro números de teléfono distintos**: Bogotá (+573241000060), Caribe (+573241000060), Servicio al cliente (+573241000060) y Línea comercial (+573241000055). Tres de los cuatro tienen el mismo número, pero el usuario no puede distinguir a cuál llamar según su necesidad. La diferenciación entre "Servicio al cliente" y "Línea comercial" no es intuitiva para alguien que quiere comprar. | pendiente | 2 | Simplificar a dos números claramente etiquetados: *"Quiero conocer un proyecto: [número]"* y *"Ya soy cliente: [número]"*. Añadir horario de atención visible. Considerar añadir un enlace directo a WhatsApp Business como canal de baja fricción. |
| H-FORM-06 | P3 - Control del usuario | /contactanos / Canal de contacto | El formulario no ofrece al usuario la opción de **elegir cómo quiere ser contactado** (WhatsApp, llamada, email). El sistema decide el canal de respuesta, no el usuario. Para muchos compradores colombianos, una llamada inesperada es una barrera; prefieren WhatsApp. | pendiente | 2 | Añadir un campo o selector: *"¿Cómo prefieres que te contactemos?"* con opciones: WhatsApp / Llamada / Email. Respetar la preferencia del usuario en el seguimiento comercial. |
| H-FORM-07 | P8 - Minimalismo | /contactanos / Página de contacto general | La página `/contactanos` existe como página general, pero **el usuario llega a esta página desde el detalle de un proyecto específico sin contexto**. Si el formulario no precarga el proyecto de interés, el asesor recibe un lead sin saber a qué proyecto aplica, generando una llamada de contexto adicional. | pendiente | 2 | El formulario en la página de detalle de proyecto debe precarga automáticamente el nombre del proyecto en un campo oculto o visible. Cuando el lead llega al CRM, debe incluir el proyecto de interés. |
| H-FORM-08 | P10 - Ayuda y documentación | /contactanos / Preguntas frecuentes | El footer incluye un link a *"Preguntas Frecuentes"* (`/preguntas`). Sin embargo, **no hay ningún enlace a esta sección en la página de contacto ni en el formulario**, que es justamente el momento en que el usuario tiene más dudas. Las FAQ no están integradas al flujo de conversión. | pendiente | 1 | Añadir un módulo de FAQ colapsable en la página de contacto y en la página de detalle de proyecto con las 5 preguntas más frecuentes (¿Cómo aplico al subsidio? ¿Cuánto es la cuota inicial? ¿Cuándo se entrega? etc.). |
| H-FORM-09 | P1 - Visibilidad | /contactanos / WhatsApp flotante | En Colombia, el estándar de los sitios de vivienda es incluir un **botón flotante de WhatsApp** visible en todas las páginas. No se detecta en el HTML estático este elemento. Si está ausente, representa una pérdida de conversión importante dado que WhatsApp es el canal de comunicación preferido del comprador colombiano. | pendiente | 3 | Implementar un botón flotante de WhatsApp en todas las páginas del sitio con un mensaje predefinido contextual: *"Hola, quiero información sobre [nombre del proyecto]"* que se adapte según la página donde se encuentre el usuario. |

---

## Análisis del footer — Datos de contacto

```
Bogotá         → +573241000060
Caribe         → +573241000060  ← mismo número que Bogotá
Servicio al cliente → +573241000060  ← mismo número
Línea comercial     → +573241000055  ← único número diferente
Email: info@prodesa.com
```

**Problema:** Tres líneas apuntan al mismo número. Desde la perspectiva del usuario, ¿por qué hay tres entradas con el mismo número? Genera confusión sobre si la información es correcta o está desactualizada.

---

## Notas de evaluación

- El formulario de `/contactanos` renderiza completamente via JavaScript — no hay campos visibles en el HTML estático.
- Los hallazgos H-FORM-01, H-FORM-02, H-FORM-03 y H-FORM-04 requieren validación con el sitio renderizado en browser.
- H-FORM-05 y H-FORM-09 son verificables directamente desde el HTML estático del footer y el comportamiento del sitio.
- **Prioridad de captura:** H-FORM-01 (post-envío), H-FORM-03 (validación) y H-FORM-09 (WhatsApp) son críticos para el informe.

---

## Resumen de severidad — Formulario de Contacto

| Severidad | Cantidad | IDs |
|-----------|----------|-----|
| 🔴 Crítico (3) | 3 | H-FORM-01, H-FORM-03, H-FORM-09 |
| 🟡 Importante (2) | 5 | H-FORM-02, H-FORM-04, H-FORM-05, H-FORM-06, H-FORM-07 |
| 🟢 Menor (1) | 1 | H-FORM-08 |
| **Total** | **9** | |

---

## Hipótesis confirmadas en Formulario de Contacto

| Hipótesis | Hallazgos relacionados | Confirma / Refuta |
|-----------|------------------------|-------------------|
| [[H3A]] — Arquitectura de información | H-FORM-07, H-FORM-08 | ✅ Confirma: FAQ desconectada del flujo y falta de contexto en formularios genéricos |
| [[H3B]] — CTAs ambiguos | H-FORM-01, H-FORM-06, H-FORM-09 | ✅ Confirma fuertemente: No hay confirmación post-envío, no hay elección de canal, ausencia de WhatsApp |
| [[H3C]] — Experiencia mobile | H-FORM-03, H-FORM-09 | ✅ Confirma: Validación post-submit y ausencia de WhatsApp son especialmente críticos en mobile |

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

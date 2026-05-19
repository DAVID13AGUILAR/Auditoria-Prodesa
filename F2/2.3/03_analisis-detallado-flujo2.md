---
tags:
  - prodesa
  - cognitive-walkthrough
  - flujo-2
  - analisis
  - contacto
  - conversion
aliases:
  - Análisis Flujo 2
  - Análisis Detallado Contacto
---

# Análisis Detallado — Flujo 2: Registro y Contacto

**Persona:** [[00_persona-valentina|Valentina Morales]]  
**Método:** Cognitive Walkthrough  
**Fecha:** Mayo 2026  
**Referencia cruzada:** [[01_walkthrough-flujo2|Walkthrough]] · [[02_hallazgos-flujo2|Hallazgos]] · [[../../research/CW-F2-importancia-cognitive-walkthrough|Research CW Flujo 2]]

---

## Por qué este flujo es el más importante del proyecto

El flujo de contacto es el único punto donde el sitio tiene oportunidad de convertir al visitante en lead. Toda la arquitectura de información (H3A), todos los CTAs del detalle del proyecto (H3B) y toda la experiencia mobile (H3C) confluyen aquí. Si el usuario abandona en cualquier punto de este flujo, la inversión de Prodesa en atraerlo no produce ningún resultado comercial.

La evaluación heurística (Fase 2.1) identificó los problemas individuales. El cognitive walkthrough revela algo diferente: **cómo esos problemas se experimentan en secuencia, desde la perspectiva de una persona real que quiere hacer algo concreto**.

---

## El patrón central: tres quiebres consecutivos en el funnel

El walkthrough de Valentina revela que el flujo de contacto no falla una vez — falla tres veces, en tres momentos críticos y consecutivos:

### Quiebre 1 — Paso 2: El sitio no abre la puerta cuando el usuario está listo

Valentina termina de leer "Acerca del proyecto". Es el momento de mayor intención: acaba de invertir tiempo en leer la descripción completa, el precio le encaja y tiene preguntas concretas. El único CTA disponible en ese momento es **"Descargar brochure"** y **"Compartir"**.

El sitio lleva al usuario hasta la puerta y no la abre.

**Por qué esto es un problema de diseño, no de copy:** El problema no es la redacción de los botones — es la ausencia de un botón de contacto en el momento correcto. La solución no es cambiar el texto de "Descargar brochure" sino añadir un CTA de contacto directo (WhatsApp preferiblemente) al final de la sección de descripción.

**Evidencia de apoyo:** [[../../research/CW-F2-importancia-cognitive-walkthrough#3.2|Research §3.2]] — Los problemas de H3A, H3B y H3C convergen en este flujo.

---

### Quiebre 2 — Paso 5: El CTA engañoso destruye la confianza en el momento de decisión

Valentina decide usar el canal "Agenda tu cita en sala" porque interpreta "en sala" como sala de ventas física — una visita presencial, que es exactamente lo que quiere. El sistema abre un calendario de Microsoft Teams para una videollamada de 30 minutos.

La promesa y la entrega son completamente opuestas.

**Por qué esto es grave en bienes raíces específicamente:** La compra de vivienda es la decisión financiera más importante de la vida del comprador. La confianza es el activo más crítico. Un CTA que engaña al usuario en el momento exacto de mayor intención no solo genera una queja de usabilidad — genera una actualización negativa de la percepción de la empresa.

Nielsen Norman Group (2023) lo documenta específicamente: *"When a CTA promises an experience and delivers something different, the user's trust in the brand is damaged at the highest-intent moment."*

**El daño tiene dos capas:**
1. Valentina, que quería una visita física, siente que la engañaron → abandona
2. Valentina, que sí hubiera querido una videollamada, no sabe que esa opción existe bajo ese nombre → tampoco la usa

---

### Quiebre 3 — Paso 14: La confirmación no entrega ningún valor

Valentina completa el formulario. Después de llenar 6 campos (incluyendo su cédula), ver todos los errores simultáneamente al enviar y corregirlos, finalmente da clic en "Enviar". El sistema muestra: *"¡Gracias [correo electrónico] por contactarnos!"* sobre una imagen genérica de vivienda.

No hay canal de respuesta. No hay tiempo estimado. No hay CTA de respaldo. No hay opción de explorar más proyectos.

**El momento de mayor riesgo de pérdida del lead:** La investigación de HubSpot (2023) indica que el período inmediatamente posterior al envío del formulario es cuando el lead es más vulnerable a buscar alternativas. Un usuario que no sabe cuándo o cómo lo van a contactar puede visitar el sitio de Amarilo, Constructora Bolívar o Urbansa antes de que el asesor de Prodesa llame.

**El problema de privacidad añadido:** Mostrar el correo electrónico del usuario en la confirmación no cumple ninguna función de UX — el usuario sabe cuál es su correo. Solo sirve para exponer un dato personal en pantalla, que puede ser visto por otras personas cercanas.

---

## Análisis de la estructura del formulario

### Por qué pedir la cédula en el primer contacto es un error estratégico

El formulario actual solicita Tipo de Documento y Número de Documento como campos obligatorios. Desde la perspectiva del usuario, esto plantea una pregunta legítima: *"¿Para qué necesitan mi cédula si solo quiero que me llamen?"*

Esta pregunta no es paranoica — es razonable. El número de cédula es el dato más sensible del documento de identidad colombiano, asociado a consultas de crédito, reportes en centrales de riesgo, y procesos legales. En Colombia, el contexto de fraude y suplantación hace que los usuarios tengan una sensibilidad especial hacia este dato.

**Cuándo pertenece cada dato al funnel:**

| Dato | Etapa correcta | Razón |
|------|----------------|-------|
| Nombre | Primer contacto | Personalización mínima |
| Teléfono | Primer contacto | Canal de respuesta |
| Ciudad / Proyecto de interés | Primer contacto | Cualificación básica del lead |
| Correo electrónico | Primer contacto (opcional) | Comunicación secundaria |
| Cédula | Separación / Promesa de venta | Proceso legal — contrato |
| Ingresos | Cualificación avanzada | Evaluación de subsidio |

La cédula no pertenece al formulario de primer contacto. Pedirla ahí no acelera el proceso de venta — lo interrumpe.

**Baymard Institute (2022):** La inclusión de datos personales sensibles en formularios de primer contacto reduce la tasa de completado hasta un 34%.

---

### La validación del teléfono: un problema que tiene dos víctimas

El campo de teléfono acepta "+57 5464326" sin ningún error. Este número tiene 7 dígitos y no empieza por 3 — no es un celular colombiano válido.

**Primera víctima — el usuario:** Valentina no sabe que su teléfono es inválido. Envía el formulario convencida de que fue contactada exitosamente. Espera una llamada que nunca llegará.

**Segunda víctima — el asesor comercial:** El asesor recibe un lead con un número de teléfono que no existe. Solo descubre el problema al intentar marcar — después de haber revisado el lead, preparado la llamada y separado tiempo en su agenda. Este es un problema de calidad de datos del CRM, no solo de UX.

**La solución es estándar y técnicamente simple:** validar que el campo tenga 10 dígitos y empiece por 3 (celulares colombianos). El mensaje de error debe ser específico: *"Ingresa tu celular colombiano: 3001234567"*.

---

### Validación post-submit vs. inline: el impacto real

La validación actual es 100% post-submit: ningún campo muestra error mientras el usuario lo llena. Al dar clic en "Enviar", todos los errores aparecen simultáneamente.

En desktop, el formulario con errores se extiende más allá del viewport. El usuario que llenó todos los campos debe hacer scroll hacia arriba para encontrar el primer error, corregirlo, volver hacia abajo para continuar, y potencialmente repetir el proceso.

**El efecto psicológico acumulado:** Cada error post-submit genera una sensación de "trabajo perdido". El usuario que llevó tiempo llenando 6 campos y ve que debe corregir 3 actualiza su percepción del formulario de "casi listo" a "hay que empezar de nuevo". Baymard (2024) documenta una reducción del 16% en abandono cuando se implementa validación inline onBlur.

---

## El único camino sin fricción: WhatsApp

El paso 6 del walkthrough es el único donde Valentina no encuentra ninguna fricción: "Escríbenos a WhatsApp" tiene un label claro, un icono reconocible, y la acción redirige correctamente con un mensaje predefinido.

**Esto no es un dato menor — es la solución.** El canal que funciona perfectamente es el que más se alinea con las preferencias de la persona objetivo (Valentina prefiere WhatsApp sobre llamadas) y con el comportamiento digital colombiano (92% de penetración de WhatsApp en Colombia).

**El problema no es que WhatsApp no funcione — es que no está donde debería estar:**
- Ausente en el homepage
- Ausente en el listado de proyectos
- Solo disponible desde el tercer nivel del funnel (página de detalle)

El canal de menor fricción tiene la menor cobertura del funnel. Esta es la inversión más evidente que se puede recomendar: extender WhatsApp a homepage y listado de proyectos.

---

## Conexión con las hipótesis del proyecto

| Hipótesis | Cómo la confirma este walkthrough |
|-----------|-----------------------------------|
| [[../../F2/2.1/H3B\|H3B — CTAs ambiguos]] | CW-F2-01 (Teams), CW-F2-04 (sin CTA al terminar de leer), CW-F2-10 (sin próximos pasos) — tres fallas consecutivas del mismo embudo de conversión |
| [[../../F2/2.1/H3C\|H3C — Mobile inferior]] | CW-F2-05 (cédula requiere cambio de teclado en mobile), CW-F2-08 (errores post-submit más agresivos en pantalla pequeña) |
| [[../../F2/2.1/H3A\|H3A — Arquitectura]] | El quiebre en el paso 2 (sin CTA al terminar de leer) es consecuencia directa de la arquitectura de CTAs del detalle |

**Veredicto:** El cognitive walkthrough no solo confirma las hipótesis — las convierte en una narrativa coherente. H3A, H3B y H3C no son problemas paralelos. Son **etapas consecutivas de la misma falla de diseño**: el sitio no facilita la conversión en ninguno de los tres puntos críticos del funnel de contacto.

---

## Priorización de recomendaciones por impacto

### Inmediato — alta conversión, bajo esfuerzo de implementación

| Recomendación | Hallazgo | Impacto estimado |
|---------------|----------|------------------|
| Renombrar "Agenda tu cita en sala" → "Reunión virtual por Teams" | CW-F2-01 | Elimina confusión en paso 5 — recovery inmediato de leads perdidos por CTA engañoso |
| Reducir formulario a 3 campos: Nombre, Teléfono, Ciudad | CW-F2-05 | Baymard: -34% abandono por campos sensibles |
| Agregar validación inline onBlur en teléfono y email | CW-F2-06, CW-F2-08 | Baymard: -16% abandono + elimina leads incontactables |
| Reemplazar correo por nombre en confirmación | CW-F2-02 | Elimina riesgo de privacidad + mejora percepción |

### Segunda ola — impacto estratégico, requiere diseño

| Recomendación | Hallazgo | Impacto estimado |
|---------------|----------|------------------|
| CTA de contacto (WhatsApp) al final de "Acerca del proyecto" | CW-F2-04 | Captura la intención en el momento correcto |
| Confirmación con canal, tiempo estimado y CTA de respaldo | CW-F2-10 | Unbounce: +63% conversión con confirmación bien diseñada |
| Extender WhatsApp a homepage y listado de proyectos | [[../../F2/2.1/04_formulario-contacto#H-FORM-09\|H-FORM-09]] | Canal más efectivo disponible en todo el funnel |
| Proyectos similares al final de la confirmación | CW-F2-11 | Retención post-conversión — elimina el callejón sin salida |

---

## Conclusión

El cognitive walkthrough de Valentina Morales sobre el flujo de contacto de Prodesa revela que la barrera para convertir no es la falta de opciones de contacto — WhatsApp funciona y es el mejor camino. La barrera es que el sitio **no facilita activamente la conversión en los tres momentos donde el usuario está más dispuesto a actuar**.

Corregir los cuatro hallazgos de alta prioridad (renombrar el CTA engañoso, reducir el formulario, añadir validación inline y mejorar la confirmación) no requiere rediseñar el sitio — requiere ajustes quirúrgicos de copy, validación de formulario y estructura de la pantalla de confirmación. El retorno potencial sobre esas intervenciones es significativamente mayor que la inversión necesaria para implementarlas.

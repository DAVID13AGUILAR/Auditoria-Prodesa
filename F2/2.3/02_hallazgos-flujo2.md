---
tags:
  - prodesa
  - cognitive-walkthrough
  - flujo-2
  - hallazgos
  - contacto
aliases:
  - Hallazgos Flujo 2
  - Hallazgos Contacto Walkthrough
---

# Hallazgos — Flujo 2: Registro y Contacto
**Persona:** [[00_persona-valentina|Valentina Morales]]  
**Fecha:** Mayo 2026  
**Referencia cruzada:** [[../2.1/04_formulario-contacto|04_formulario-contacto]] · [[../2.1/03_detalle-proyecto|03_detalle-proyecto]]

---

## Resumen de severidad

| Severidad | Cantidad |
|-----------|----------|
| 🔴 Crítico | 7 |
| 🟠 Importante | 3 |
| 🟡 Menor | 1 |
| **Total** | **11** |

---

## Categoría 1 — Copy y micro-copy

### CW-F2-01 🔴 Crítico
**Problema:** El CTA "Agenda tu cita en sala" promete una visita física pero entrega una videollamada por Microsoft Teams.  
**Paso del walkthrough:** Paso 5  
**Impacto:** El usuario que quería una visita presencial se siente engañado. El usuario que sí quiere una reunión virtual no sabe que esa opción existe bajo ese nombre.  
**Recomendación:** Renombrar a *"Agendar videollamada con asesor"* o *"Reunión virtual — Microsoft Teams"*.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-06|H-FORM-06]]

---

### CW-F2-02 🔴 Crítico
**Problema:** La confirmación post-envío muestra el correo electrónico del usuario en el mensaje: *"¡Gracias [email] por contactarnos!"*  
**Paso del walkthrough:** Paso 14  
**Impacto (doble):** (1) Privacidad — el correo queda expuesto en pantalla. (2) UX — el usuario no necesita ver su propio correo; necesita saber qué pasa a continuación.  
**Recomendación:** Usar el nombre: *"¡Gracias [Nombre] por contactarnos!"* + próximo paso + CTA de respaldo.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-01|H-FORM-01]]

---

### CW-F2-03 🟠 Importante
**Problema:** Los mensajes de error del formulario dicen "RELLENA ESTE CAMPO OBLIGATORIO." — todo en mayúsculas, idéntico para todos los campos, sin orientación sobre qué corregir.  
**Paso del walkthrough:** Paso 12  
**Impacto:** El usuario no puede distinguir entre un campo vacío y un campo con formato incorrecto. El tono agresivo (mayúsculas) genera rechazo en un contexto de compra de alto valor.  
**Recomendación:** Mensajes en minúsculas, específicos por campo: *"Ingresa un celular colombiano de 10 dígitos, ej: 3001234567"*.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-04|H-FORM-04]]

---

### CW-F2-04 🟠 Importante
**Problema:** La sección "Acerca del proyecto" termina con "Descargar brochure" y "Compartir" — ninguno de los dos lleva al contacto directo con el asesor.  
**Paso del walkthrough:** Paso 2  
**Impacto:** El momento de mayor intención del usuario (al terminar de leer la descripción) no tiene CTA de conversión disponible. El usuario debe buscar activamente cómo contactar.  
**Recomendación:** Añadir CTA de contacto directo (WhatsApp) al final de "Acerca del proyecto" con tratamiento visual primario.  
**Referencia cruzada:** [[../2.1/03_detalle-proyecto#H-DETALLE-03|H-DETALLE-03]]

---

## Categoría 2 — Formulario y campos

### CW-F2-05 🔴 Crítico
**Problema:** El formulario solicita tipo y número de documento de identidad como campos obligatorios en un primer contacto.  
**Paso del walkthrough:** Pasos 8 y 9  
**Impacto:** Pedir la cédula para "que me llamen" genera desconfianza activa. El comprador primerizo se pregunta para qué necesita Prodesa su ID en este punto del funnel. Este dato pertenece a la etapa de separación, no de interés inicial.  
**Recomendación:** Reducir a 3 campos: Nombre, Teléfono, y ciudad o proyecto de interés. Cédula solo en etapas avanzadas.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-02|H-FORM-02]]

---

### CW-F2-06 🔴 Crítico
**Problema:** El campo de teléfono acepta números inválidos sin generar ningún error — "+57 5464326" (7 dígitos, no empieza por 3) pasa al CRM sin validación.  
**Paso del walkthrough:** Paso 10 y 13  
**Impacto:** El asesor recibe un lead incontactable. Solo descubre el problema al intentar llamar — después de haber invertido tiempo en preparar la llamada.  
**Recomendación:** Validar formato colombiano: 10 dígitos, empieza por 3. Mensaje específico: *"Ingresa tu celular colombiano: 3001234567"*.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-03|H-FORM-03]]

---

### CW-F2-07 🟡 Menor
**Problema:** Al hacer clic en "Déjanos tus datos", la página hace scroll hacia arriba para mostrar el formulario embebido. El usuario no lo anticipa.  
**Paso del walkthrough:** Paso 7  
**Impacto:** Desorientación leve — Valentina puede no entender qué pasó al ver que la página se mueve sin haber navegado.  
**Recomendación:** Añadir una animación de scroll suave con un ancla visual (resaltado del formulario) para que el usuario entienda que fue llevado al formulario.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-07|H-FORM-07]]

---

## Categoría 3 — Feedback del sistema

### CW-F2-08 🔴 Crítico
**Problema:** La validación del formulario es 100% post-submit — ningún campo muestra error mientras el usuario lo llena. Todos los errores aparecen simultáneamente al dar "Enviar".  
**Paso del walkthrough:** Paso 11  
**Impacto:** En desktop los errores extienden el formulario fuera del viewport, obligando a scroll para encontrarlos. El usuario que llenó 6 campos debe volver a revisar todos.  
**Recomendación:** Validación inline `onBlur` — validar cada campo cuando el usuario lo abandona, antes del envío.  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-03|H-FORM-03]]

---

### CW-F2-09 🟠 Importante
**Problema:** No hay ningún indicador de progreso ni de campos completados durante el llenado del formulario.  
**Paso del walkthrough:** Pasos 8 al 12  
**Impacto:** El usuario no tiene feedback sobre cuánto le falta para terminar. En un formulario de 6 campos esto es tolerable, pero sumado a los otros problemas aumenta la carga cognitiva.  
**Recomendación:** Indicar visualmente cuántos campos han sido completados correctamente (check verde al salir del campo con datos válidos).  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-03|H-FORM-03]]

---

## Categoría 4 — Post-conversión

### CW-F2-10 🔴 Crítico
**Problema:** La pantalla de confirmación no indica canal de respuesta, tiempo estimado ni ofrece ninguna acción de respaldo.  
**Paso del walkthrough:** Pasos 14 y 15  
**Impacto:** Valentina no sabe si la llamarán hoy, mañana, por WhatsApp o por teléfono. La incertidumbre inmediatamente post-envío es el momento de mayor riesgo de pérdida del lead — el usuario puede buscar otra constructora antes de ser contactado.  
**Recomendación:** Confirmación con: (1) nombre del usuario en lugar de correo, (2) canal de respuesta ("te escribiremos por WhatsApp"), (3) tiempo estimado ("en máximo 24 horas hábiles"), (4) CTA de respaldo (botón WhatsApp directo).  
**Referencia cruzada:** [[../2.1/04_formulario-contacto#H-FORM-01|H-FORM-01]]

---

### CW-F2-11 🔴 Crítico
**Problema:** Después de enviar el formulario, no hay ninguna opción para explorar más proyectos, guardar el proyecto como favorito, ni continuar navegando.  
**Paso del walkthrough:** Paso 15  
**Impacto:** El flujo termina en un callejón sin salida. Un usuario que no está 100% seguro de Orizzo no tiene un camino natural para explorar alternativas desde ese punto.  
**Recomendación:** Añadir al final de la confirmación: sección de proyectos similares + opción de "Guardar proyecto" o "Ver más proyectos en Bogotá".  
**Referencia cruzada:** [[../2.1/03_detalle-proyecto#H-DETALLE-06|H-DETALLE-06]] (Orizzo sí tiene proyectos similares; Pietra no)

---

## Conexión con hipótesis H3B

Este walkthrough confirma directamente **[[../2.1/H3B|H3B — CTAs ambiguos o insuficientes]]**:

| Quiebre del flujo | Hallazgo relacionado | Confirmación H3B |
|-------------------|----------------------|------------------|
| Sin CTA de contacto al terminar de leer | [[../2.1/03_detalle-proyecto#H-DETALLE-03\|H-DETALLE-03]] | ✅ El momento de mayor intención no tiene canal de conversión |
| "Agenda tu cita en sala" lleva a Teams | [[../2.1/04_formulario-contacto#H-FORM-06\|H-FORM-06]] | ✅ CTA engañoso destruye la confianza en el momento de decisión |
| Confirmación sin próximo paso | [[../2.1/04_formulario-contacto#H-FORM-01\|H-FORM-01]] | ✅ El usuario queda sin orientación post-conversión |
| WhatsApp no está en homepage ni listado | [[../2.1/04_formulario-contacto#H-FORM-09\|H-FORM-09]] | ✅ El canal de menor fricción no está disponible en las fases previas del funnel |

**Veredicto H3B desde el walkthrough:** La hipótesis se confirma fuertemente. El flujo de contacto falla en los tres momentos críticos: cuando el usuario está listo para actuar (paso 2), cuando elige el canal (paso 5) y cuando completó la acción (paso 14). Son fallas consecutivas del mismo funnel.

---

## Material para tarea 3.1

Este documento, junto con [[01_walkthrough-flujo2|la plantilla del walkthrough]] y las capturas referenciadas, es material directo para el informe final (tarea 3.1). Los hallazgos CW-F2-01, CW-F2-05, CW-F2-08 y CW-F2-10 son los de mayor impacto en conversión y deben aparecer en la sección de hallazgos críticos del informe.

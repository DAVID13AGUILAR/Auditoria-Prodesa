---
tags:
  - prodesa
  - cognitive-walkthrough
  - flujo-2
  - contacto
  - registro
aliases:
  - Walkthrough Flujo 2
  - Registro y Contacto
---
2
# Cognitive Walkthrough — Flujo 2: Registro y Contacto
**Persona:** [[00_persona-valentina|Valentina Morales]]  
**Tarea:** *"Contactar al asesor del proyecto Orizzo para recibir más información sobre el subsidio y el proceso de compra."*  
**Punto de entrada:** Página de detalle del proyecto Orizzo — `prodesa.com/proyecto-vivienda/bogota/orizzo`  
**Dispositivo evaluado:** Desktop (Chrome) + Mobile (Android)  
**Fecha:** Mayo 2026

---

## Plantilla de registro

| Paso | Acción esperada | ¿Es obvio qué hacer? | ¿El sistema responde como se anticipa? | Fricción detectada | Captura |
|------|----------------|----------------------|----------------------------------------|--------------------|---------|
| 1 | Valentina llega a la página de detalle de Orizzo. Espera encontrar información del proyecto y un botón visible para contactar al asesor. | ✅ Sí — sabe que entró a la página del proyecto | ⚠️ Parcial — el hero muestra foto, nombre, precio y área, pero **no hay CTA de contacto visible above the fold en desktop** | La jerarquía visual del hero prioriza el precio sobre el nombre del proyecto. No hay ningún botón de contacto en el primer fold de desktop. | ![[H-DETALLE-1_AGORA-FALLO-JERARQUIA.png]] |
| 2 | Valentina empieza a leer la sección "Acerca del proyecto". Espera encontrar un botón de contacto al terminar de leer — es el momento natural de mayor intención. | ✅ Sí — leer la descripción es el siguiente paso lógico | ❌ No — la sección termina con **"Descargar brochure"** y **"Compartir"**, sin ninguna opción de contacto directo | 🔴 **Crítico:** el momento de mayor intención del usuario no tiene CTA de conversión. Valentina debe buscar activamente dónde contactar. | ![[H-DETALLE-3_DESCONECTADO-WEB.png]] |
| 3 | Valentina hace scroll hacia abajo buscando algo que le permita contactar. Eventualmente descubre la **barra sticky** en la parte inferior con tres opciones: "Déjanos tus datos", "Agenda tu cita" y "Escríbenos a WhatsApp". | ⚠️ Parcial — la barra es persistente pero no llama la atención activamente en desktop | ✅ Sí — la barra sticky está disponible durante todo el scroll | 🟠 **Importante:** Valentina no descubrió el canal de contacto de inmediato — tuvo que buscar. En mobile la barra es más visible porque ocupa el ancho completo de la pantalla. | ![[H-DETALLE-3_CTA-MOBILE.png]] |
| 3a | Valentina observa cuál de los tres CTAs de la barra sticky tiene mayor protagonismo visual — cuál parece "el principal". | ⚠️ Parcial — los tres botones compiten sin jerarquía clara | ❌ No — los tres CTAs tienen peso visual similar; no existe un botón primario claramente diferenciado del resto. Evaluador: contraste WCAG de los botones contra el fondo de la barra pendiente de verificar con herramienta de accesibilidad (referencia cruzada con tarea 2.4). | 🟠 **Importante:** sin jerarquía visual entre los tres CTAs, Valentina elige por posición y no por intención. En mobile los tres botones ocupan el mismo ancho — el ojo no tiene un punto de entrada claro. | — |
| 4 | Valentina evalúa las tres opciones de contacto. Lee los labels y trata de entender qué hace cada uno. | ⚠️ Parcial — WhatsApp y "Déjanos tus datos" son claros, pero **"Agenda tu cita"** es ambiguo | ❌ No totalmente — "Agenda tu cita" no indica si es visita física, videollamada o llamada telefónica | 🟠 **Importante:** el label "Agenda tu cita" no comunica el nivel de compromiso ni el canal. Valentina no sabe si agendará una visita presencial o algo virtual. | — |
| 5 | Valentina hace clic en **"Agenda tu cita en sala"** porque interpreta "en sala" como una visita a la sala de ventas del proyecto. Espera ver un formulario para agendar la visita física. | ❌ No — el label es engañoso | ❌ No — el sistema abre un **calendario de Microsoft Teams** para una reunión virtual de 30 minutos | 🔴 **Crítico:** promesa vs. entrega completamente desalineadas. Valentina esperaba una visita física ("en sala") y encuentra una interfaz de videollamada. Esto genera confusión y pérdida de confianza. | ![[H-FORMULARIO-6_CTA-TEAMS.png]] |
| 6 | Valentina retrocede y decide intentar **"Escríbenos a WhatsApp"** — su canal preferido. | ✅ Sí — el label es claro y el icono de WhatsApp es reconocible | ✅ Sí — la acción redirige correctamente a WhatsApp con un mensaje predefinido | ✅ Sin fricción — este es el camino de menor fricción del flujo y funciona correctamente | — |
| 7 | *Ruta alternativa:* Valentina vuelve al detalle y decide usar **"Déjanos tus datos"** en lugar de WhatsApp. Espera ver un formulario corto para dejar su nombre y teléfono. | ✅ Sí — el label sugiere un formulario | ⚠️ Parcial — la página hace **scroll hacia arriba** para mostrar el formulario embebido. Valentina puede confundirse al ver que la página se mueve sin haber navegado a ningún lado | 🟡 **Menor:** el comportamiento de scroll inesperado puede desorientar al usuario que esperaba que se abriera una ventana modal o una nueva página | — |
| 8 | Valentina ve el formulario. Espera pedir solo su nombre y teléfono para que la contacten. | ⚠️ Parcial — ve un formulario pero tiene más campos de los esperados | ❌ No — el formulario tiene **6 campos obligatorios** incluyendo **Tipo de Documento** y **Nro de Documento** | 🔴 **Crítico:** pedir número de cédula en un primer contacto genera desconfianza. Valentina se pregunta: *"¿Para qué necesitan mi cédula solo para que me llamen?"* Evaluador — estructura del formulario: los labels no son flotantes (desaparecen al escribir). Orden de campos: Nombre → Tipo Documento → Nro Documento → Celular → Correo → Ciudad → Proyecto de interés — el dato más sensible (cédula) aparece en el tercer campo, no al final. Todos los campos obligatorios marcados con asterisco (*) sin leyenda explicativa al pie del formulario. Placeholders genéricos sin ejemplo de formato (campo celular sin "ej: 3001234567"). | ![[H-FORMULARIO-2_WEB.png]] |
| 8a | *Solo mobile:* Valentina intenta tocar cada campo con el dedo y llena el formulario con el teclado táctil. | ✅ Sí — los campos son visibles | ⚠️ Parcial — los campos tienen altura razonable, pero el botón "Enviar" puede quedar oculto bajo el teclado táctil en pantallas pequeñas (Samsung Galaxy A) | 🟠 **Importante:** si el botón de envío queda tapado por el teclado, Valentina puede asumir que no existe o que el formulario no tiene envío. Touch targets pendientes de verificar: referencia 44×44pt (iOS HIG) / 48×48dp (Material Design). | — |
| 9 | Valentina empieza a llenar el formulario. Al llegar a "Tipo De Documento" y "Nro De Documento" duda si continuar. | ❌ No — no es obvio por qué son necesarios en este punto | ❌ No — no hay ningún texto de ayuda que explique para qué sirven estos campos | 🔴 **Crítico:** ausencia total de micro-copy explicativo. Los labels usan capitalización inconsistente ("Tipo De Documento") y la abreviatura "Nro" no es estándar | ![[H-FORMULARIO-2_MOBILE.png]] |
| 10 | Valentina ingresa su número de teléfono: escribe "+57 5464326" (formato inválido — 7 dígitos, no empieza por 3). Espera que el sistema le avise si hay un error. | ✅ Sí — escribe en el campo de teléfono | ❌ No — **el sistema no muestra ningún error** mientras escribe ni al salir del campo | 🔴 **Crítico:** ausencia de validación inline. Valentina no sabe que su teléfono es inválido. Este dato llegará al CRM sin ninguna alerta, generando un lead incontactable. | ![[H-FORMULARIO-3_ERROR-MOBILE.png]] |
| 11 | Valentina deja algunos campos vacíos y da clic en **"Enviar"**. Espera que el sistema le indique qué falta. | ✅ Sí — da clic al botón naranja "Enviar" | ❌ No — todos los errores aparecen **simultáneamente al enviar**, no de forma progresiva | 🔴 **Crítico:** validación 100% post-submit. En desktop los errores extienden el formulario fuera del viewport — Valentina debe hacer scroll para verlos todos. En mobile son visibles sin scroll. | ![[H-FORMULARIO-3_ERROR-WEB.png]] |
| 12 | Valentina lee los mensajes de error para saber qué corregir. | ⚠️ Parcial — los mensajes están en rojo, son visibles | ❌ No — todos dicen **"RELLENA ESTE CAMPO OBLIGATORIO."** en mayúsculas, sin indicar qué formato se espera ni por qué es necesario cada campo | 🟠 **Importante:** mensajes genéricos en mayúsculas son agresivos y no orientan la corrección. El campo de teléfono inválido no recibe ningún mensaje específico. | ![[H-FORMULARIO-3_ERROR-MOBILE.png]] |
| 13 | Valentina corrige los campos vacíos pero no el teléfono (no sabe que es inválido). Da clic en **"Enviar"** de nuevo. | ✅ Sí | ⚠️ Parcial — el formulario se envía exitosamente a pesar del teléfono inválido | 🔴 **Crítico:** el CRM recibe un lead con número de teléfono incontactable. El asesor solo descubrirá el problema al intentar llamar. | — |
| 13a | Valentina presiona **"Enviar"** y espera que el sistema procese el formulario. | ✅ Sí — presiona el botón | ⚠️ Sin datos — no se documentó si hay indicador de carga (spinner o barra de progreso) durante el procesamiento, ni la latencia percibida entre el clic y la respuesta del sistema | 🟡 **Menor:** si la latencia es perceptible (>300 ms) sin ningún feedback visual, Valentina puede presionar "Enviar" varias veces creyendo que no funcionó, generando leads duplicados en el CRM. Pendiente verificar. | — |
| 14 | Valentina ve la **pantalla de confirmación**. Espera saber cuándo y cómo la contactarán. | ✅ Sí — espera una confirmación | ❌ No — la pantalla muestra: *"¡Gracias [correo electrónico] por contactarnos!"* sobre una imagen genérica de vivienda. Sin canal, sin tiempo de respuesta, sin próximo paso. Tipo de confirmación: página separada (nueva vista), no un mensaje inline dentro del formulario. | 🔴 **Crítico (privacidad):** el mensaje expone el correo electrónico del usuario en pantalla. Además, Valentina no sabe si la llamarán hoy, mañana, por WhatsApp o por teléfono. Tono: genérico — no transmite calidez ni urgencia apropiada para una decisión de compra de vivienda de alto valor. | ![[H-DETALLE-9_SIN-TOOLTIP-WEB.png]] |
| 15 | Valentina busca algo que hacer mientras espera ser contactada — explorar más proyectos, añadir a favoritos, o contactar por WhatsApp directamente. | ✅ Sí — querría tener una acción de respaldo | ❌ No — la pantalla de confirmación no ofrece ninguna acción adicional. Es un callejón sin salida visual. | 🔴 **Crítico:** sin CTA de respaldo (WhatsApp directo), sin link a explorar proyectos similares, sin opción de guardar el proyecto. El flujo termina sin retención. | — |
| 16 | Valentina revisa su correo y WhatsApp esperando una confirmación automática de que su solicitud fue recibida. | ✅ Sí — espera al menos un acuse de recibo del sistema | ❌ Sin datos — no se verificó si el sitio envía email o SMS automático post-envío. Pendiente probar con email de prueba y documentar contenido y timing de respuesta. | 🟠 **Importante:** si no hay confirmación automática por email o SMS, Valentina no tiene ningún registro de haber enviado la solicitud. Esto amplifica la incertidumbre post-conversión documentada en los pasos 14 y 15. | — |

---

## Evaluación mobile — diferencias respecto a desktop

| Paso | Comportamiento en mobile | Diferencia vs. desktop |
|------|--------------------------|----------------------|
| 1 | Barra sticky más visible desde el inicio — ocupa todo el ancho inferior | ✅ Mejor que desktop |
| 3 | Los 3 CTAs de contacto son inmediatamente visibles en la barra sticky | ✅ Mejor que desktop |
| 8 | 6 campos en teclado táctil — la cédula requiere cambiar a teclado numérico manualmente | ❌ Peor que desktop |
| 8a | El botón "Enviar" puede quedar oculto bajo el teclado táctil en pantallas pequeñas. Touch targets pendientes de verificar. | ❌ Peor que desktop |
| 11 | Los errores post-submit son visibles sin hacer scroll | ✅ Mejor que desktop |
| 12 | Los mensajes en mayúsculas ocupan más espacio relativo en pantalla pequeña — más agresivos visualmente | ❌ Peor que desktop |

---

## Resumen de quiebres del flujo

El flujo de contacto de Valentina tiene **3 quiebres críticos** que pueden generar abandono:

1. **Paso 2** — Después de leer el proyecto y estar lista para actuar, no hay CTA de contacto directo. El sitio no le abre la puerta en el momento correcto.
2. **Paso 5** — "Agenda tu cita en sala" lleva a Teams. Si Valentina quería una visita física, se siente engañada y vuelve atrás — o abandona.
3. **Paso 14** — Después de esforzarse en llenar 6 campos, la confirmación no le dice nada útil. La incertidumbre post-envío puede llevarla a buscar otra constructora.

El **único camino sin fricción** en este flujo es el botón de WhatsApp (Paso 6) — pero Valentina tiene que descubrirlo activamente.

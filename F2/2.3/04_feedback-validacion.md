---
status: en-progreso
created: 2026-06-09
tags:
  - prodesa
  - cognitive-walkthrough
  - feedback
  - validacion
  - flujo-2
fase: "2.3"
aliases:
  - Feedback y Validación Flujo 2
---

# 04 — Feedback del sistema y validación — CW Flujo 2

**Persona:** [[01_persona|Valentina Ríos]]
**Hipótesis:** [[H3B]]
**Ref. cruzada:** [[F2/2.1/04_formulario-contacto#H-FORM-03]] · [[F2/2.1/04_formulario-contacto#H-FORM-04]]

---

## Registro de walkthrough — Feedback y validación

| Paso | Acción esperada | Q1 ¿Sabe qué hacer? | Q2 ¿Ve el control? | Q3 ¿Entiende causa→efecto? | Q4 ¿El sistema confirma progreso? | Fricción detectada | Severidad | Captura |
|------|----------------|---------------------|--------------------|-----------------------------|-----------------------------------|--------------------|-----------|---------|
| 3a | Valentina escribe un número de teléfono inválido (ej. "+57 54643"). Espera que el sistema le avise mientras escribe o al salir del campo. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |
| 3b | Valentina escribe un correo con formato inválido. Evalúa si hay validación inline al salir del campo. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |
| 3c | Valentina deja campos obligatorios vacíos y hace clic en "Enviar". Evalúa si los errores aparecen de forma progresiva o todos de golpe. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |
| 3d | Valentina lee los mensajes de error. Evalúa si son claros, específicos y proporcionales. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |
| 3e | Valentina envía el formulario con datos inválidos (teléfono de 7 dígitos). Evalúa si el sistema los acepta o rechaza. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |
| 3f | Valentina hace clic en "Enviar" con datos válidos. Evalúa si hay indicador de carga mientras el sistema procesa. | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente | pendiente |

---

## Checklist de evaluación

- [ ] ¿Hay validación inline al salir de un campo (onBlur)?
- [ ] ¿La validación de teléfono rechaza formatos inválidos?
- [ ] ¿La validación de correo rechaza formatos inválidos?
- [ ] ¿Los errores aparecen todos al enviar (post-submit) o de forma progresiva?
- [ ] ¿Los mensajes de error son específicos por campo o genéricos para todos?
- [ ] ¿Los mensajes de error están en mayúsculas? ¿el tono es agresivo?
- [ ] ¿Datos falsos (teléfono inválido) pasan al CRM sin ninguna alerta?
- [ ] ¿Hay indicador de carga entre el clic en "Enviar" y la respuesta del sistema?
- [ ] En mobile: ¿el teclado tapa el botón "Enviar"?

---

## Comportamiento de validación documentado

| Campo | Validación inline | Mensaje de error | Acepta datos inválidos |
|-------|-------------------|------------------|------------------------|
| Teléfono | pendiente | pendiente | pendiente |
| Correo | pendiente | pendiente | pendiente |
| Nombre | pendiente | pendiente | pendiente |
| Documento | pendiente | pendiente | pendiente |
| Checkbox política | pendiente | pendiente | pendiente |

---

→ [[03_formulario]] · [[05_confirmacion-postenvio]]

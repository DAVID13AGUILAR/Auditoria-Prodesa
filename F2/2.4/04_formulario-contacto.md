---
tags:
  - prodesa
  - accesibilidad
  - wcag
  - formulario
aliases:
  - Accesibilidad Formulario
---

# Accesibilidad — Formulario de Contacto
**Tarea:** [[00_plantilla|2.4 — Revisión de accesibilidad (WCAG 2.0)]]
**URL:** https://prodesa.com/contactanos (y formulario incrustado en detalle de proyecto)
**Fecha:** Junio 2026
**Estado:** ✅ Validado con WAVE — 7 errores, 11 contraste, 74 alertas · AIM Score 6.0/10

---

## Contexto previo (de tarea 2.1)

- **H-FORM-01** — Sin pantalla de confirmación post-envío. Crítico.
- **H-FORM-03** — Validación probablemente solo al enviar (post-submit), no inline.
- **H-FORM-05** — Footer tiene 4 teléfonos, 3 con el mismo número (confirmado en HTML).
- **H-FORM-09** — Sin botón flotante de WhatsApp.

---

## Resumen WAVE

| Métrica | Valor |
|---------|-------|
| AIM Score | **6.0 / 10** |
| Errores | **7** (1 missing label + 3 empty buttons + 3 broken ARIA) |
| Contraste | **11 Very low contrast** |
| Alertas | **74** (9 fieldset sin legend + 4 skipped headings + 21 very small text + más) |
| Form labels positivos | **8** |
| Estructura | H1(1) · H2(9) · H3(15) · H6(11) · 5 iframes |

---

## Inventario de hallazgos

| ID | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|----------|---------------|-------|-------------|-----------|
| A-CONTACT-01 | Jerarquía de headings | 1.3.1 Info y relaciones | A | **CONFIRMADO** — 4 saltos de nivel confirmados por WAVE. H1→H6 (5 niveles de golpe) para el bloque EMMA/teléfonos/email. H2→H6 ×2. H3→H6 en FAQ. 11 H6 usados para datos de contacto y preguntas frecuentes — semántica de estilo, no de estructura | 🔴 Crítico |
| A-CONTACT-02 | 3 Broken ARIA references | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — 3 atributos `aria-labelledby` o `aria-describedby` apuntan a IDs que no existen en el DOM. Bug del SPA React: IDs dinámicos que se pierden entre re-renders. Screen reader anuncia el elemento pero no puede leer su etiqueta — queda completamente sin contexto | 🔴 Crítico |
| A-CONTACT-03 | 9 Fieldsets sin legend | 1.3.1 Info y relaciones | A | **CONFIRMADO** — 9 `<fieldset>` sin `<legend>`. El formulario tiene múltiples grupos (datos personales, proyecto de interés, etc.) que el screen reader no puede identificar. El usuario navega campos sin saber a qué sección pertenecen | 🟠 Importante |
| A-CONTACT-04 | Label chaos en el formulario | 3.3.2 Etiquetas o instrucciones | A | **CONFIRMADO** — Triple problema: (1) 1 Missing form label en error rojo, (2) 3 Orphaned form labels (labels que existen pero no están vinculados a ningún input), (3) 1 Select sin label. El formulario tiene labels rotos en ambas direcciones | 🔴 Crítico |
| A-CONTACT-05 | 11 errores de contraste | 1.4.3 Contraste | AA | **CONFIRMADO** — 11 Very low contrast. Más que Siena (8), menos que homepage (20). Patrón sistémico confirmado en las 4 páginas del flujo | 🔴 Crítico |
| A-CONTACT-06 | 3 Empty buttons | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — 3 botones sin texto ni aria-label. Refuerza A-HOME-03 como sistémico: homepage(2) + Siena(1) + /contactanos(3) = 6 empty buttons en el sitio | 🔴 Crítico |
| A-FORM-02 | Campos requeridos | 3.3.2 / 1.3.1 | A | **POSITIVO** — Los inputs tienen `required=""` correctamente. Screen readers anuncian los campos como obligatorios. El formulario es un **embed de HubSpot** (`class="hs-input"`, IDs con GUID dinámico) — los problemas de labels y placeholders requieren configuración en HubSpot, no CSS propio | ✅ Pasa |
| A-FORM-03 | Mensajes de error insuficientes y poco visibles | 3.3.1 / 3.3.3 Identificación y sugerencia de errores | A/AA | **CONFIRMADO** — Los mensajes aparecen pero: (1) Solo dicen "campo obligatorio" sin describir cuál es el error ni cómo corregirlo (falla 3.3.3). (2) El texto es muy pequeño, difícil de leer especialmente en mobile. (3) No indican formato esperado (ej. para teléfono: "Ingresa 10 dígitos sin espacios"). WCAG exige identificar el campo con error Y describir el problema en texto | 🔴 Crítico |
| A-FORM-04 | Contraste del botón de envío | 1.4.3 Contraste | AA | **PENDIENTE VALIDAR** — Medir ratio con Colour Contrast Analyser: hex texto = ___ / hex fondo = ___ / ratio = ___ | pendiente |
| A-FORM-05 | Confirmación post-envío sin pasos siguientes ni seguimiento | 4.1.3 / 3.3.4 Mensajes de estado | AA | **CONFIRMADO** — Redirige a `/Thankyou` en español. Técnicamente accesible. Pero: (1) La página no indica cuándo ni cómo contactarán al usuario. (2) No se recibe correo ni SMS de confirmación tras el envío. (3) El usuario no sabe si su solicitud fue recibida realmente, quién maneja sus datos ni bajo qué condiciones. Genera incertidumbre activa sobre el destino de datos personales (nombre, email, teléfono) entregados voluntariamente | 🔴 Crítico |
| A-FORM-06 | Navegación por teclado — 3 fallos | 2.4.7 / 2.1.1 | AA/A | **CONFIRMADO** — (1) El foco recae sobre el texto de la etiqueta flotante en lugar del `<input>` — el usuario no sabe qué campo está activo. (2) El campo de teléfono no muestra indicador de foco — no se puede saber si está seleccionado. (3) El campo de tipo de documento tampoco muestra foco. Los campos sin foco visible son inoperables por teclado: falla 2.4.7 (Focus Visible) y 2.1.1 (Teclado) | 🔴 Crítico |
| A-FORM-07 | Teléfonos duplicados en footer | 1.3.1 Info y relaciones | A | **CONFIRMADO** — (de 2.1 H-FORM-05) Footer tiene 4 teléfonos pero 3 muestran el mismo número (+573241000060). Para screen readers, repetición confusa sin propósito diferenciado | 🟠 Importante |
| A-FORM-08 | Campo de teléfono con selector de país sin instrucción clara | 3.3.2 Etiquetas o instrucciones / 1.3.1 | A | **CONFIRMADO** — El campo de teléfono combina un selector de indicativo de país (+57) con el número, pero no hay instrucción visible que explique que son dos partes del mismo campo. El usuario interpreta el selector de país como un campo separado, comete el error e intenta interactuar con él incorrectamente, provocando un fallo. Diseño ambiguo que genera error de usuario antes de llegar al envío | 🔴 Crítico |
| A-FORM-09 | Placeholders no desaparecen al escribir | 1.4.3 / 3.3.2 | A | **CONFIRMADO** — El texto placeholder permanece visible mientras el usuario escribe, solapándose con el texto ingresado. El usuario no puede leer lo que está escribiendo. Puede causar errores no detectados antes del envío. Especialmente crítico en mobile donde el área ya es pequeña | 🔴 Crítico |
| A-FORM-10 | Área de escritura de inputs demasiado pequeña | 2.5.5 Tamaño del objetivo | AAA | **CONFIRMADO** — Los campos del formulario tienen un área interactiva muy reducida, generando frustración y errores de toque en mobile. Crítico considerando que el 81% del tráfico de Prodesa es mobile (Android, Colombia). Un input pequeño = mayor tasa de abandono del formulario | 🔴 Crítico |

---

## Checklists de validación

### WAVE
- [x] WAVE ejecutado en `https://prodesa.com/contactanos` ✅
  - 7 errores · 11 contraste · 74 alertas · AIM 6.0

### Pendientes de validación manual
- [ ] Enviar formulario vacío → capturar mensajes de error (A-FORM-03)
- [ ] Enviar formulario con datos reales → verificar mensaje de confirmación (A-FORM-05)
- [ ] Medir contraste botón de envío con Colour Contrast Analyser (A-FORM-04)
- [ ] Navegar formulario solo con Tab → orden lógico y sin trampa de foco (A-FORM-06)
- [ ] En DevTools: verificar `required`/`aria-required` en campos con asterisco (A-FORM-02)

---

## Notas de revisión en campo

> Anotar aquí observaciones libres durante la revisión.

---

→ [[00_plantilla]] · [[03_detalle-proyecto]] · [[05_inventario-final]]

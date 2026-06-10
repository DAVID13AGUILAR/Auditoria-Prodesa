---
status: completado
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - inventario
  - hallazgos
aliases:
  - Inventario CW Flujo 1
fase: "2.2"
---

# 08 — Inventario de hallazgos — Cognitive Walkthrough Flujo 1
**Persona:** [[01_persona-valentina]]
**Hipótesis principal:** [[H3A]] · Secundarias: [[H3B]] · [[H3C]]

---

## Hallazgos por categoría

### AI — Arquitectura de información

| ID | Paso | Descripción | Sev. | Ref. 2.1 | Hipótesis |
|----|------|-------------|------|----------|-----------|
| CW-01 | 1b | Modal promocional "PONTE LA 10" sin botón de cierre visible — primera impresión bloqueante | 🔴 | — | H3A |
| CW-03 | 3a | Filtro de tipo VIS ausente en desktop — tarea parcialmente irrealizable | 🔴 | H-FILTROS-07 | H3A |
| CW-04 | 3a | Filtros no persistentes al navegar al detalle y volver | 🔴 | H-DETALLE-07 / H-FILTROS-03 | H3A |
| CW-05 | 4a | Chip VIS en tarjetas sin tooltip — compradora primeriza no puede auto-calificarse | 🟠 | H-HOME-04 / H-FILTROS-02 | H3A / H3B |
| CW-06 | 4a | Sin estado del proyecto en tarjetas (preventa / construcción / entrega) | 🟠 | H-DETALLE-08 | H3A / H3B |
| CW-07 | 4b | Scanneabilidad insuficiente — no puede comparar proyectos sin entrar a cada uno | 🟠 | H-FILTROS-01 / H-DETALLE-06 | H3A |
| CW-64 | 4a | Sin criterio visible de ordenamiento en resultados — Valentina no sabe si ve los proyectos por precio, relevancia o distancia | 🟠 | H-FILTROS-01 | H3A |
| CW-08 | 4c | Tabs Todos / Disponibles / Vendidos sin contexto — Valentina puede tener resultados en "Todos" sin saberlo | 🟠 | H-FILTROS-05 | H3A |
| CW-09 | 4d | Sección "otras ciudades" sin separación visual — puede confundirse con más resultados de Bogotá | 🟠 | H-FILTROS-05 | H3A |
| CW-10 | 4d | Sin confirmación de fin de resultados — no sabe si vio todas las opciones disponibles | 🟠 | H-FILTROS-01 | H3A |
| CW-11 | 5a | Chip redundante "Proyecto de vivienda" sobre el nombre en mobile | 🟠 | H-DETALLE-01 | H3B |
| CW-12 | 5a | Sin chip de estado del proyecto en el hero (preventa / en construcción / entrega) | 🟠 | H-DETALLE-08 | H3A / H3B |
| CW-13 | 5a | Asterisco con precio en SMMLV — jerga técnica, primera compradora no entiende el precio exacto | 🟠 | H-DETALLE-05 | H3A / H3B |
| CW-14 | 5a | Sin breadcrumbs en el detalle — al volver al listado pierde filtros y posición | 🟠 | H-HOME-07 / H-DETALLE-07 | H3A |
| CW-02 | 5d | "Obra gris" sin tooltip ni definición — primera compradora VIS no sabe qué estado de entrega implica | 🟠 | H-HOME-04 | H3A / H3B |
| CW-15 | 5e | "Mi Casa Ya" ausente en todo el sitio — término clave del comprador VIS invisible | 🔴 | H-DETALLE-09 | H3A |
| CW-16 | 5e | "Subsidio de caja de compensación" enterrado en prosa de marketing a ~2 scrolls | 🟠 | H-DETALLE-09 | H3A / H3B |
| CW-17 | 5e | Sin monto, requisitos ni enlace externo del subsidio — Valentina no sabe si califica | 🟠 | H-DETALLE-09 | H3A / H3B |
| CW-18 | 5e | Mención de subsidio solo en algunos proyectos — inconsistencia de contenido | 🟠 | H-DETALLE-06 | H3A |
| CW-19 | 5f | Sin comparador de proyectos — gestiona decisión de alto riesgo en 2 ventanas del navegador | 🔴 | H-DETALLE-06 / H-DETALLE-07 | H3A |
| CW-20 | 5f | Tabs con opciones inconsistentes entre proyectos — modelo mental roto al comparar | 🔴 | H-DETALLE-06 | H3A |
| CW-21 | 5f | Sin ficha técnica estandarizada — información diferente en diferente orden | 🟠 | H-DETALLE-06 | H3A |
| CW-22 | 6c | Confirmación post-envío sin próximo paso — sin canal, sin tiempo de respuesta, sin CTA de respaldo | 🟠 | H-FORM-01 | H3A |
| CW-23 | 6c | Mobile redirige a página genérica de contacto, no a pantalla de "gracias" dedicada | 🟠 | H-FORM-01 | H3A / H3C |
| CW-24 | 6c | Inconsistencia mobile/desktop en confirmación — mobile genérico, desktop expone email del usuario | 🟠 | H-FORM-01 / H-DETALLE-06 | H3A / H3C |

### VD — Visual design / jerarquía

| ID | Paso | Descripción | Sev. | Ref. 2.1 | Hipótesis |
|----|------|-------------|------|----------|-----------|
| CW-25 | 2a | Hero sin propuesta de valor — no puede confirmar en 5 segundos que hay proyectos VIS en Bogotá | 🟠 | H-HOME-09 | H3A / H3B |
| CW-26 | 2b | Doble navbar — gasta tiempo cognitivo entendiendo estructura en lugar de buscar proyectos | 🟠 | H-HOME-02 | H3A |
| CW-27 | 2c | CTA "Buscar proyecto" de bajo contraste en mobile — compite con "Realizar Pago" | 🟠 | H-HOME-09 / H-FILTROS-07 | H3A / H3C |
| CW-28 | 4a | Precio domina visualmente sobre nombre del proyecto en tarjetas | 🟠 | H-DETALLE-02 | H3B |
| CW-29 | 5a | Jerarquía visual plana en detalle — precio y m² con igual peso visual | 🟠 | H-DETALLE-01 / H-DETALLE-02 | H3B |
| CW-30 | 5d | Íconos decorativos sobredimensionados en mobile (~60-70px) — scroll fatigue y texto truncado | 🟠 | — | H3A / H3C |

### FI — Filtros / interacción

| ID | Paso | Descripción | Sev. | Ref. 2.1 | Hipótesis |
|----|------|-------------|------|----------|-----------|
| CW-31 | 3b | Slider de precio sin campo de texto · escala lineal inadecuada — $200M = 9% del ancho | 🟠 | H-FILTROS-06 | H3A / H3C |
| CW-32 | 3b | Filtro de precio below the fold en desktop — Valentina puede no saber que existe | 🟠 | H-FILTROS-07 | H3A |
| CW-33 | 3c | Sin scroll automático ni confirmación de resultados tras aplicar filtros | 🟠 | H-FILTROS-09 | H3A |
| CW-34 | 3d | "Limpiar filtros" como texto plano sin affordance de botón — resetea todos los filtros sin aviso | 🟠 | H-FILTROS-03 | H3A |
| CW-35 | 3e | Panel "Busca un lugar" contiene tipos de proyecto — etiqueta contradictoria | 🟠 | H-FILTROS-02 | H3A |
| CW-36 | 3e | Sin tooltip en opciones VIS / VIP / NO VIS — Valentina selecciona a ciegas | 🟠 | H-FILTROS-02 / H-HOME-04 | H3A / H3B |
| CW-37 | 3e | Selección múltiple VIS + VIP sin indicación de cómo se combinan los filtros | 🟠 | H-FILTROS-02 | H3A |
| CW-38 | 4a | Asterisco con significado distinto en cada tarjeta — "Precio fijo" en unas, otro texto en otras | 🟠 | H-FILTROS-06 | H3A / H3B |
| CW-39 | 6a | Sticky de contacto inconsistente — 2 o 3 CTAs según proyecto | 🟠 | H-DETALLE-06 / H-FORM-09 | H3A |
| CW-40 | 6a | "Agenda tu cita" abre Teams en ventana nueva sin aviso ni contexto del proyecto | 🟠 | H-FORM-06 / H-DETALLE-01 | H3A / H3B |
| CW-41 | 6b | Validación 100% post-submit — errores en bloque, mensajes idénticos en mayúsculas | 🔴 | H-FORM-03 / H-FORM-04 | H3A / H3C |
| CW-42 | 6b | Sin validación de autenticidad — datos falsos (nombre, teléfono, correo inventados) pasan al CRM | 🔴 | H-FORM-03 | H3A |
| CW-43 | 6b | Inconsistencia de campos mobile/desktop en el mismo formulario — mobile 4 campos, desktop 6 | 🟠 | H-FORM-02 / H-DETALLE-06 | H3A / H3C |
| CW-44 | 6b | Formulario no cabe en mobile — sticky se superpone, botón "Enviar" fuera del viewport | 🟠 | H-FORM-02 | H3C |
| CW-45 | 6b | Sin campo de proyecto — Valentina no confirma a qué proyecto corresponde su contacto | 🟠 | H-FORM-07 / H-DETALLE-07 | H3A |
| CW-46 | 6b | Checkbox de política de datos obligatorio con texto legal extenso — fricción en primer contacto | 🟠 | H-FORM-02 | H3A / H3B |
| CW-47 | 6c | Mobile muestra 3 de 4 teléfonos de contacto con el mismo número | 🟠 | H-FORM-05 | H3B |
| CW-48 | 6d | "Agenda tu cita" no indica que es videollamada — Valentina espera visita presencial | 🟠 | H-FORM-06 | H3A / H3B |
| CW-49 | 6d | Teams no pre-carga el proyecto — asesor recibe cita sin contexto de origen | 🟠 | H-FORM-06 / H-FORM-07 | H3A |

### RP — Rendimiento percibido

| ID | Paso | Descripción | Sev. | Ref. 2.1 | Hipótesis |
|----|------|-------------|------|----------|-----------|
| CW-50 | 1a | SPA sin SSR — Performance Score: 3/100 · FCP: 14,3 s · LCP: 39,6 s · TBT: 2.050 ms · Speed Index: 15,1 s | 🔴 | H-HOME-01 | H3A / H3C |
| CW-63 | 1a | CLS: 0,882 — elementos se mueven durante la carga, Valentina puede tocar el elemento equivocado | 🔴 | H-HOME-01 | H3C |
| CW-51 | 4c | Empty state invisible — mobile: mensaje "No se encuentra información" debajo del fold | 🟠 | H-FILTROS-05 | H3A / H3C |
| CW-52 | 5b | Mapa a 6–7 scrolls — conectividad de transporte sepultada al fondo de la página | 🟠 | H-DETALLE-05 / H-DETALLE-03 | H3A |
| CW-53 | 5b | Precio sin desglose por unidad — solo "Desde $X", sin tipologías disponibles | 🟠 | H-DETALLE-05 | H3A / H3B |
| CW-54 | 5b | Información de transporte solo en texto corrido de "Acerca del proyecto" — no escaneable | 🟠 | H-DETALLE-05 | H3A |
| CW-55 | 5c | Precio por unidad existe en galería/plano pero no en la sección principal de precio | 🟠 | H-DETALLE-05 / H-DETALLE-06 | H3A / H3B |
| CW-56 | 5d | Fecha de entrega ausente en toda la página — Valentina no puede planificar mudanza | 🔴 | H-DETALLE-05 / H-DETALLE-08 | H3A |
| CW-57 | 5d | Label "Inmuebles disponibles" no intuitivo para encontrar planos | 🟠 | H-HOME-04 / H-DETALLE-01 | H3A |

### 🟡 Menores

| ID | Paso | Descripción | Sev. | Ref. 2.1 | Hipótesis |
|----|------|-------------|------|----------|-----------|
| CW-58 | 4a | Resultados superan el presupuesto filtrado — consecuencia de la imprecisión del slider (→ CW-31) | 🟡 | H-FILTROS-06 / H-FILTROS-09 | H3A |
| CW-59 | 4c | Selector COP / USD / EUR — ruido visual irrelevante para compradora local | 🟡 | H-HOME-03 | H3A |
| CW-60 | 5c | Descripciones de imágenes en galería demasiado pequeñas para leer | 🟡 | H-DETALLE-01 | H3A |
| CW-61 | 6b | Teléfono inválido no genera error específico — pasa al CRM sin validación de formato | 🟡 | H-FORM-03 | H3A / H3C |
| CW-62 | 6b | Error del checkbox de política truncado en mobile ("RELLENA ESTE CAM...") | 🟡 | H-FORM-04 | H3C |

---

## Resumen

| Categoría | 🔴 Críticos | 🟠 Importantes | 🟡 Menores |
|-----------|------------|---------------|-----------|
| AI | 6 | 19 | — |
| VD | — | 6 | — |
| FI | 2 | 17 | — |
| RP | 3 | 6 | — |
| 🟡 Menores | — | — | 5 |
| **Total** | **11** | **48** | **5** |

> **64 hallazgos documentados** (CW-01 a CW-64). Todos vinculados al paso del walkthrough y referenciados contra hallazgos de la tarea 2.1. Solo CW-01 y CW-30 son hallazgos sin precedente en 2.1 — descubiertos exclusivamente en el CW.

---

## Distribución por hipótesis

| Hipótesis | Descripción | Hallazgos |
|-----------|-------------|-----------|
| H3A | Arquitectura de información no orienta a Valentina | 52 (principal — presente en casi todos los hallazgos) |
| H3B | Valentina no confía en la información del sitio | 18 (precios ambiguos, jerga técnica, términos opacos) |
| H3C | Experiencia mobile inferior a desktop | 14 (performance, formulario, filtros, layout shift) |

---

## Conclusión H3A

**H3A confirmada en todas las etapas del flujo:**

La arquitectura de información no orienta a Valentina hacia el proyecto correcto para su perfil en ningún punto del recorrido. Los filtros no persistentes y la ausencia del filtro VIS en desktop bloquean el descubrimiento desde el inicio (CW-03, CW-04). La jerarquía visual plana, la falta de estado del proyecto y la fecha de entrega ausente impiden la evaluación en el detalle (CW-12, CW-29, CW-56). El término "Mi Casa Ya" es invisible en todo el sitio — el subsidio más buscado por compradores VIS no existe como concepto en la plataforma (CW-15). La ausencia de comparador obliga a gestionar una decisión financiera de alto riesgo en dos ventanas del navegador con estructura inconsistente entre proyectos (CW-19, CW-20). En el contacto, la validación post-submit, los datos falsos sin verificación y la confirmación sin próximo paso cierran el flujo sin orientar al usuario (CW-41, CW-42, CW-22). El sitio en su estado actual no está diseñado para el perfil de primera compradora VIS.

---

## Referencia tarea 3.1

> Este inventario alimenta directamente la **tarea 3.1** (consolidación de hallazgos). Para la consolidación usar:
> - Los 11 hallazgos 🔴 Críticos como prioridad máxima
> - Los hallazgos con hipótesis H3A + H3B como los de mayor impacto en conversión
> - Los hallazgos con hipótesis H3C para el análisis de brecha mobile/desktop
> - Las referencias a 2.1 (columna Ref. 2.1) para cruzar con el inventario heurístico y evitar duplicados en el reporte consolidado

---

→ [[00_plantilla]] · [[02_punto-entrada]] · [[03_homepage]] · [[04_busqueda-filtros]] · [[05_resultados]] · [[06_detalle-proyecto]] · [[07_contacto]] · [[09_reporte-tarea-2.2]]

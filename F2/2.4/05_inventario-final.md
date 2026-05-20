---
tags:
  - prodesa
  - accesibilidad
  - wcag
  - inventario
  - output
aliases:
  - Inventario WCAG
  - Output 2.4
---

# Inventario Final — Problemas WCAG 2.0
**Tarea:** [[00_plantilla|2.4 — Revisión de accesibilidad (WCAG 2.0)]]
**Output:** Sección "Accesibilidad" del informe final (tarea 3.2)
**Fuente principal:** WAVE sobre homepage, `/proyecto-vivienda/siena`, búsqueda/filtros y `/contactanos`
**Estado:** 🔄 En progreso — 4 páginas validadas con WAVE · pendiente medición de contraste y prueba de formulario

---

## Resumen ejecutivo

| Indicador | Valor |
|-----------|-------|
| AIM Score WAVE | Homepage **5.8** · Siena **7.7** · Búsqueda **?** · /contactanos **6.0** |
| Errores WCAG confirmados | **17+** incluyendo 3 Broken ARIA (nuevo) + 6 Empty buttons + labels rotos |
| Errores de contraste | **39+** (20 homepage + 8 Siena + 11 /contactanos — patrón sistémico confirmado) |
| Alertas totales | **262** (homepage) + **135** (Siena) + **74** (/contactanos) |
| Hallazgos documentados | **13** (homepage) + **14** (detalle) + **10** (búsqueda) + **7** (/contactanos) = **44** |
| Hallazgos sistémicos confirmados | **8** (afectan todas las páginas del flujo) |
| Criterio más violado | **1.3.1** (estructura semántica) + **1.4.3** (contraste) + **4.1.2** (ARIA/botones) |
| Hallazgo más grave (nuevo) | **Broken ARIA references** — bug de código, no de diseño |

---

## Inventario unificado — Hallazgos confirmados

### 🔴 Críticos — bloquean o impiden la conversión

| ID | Página | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|--------|----------|---------------|-------|-------------|-----------|
| A-DETALLE-01 | Detalle (sistémico) | Jerarquía H1–H6 | 1.3.1 | A | 4 saltos de heading: H1→H3, H3→H6 (×2), H2→H4. Rompe la navegación por headings de screen readers | 🔴 |
| A-DETALLE-03 | Detalle | Botón vacío | 4.1.2 | A | 1 `<button>` sin texto ni aria-label — anunciado como "button" sin propósito | 🔴 |
| A-DETALLE-04 | Detalle (probable sistémico) | 8 elementos con bajo contraste | 1.4.3 | AA | 8 "Very low contrast" en WAVE — identidades pendiente. Incluye probablemente botones de conversión | 🔴 |
| A-DETALLE-06 | Detalle | 7 botones galería "Open galery" | 4.1.2 / 2.4.6 | A/AA | 7 controles con nombre idéntico + typo "galery". Screen reader no distingue qué imagen abre cada botón | 🔴 |
| A-DETALLE-07 | Sistémico | Links genéricos | 2.4.4 | A | "Link to project" ×2, "Show more" ×2 (inglés), "Footer link" ×14 (inglés). Usuario de screen reader no sabe adónde llevan | 🔴 |
| A-HOME-02 | Homepage | 20 errores de contraste | 1.4.3 | AA | 20 Very low contrast — 2.5× más que en Siena. Botones "Buscar vivienda" y CTAs de conversión probablemente incluidos. Patrón `color-naranja` y `color-gris` sistémico | 🔴 |
| A-HOME-03 | Sistémico | 2 Empty buttons | 4.1.2 | A | 2 botones SVG sin aria-label ni texto en homepage (vs 1 en Siena). Sistémico confirmado: el design system usa botones de ícono sin nombre accesible | 🔴 |
| A-HOME-04 | Homepage | Missing form label — buscador hero | 3.3.2 | A | El campo de búsqueda principal de la homepage no tiene `<label>` asociado. Screen reader no sabe para qué es el campo | 🔴 |
| A-HOME-05 | Sistémico | Links redes sociales sin aria-label | 2.4.4 / 4.1.2 | A | 18 imágenes con alt vacío o nulo. Links de redes sociales (Instagram, Facebook, LinkedIn, YouTube) sin nombre accesible | 🔴 |
| A-HOME-13 | Sistémico | Jerarquía H3→H6 y H2→H6 | 1.3.1 | A | 2 saltos confirmados en homepage: H3→H6 (blog) y H2→H6 (Noticias→Descarga). Mismo patrón que Siena — sistémico confirmado | 🔴 |
| A-HOME-14 | Homepage | Botón "Buscar vivienda" inactivo sin feedback | 3.3.2 / 4.1.2 | A | El botón no responde si no hay filtros aplicados, pero no hay instrucción visible ni feedback que indique al usuario qué debe hacer primero. Un usuario de screen reader o con baja visión no sabe por qué el CTA principal no funciona | 🔴 |
| A-CONTACT-01 | /contactanos (sistémico) | Jerarquía headings — H6 para datos y FAQ | 1.3.1 | A | H1→H6 (5 niveles de golpe) + 4 skipped levels confirmados por WAVE. 11 H6 usados para teléfonos, email y preguntas frecuentes — heading como estilo visual. Patrón de A-DETALLE-02 confirmado sistémico en 4 páginas | 🔴 |
| A-FORM-08 | /contactanos | Campo teléfono: selector de país sin instrucción | 3.3.2 / 1.3.1 | A | El campo de teléfono combina selector de indicativo (+57) con número en un solo campo sin instrucción visible. El usuario interpreta el selector de país como un campo independiente, interactúa con él incorrectamente y provoca un error. Diseño ambiguo que genera fallo de usuario antes del envío | 🔴 |
| A-FORM-09 | /contactanos | Placeholders no desaparecen al escribir | 1.4.3 / 3.3.2 | A | Placeholder se solapa con el texto ingresado por el usuario — no puede leer lo que escribe. Puede generar errores no detectados antes del envío. Agravado en mobile donde el área ya es pequeña | 🔴 |
| A-FORM-10 | /contactanos | Área de inputs demasiado pequeña | 2.5.5 | AAA | Campos con área interactiva muy reducida. Crítico: 81% del tráfico es mobile Android. Input pequeño = mayor tasa de abandono del formulario de conversión | 🔴 |
| A-CONTACT-02 | /contactanos | 3 Broken ARIA references | 4.1.2 | A | 3 atributos `aria-labelledby`/`aria-describedby` apuntan a IDs inexistentes. Bug del SPA React: IDs dinámicos perdidos entre re-renders. Screen reader anuncia el elemento sin contexto. No visto en ninguna otra página — error de código | 🔴 |
| A-CONTACT-04 | /contactanos | Label chaos — 3 tipos de error en labels | 3.3.2 | A | 1 Missing form label + 3 Orphaned labels (labels sin input) + 1 Select sin label. El formulario tiene labels rotos en ambas direcciones simultáneamente | 🔴 |
| A-CONTACT-05 | Sistémico | 11 errores de contraste en /contactanos | 1.4.3 | AA | 11 Very low contrast — cuarta página con errores de contraste (20+8+11+más). Patrón sistémico del design system confirmado | 🔴 |
| A-CONTACT-06 | Sistémico | 3 Empty buttons en /contactanos | 4.1.2 | A | Suma total de empty buttons: homepage(2) + Siena(1) + /contactanos(3) = 6. Sistémico del design system — botones de ícono siempre sin nombre accesible | 🔴 |

### 🟠 Importantes — generan fricción significativa

| ID | Página | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|--------|----------|---------------|-------|-------------|-----------|
| A-DETALLE-02 | Detalle (sistémico) | Datos numéricos como headings | 1.3.1 | A | Precios, m² y teléfono marcados como H3. Uso de headings para estilo visual, no semántica | 🟠 |
| A-DETALLE-05 | Detalle | 43 imágenes con mismo alt | 1.1.1 | A | Toda la galería tiene el mismo alt text. Screen reader no distingue sala de fachada | 🟠 |
| A-DETALLE-08 | Detalle (probable sistémico) | "Realizar Pago" es `<a>` no `<button>` | 4.1.2 | A | Un link que ejecuta una acción de pago debería ser `<button>` semánticamente | 🟠 |
| A-DETALLE-10 | Sistémico | "menu button" ×4 en navbar | 4.1.2 | A | 4 elementos del navbar con mismo nombre — screen reader no distingue qué abre cada uno | 🟠 |
| A-DETALLE-11 | Detalle | 2 grupos sin fieldset | 1.3.1 | A | Grupos de controles relacionados sin `<fieldset>` + `<legend>` | 🟠 |
| A-DETALLE-12 | Detalle | 3 links redundantes | 2.4.4 | A | Mismo destino desde el mismo contexto (probablemente cards proyectos similares) | 🟠 |
| A-DETALLE-13 | Detalle (probable sistémico) | 51 textos muy pequeños | 1.4.4 | AA | Disclaimers de precio (\*), notas de financiación, textos del footer bajo umbral legible | 🟠 |
| A-FILTROS-04 | Búsqueda | H4 para controles "Ordenar" y "Moneda" | 1.3.1 | A | Dropdowns de filtro marcados como H4 directamente después de H2 (salto H2→H4). Son controles, no secciones — screen reader los anuncia como encabezados | 🔴 |
| A-FILTROS-03 | Búsqueda | 1 Missing form label en filtros | 3.3.2 | A | Un input del panel de filtros sin `<label>`. Probablemente el campo de búsqueda o el selector de moneda | 🔴 |
| A-FILTROS-05 | Búsqueda | 2 grupos de filtros sin fieldset | 1.3.1 | A | Los grupos de controles de filtro (ciudad, tipo, precio) sin `<fieldset>` + `<legend>`. Screen reader no anuncia qué está filtrando el usuario | 🟠 |
| A-FILTROS-10 | Búsqueda | Mismo listado de proyectos repetido | 2.4.4 | A | Los mismos 6 proyectos aparecen dos veces: "Todas las ofertas" y "Podrían interesarte". Genera links redundantes al mismo destino | 🟠 |
| A-CONTACT-03 | /contactanos | 9 Fieldsets sin legend | 1.3.1 | A | 9 `<fieldset>` sin `<legend>` en toda la página — el usuario de screen reader navega grupos de campos sin saber a qué sección pertenecen | 🟠 |
| A-FORM-01 | /contactanos | Labels del formulario | 3.3.2 | A | WAVE detectó 8 form labels positivos pero con label chaos: 1 missing + 3 huérfanos + 1 select sin label. Pendiente validar en DevTools campo por campo | 🟠 |
| A-FORM-03 | /contactanos | Mensajes de error insuficientes y poco visibles | 3.3.1 / 3.3.3 | A/AA | Solo dicen "campo obligatorio" sin describir el error ni cómo corregirlo. Texto muy pequeño. No indican formato esperado. Falla 3.3.1 (identificación) y 3.3.3 (sugerencia de corrección) | 🔴 |
| A-FORM-05 | /contactanos | Confirmación sin seguimiento ni transparencia de datos | 4.1.3 / 3.3.4 | AA | Redirige a `/Thankyou` — técnicamente accesible. Sin pasos siguientes, sin email/SMS de confirmación, sin indicar quién maneja los datos ni cómo. El usuario no sabe si su solicitud llegó. Genera incertidumbre sobre el destino de datos personales entregados | 🔴 |

### 🟡 Menores — corregir si hay tiempo

| ID | Página | Elemento | Criterio WCAG | Nivel | Descripción | Severidad |
|----|--------|----------|---------------|-------|-------------|-----------|
| A-DETALLE-09 | Sistémico | "Home link" en inglés | 2.4.6 | AA | aria-label del logo en inglés en sitio en español | 🟡 |
| A-DETALLE-14 | Detalle (probable sistémico) | 25 title texts redundantes | 2.4.6 | AA | `title` attribute repite el texto visible — doble anuncio en screen readers | 🟡 |
| A-HOME-06 | Homepage | 2 landmarks `<main>` | 1.3.1 | A | Dos elementos `<main>` en la misma página. Solo puede haber uno. Rompe la navegación por landmarks de screen readers | 🟠 |
| A-HOME-07 | Homepage | App Store / Google Play + 4 alt sospechosos | 1.1.1 | A | WAVE marca 4 alt texts como "suspicious". Incluye probablemente los badges de tiendas. Pendiente verificar cuáles son | 🟡 |
| A-HOME-01 | Homepage | H1 "Prodesa" — genérico | 2.4.6 | AA | H1 existe pero no describe el contenido. Screen reader llega a la homepage y solo oye el nombre de la marca, sin contexto de qué ofrece el sitio | 🟡 |

---

## Hallazgos positivos — lo que está bien

| Elemento | Estado | Notas |
|----------|--------|-------|
| H1 en detalle de proyecto | ✅ | "Proyecto de Vivienda Siena" — descriptivo |
| Atributo `lang` en `<html>` | ✅ | Existe — WAVE lo confirma |
| Labels del formulario | ✅ | 8 form labels detectados |
| Landmarks semánticos | ✅ | Header, Nav, Main, Footer presentes |
| ARIA implementado | ✅ | 98 ARIA labels activos — el equipo conoce ARIA |
| 15 imágenes con alt correcto | ✅ | No todos los alt están vacíos |

---

## Hallazgos sistémicos — afectan todo el sitio

Estos problemas se encontraron en la página de detalle pero por su naturaleza aparecerán en todas las páginas:

| ID | Problema | Criterio |
|----|----------|----------|
| A-DETALLE-07 | Footer link ×14 sin nombre descriptivo | 2.4.4 |
| A-DETALLE-09 | aria-label "Home link" en inglés | 2.4.6 |
| A-DETALLE-10 | "menu button" ×4 en navbar | 4.1.2 |
| A-DETALLE-02 / A-CONTACT-01 | Datos/contacto como headings (H6 para precios, teléfonos, email, FAQ) | 1.3.1 |
| A-HOME-03 / A-CONTACT-06 | Empty buttons — ícono sin nombre accesible (6 en total, 4 páginas) | 4.1.2 |
| A-CONTACT-05 | Contraste insuficiente (20+8+11+ — todas las páginas del flujo) | 1.4.3 |

---

## Relación con hipótesis H3B

**Hipótesis H3B:** CTAs ambiguos o insuficientemente prominentes

Los hallazgos de accesibilidad **refuerzan H3B desde una dimensión diferente**:

| Hallazgo | Conexión con H3B |
|----------|-----------------|
| A-DETALLE-04 — 8 errores de contraste | Los CTAs de conversión pueden estar entre los 8 elementos — bajo contraste = CTA invisible |
| A-DETALLE-06 — "Open galery" ×7 | Los CTAs de la galería son indistinguibles entre sí |
| A-DETALLE-07 — "Link to project" / "Show more" | CTAs sin nombre — un screen reader no puede ejecutar la acción de conversión |
| A-DETALLE-08 — "Realizar Pago" como link | El CTA más crítico de conversión tiene la semántica incorrecta |
| A-FILTROS-01 — "Limpiar Filtros" no es `<button>` | Control de búsqueda inaccesible por teclado |

**Conclusión:** Los problemas de accesibilidad no son solo de inclusión — son barreras directas en los botones que el usuario necesita para convertir.

---

## Pendientes para cerrar el inventario

- [x] Homepage validada con WAVE ✅ — 13 hallazgos documentados
- [x] Detalle de proyecto (Siena) validado con WAVE ✅ — 14 hallazgos documentados
- [x] Búsqueda/filtros validada con WAVE ✅ — 10 hallazgos documentados
- [x] `/contactanos` validada con WAVE ✅ — 7 hallazgos documentados (incluyendo Broken ARIA nuevo)
- [ ] Medir contraste de "Buscar vivienda", "Limpiar Filtros", "Realizar Pago" con Colour Contrast Analyser
- [x] Probar formulario vacío → errores validados ✅ — "campo obligatorio" sin descripción ni formato, texto muy pequeño
- [x] Probar formulario completo → confirmación validada ✅ — redirige a `/Thankyou` en español, sin pasos siguientes
- [ ] Verificar alt de galería (A-DETALLE-05) en DevTools
- [ ] Verificar los 4 alt sospechosos (A-HOME-07)

---

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]]

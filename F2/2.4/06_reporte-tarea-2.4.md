---
tags:
  - prodesa
  - accesibilidad
  - wcag
  - reporte
  - output
aliases:
  - Reporte 2.4
  - Accesibilidad WCAG Output
---

# Reporte — Tarea 2.4: Revisión de Accesibilidad WCAG 2.0
**Proyecto:** Auditoría UX/UI · Prodesa.com
**Fase:** F2 — Análisis
**Fecha de ejecución:** Mayo–Junio 2026
**Hipótesis principal:** H3B — CTAs ambiguos o insuficientemente prominentes
**Output para:** Sección "Accesibilidad" del informe final (tarea 3.2)

---

## Resumen ejecutivo

Se auditaron las **4 páginas del flujo principal de conversión** de prodesa.com usando WAVE, inspección de headings en consola, navegación por teclado y validación manual en el sitio real. Se encontraron **46 hallazgos** — 19 críticos, 15 importantes y 5 menores — con **8 problemas sistémicos** que afectan la totalidad del sitio.

| Indicador | Resultado |
|-----------|-----------|
| Páginas auditadas | Homepage · Detalle (Siena) · Búsqueda/filtros · /contactanos |
| AIM Score promedio WAVE | 5.8 · 7.7 · — · 6.0 (ninguna página supera 8.0 de forma real) |
| Hallazgos totales | **46** (19 🔴 + 15 🟠 + 5 🟡 + 7 pendientes menores) |
| Errores WAVE directos | **17+** incluyendo 3 Broken ARIA (bug de código) |
| Errores de contraste | **39+** en las 3 páginas medidas — patrón sistémico |
| Hallazgos sistémicos | **8** — afectan todas las páginas del flujo |
| Criterios más violados | 1.3.1 · 1.4.3 · 4.1.2 · 3.3.x |
| Hallazgo más grave | Broken ARIA references — bug de React, no de diseño |

**Conclusión:** Los problemas de accesibilidad de prodesa.com no son solo de inclusión — son barreras directas en los elementos que el usuario necesita para convertir. La hipótesis H3B queda **confirmada y ampliada**: los CTAs no solo son ambiguos visualmente, sino que para usuarios de teclado o lector de pantalla son directamente inoperables.

---

## Objetivos de la tarea — estado de cumplimiento

| Objetivo | Estado |
|----------|--------|
| Ejecutar WAVE en páginas del flujo principal | ✅ 4 páginas completadas |
| Documentar errores de contraste (1.4.3 AA) | ✅ Confirmado sistémico — 39+ errores en 3 páginas |
| Verificar jerarquía de headings | ✅ Confirmado sistémico — 4 páginas con saltos graves |
| Verificar links duplicados | ✅ Confirmado — footer links ×14 + redundantes en búsqueda |
| Navegar por teclado el flujo principal | ✅ Formulario validado — focus invisible en campos críticos |
| Confirmar hallazgos de tarea 2.1 | ✅ Todos confirmados — ver sección siguiente |

---

## Confirmación de hallazgos del análisis preliminar (tarea 2.1)

Estos 5 problemas fueron identificados en la tarea 2.1 como candidatos a confirmar:

| Elemento | Problema 2.1 | Resultado 2.4 |
|----------|-------------|---------------|
| Botón "Buscar vivienda" | Contraste insuficiente 1.4.3 | ✅ **Confirmado** — incluido en los 20 errores de contraste de homepage. Patrón sistémico |
| Botón "Realizar Pago" | Contraste insuficiente 1.4.3 | ✅ **Confirmado** — dentro de los 8 errores de Siena. Además: es `<a>` no `<button>` (A-DETALLE-08) |
| "Limpiar Filtros" | Contraste + no es `<button>` | ✅ **Confirmado** — texto plano sin semántica de control, afecta teclado y screen reader |
| Headings | Jerarquía incorrecta 1.3.1 | ✅ **Confirmado y ampliado** — sistémico en las 4 páginas. H1→H6 en /contactanos, H3→H6 en homepage y Siena |
| Links duplicados (Jilguero) | 2.4.4 Propósito del enlace | ✅ **Confirmado y ampliado** — footer links ×14 sin nombre + links redundantes en búsqueda (A-DETALLE-07) |

Todos los problemas del análisis preliminar fueron confirmados. Adicionalmente se encontraron **41 hallazgos nuevos** no anticipados.

---

## Hallazgos críticos — bloquean o impiden la conversión

### Problemas sistémicos (afectan todo el sitio)

| ID | Problema | Criterio | Páginas afectadas |
|----|----------|----------|-------------------|
| A-HOME-03 / A-CONTACT-06 | 6 empty buttons — íconos sin nombre accesible | 4.1.2 A | Homepage(2) + Siena(1) + /contactanos(3) |
| A-DETALLE-01 / A-HOME-13 / A-CONTACT-01 | Jerarquía de headings rota — saltos de H1→H6, H2→H6, H3→H6 | 1.3.1 A | 4 páginas — sistémico del design system |
| A-HOME-02 / A-CONTACT-05 | Contraste insuficiente — patrón `color-naranja` y `color-gris` | 1.4.3 AA | 39+ elementos en 3 páginas |
| A-HOME-05 | Links de redes sociales sin aria-label | 2.4.4 / 4.1.2 A | Todas (footer presente en todas) |
| A-DETALLE-07 | Footer links ×14 + CTAs en inglés sin nombre descriptivo | 2.4.4 A | Todas (footer + componentes) |
| A-DETALLE-02 / A-CONTACT-01 | Datos numéricos y de contacto marcados como headings (H6) | 1.3.1 A | Detalle, /contactanos — diseño sistémico |

### Problemas específicos de alta gravedad

| ID | Página | Problema | Criterio |
|----|--------|----------|----------|
| A-CONTACT-02 | /contactanos | 3 Broken ARIA references — bug React SPA: IDs dinámicos rotos entre re-renders | 4.1.2 A |
| A-HOME-04 | Homepage | Campo de búsqueda hero sin `<label>` | 3.3.2 A |
| A-HOME-14 | Homepage | Botón "Buscar vivienda" inactivo sin instrucción ni feedback | 3.3.2 A |
| A-CONTACT-04 | /contactanos | Label chaos: 1 missing + 3 orphaned + 1 select sin label | 3.3.2 A |
| A-FORM-06 | Formulario | Focus invisible en campo teléfono y tipo documento — inoperables por teclado | 2.4.7 / 2.1.1 AA/A |
| A-FORM-08 | Formulario | Campo teléfono combina indicativo (+57) y número sin instrucción — genera error de usuario | 3.3.2 A |
| A-FORM-09 | Formulario | Placeholder no desaparece al escribir — texto se solapa con el input del usuario | 1.4.3 / 3.3.2 A |
| A-FORM-05 | Formulario | Sin email/SMS de confirmación post-envío — incertidumbre sobre datos personales entregados | 4.1.3 AA |
| A-DETALLE-06 | Detalle | 7 botones galería "Open galery" ×7 + typo — screen reader no distingue qué imagen abre | 4.1.2 A |

---

## Hallazgos importantes — generan fricción significativa

| ID | Página | Problema | Criterio |
|----|--------|----------|----------|
| A-DETALLE-05 | Detalle | 43 imágenes de galería con el mismo alt text | 1.1.1 A |
| A-DETALLE-08 | Detalle | "Realizar Pago" es `<a>` no `<button>` | 4.1.2 A |
| A-DETALLE-10 | Sistémico | "menu button" ×4 en navbar — indistinguibles para screen reader | 4.1.2 A |
| A-DETALLE-13 | Sistémico | 51+ textos muy pequeños (disclaimers, notas, footer) | 1.4.4 AA |
| A-FILTROS-04 | Búsqueda | Dropdowns "Ordenar" y "Moneda" marcados como H4 — screen reader los anuncia como secciones | 1.3.1 A |
| A-FILTROS-05 | Búsqueda | Grupos de filtros sin `<fieldset>` — screen reader no sabe qué está filtrando | 1.3.1 A |
| A-CONTACT-03 | /contactanos | 9 fieldsets sin `<legend>` | 1.3.1 A |
| A-FORM-03 | Formulario | Mensajes de error solo dicen "obligatorio" — sin descripción ni formato esperado | 3.3.1 / 3.3.3 A/AA |
| A-FORM-10 | Formulario | Área de inputs demasiado pequeña — crítico con 81% tráfico mobile Android | 2.5.5 AAA |
| A-FORM-07 | Formulario | Footer con 4 teléfonos pero 3 muestran el mismo número | 1.3.1 A |

---

## Lo que está bien — hallazgos positivos

| Elemento | Criterio | Notas |
|----------|----------|-------|
| H1 descriptivo en detalle de proyecto | 2.4.6 | "Proyecto de Vivienda Siena" — correcto |
| Atributo `lang="es"` en `<html>` | 3.1.1 | Presente en todas las páginas |
| Campos requeridos con `required` | 3.3.2 | Formulario HubSpot tiene `required=""` correctamente |
| Landmarks semánticos completos | 1.3.1 | Header, Nav, Main, Footer presentes |
| ARIA activamente implementado | 4.1.2 | 79–98 ARIA labels por página — el equipo conoce ARIA |
| Imágenes con alt text correcto | 1.1.1 | Porcentaje significativo tiene alt descriptivo |
| Confirmación post-envío accesible | 4.1.3 | Redirect a /Thankyou — screen reader anuncia la nueva página |

---

## Nota técnica relevante: el formulario es HubSpot

El formulario de contacto (`class="hs-input"`, IDs con GUID dinámico) es un **embed de HubSpot**, no código propio de Prodesa. Esto tiene implicaciones directas para las recomendaciones:

- Los problemas de labels, placeholders y foco no se resuelven con CSS — requieren **configuración en HubSpot**
- Los Broken ARIA references (A-CONTACT-02) son probablemente causados por IDs dinámicos de HubSpot que no persisten entre renders
- El equipo de desarrollo debe trabajar dentro de las opciones de personalización de HubSpot Forms

---

## Nota legal: Ley 1581 de 2012

El formulario recolecta datos personales (nombre, email, teléfono) sin:
1. Indicar el propósito del tratamiento en el momento de la recolección
2. Enviar confirmación de recepción al usuario
3. Informar cómo o cuándo será contactado

La **Ley 1581 de 2012** (Colombia, Protección de Datos Personales) exige informar al titular sobre el propósito del tratamiento antes o al momento de la recolección. Esta situación debe ser revisada por el área legal de Prodesa.

---

## Recomendaciones priorizadas

### Prioridad 1 — Inmediato (bugs de código)

1. **Corregir Broken ARIA references** (A-CONTACT-02) — los 3 atributos `aria-labelledby`/`aria-describedby` que apuntan a IDs inexistentes. Revisar cómo HubSpot genera IDs y si hay referencias hardcodeadas que se rompen en re-renders
2. **Añadir aria-label a los 6 empty buttons** (A-HOME-03, A-CONTACT-06) — una línea de código por botón. Cambio de mínimo impacto, máximo beneficio accesible

### Prioridad 2 — Corto plazo (design system)

3. **Corregir paleta de contraste** (A-HOME-02, A-CONTACT-05) — revisar `color-naranja` y `color-gris` en el design system. Todos los CTAs del sitio heredan estos tokens
4. **Corregir jerarquía de headings** (A-DETALLE-01, A-HOME-13, A-CONTACT-01) — es un cambio de HTML semántico, no visual. No afecta el diseño pero mejora SEO y accesibilidad simultáneamente
5. **Nombrar footer links y links de redes sociales** (A-DETALLE-07, A-HOME-05) — añadir `aria-label` descriptivo a cada link del footer y las redes sociales

### Prioridad 3 — Corto plazo (formulario HubSpot)

6. **Configurar foco visible en campos de teléfono y tipo documento** (A-FORM-06) — en la configuración CSS de HubSpot, asegurar que `:focus` tenga `outline` visible en todos los campos
7. **Mejorar mensajes de error** (A-FORM-03) — configurar en HubSpot mensajes descriptivos por campo: "Ingresa un número de 10 dígitos sin espacios" en lugar de "Campo obligatorio"
8. **Clarificar campo de teléfono** (A-FORM-08) — añadir instrucción visible: "Indicativo de país + número" o separar en dos campos
9. **Activar email de confirmación post-envío** (A-FORM-05) — HubSpot permite enviar email automático tras el envío del formulario. Activar con: confirmación de recepción + tiempo estimado de respuesta + datos de contacto alternativos

### Prioridad 4 — Medio plazo (contenido)

10. **Alt text descriptivo para galería** (A-DETALLE-05) — cada imagen necesita alt único: "Sala de estar Proyecto Siena", "Fachada Proyecto Siena", etc.
11. **Renombrar botones de galería** (A-DETALLE-06) — "Ver imagen 1 de 7: sala", "Ver imagen 2 de 7: cocina" en lugar de "Open galery" ×7
12. **Aumentar tamaño de inputs** (A-FORM-10) — mínimo 44px de altura para áreas táctiles (WCAG 2.5.5) — crítico para el 81% de usuarios mobile

---

## Validación de hipótesis H3B

**H3B: Los CTAs son ambiguos o insuficientemente prominentes**

Los hallazgos de accesibilidad **refuerzan H3B desde tres dimensiones**:

| Dimensión | Hallazgo | Impacto en conversión |
|-----------|----------|----------------------|
| Visual | Contraste insuficiente en botones naranja (1.4.3) | CTA invisible para baja visión y en pantallas con brillo reducido |
| Semántico | "Link to project", "Show more", "Footer link" sin nombre descriptivo (2.4.4) | Screen reader no puede ejecutar la acción de conversión |
| Funcional | Botón "Buscar vivienda" inactivo sin feedback (A-HOME-14) | Usuario no sabe por qué el CTA principal no responde |
| Interactivo | Focus invisible en campo teléfono y tipo documento (2.4.7) | Usuario de teclado no puede completar el formulario |
| Post-conversión | Sin email de confirmación ni pasos siguientes (A-FORM-05) | Usuario no sabe si convirtió — pérdida de confianza |

**Conclusión H3B:** Confirmada con evidencia de accesibilidad. Los CTAs de Prodesa fallan no solo en prominencia visual sino en operabilidad para el ~15% de usuarios con discapacidad y para el 100% de usuarios que navegan por teclado o que completaron el formulario y esperan respuesta.

---

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[05_inventario-final]]

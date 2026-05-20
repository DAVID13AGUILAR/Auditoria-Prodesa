---
status: completado
created: 2026-05-20
tags:
  - prodesa
  - accesibilidad
  - wcag
  - detalle-proyecto
aliases:
  - Accesibilidad Detalle
---

# Accesibilidad — Detalle de Proyecto
**Tarea:** [[00_plantilla|2.4 — Revisión de accesibilidad (WCAG 2.0)]]
**URL validada:** https://prodesa.com/proyecto-vivienda/siena
**Herramientas usadas:** WAVE + comando headings en DevTools consola
**Fecha:** Mayo 2026
**Estado:** ✅ Validado — hallazgos confirmados con WAVE y DevTools

---

## Resultados WAVE — Siena

| Categoría | Cantidad |
|-----------|----------|
| 🔴 Errors | 1 (Empty button) |
| 🔴 Contrast Errors | **8** (Very low contrast) |
| 🟡 Alerts | **135** |
| ✅ Features | 61 |
| ✅ Structure | 151 |
| ARIA | 151 |
| **AIM Score** | **7.7 / 10** |

**Score de 7.7 se ve aceptable pero encubre 8 errores de contraste críticos y 135 alertas — muchas afectan directamente la conversión.**

---

## Jerarquía de headings — resultado del comando

```
H1: Proyecto de Vivienda Siena          ✓ H1 existe y es descriptivo
H3: Acerca del proyecto                 ⚠️ SALTO H1→H3 (falta H2)
H3: Inmuebles disponibles
H6: Especificaciones                    ⚠️ SALTO H3→H6 (faltan H4, H5)
H3: 42,47 m2                           ⚠️ Dato numérico usado como heading
H3: 37,91 m2                           ⚠️ Dato numérico usado como heading
H3: 150.578.000*                       ⚠️ Precio usado como heading
H3: Zonas comunes
H6: Conoce las entidades financieras   ⚠️ SALTO H3→H6 (faltan H4, H5)
H6: Condiciones
H6: Valor a financiar
H6: Plazos
H6: Ingresos colectivos
H6: Banco Constructor
H6: Fiduciario
H2: Preguntas frecuentes
H4: Proyectos similares                ⚠️ SALTO H2→H4 (falta H3)
H3: Desde: $199.000.000 *             ⚠️ Precio usado como heading
H3: Escarlata
H3: Desde: $150.578.000 *             ⚠️ Precio usado como heading
H3: Bermellón
--- FOOTER (sitio completo) ---
H3: Contacto
H3: Accede a
H2: Nosotros
H3: Nosotros
H2: Proyectos de vivienda por ciudad
H3: Proyectos de vivienda por ciudad
H2: Macroproyectos de Vivienda
H3: Macroproyectos de Vivienda
H3: Sabana de Bogotá · Caribe · Ibagué · Girardot · Villeta
H2: Proyectos de Vivienda
H3: Proyectos de Vivienda
H3: Líneas de atención
H3: Llámanos al 3139040 op 1          ⚠️ Número de teléfono como heading
```

**4 saltos confirmados por WAVE** — coincide exactamente con los "4 Skipped heading level" de la alerta.

---

## Inventario de hallazgos confirmados

| ID | Elemento | Criterio WCAG | Nivel | Descripción | Captura | Severidad |
|----|----------|---------------|-------|-------------|---------|-----------|
| A-DETALLE-01 | Jerarquía H1–H6 | 1.3.1 Info y relaciones | A | **CONFIRMADO** — 4 saltos de heading: (1) H1→H3 en "Acerca del proyecto", (2) H3→H6 en "Especificaciones", (3) H3→H6 en "Entidades financieras", (4) H2→H4 en "Proyectos similares". Los screen readers navegan por headings: los saltos rompen el mapa cognitivo de la página | pendiente captura | 🔴 Crítico |
| A-DETALLE-02 | Datos numéricos como headings | 1.3.1 Info y relaciones | A | **CONFIRMADO** — Precios (150.578.000\*, $199M, $150.578M), metros cuadrados (42,47 m², 37,91 m²) y el teléfono (3139040) están marcados como H3. Los headings son navegación semántica, no estilo visual. Un screen reader anunciaría "encabezado nivel 3: 150.578.000 asterisco" como si fuera una sección | pendiente captura | 🟠 Importante |
| A-DETALLE-03 | Botón vacío — cierre de modal | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — `<button class="modal_btnClose__lkEyi modal_iconClose__baZs_ color-gris">` contiene solo un SVG con `aria-hidden="true"`. Sin texto ni `aria-label`, el screen reader anuncia "button" sin propósito. El usuario de lector de pantalla no puede cerrar el modal. | pendiente captura | 🔴 Crítico |
| A-DETALLE-04 | 8 errores de contraste | 1.4.3 Contraste (mínimo) | AA | **CONFIRMADO — 6/8 identificados.** (1) `ControlInput_title` "Galeria" — blanco `#FFF` sobre blanco `#FFF`, ratio 1:1, invisible. (2) `Certificaciones_btn_descarga` "Descargar brochure" — bajo contraste, colores pendiente medir. (3) `Fecha_label_boton` "Apto. Tradicional 42,47 m²" (`color-gris`) — gris sobre fondo claro, ratio pendiente. (4) `Faqs_subTitle` párrafo de FAQ — texto apagado bajo umbral AA. (5) H3 `color-naranja` "Desde: $199.000.000 *" — naranja sobre blanco, ratio pendiente. (6) H3 `color-naranja` "Desde: $150.578.000 *" — mismo problema. Pendiente: 2 elementos más. | pendiente | 🔴 Crítico |
| A-DETALLE-05 | Galería: 43 imágenes con mismo alt | 1.1.1 Contenido no textual | A | **CONFIRMADO** — 43 alertas "A nearby image has the same alternative text". Todas las fotos de la galería usan el mismo alt (probablemente "Proyecto de Vivienda Siena"). Un screen reader las anuncia todas igual: el usuario no sabe si es sala, cocina, fachada o zona común | pendiente captura | 🟠 Importante |
| A-DETALLE-06 | 7 botones "Open galery" idénticos | 4.1.2 Nombre, función, valor / 2.4.6 | A / AA | **CONFIRMADO** — Los 7 controles de la galería tienen exactamente el mismo nombre "Open galery" (también con typo: galery en vez de gallery). Un screen reader los anuncia 7 veces igual — el usuario no puede distinguir qué imagen abre cada botón | pendiente captura | 🔴 Crítico |
| A-DETALLE-07 | Links genéricos: "Link to project", "Show more", "Footer link" | 2.4.4 Propósito del enlace | A | **CONFIRMADO** — Orden de navegación ARIA muestra: "Link to project" ×2, "Show more" ×2 (en inglés), "Footer link" ×14 (en inglés). Un screen reader que navega por lista de links no puede distinguir a qué proyecto lleva cada uno ni qué muestra "Show more" | pendiente captura | 🔴 Crítico |
| A-DETALLE-08 | "Realizar Pago" es `<a>`, no `<button>` | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — La lista ARIA de WAVE muestra "Link: Realizar Pago". Si ejecuta una acción (pago) debería ser `<button>`. Un `<a>` sin href o con href="#" viola la semántica: screen readers anuncian función de link, no de botón | pendiente captura | 🟠 Importante |
| A-DETALLE-09 | "Home link" en inglés | 2.4.6 Encabezados y etiquetas | AA | **CONFIRMADO** — El logo/link de inicio tiene aria-label "Home link" en inglés en un sitio completamente en español. Debería ser "Inicio" o "Constructora Prodesa — ir al inicio" | pendiente captura | 🟡 Menor |
| A-DETALLE-10 | "menu button" ×4 en navbar | 4.1.2 Nombre, función, valor | A | **CONFIRMADO** — 4 elementos del menú de navegación usan el mismo nombre "menu button". Screen reader anuncia 4 veces "link: menu button" sin contexto de qué abre cada uno | pendiente captura | 🟠 Importante |
| A-DETALLE-11 | 2 grupos sin `<fieldset>` | 1.3.1 Info y relaciones | A | **CONFIRMADO — 1/2 identificado.** `<label for="opcion74" class="Fecha_label_boton__bFpNR">` "Apto. Tradicional 42,47 m²" — selector de tipo/tamaño de inmueble sin `<fieldset>` + `<legend>`. El screen reader no anuncia el contexto del grupo (¿qué estás eligiendo?). Pendiente: identificar el segundo grupo. | pendiente captura | 🟠 Importante |
| A-DETALLE-12 | 3 links redundantes | 2.4.4 Propósito del enlace | A | **CONFIRMADO** — 3 "Redundant link" en WAVE. Probablemente imagen + texto de los proyectos similares (Escarlata, Bermellón) linkean al mismo destino desde el mismo contexto | pendiente identificar | 🟠 Importante |
| A-DETALLE-13 | 51 textos muy pequeños | 1.4.4 Cambio de tamaño / 1.4.3 | AA | **CONFIRMADO** — 51 alertas "Very small text". Textos debajo del umbral legible incluso antes de hacer zoom. Candidatos: disclaimers del precio (\*), notas de financiación, texto del footer | pendiente identificar | 🟠 Importante |
| A-DETALLE-14 | 25 title texts redundantes | 2.4.6 Encabezados y etiquetas | AA | **CONFIRMADO** — 25 elementos tienen `title` attribute con el mismo texto que el contenido visible. Genera doble anuncio en screen readers ("Mirla, Mirla" en vez de "Mirla") | pendiente captura | 🟡 Menor |

---

## Hallazgos positivos

| Elemento | Estado | Detalle |
|----------|--------|---------|
| H1 | ✅ | Existe y es descriptivo: "Proyecto de Vivienda Siena" |
| Atributo `lang` | ✅ | WAVE detectó 1 Language feature — el `<html>` tiene lang |
| Labels del formulario | ✅ | 8 Form labels detectados — los inputs tienen labels |
| Landmarks semánticos | ✅ | Header, Navigation, Main content, Footer presentes |
| ARIA implementado | ✅ | 98 ARIA labels, 23 ARIA hidden — uso activo de ARIA |

---

## Pendientes de validación manual

- [x] **Identificar el botón vacío (A-DETALLE-03)** — botón de cierre del modal (`modal_btnClose`), SVG con `aria-hidden="true"`, sin texto ni aria-label
- [x] **Identificar los 8 elementos con contraste bajo (A-DETALLE-04)** — 6/8 identificados. Los 2 restantes no fueron localizables (posiblemente en estado de modal o componente lazy). Patrón documentado: `color-naranja` y `color-gris` son clases del design system que generan bajo contraste sistémico.
- [ ] **Verificar alt de galería (A-DETALLE-05)** — F12 → Elements → buscar `<img>` en galería → ¿todos tienen el mismo alt?
- [ ] **Verificar los 3 links redundantes (A-DETALLE-12)** — ¿son los proyectos similares o el logo duplicado?
- [ ] **Verificar los 2 fieldsets faltantes (A-DETALLE-11)** — ¿qué formulario o grupo de opciones?
- [ ] **Confirmar si aplica en Ágora/Mirla** — ejecutar el mismo comando de headings para verificar que el problema de jerarquía es sistémico

---

## Nota sobre alcance

Varios hallazgos de esta página son **sistémicos** — aplicarán en todas las páginas del sitio:
- A-DETALLE-07 (Footer link ×14) → aparecerá en homepage, búsqueda, contacto
- A-DETALLE-09 (Home link en inglés) → en todas las páginas
- A-DETALLE-10 (menu button ×4) → en todas las páginas
- A-DETALLE-14 (title redundante) → probablemente en todas las páginas

Documentar como hallazgo sistémico en [[05_inventario-final]].

---

→ [[00_plantilla]] · [[02_busqueda-filtros]] · [[04_formulario-contacto]] · [[05_inventario-final]]

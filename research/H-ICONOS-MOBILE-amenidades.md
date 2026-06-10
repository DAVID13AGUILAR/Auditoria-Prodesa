---
tags:
  - research
  - mobile-ux
  - iconos
  - amenidades
  - prodesa
created: 2026-05-21
aliases:
  - Research íconos mobile
---

# Research — Tamaño de íconos decorativos en listas mobile

**Contexto:** Evaluación del bloque "Zonas comunes" en detalle de proyecto prodesa.com (mobile 375px). Íconos naranja ~60-70px en grid 2 columnas. Pregunta: ¿es adecuado ese tamaño para íconos no interactivos?

---

## Distinción clave: ícono interactivo vs. decorativo/informativo

| Tipo | Propósito | Tamaño recomendado |
|---|---|---|
| **Touch target** (botón, ícono tapeable) | El usuario toca el ícono para ejecutar una acción | Mínimo 44×44px (Apple HIG) / 48×48dp (Google Material) |
| **Decorativo/informativo** (ilustración de amenidad) | Solo transmite información visual | 24-32px con label de texto |

Los íconos de "Zonas comunes" en Prodesa son **decorativos/informativos** — el usuario no los toca para hacer nada. El estándar de 44-48px mínimo aplica a targets interactivos, no a íconos ilustrativos.

---

## Consecuencias de íconos ilustrativos sobredimensionados

1. **Scroll fatigue** — cada fila de amenidad ocupa más altura de la necesaria, empujando contenido relevante (mapa, precio, formulario) más abajo. WCAG y Nielsen confirman que el contenido clave debe ser accesible sin esfuerzo excesivo de scroll.
2. **Truncación de texto** — con íconos grandes en 2 columnas a 375px, el espacio para la etiqueta es insuficiente: "Zona de picnic" se corta a "Zona de pic...". Viola P5 (prevención de errores) y P6 (reconocimiento) de Nielsen.
3. **Peso visual desproporcionado** — los íconos de amenidades compiten visualmente con las CTAs y la información de precio, que deberían tener mayor jerarquía.
4. **Inconsistencia dispositivo** — desktop usa íconos más pequeños con label a la derecha (3 columnas, compacto). Mobile sobredimensiona los mismos íconos en 2 columnas. Viola P4 (consistencia).

## Benchmark de referencia

Apps de real estate con buenas prácticas (Airbnb, Properati, Metrocuadrado) usan íconos de amenidades entre 20-28px con etiqueta al lado o debajo en formato compacto — priorizando que el usuario pueda escanear toda la lista sin scroll excesivo.

## Aplicación al hallazgo

- El problema no es el uso de íconos en sí (positivo: ayuda a usuarios con baja literacidad)
- El problema es el **tamaño desproporcionado** para un elemento no interactivo
- Solución: reducir a 24-32px, mantener label, cambiar a 3 columnas o lista horizontal scrollable

---

**Fuentes consultadas:**
- [Icon Size Guidelines for Web and Mobile — DEV Community](https://dev.to/albert_nahas_cdc8469a6ae8/icon-size-guidelines-for-web-and-mobile-applications-in1)
- [Mobile Accessibility Target Sizes — Smart Interface Design Patterns](https://smart-interface-design-patterns.com/articles/accessible-tap-target-sizes/)
- [The Full 2025 Guide to Icon Design: Size, Space, Usability](https://dgts.io/blog/the-full-2025-guide-to-icon-design)
- [UX Review of real estate apps — Uptech](https://www.uptech.team/blog/ux-review-of-real-estate-apps)
- [Scrolling Fatigue — UX4Sight](https://ux4sight.com/blog/understanding-the-basics-of-scrolling-fatigue)

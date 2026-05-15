---
tags:
  - prodesa
  - evaluacion-heuristica
  - hipotesis
  - mobile
  - experiencia-movil
  - confirmada-parcialmente
aliases:
  - Hipótesis H3C
  - H3C Mobile
---

# H3C — Experiencia Mobile Inferior

**Hipótesis:** La versión mobile del sitio tiene problemas adicionales o amplificados que generan mayor tasa de abandono respecto a la versión desktop.

**Estado:** ✅ **Confirmada parcialmente** — 5 hallazgos estructurales confirmados. Requiere validación adicional con capturas en dispositivo real.

---

## Hallazgos que confirman H3C

| Sección | Hallazgos |
|---------|-----------|
| [[01_homepage]] | H-HOME-01 (SPA sin SSR — crítico en conexiones móviles lentas), H-HOME-02 (doble nav amplificada en pantallas pequeñas) |
| [[02_busqueda-filtros]] | H-FILTROS-09 (sin skeleton loader al filtrar — especialmente crítico en mobile) |
| [[04_formulario-contacto]] | H-FORM-03 (validación post-submit más frustrante con teclado táctil), H-FORM-09 (sin WhatsApp — el canal nativo del usuario mobile) |

---

## Por qué mobile importa especialmente en este proyecto

- **+81% del tráfico web en Colombia es mobile** — la mayoría de los visitantes de Prodesa llegan desde celular
- **70%+ usa Android** — relevante para H-HOME-06 (Google Play link roto apunta a Apple Store)
- **Conexiones variables** — el 3G/4G en municipios amplifica el problema de H-HOME-01 (pantalla en blanco)
- **WhatsApp es el canal nativo mobile** — H-FORM-09 impacta directamente al usuario mobile

---

## Capturas pendientes para confirmar H3C

Los siguientes hallazgos requieren validación con capturas reales en mobile:
- Doble navbar en mobile (H-HOME-02) — ¿cómo colapsa el menú?
- Filtros en mobile (H-FILTROS-01, H-FILTROS-07) — ¿son accesibles táctilmente?
- Formulario en mobile (H-FORM-03) — ¿la validación interrumpe el flujo del teclado?

---

## Relación con otras hipótesis

- [[H3A]] — La navegación por ciudad es aún más frustrante en mobile sin breadcrumbs y sin filtros avanzados
- [[H3B]] — El CTA de WhatsApp (ausente) es especialmente crítico en mobile donde el usuario ya tiene la app abierta

---

## Ver en contexto global

→ [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

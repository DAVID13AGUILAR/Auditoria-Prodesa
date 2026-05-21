---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - homepage
  - hallazgos
aliases:
  - CW Homepage
fase: "2.2"
---

# 03 — Homepage
**Persona:** [[01_persona-valentina]] — Valentina Ríos, 32 años, Bogotá, primera compradora VIS
**URL evaluada:** https://prodesa.com/
**Dispositivo:** Mobile (375px) · Desktop (1440px) · Modo incógnito

---

## Registro de pasos

| Paso # | Acción esperada | Q1 — ¿Sabe qué hacer? | Q2 — ¿Ve el control? | Q3 — ¿Entiende causa→efecto? | Q4 — ¿Sistema confirma progreso? | Fricción detectada | Sev. | Captura Mobile (375px) | Captura Desktop (1440px) |
|--------|-----------------|----------------------|---------------------|------------------------------|----------------------------------|--------------------|------|------------------------|--------------------------|
| 2a | Valentina identifica si el sitio es relevante para ella sin hacer scroll | Parcial — hero visible pero sin H1 ni mención de VIS ni precio | Parcial — CTA presente pero puede estar bajo el fold en mobile | Parcial — el CTA no confirma que filtre por VIS | **No** — sin confirmación de llegada desde el anuncio | 🟠 Hero sin propuesta de valor: no puede confirmar en 5 segundos que hay proyectos VIS en Bogotá → [[F2/2.1/05_inventario-final#H-HOME-04]] | 🟠 | ![[assets/home/H-HOME-9_HERO-SIN-CONTEXTO-MOBILE.png]] | ![[assets/home/H-HOME-9_ HERO-SIN-CONTEXTO WEB.png]] |
| 2b | Valentina usa la navegación para orientarse en el sitio | Parcial — dos navbars generan duda sobre cuál usar | **No** — ninguna navbar es claramente la principal | **No** — jerarquía de navegación no es legible | **Parcial** — al hacer clic no hay estado activo claro en el ítem seleccionado. Sin breadcrumbs, no sabe en qué sección aterrizó ni si avanzó hacia su objetivo → [[F2/2.1/05_inventario-final#H-HOME-07]] | 🟠 Doble navbar: gasta tiempo cognitivo entendiendo estructura en lugar de buscar proyectos → [[F2/2.1/05_inventario-final#H-HOME-02]] | 🟠 | ![[assets/home/H-HOME-2 NAV BAR MOBILE.png]] | ![[assets/home/H-HOME-2 NAV BAR WEB.png]] |
| 2c | Valentina encuentra el buscador y entiende cómo iniciar la búsqueda | **Desktop: Sí** — filtros visibles y aplicables directamente. **Mobile: Parcial** — debe hacer clic en "Buscar proyecto" antes de acceder a los filtros. El CTA tiene bajo contraste (texto naranja sobre blanco) y puede perderse | **Desktop: Sí** — filtros visibles above the fold, accesibles de inmediato. **Mobile: Parcial** — "Buscar proyecto" visible pero de bajo contraste y compite en jerarquía con "Realizar Pago" (botón naranja sólido, más prominente) | **Desktop: Sí** — filtros disponibles visibles antes de buscar. **Mobile: Parcial** — Valentina no sabe qué filtros hay hasta hacer clic en "Buscar proyecto". El filtro VIS aparece solo después de ese clic | Parcial — la búsqueda ejecuta una transición visible pero no confirma explícitamente qué filtros quedaron activos | 🟠 **Inconsistencia mobile vs. desktop:** en desktop los filtros son directamente accesibles; en mobile requieren un paso extra (clic en CTA de bajo contraste) que no es obvio. Patrón de interacción diferente entre dispositivos → [[F2/2.1/05_inventario-final#H-FILTROS-03]] · Vincula con [[H3C]] | 🟠 | ![[Pasted image 20260520205148.png]] | ![[Pasted image 20260520204712.png]] |

---

→ [[00_plantilla]] · [[02_punto-entrada]] · [[04_busqueda-filtros]] · [[05_resultados]] · [[06_detalle-proyecto]] · [[07_contacto]] · [[08_inventario-hallazgos]]

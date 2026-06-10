---
tags:
  - research
  - comparador
  - decision-making
  - cognitive-load
  - prodesa
created: 2026-05-21
aliases:
  - Research comparador proyectos
---

# Research — Ausencia de comparador de proyectos

**Contexto:** Prodesa no ofrece herramienta de comparación entre proyectos. Valentina debe abrir dos ventanas del navegador para comparar, mientras las estructuras de cada detalle de proyecto son inconsistentes.

---

## Estándar de industria

El 38% de los top 60 sitios ecommerce tiene una herramienta de comparación dedicada (Baymard Institute). Para productos multi-atributo de alto valor — como vivienda — la comparación es una etapa crítica del proceso de decisión y NN/G la considera un patrón de diseño establecido.

**Referencia:** Real estate apps líderes (Properati, Metrocuadrado, Zillow) incluyen comparadores o fichas técnicas estandarizadas que permiten contraste directo entre propiedades.

---

## Impacto en la decisión del usuario

Sin herramienta de comparación, los usuarios deben gestionar la información en memoria de trabajo mientras navegan entre páginas o pestañas:

- **Precisión de decisión**: cae de 90% a tan solo 30% dependiendo de la carga cognitiva del task (research Baymard / arxiv.org)
- **Abandono**: usuarios sin soporte de comparación tienen journeys "fragmentados" y mayor tasa de abandono (ContentSquare, 2024)
- **Carga cognitiva**: comparar dos proyectos en dos ventanas del navegador es el escenario de máxima carga — el usuario debe recordar datos de un proyecto mientras lee el otro

---

## Agravante: inconsistencia estructural entre proyectos

Cuando además la estructura de cada página de detalle es diferente (tabs distintas, secciones en distinto orden, información disponible solo en algunos proyectos), el usuario no puede desarrollar una estrategia de comparación sistemática. Cada proyecto es una "caja sorpresa" con información diferente.

Esto viola Nielsen P4 (consistencia) y maximiza el esfuerzo cognitivo en una decisión de alto riesgo.

---

## Recomendación de diseño (referencia)

- Ficha técnica estandarizada con los mismos campos en todos los proyectos: precio, m², tipologías, fecha de entrega, subsidios, amenidades
- Botón "Comparar" desde tarjetas del listado — permite seleccionar 2-3 proyectos y ver ficha lado a lado
- Alternativa ligera: sección de resumen con los datos clave always-visible (sticky) mientras el usuario navega el detalle

---

**Fuentes consultadas:**
- [102 'Comparison Tool' Design Examples — Baymard Institute](https://baymard.com/ecommerce-design-examples/39-comparison-tool)
- [Comparison Tables for Products, Services, and Features — NN/G](https://www.nngroup.com/articles/comparison-tables/)
- [Comparing products: UX design best practices — ContentSquare](https://contentsquare.com/blog/product-comparison-ui-ux/)
- [How to design feature comparison tables — LogRocket](https://blog.logrocket.com/ux-design/ui-design-comparison-features/)
- [UX Review of real estate apps — Uptech](https://www.uptech.team/blog/ux-review-of-real-estate-apps)

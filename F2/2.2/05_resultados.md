---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - resultados
  - hallazgos
aliases:
  - CW Resultados
fase: "2.2"
---

# 05 — Resultados
**Persona:** [[01_persona-valentina]] — Valentina Ríos, 32 años, Bogotá, primera compradora VIS
**URL evaluada:** https://prodesa.com/ (listado filtrado)
**Dispositivo:** Mobile (375px) · Desktop (1440px) · Modo incógnito

---

## Registro de pasos

| Paso # | Acción esperada | Q1 — ¿Sabe qué hacer? | Q2 — ¿Ve el control? | Q3 — ¿Entiende causa→efecto? | Q4 — ¿Sistema confirma progreso? | Fricción detectada | Sev. | Captura Mobile (375px) | Captura Desktop (1440px) |
|--------|-----------------|----------------------|---------------------|------------------------------|----------------------------------|--------------------|------|------------------------|--------------------------|
| 4a | Valentina escanea las tarjetas de resultados y decide en cuál entrar | **Sí** — entiende que debe revisar tarjetas y hacer clic en "Ver detalles" | Parcial — cada tarjeta muestra: imagen · badge opcional (varía por proyecto) · precio "Desde: $X *" · tipo · m² · nombre · habitaciones · baños · ciudad · CTA. **Falta en todas:** estado del proyecto, conectividad de transporte. Chip VIS presente pero sin tooltip | **Parcial** — el precio domina visualmente en naranja grande antes que el nombre del proyecto. **El asterisco (*) aparece en TODAS las tarjetas pero su significado varía por proyecto** — en algunas significa "Precio Fijo", en otras muestra información diferente. Valentina no sabe qué significa en cada caso. Sin criterio visible de ordenamiento | **No** — sin contador de resultados. Agravante: algunos precios mostrados superan su presupuesto de $200M — confirma que el slider de 3b no permitió fijar el límite con precisión → [[F2/2.1/05_inventario-final#H-FILTROS-05]] | 🟠 **Asterisco inconsistente entre tarjetas:** aparece en todas pero con significado distinto en cada proyecto. 🟠 Precio domina sobre nombre → [[F2/2.1/05_inventario-final#H-DETALLE-02]]. 🟠 Chip VIS sin tooltip. 🟠 Resultados fuera del presupuesto por imprecisión del slider (3b). 🟠 Sin estado del proyecto ni info de transporte | 🟠 | ![[assets/filtros/H-FILTROS-1-SIN-CONTADOR-DE-RESULTADOS-MOBILE.png]] | ![[assets/filtros/H-FILTROS-1_SIN-CONTADOR-DE-RESULTADOS-WEB.png]] |
| 4b | Valentina intenta comparar dos proyectos para decidir en cuál entrar sin hacer clic | Parcial — entiende que debe revisar las tarjetas para elegir, pero la información disponible no le permite descartar proyectos con confianza | **Desktop: Sí** — lista horizontal, tarjetas consistentes y visibles. **Mobile: Sí** — scroll vertical, mismo contenido. Presentación consistente entre tarjetas | **No** — las tarjetas no muestran los criterios que Valentina necesita para comparar: estado del proyecto, conectividad de transporte, fecha de entrega. Debe entrar a cada proyecto individualmente para obtener esa información | **No** — no hay herramienta de comparación. Cada proyecto requiere un clic separado. Agravante: combinado con 3a (filtros no persistentes), cada vez que entra y vuelve pierde su posición y filtros — ciclo de fricción acumulada | 🟠 **Scanneabilidad insuficiente:** Valentina no puede comparar proyectos sin entrar a cada uno. Combinado con filtros no persistentes (3a), explorar varios proyectos implica rehacer la búsqueda en cada regreso → ciclo de fricción que aumenta el abandono | 🟠 | ![[assets/filtros/H-FILTROS-1-SIN-CONTADOR-DE-RESULTADOS-MOBILE.png]] | ![[assets/filtros/H-FILTROS-1_SIN-CONTADOR-DE-RESULTADOS-WEB.png]] |
| 4c | Valentina aplica filtros que no devuelven resultados y necesita entender qué pasó | **No** — no sabe qué hacer. El sistema no la guía hacia ninguna acción concreta | **No** — el mensaje "No se encuentra información" aparece en gris abajo a la izquierda después de un área blanca vacía muy grande. **Mobile: el mensaje queda debajo del fold** — Valentina no puede saber a primera vista que no hay resultados, tiene que hacer scroll para descubrirlo. Desktop: visible tras un área en blanco extensa pero de muy bajo contraste y posición no esperada | **No** — el sistema no explica por qué no hay resultados ni qué filtro está siendo demasiado restrictivo. Valentina no sabe si es el precio, la ciudad, las habitaciones o la combinación | **No** — sin sugerencia de acción. "Limpiar Filtros" existe en la barra pero no se destaca como solución. **NUEVO:** existen tabs "Todos / Disponibles / Vendidos" — Valentina podría tener resultados en "Todos" sin saber que debe cambiar de tab | 🟠 **Empty state invisible** (mobile: debajo del fold). 🟠 **Tabs Todos/Disponibles/Vendidos sin contexto.** 🟡 **Selector COP/USD/EUR:** ruido visual irrelevante para una compradora local → [[F2/2.1/05_inventario-final#H-FILTROS-05]] | 🟠 | ![[assets/filtros/H-FILTROS-05_ EMPTY-STATE-INVISIBLE-MOBILE.png]] | ![[Pasted image 20260520215647.png]] |
| 4d | Valentina llega al final del listado filtrado y evalúa si vio todas las opciones disponibles | Parcial — ve que la lista termina pero no sabe si son todos los proyectos disponibles o si hay más que no cargaron | **No** — no hay indicador de total de resultados ("2 de 2 proyectos"). No hay paginación porque con filtros aplicados el promedio es ~2 proyectos por ciudad. Layout: desktop horizontal · mobile vertical scroll | **No** — al terminar los resultados filtrados aparece una sección **"Podrían interesarte estas ofertas de otras ciudades"** sin separación visual clara. Valentina puede confundir estos proyectos de otras ciudades con resultados adicionales de Bogotá | **No** — el sistema no confirma que Valentina ya vio todas las opciones disponibles para su búsqueda. La sección de otras ciudades no aclara que los resultados de Bogotá se agotaron | 🟠 **Sin confirmación de fin de resultados.** 🟠 **Sección "Podrían interesarte estas ofertas de otras ciudades" sin separación clara:** puede confundirse con más resultados de Bogotá | 🟠 | ![[Pasted image 20260520220542.png]] | ![[Pasted image 20260520220516.png]] |

---

→ [[00_plantilla]] · [[02_punto-entrada]] · [[03_homepage]] · [[04_busqueda-filtros]] · [[06_detalle-proyecto]] · [[07_contacto]] · [[08_inventario-hallazgos]]

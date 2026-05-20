---
tags:
  - research
  - ux-patterns
  - real-estate
  - detalle-proyecto
  - visibilidad
  - estado-proyecto
  - colombia
aliases:
  - Research H-DETALLE-08 Visibilidad Estado del Proyecto
---

# Research: Por qué el estado del proyecto es información crítica en la página de detalle inmobiliario

**Contexto:** H-DETALLE-08 — ausencia de etiqueta visible de estado del proyecto (preventa / en construcción / listo para entrega / agotado) en las páginas de detalle de prodesa.com  
**Fecha:** Mayo 2026  
**Método:** Benchmarking de portales maduros + literatura UX especializada en real estate + contexto del mercado inmobiliario colombiano

---

## 1. El principio violado: Heurística #1 de Nielsen — Visibilidad del estado del sistema

La primera heurística de Jakob Nielsen establece:

> *"El diseño debe mantener siempre a los usuarios informados sobre lo que está ocurriendo, mediante retroalimentación apropiada y en el momento correcto."*

En el contexto de un portal inmobiliario, el **estado del proyecto** es la pieza de información que define el "estado del sistema" más relevante para el comprador: le dice si el proyecto existe como posibilidad real para él en este momento, o si está mirando algo que no puede comprar. Sin esa información visible, el usuario no puede determinar cuál es su próximo paso — ni siquiera si tiene sentido seguir leyendo.

Nielsen Norman Group (actualizado 2024) es explícito: *"Los usuarios que no conocen el estado actual del sistema no pueden decidir qué hacer a continuación para lograr sus objetivos."* En una página de proyecto inmobiliario, ese principio se traduce directamente: un usuario que no sabe si el proyecto está en preventa o listo para entrega no puede evaluar si ese proyecto encaja en su plan de vida.

---

## 2. Las fases de un proyecto inmobiliario en Colombia y por qué cada una importa

En Colombia, un proyecto inmobiliario atraviesa etapas bien definidas, y **cada una implica condiciones radicalmente distintas** de precio, plazo, forma de pago, riesgo y elegibilidad para subsidios. Para el comprador, saber en qué fase está el proyecto no es un dato secundario — es el primer filtro que determina si el proyecto es relevante para él.

| Estado | Qué significa para el comprador | Condiciones financieras | Riesgo |
|--------|--------------------------------|------------------------|--------|
| **Preventa / Sobre planos** | El proyecto no está construido. Se compra basado en renders y planos. Precio más bajo del ciclo. | Plan de pagos extendido durante la construcción — cuotas mensuales bajas. No hay desembolso total inmediato. | Depende de que la constructora cumpla plazos y condiciones pactadas. Los recursos quedan en fiducia. |
| **En construcción** | El proyecto existe físicamente en algún punto de avance. Precio intermedio. | Plan de pagos parcial — se paga durante la construcción, saldo contra escritura. | Menor que preventa — la construcción ya inició y hay avance verificable. |
| **Listo para entrega** | El proyecto está terminado o en proceso de escrituración. Precio final de mercado. | Crédito hipotecario inmediato — el banco desembolsa contra la escritura, no contra planos. | Mínimo — el comprador puede ver el producto terminado antes de firmar. |
| **Agotado** | No hay unidades disponibles. | No aplica. | El usuario no puede comprar — cualquier lead generado es un lead frustrado. |

**Fuente:** La Haus — Fases de un proyecto inmobiliario en Colombia; Ciencuadras — Etapas de un proyecto inmobiliario; Llegué a Casa — Preventa, sobre planos o entrega inmediata.

---

## 3. El impacto directo de no mostrar el estado

### Para el usuario

Un comprador que necesita mudarse en 8 meses **no puede comprar un proyecto en preventa con entrega en 2027** — pero si la página no muestra el estado, puede avanzar en el proceso (leer la descripción, revisar las tipologías, llenar el formulario de contacto) hasta que un asesor le comunique la realidad. Ese momento de descubrimiento tardío genera frustración activa: el usuario invirtió tiempo y expectativa emocional en un proyecto que no le aplica.

La investigación de Nielsen Norman Group es clara: *"Los usuarios que no conocen el estado del sistema no pueden determinar si sus acciones tuvieron efecto ni cuáles son sus próximos pasos."* En real estate, el "próximo paso" correcto depende enteramente del estado del proyecto.

### Para el negocio (Prodesa)

La ausencia del estado del proyecto no es neutral para el equipo comercial:

- **Leads de menor calidad:** El asesor debe atender una consulta básica ("¿Cuándo entrega el proyecto?") en lugar de una consulta de cierre. Eso consume tiempo del equipo en una etapa que el usuario debería poder resolver por sí mismo con la página.
- **Expectativas incorrectas:** Un proyecto en preventa presentado sin esa etiqueta puede generar leads de usuarios que esperan entrega inmediata — la conversación empieza con una decepción.
- **Leads de proyectos agotados:** Un proyecto agotado sin etiqueta de "Agotado" sigue generando visitas, formularios y llamadas de usuarios que no van a poder comprar. Ese costo operativo es evitable.

---

## 4. El estándar de la industria

Todos los portales inmobiliarios con presencia digital madura muestran el estado del proyecto de forma prominente. El patrón es tan consistente que su ausencia es inmediatamente notada por el usuario como una señal de alarma.

### Cómo lo implementan los portales maduros

- **Chip de color en el hero** — visible sin scroll, en la misma zona que el nombre y el precio. Código de color intuitivo:
  - 🟢 Verde — Disponible / Listo para entrega
  - 🟡 Amarillo — Últimas unidades
  - 🔵 Azul / Gris — En preventa / Sobre planos
  - 🔴 Rojo — Agotado
- **Chip en la tarjeta del listado** — el filtro mental del comprador empieza en el listado, no en el detalle. Si el estado no está en la tarjeta, el usuario puede entrar a un proyecto agotado sin saberlo.
- **Consistencia entre listado y detalle** — el estado mostrado en la tarjeta debe coincidir con el estado en el hero del detalle. Cualquier discrepancia genera desconfianza.

### Por qué el color code funciona

El color es procesado de forma pre-atentiva — el cerebro lo procesa antes de leer el texto. Un chip rojo de "Agotado" detiene al usuario antes de que invierta tiempo en leer la descripción del proyecto. Esa es exactamente la función que debe cumplir: **ahorrarle al usuario el tiempo de descubrir la realidad por sí solo**.

---

## 5. El contexto específico del mercado colombiano

El mercado de vivienda en Colombia tiene características que hacen el estado del proyecto **especialmente crítico**:

1. **Alta proporción de ventas en preventa.** En Colombia, una fracción significativa de las ventas de vivienda nueva se realiza antes de que la construcción esté terminada. El comprador primerizo colombiano está habituado a comprar "sobre planos" — pero necesita saber que eso es lo que está haciendo.

2. **Subsidios con condiciones de estado.** El subsidio *Mi Casa Ya* tiene restricciones que dependen del estado del proyecto — no todos los proyectos en preventa están habilitados para subsidio en el mismo momento. Si el usuario no sabe el estado, no puede evaluar si su subsidio aplica.

3. **Protección fiduciaria vinculada al estado.** En preventa, los recursos van a una fiducia y solo se liberan cuando se cumplen condiciones de preventas mínimas. Este mecanismo de protección al comprador — regulado por la SIC — está directamente ligado al estado del proyecto. Un comprador informado sabe que en preventa sus recursos tienen esa protección; un comprador desinformado no puede hacer esa evaluación.

4. **Retrasos en construcción como riesgo real.** Los portales especializados en Colombia (La Haus, Properati) documentan que los retrasos en construcción son comunes y pueden generar gastos adicionales. La visibilidad del estado — y de la fecha estimada de entrega — es la única herramienta que tiene el comprador para evaluar ese riesgo antes de comprometerse.

---

## 6. Conexión con otros hallazgos del proyecto

| Hallazgo relacionado | Conexión |
|----------------------|----------|
| **H-DETALLE-05** — Fecha de entrega ausente | El estado del proyecto y la fecha de entrega son la misma necesidad de información vista desde dos ángulos: el estado dice *en qué fase está*, la fecha dice *cuándo termina esa fase*. Ninguno de los dos existe actualmente en prodesa.com. |
| **H-FILTROS-06** — Tarjetas sin estado en el listado | La inconsistencia es transversal: el estado no aparece en el detalle (H-DETALLE-08) ni en la tarjeta del listado (H-FILTROS-06). El usuario nunca recibe esta información en ningún punto del flujo. |
| **H-DETALLE-06** — Sin plantilla estandarizada | Aunque algún proyecto tuviera el estado visible, sin una plantilla obligatoria no hay garantía de que todos los proyectos lo muestren. El estado del proyecto debe ser un campo obligatorio de la plantilla. |

---

## 7. Cómo evidenciarlo

**Captura 1 — Hero del detalle:** screenshot del hero de cualquier página de proyecto de prodesa.com mostrando la ausencia de chip, badge o etiqueta de estado. El hero tiene nombre, precio, área y CTAs — el estado no aparece en ninguna posición.

**Captura 2 — Tarjeta del listado:** screenshot de las tarjetas en `/proyecto-vivienda` confirmando que tampoco en el listado hay etiqueta de estado — la inconsistencia es transversal.

**Captura 3 — Benchmark:** screenshot de un portal maduro (La Haus, Properati, o una constructora colombiana con implementación correcta) mostrando el chip de estado en el hero — para contrastar el estándar de industria con la implementación actual.

---

## Conclusión aplicada a Prodesa

El estado del proyecto es el dato que responde la pregunta más básica del comprador antes de invertir tiempo en una página: *"¿Este proyecto es una opción real para mí hoy?"* Su ausencia no es una omisión menor — es una falla de visibilidad que viola el principio más fundamental de usabilidad (Heurística #1 de Nielsen), genera leads de menor calidad para el equipo comercial, y expone al usuario a tomar decisiones basadas en información incompleta sobre una de las compras más importantes de su vida.

La solución es técnicamente simple: un chip de color en el hero del detalle y en la tarjeta del listado, con un campo obligatorio en el CMS que impida publicar un proyecto sin definir su estado.

---

## Fuentes

- [Visibility of System Status (Usability Heuristic #1) — NN/G](https://www.nngroup.com/articles/visibility-system-status/)
- [10 Usability Heuristics for User Interface Design — NN/G](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [¿Cuáles son las fases de un proyecto inmobiliario en Colombia? — La Haus](https://www.lahaus.com/blog/comprar-vivienda/fases-de-un-proyecto-inmobiliario-en-colombia)
- [Guía completa sobre las preventas inmobiliarias en Colombia — La Haus](https://www.lahaus.com/guias-inmobiliarias/tipos-de-inversion/preventa-inmobiliaria)
- [Proyecto de Vivienda: ¿Preventa, Sobre planos o Entrega Inmediata? — Llegué a Casa](https://llegueacasa.com/proyecto-de-vivienda-preventa-sobre-planos-o-entrega-inmediata-guia-2025-para-compradores-inteligentes/)
- [Conoce las etapas de un proyecto inmobiliario — Ciencuadras](https://www.ciencuadras.com/blog/proyectos-de-vivienda/conoce-las-etapas-de-un-proyecto-inmobiliario)
- [Ventajas de comprar proyectos inmobiliarios en preventa — Ciencuadras](https://www.ciencuadras.com/blog/guia-para-comprar-vivienda/ventajas-de-comprar-proyectos-inmobiliarios-en-preventa)
- [Todo lo que necesitas saber sobre la preventa de vivienda en Colombia en 2025 — La Haus](https://www.lahaus.com/blog/tendencias-del-mercado/lo-que-necesitas-saber-sobre-la-preventa-de-vivienda-en-colombia-en-2025)
- [Heuristic #1: Visibility of system status — Dualoop](https://dualoop.com/blog/heuristic-visibility-of-system-status)
- [Real Estate Website UI/UX Development: Best Practices — DCastalia](https://dcastalia.com/blog/real-estate-website-ui-ux-development/)

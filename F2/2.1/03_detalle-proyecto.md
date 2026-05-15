---
tags:
  - prodesa
  - evaluacion-heuristica
  - detalle-proyecto
  - hallazgos
  - critico
aliases:
  - Hallazgos Detalle de Proyecto
---

# 03 — Hallazgos Detalle de Proyecto
**URLs evaluadas:**
- https://prodesa.com/proyecto-vivienda/agora → redirect a `/proyecto-vivienda/cali/agora`
- https://prodesa.com/proyecto-vivienda/centrico
- Patrón general de páginas de proyecto en prodesa.com

**Fecha:** Mayo 2026

---

## Resumen de hallazgos

| ID | Principio | Página/Elemento | Descripción del problema | Captura | Severidad | Recomendación |
|----|-----------|-----------------|--------------------------|---------|-----------|---------------|
| H-DETALLE-01 | P8 - Minimalismo + P6 - Reconocimiento | Detalle proyecto / Hero | **Corregido tras validación visual.** El H1 no replica el meta-título — es simplemente "Proyecto de Vivienda [Nombre]". Sin embargo, la validación reveló tres problemas reales: (1) **Redundancia doble en el H1**: el prefijo "Proyecto de Vivienda" es genérico e idéntico en todos los proyectos. En mobile se agrava: existe un chip separado que dice "Proyecto de vivienda" encima de la imagen, y el H1 debajo repite "Proyecto de Vivienda Mirla" — dos elementos distintos comunicando lo mismo, antes de llegar al nombre real del proyecto. (2) **Inversión de jerarquía visual**: el precio aparece en naranja con tipografía grande, con mayor peso visual que el H1 en gris — la página comunica que el precio es más importante que el nombre del proyecto. (3) **Redundancia de CTAs en desktop**: "Déjanos tus datos" en la barra sticky duplica el formulario ya visible en el hero; "Agenda tu cita" solicita correo electrónico cuando solo debería pedir teléfono. | ✅ validado en Ágora y Mirla — desktop y mobile | 2 🟡 | (1) Eliminar el prefijo "Proyecto de Vivienda" del H1 y el chip en mobile — el H1 debe ser el nombre del proyecto. (2) Dar al nombre del proyecto el mayor peso tipográfico del hero, por encima del precio. (3) En desktop, eliminar "Déjanos tus datos" de la barra sticky cuando el formulario ya está visible; simplificar "Agenda tu cita" para requerir solo teléfono. |
| H-DETALLE-02 | P6 - Reconocimiento + P8 - Minimalismo | Detalle proyecto / Hero — precio y área | **Corregido tras validación visual.** El precio sí aparece prominente en naranja — la premisa del "texto corrido" era incorrecta. El problema real es de **jerarquía interna entre precio y área**: en la página de detalle ambos datos aparecen con idéntico peso visual (mismo tamaño, mismo color naranja, mismo estilo tipográfico). El precio es el dato más determinante para la decisión de compra; el área es secundario. Al tener igual peso visual, el usuario no recibe ninguna señal de qué dato priorizar. Contraste: en las tarjetas del listado mobile, el precio sí tiene más peso visual que el área (naranja más grande vs. texto gris más pequeño) — la diferenciación correcta existe en el listado pero desaparece en el detalle. | ✅ validado en Mirla y Ágora (desktop y mobile) | 2 🟡 | El precio debe tener claramente mayor tamaño tipográfico que el área. El área pasa a un segundo nivel visual: tipografía más pequeña o color menos saturado. La jerarquía correcta es: nombre del proyecto → precio → área → datos secundarios (habitaciones, fecha de entrega). |
| H-DETALLE-03 | P3 - Control del usuario + P8 - Minimalismo | Detalle proyecto / Sección "Acerca del proyecto" — desktop | **Reformulado tras validación visual. Problema exclusivo de desktop.** La sección "Acerca del proyecto" cierra con dos CTAs: **"Descargar brochure"** (botón naranja relleno — CTA primario visual) y **"Compartir"** (botón outline — CTA secundario). En desktop, el canal de contacto más cercano es el formulario en la columna derecha — estructuralmente separado del texto, no integrado en la sección. Dos problemas: (1) **Desconexión contextual en desktop**: el usuario termina de leer la descripción y debe cambiar de columna para contactar — fricción entre el momento de intención y la acción disponible. (2) **Jerarquía invertida en ambas versiones**: "Descargar brochure" (intención media) recibe el CTA primario visual; el contacto directo (intención alta) no tiene representación en la sección. **En mobile no aplica el problema de desconexión**: la barra sticky con WhatsApp, "Agenda tu cita" y "Déjanos tus datos" es persistente durante todo el scroll — el usuario siempre tiene acceso inmediato sin interrumpir su flujo de lectura. | ✅ validado en Ágora desktop y Praseo mobile | 2 🟡 | En desktop: añadir CTA de contacto directo al final de la sección "Acerca del proyecto" (*"Escríbenos por WhatsApp"*) con tratamiento primario; "Descargar brochure" pasa a secundario. En mobile: el patrón actual de barra sticky funciona correctamente — mantener. |
| H-DETALLE-05 | P6 - Reconocimiento + P1 - Visibilidad | Detalle proyecto / Ficha técnica | **Corregido tras validación visual.** La información de habitaciones, m² y precio detallado sí existe — aparece en la sección "Inmuebles disponibles" con formato de fichas visuales. El problema es doble: (1) **Ubicación**: estos datos requieren scroll para encontrarse — no están en el hero ni en el primer fold, obligando al usuario a buscar activamente información básica de decisión. (2) **Dato ausente crítico**: la **fecha estimada de entrega** no aparece en ningún lugar de la página — ni en el hero, ni en la ficha técnica, ni en las especificaciones. Para un comprador, saber si el proyecto entrega en 6 meses o en 3 años es determinante. Su ausencia impide que el usuario evalúe si el proyecto encaja en su plan de vida. | ✅ validado en Ágora desktop — sección "Inmuebles disponibles" | 2 🟡 | (1) Subir los datos clave (habitaciones, m², precio) al hero — visibles sin scroll junto al nombre del proyecto. (2) Añadir fecha estimada de entrega como campo obligatorio en la ficha técnica, en formato claro: *"Entrega estimada: 2do semestre 2026"*. |
| H-DETALLE-06 | P4 - Consistencia | Múltiples proyectos / Diseño | Prodesa tiene más de 15 proyectos activos. Sin una plantilla de página de detalle estrictamente estandarizada, **la experiencia puede variar entre proyectos**: algunos pueden tener más fotos, otros más texto, otros sin precio visible. Esta inconsistencia genera desconfianza y obliga al usuario a "reaprender" la interfaz en cada proyecto. | pendiente | 2 | Definir y aplicar una plantilla única de página de proyecto: hero con imagen + precio + CTA, ficha técnica, galería, mapa, formulario de interés. Todos los proyectos deben seguir exactamente el mismo layout. |
| H-DETALLE-07 | P3 - Control del usuario | Detalle proyecto / Navegación de regreso | En el flujo homepage → listado → detalle, el usuario debe poder **regresar al listado manteniendo sus filtros activos**. Si al volver al listado los filtros se pierden, el usuario tiene que reconfigurar su búsqueda desde cero, lo que genera frustración y abandono. | pendiente | 2 | Implementar navegación "breadcrumb + back" que preserve el estado de los filtros al regresar al listado. Usar parámetros en la URL para persistir el estado de la búsqueda. |
| H-DETALLE-08 | P1 - Visibilidad | Detalle proyecto / Estado del proyecto | No se detecta en los metadatos o en la estructura del HTML un campo visible de **estado del proyecto** (En preventa / En construcción / Listo para entrega / Agotado). Para el comprador, esta es información crítica que afecta directamente la decisión. | pendiente | 3 | Mostrar el estado del proyecto de forma prominente y visible (ej. chip de color: 🟢 Disponible / 🟡 Últimas unidades / 🔴 Agotado) en el hero de la página y en la tarjeta del listado. |
| H-DETALLE-09 | P10 - Ayuda y documentación | Detalle proyecto / Información de subsidios | La meta-descripción menciona *"subsidio disponible"* pero no ofrece contexto sobre **qué subsidio, a quién aplica, ni cómo acceder a él**. El proceso de subsidio de vivienda en Colombia es complejo (Mi Casa Ya, Caja de Compensación, etc.) y los compradores primerizo necesitan orientación en este punto. | pendiente | 2 | Incluir en la página de detalle una sección o acordeón de "¿Puedo acceder al subsidio?" con criterios básicos de elegibilidad y un CTA a "Consultar con asesor". Esto también aumenta el número de leads calificados. |

---

## Análisis detallado por hallazgo — ¿Por qué es importante solucionarlo?

### H-DETALLE-01 — H1 redundante, jerarquía visual invertida y CTA de alta fricción


**Problema 1 — El H1 es redundante y entierra la marca. En mobile, la redundancia se duplica.**

"Proyecto de Vivienda" es un prefijo genérico idéntico en todos los proyectos del sitio. El usuario que llega a esta página ya sabe que está viendo un proyecto de vivienda — está en prodesa.com. El prefijo no aporta ninguna información nueva y, lo más importante, desplaza el nombre de marca al final de la línea. "Ágora" y "Mirla" son los nombres que el usuario vio en el listado, recordó mientras navegaba, y buscó en la página. Que aparezcan al final de "Proyecto de Vivienda Ágora" en lugar de ser el primer elemento que el ojo encuentra es una oportunidad perdida de anclar la identidad del proyecto.

En mobile el problema se agrava: aparece un chip encima de la imagen que dice *"Proyecto de vivienda"* y el H1 debajo que dice *"Proyecto de Vivienda Mirla"*. Son dos elementos visuales distintos comunicando exactamente la misma información genérica, uno encima del otro. El nombre real del proyecto — "Mirla" — sigue siendo lo último que el ojo procesa.

**Problema 2 — El precio visualmente domina sobre el nombre del proyecto.**

En ambas páginas, el precio — "Desde $ 236.372.175 \*" — aparece en naranja, con tipografía notablemente más grande que el H1, que está en gris y en un tamaño normal. El área también tiene el mismo tratamiento naranja prominente. La jerarquía visual resultante es: precio → área → nombre del proyecto. Esa es una inversión del orden correcto.

El nombre del proyecto es el elemento de identidad — el ancla de la página. El precio es un atributo. En ningún portal inmobiliario maduro el precio tiene mayor peso visual que el nombre del proyecto en el hero. La razón es simple: el usuario que llegó a esta página ya vio el precio en el listado y lo consideró razonable. Lo que necesita confirmar ahora es que está en el proyecto correcto, no que el precio sigue siendo el mismo. Darle al precio el protagonismo visual que debería tener el nombre es responder una pregunta que el usuario ya no tiene.

**Problema 3 — Redundancia de CTAs en desktop y fricción innecesaria en "Agenda tu cita" en ambas versiones.**

La validación confirmó que el WhatsApp funciona correctamente como opción de contacto directo — el usuario puede escribir sin completar ningún formulario. Ese canal de baja fricción existe y está disponible en desktop y mobile.

**En desktop**, la barra sticky inferior tiene tres opciones: "Déjanos tus datos", "Agenda tu cita" y "Escríbenos a Whatsapp". El primero — "Déjanos tus datos" — hace exactamente lo mismo que el formulario de 6 campos que ya está visible en el hero a la derecha. Cuando un elemento ya ocupa espacio prominente en pantalla, un CTA que lleva al mismo elemento no agrega valor — genera ruido visual y multiplica opciones sin aumentar la utilidad.

**En mobile**, el formulario de 6 campos no aparece en el hero. En esta versión "Déjanos tus datos" sí tiene sentido como CTA porque el formulario no es visible — no es redundante. La arquitectura de CTAs funciona mejor en mobile en este punto concreto.

**En ambas versiones**, "Agenda tu cita" introduce una fricción innecesaria: solicita correo electrónico para agendar una visita a la sala de ventas. Para ese objetivo, el teléfono debería ser suficiente — el correo es un campo extra que no corresponde a la necesidad inmediata del usuario.

El resultado en desktop es una barra de tres CTAs donde uno duplica algo ya visible en pantalla y otro pide más datos de los necesarios. En mobile la arquitectura es más limpia, pero el problema de "Agenda tu cita" persiste en ambas.![[H-DETALLE-1_MIRLA-FALLO-JERARQUIA.png|495]]

![[H-DETALLE-1_AGORA-FALLO-JERARQUIA.png|495]]
![[H-DETALLE-1_FALLO-JERARQUIA-MOBILE.png|133]]

---

### H-DETALLE-02 — Sin jerarquía visual entre precio y área en la página de detalle

**Corrección respecto a la hipótesis inicial**

La validación visual en Mirla y Ágora confirmó que el precio sí aparece prominente en naranja — la premisa del "texto corrido" era incorrecta. Sin embargo, la comparación entre el listado y el detalle en mobile reveló un problema real de jerarquía interna que justifica mantener el hallazgo con un enfoque distinto.

**El problema: precio y área con idéntico peso visual.**

En la página web, tanto el precio como el área aparecen con exactamente el mismo tratamiento tipográfico: mismo tamaño, mismo color naranja, mismo peso visual. Para Mirla: *"Desde $ 206.172.000 \*"* y *"Desde 46m² área construida"* — línea a línea, sin ninguna diferencia de jerarquía entre ellas.

El precio y el área no son datos equivalentes en la decisión de compra. El precio determina si el proyecto es financieramente alcanzable — es el primer filtro mental del comprador. El área determina si el espacio es suficiente — es un filtro secundario, relevante solo si el precio ya pasó. Darles el mismo peso visual elimina esa señal de prioridad y obliga al usuario a decidir por sí mismo qué dato procesar primero, en lugar de que el diseño lo guíe.

**El contraste con el listado lo hace más evidente.**

En las tarjetas del listado Mobile, el sistema sí diferencia correctamente: el precio aparece en naranja con mayor tamaño, y el área en texto gris más pequeño. La jerarquía correcta existe en el listado — el dato más importante tiene más peso visual. Esa misma lógica desaparece en la página de detalle, donde ambos datos se nivelan visualmente. Es una inconsistencia interna del propio sistema: el listado enseña una jerarquía que el detalle no respeta.

**El impacto en la lectura.**

Un usuario que escanea el Hero de la página web ve dos líneas naranjas del mismo tamaño y debe decidir cuál leer primero. En un proceso de compra de alta implicación como la vivienda, esa micro-decisión es irrelevante — pero acumula fricción cognitiva innecesaria. El diseño debe resolver esa decisión por el usuario, no delegársela.
![[H-DETALLE-2_SIN-JERARQUIA-WEB.png|205]]
![[H-DETALLE-2_JERARQUIA-MOBILE.png|197]]



---

### H-DETALLE-03 — "Descargar brochure" como CTA primario, contacto directo desconectado del flujo de lectura

**Reformulación tras validación visual**

La validación en Ágora confirmó que los canales de contacto sí existen en la página: el formulario está en la columna derecha en desktop, y la barra sticky tiene WhatsApp, "Agenda tu cita" y "Déjanos tus datos". La hipótesis original de "ausencia total de CTA de contacto" era incorrecta. Sin embargo, la captura reveló dos problemas reales que justifican mantener el hallazgo con severidad 2.

**Problema 1 — Desconexión contextual en desktop: el CTA correcto no está donde el usuario termina de leer.**

La sección "Acerca del proyecto" termina con el texto: *"¡Invierte en centro de Cali con alta plusvalía garantizada!"* — una frase que intenta activar la intención de compra. Inmediatamente después, los únicos CTAs disponibles en esa sección son "Descargar brochure" y "Compartir".

En desktop, el formulario de contacto está en la columna derecha — estructuralmente separado del texto que el usuario acaba de leer. El usuario que termina la descripción motivado para actuar tiene que cambiar de columna para encontrar el canal de contacto. Esa separación espacial entre el momento de intención y la acción disponible introduce fricción innecesaria.

En mobile este problema no se replica de la misma forma: la barra sticky con WhatsApp, "Agenda tu cita" y "Déjanos tus datos" es persistente en la parte inferior de la pantalla durante todo el scroll. El usuario siempre tiene acceso inmediato a los canales de contacto sin cambiar de contexto visual. La desconexión contextual es un problema exclusivo de la experiencia desktop.

**Problema 2 — Jerarquía invertida de CTAs.**

"Descargar brochure" recibe el tratamiento visual de CTA primario — botón naranja relleno, el más prominente de la sección. "Compartir" es secundario. El contacto directo no tiene representación.

Esta jerarquía invierte la lógica del funnel: "Descargar brochure" es una acción de intención media — el usuario que descarga el brochure sigue en fase de investigación. El contacto directo con un asesor es la acción de mayor intención — el paso previo a la visita y al cierre. Dar el protagonismo visual al paso de menor intención y no representar el de mayor intención en el mismo punto es una señal de que el diseño no está optimizado para conversión.
![[H-DETALLE-3_CTA-MOBILE.png|184]]![[H-DETALLE-3_DESCONECTADO-WEB.png|506]]

---


### H-DETALLE-05 — Datos clave requieren scroll y fecha de entrega ausente

**Corrección respecto a la hipótesis inicial**

La validación en la sección "Inmuebles disponibles" de Ágora confirmó que la información de habitaciones, m² y precio detallado sí existe y tiene un buen formato visual — fichas con íconos, área construida vs. área privada, precio en tarjeta. La hipótesis de que esta información estaba completamente ausente era incorrecta. Sin embargo, la validación reveló dos problemas reales que justifican mantener el hallazgo.

**Problema 1 — Los datos clave están en la página pero requieren scroll.**

La ficha técnica con habitaciones y m² no está en el hero — está en la sección "Inmuebles disponibles", más abajo en la página. El usuario que llega a la página de detalle ve primero: nombre del proyecto, precio general, área general, íconos de navegación (Fotografías, Urbanismo, Ubicación, Simulador). Para encontrar el número de habitaciones y las especificaciones detalladas tiene que hacer scroll hasta llegar a la sección correcta.

En un proceso de decisión de compra, los datos básicos — habitaciones, m², precio — son los primeros filtros mentales que el usuario aplica. Si esos datos no están visibles en el primer fold, el usuario tiene que invertir tiempo en buscarlos antes de saber si el proyecto le aplica. Esa fricción es evitable: esos datos podrían estar en el hero junto al precio general.

**Problema 2 — La fecha estimada de entrega no aparece en ningún lugar de la página.**

Ni en el hero, ni en la sección "Acerca del proyecto", ni en la ficha de especificaciones. La fecha de entrega es un dato crítico para la decisión de compra que no tiene equivalente en otros campos: saber cuándo se entrega el proyecto determina si el comprador puede adquirirlo según su plan de vida. Un usuario que necesita mudarse en 8 meses no puede comprar un proyecto en preventa con entrega en 2027 — pero sin la fecha visible, puede avanzar en el proceso hasta que un asesor se lo comunique, generando una frustración tardía para ambas partes.

La ausencia de este dato no es menor: en el mercado colombiano de vivienda, los proyectos pueden estar en preventa, en construcción o listos para entrega. Cada estado implica condiciones de financiación, plazos y riesgos completamente diferentes. Ocultarlo por omisión no es una opción neutral — genera decisiones mal informadas.
![[H-DETALLE-5_DATOS-SCROLL-MOBILE.png|159]]
![[H-DETALLE-5_FALTA-DATOS-MOBILE.png|159]]
![[H-DETALLE-5_FALTAN-DATOS-WEB.png|423]]

![[H-DETALLE-5_SCROLL-DATOS-WEB.png]]

---

### H-DETALLE-06 — Sin plantilla estandarizada entre proyectos

**¿Por qué es importante solucionarlo?**

Prodesa tiene más de 15 proyectos activos distribuidos en 16 ciudades. Si cada página de proyecto fue construida o editada de forma independiente, sin una plantilla estricta, la experiencia puede variar significativamente entre proyectos: algunos tendrán más fotos, otros más texto, algunos mostrarán el precio arriba y otros abajo, algunos tendrán mapa y otros no.

**El problema de la inconsistencia para el usuario.** Cuando el usuario compara dos proyectos — lo cual es casi universal en un proceso de compra de vivienda — necesita poder hacer esa comparación sin tener que "reaprender" la página en cada proyecto. Si Mirla muestra el precio en la descripción y Ágora lo muestra en una ficha técnica, y Céntrico no lo muestra hasta el tercer scroll, el usuario está invirtiendo energía cognitiva en navegar la interfaz en lugar de en evaluar los proyectos. Esa energía cognitiva es limitada y su consumo innecesario aumenta la probabilidad de abandono.

**El impacto en la confianza.** Una interfaz inconsistente comunica desorganización. Un comprador que está tomando la decisión más importante de su vida financiera necesita confiar en que la empresa a la que le va a entregar sus ahorros es ordenada y profesional. La inconsistencia en las páginas de proyecto genera una señal de alarma inconsciente.

**El problema sistémico.** La ausencia de plantilla no es solo un problema de UX — es un problema de gobernanza de contenidos. Si el equipo de marketing de Prodesa puede editar cada página de proyecto de forma independiente, cada publicación nueva reproduce la inconsistencia. La solución no es solo de diseño sino de sistema de gestión de contenidos (CMS) que fuerce la estructura.

**Cómo evidenciarlo:** captura side-by-side de dos proyectos distintos (ej. Mirla y Ágora) mostrando diferencias en la posición o presencia del precio, la ficha técnica o los CTAs.

---

### H-DETALLE-07 — Al regresar al listado se pierden los filtros aplicados

**¿Por qué es importante solucionarlo?**

El flujo natural de un usuario que busca vivienda es: aplica filtros en el listado → entra al detalle de un proyecto → vuelve al listado → entra al siguiente proyecto que le interesó. Si al volver al listado los filtros se pierden y el sistema muestra todos los proyectos sin filtrar, el usuario tiene que reconfigurar su búsqueda desde cero en cada ciclo de comparación.

**El costo real en tiempo y fricción.** En una sesión de búsqueda típica, un comprador puede revisar entre 5 y 10 proyectos antes de tomar una decisión de contacto. Si cada vez que vuelve al listado debe reseleccionar ciudad, rango de precio, habitaciones y tipo (VIS/NO VIS), está repitiendo los mismos 4 o 5 pasos entre 5 y 10 veces. Lo que debería ser una navegación fluida entre proyectos se convierte en una tarea repetitiva y frustrante.

**El efecto de desorientación adicional.** Cuando el usuario vuelve al listado y no ve sus filtros aplicados, puede creer que algo falló — que su búsqueda personalizada desapareció. Esa sensación de pérdida de control viola directamente P3 (Control del usuario): el sistema anuló una configuración que el usuario había hecho deliberadamente, sin que el usuario lo pidiera.

**La solución técnica es estándar.** Persistir el estado de los filtros al navegar entre el listado y el detalle es un comportamiento esperado en cualquier e-commerce moderno. Se implementa pasando los parámetros de filtro en la URL (ej. `/proyecto-vivienda?ciudad=bogota&precio-max=300M`) o almacenándolos en el estado de sesión del navegador. Es una práctica tan común que su ausencia es notada inmediatamente por usuarios habituados a portales como Mercado Libre o Airbnb.

**Cómo evidenciarlo:** (1) aplicar un filtro en el listado, (2) entrar al detalle de un proyecto, (3) usar el botón "atrás" del navegador o cualquier link de regreso al listado, (4) capturar el estado del listado mostrando que los filtros están en blanco o en valores default.

---

### H-DETALLE-08 — Sin etiqueta de estado del proyecto visible

**¿Por qué es importante solucionarlo?**

Este es el segundo hallazgo más crítico de la sección. El estado del proyecto — en preventa, en construcción, listo para entrega, o agotado — es información que determina directamente si el proyecto es relevante para el comprador en este momento. Un usuario que necesita mudarse en seis meses no puede comprar un proyecto en preventa con entrega en 2027. Si esa información no está visible en la página de detalle, el usuario puede invertir tiempo y energía emocional en un proyecto que finalmente no le aplica.

**El problema de la decisión basada en información incompleta.** El proceso de compra de vivienda en Colombia involucra múltiples actores y semanas o meses de deliberación. El comprador que no sabe el estado del proyecto tiene que contactar a un asesor para hacer una pregunta que debería poder responder solo con la página. Eso es un lead de menor calidad para Prodesa (el asesor atiende una consulta básica en lugar de una consulta de cierre) y una fricción innecesaria para el usuario.

**El benchmark del sector.** Todas las constructoras con presencia digital madura muestran el estado del proyecto de forma prominente: un chip de color en el hero de la página y en la tarjeta del listado. El código de color es intuitivo: verde para disponible, amarillo para últimas unidades, rojo para agotado, azul o gris para preventa. Este patrón es tan estándar que su ausencia genera confusión — el usuario asume que si no dice nada, el proyecto está disponible, lo cual puede ser una información incorrecta.

**El impacto en la confianza y en la gestión comercial.** Un proyecto agotado que no dice que está agotado genera leads de usuarios que no van a poder comprar. Eso cuesta tiempo al equipo comercial de Prodesa y genera frustración en los usuarios que descubren la realidad después de hacer contacto. Un proyecto en preventa sin fecha de entrega visible genera expectativas incorrectas. La ausencia de estado no es neutral — es una fuente activa de malentendidos.

**Cómo evidenciarlo:** captura del hero de la página de detalle mostrando la ausencia de cualquier chip, badge o etiqueta que indique el estado del proyecto. Complementar con la tarjeta del listado para mostrar que la inconsistencia es transversal (tampoco está en el listado, ya documentado en H-FILTROS-06).

---

### H-DETALLE-09 — "Subsidio disponible" sin contexto de tipo, requisitos ni proceso

**¿Por qué es importante solucionarlo?**

La meta-descripción de proyectos como Mirla menciona *"subsidios disponibles hasta $42.7 millones"* pero no ofrece ningún contexto sobre qué subsidio es, a quién aplica ni cómo acceder a él. En el mercado objetivo de Prodesa — compradores primerizos de vivienda VIS y VIP en Colombia — el subsidio es frecuentemente el factor determinante de si la compra es posible o no. Sin entender el subsidio, el usuario no puede evaluar correctamente si ese proyecto está dentro de su alcance real.

**La complejidad del sistema de subsidios colombiano.** En Colombia coexisten múltiples programas de subsidio de vivienda: *Mi Casa Ya* del gobierno nacional (aplica a VIS, requiere no ser propietario y estar vinculado al sistema de seguridad social), las Cajas de Compensación Familiar (el monto varía según la caja y la categoría del beneficiario), y el subsidio de tasa de interés de algunos bancos. Para un comprador primerizo, entender cuál aplica para él requiere investigación activa que la mayoría no está dispuesta a hacer sin una guía clara.

**El costo de la ambigüedad.** Cuando el sitio menciona "subsidio disponible" sin explicar cuál, ocurren tres rutas posibles, todas subóptimas: el usuario ignora la mención porque no la entiende y no cuenta el subsidio en su presupuesto (pierde un beneficio económico real), el usuario sobreestima el subsidio y contacta con expectativas incorrectas (lead de menor calidad para Prodesa), o el usuario sale del sitio a investigar el subsidio en Google (puede no volver). En ninguna de las tres rutas Prodesa aprovecha el potencial de conversión que el subsidio representa.

**La oportunidad que se está perdiendo.** Para el segmento VIS, el subsidio *Mi Casa Ya* puede representar hasta $42.7M — casi el 28% del precio de un apartamento de $150M. Eso es un argumento de venta poderoso. Un usuario que entiende que puede acceder a ese beneficio tiene una motivación adicional para avanzar en el proceso de compra. La página de detalle podría estar convirtiendo ese dato en un acelerador de conversión — pero para eso necesita explicarlo, no solo mencionarlo.

**Cómo evidenciarlo:** captura de la descripción del proyecto Mirla mostrando la mención del subsidio en el texto corrido, sin ningún tooltip, acordeón ni link que lleve a más información. Complementar con una captura de búsqueda en Google de "Mi Casa Ya requisitos" para ilustrar la cantidad de información que el usuario tendría que buscar por su cuenta.

---

## Observaciones sobre el proyecto Ágora (caso de estudio)

- **URL canónica:** `https://prodesa.com/proyecto-vivienda/cali/agora`
- **Redirect detectado:** `/proyecto-vivienda/agora` → `/proyecto-vivienda/cali/agora` (comportamiento correcto para SEO)
- **Meta-descripción:** *"3 torres de apartamentos en el centro de Cali, Calle 13A con Carrera 12. Con y sin acabados, subsidio disponible. Zona de alta valorización. ¡Vive o invierte!"*
- **Problema detectado en meta:** El frase *"¡Vive o invierte!"* al final es un CTA aspiracional pero no comunica información concreta. No hay precio en la meta-descripción, lo que también reduce el CTR en Google.
- **Renderizado:** Todo el contenido del body se carga via JS — no accesible en HTML estático.

---

## Notas de evaluación

- Los hallazgos H-DETALLE-01, H-DETALLE-02, H-DETALLE-05 y H-DETALLE-08 requieren validación con capturas del sitio renderizado en browser.
- H-DETALLE-03 y H-DETALLE-07 son verificables funcionalmente navegando el sitio en desktop y mobile.
- **Prioridad de captura:** H-DETALLE-02 (precio), H-DETALLE-03 (CTA) y H-DETALLE-08 (estado del proyecto) son los más críticos para el informe.

---

## Resumen de severidad — Detalle de Proyecto

| Severidad | Cantidad | IDs |
|-----------|----------|-----|
| 🔴 Crítico (3) | 1 | H-DETALLE-08 |
| 🟡 Importante (2) | 7 | H-DETALLE-01, H-DETALLE-02, H-DETALLE-03, H-DETALLE-05, H-DETALLE-06, H-DETALLE-07, H-DETALLE-09 |
| 🟢 Menor (1) | 0 | — |
| **Total** | **8** | |

*H-DETALLE-04 eliminado tras validación: todos los proyectos siguen el patrón `/proyecto-vivienda/[ciudad]/[slug]`. El redirect de Ágora es comportamiento correcto — manejo de URL antigua hacia la canónica. H-FILTROS-04 requiere la misma corrección.*

---

## Hipótesis confirmadas en Detalle de Proyecto

| Hipótesis | Hallazgos relacionados | Confirma / Refuta |
|-----------|------------------------|-------------------|
| [[H3A]] — Arquitectura de información | H-DETALLE-07 | ✅ Confirma parcialmente: pérdida de estado de filtros al navegar. H-DETALLE-04 eliminado — URLs son consistentes. |
| [[H3B]] — CTAs ambiguos | H-DETALLE-03, H-DETALLE-01 | ✅ Confirma fuertemente: CTA ambiguo y jerarquía visual sin foco claro |
| [[H3C]] — Experiencia mobile | H-DETALLE-02, H-DETALLE-05 | ✅ Sospecha: En mobile el precio y la ficha técnica son aún más críticos de posicionar en el primer fold |

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[04_formulario-contacto]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

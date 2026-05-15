---
tags:
  - prodesa
  - evaluacion-heuristica
  - busqueda-filtros
  - hallazgos
  - critico
aliases:
  - Hallazgos Búsqueda
  - Hallazgos Filtros
---

# 02 — Hallazgos Búsqueda y Filtros
**URLs evaluadas:**
- https://prodesa.com/proyecto-vivienda (listado general)
- https://prodesa.com/proyecto-vivienda/bogota (filtrado por ciudad)
- https://prodesa.com/proyecto-vivienda/barranquilla (filtrado por ciudad)

**Fecha:** Mayo 2026

---

## Resumen de hallazgos

| ID           | Principio                  | Página/Elemento                           | Descripción del problema                                                                                                                                                                                                                                                                                                                                                                                | Captura   | Severidad | Recomendación                                                                                                                                                                                                                                              |
| ------------ | -------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| H-FILTROS-01 | P1 - Visibilidad           | /proyecto-vivienda / Panel de filtros     | No hay **contador de resultados visible** al aplicar filtros. El usuario no sabe cuántos proyectos corresponden a su búsqueda actual ni si el filtro tuvo efecto. No hay confirmación visual de que el sistema procesó la acción.                                                                                                                                                                       | pendiente | 3         | Mostrar un contador dinámico: *"12 proyectos disponibles en Bogotá"*. Actualizar en tiempo real al cambiar cualquier filtro. Incluir un indicador de carga (spinner o skeleton) mientras los resultados se refrescan.                                      |
| H-FILTROS-02 | P2 - Mundo real            | /proyecto-vivienda / Etiquetas de filtros | Los filtros usan la nomenclatura **"VIS" y "NO VIS"** sin definición. Para un comprador primerizo, "VIS" no significa nada. El sitio no ofrece tooltips ni ayuda contextual en este punto crítico del flujo.                                                                                                                                                                                            | pendiente | 3         | Añadir tooltips o texto auxiliar en los filtros: *"VIS — Vivienda con subsidio del gobierno (precio máx. ~$150M)"*. Considerar reemplazar la etiqueta por lenguaje de beneficio orientado al usuario.                                                      |
| H-FILTROS-03 | P3 - Control del usuario + P2 - Mundo real | /proyecto-vivienda / Filtros | **Dos problemas combinados validados en sitio.** (1) **Implementación:** "Limpiar filtros" está construido como texto plano, no como `<button>`, lo que reduce affordance, área táctil en mobile y accesibilidad para lectores de pantalla. (2) **Comportamiento:** al activarlo, los filtros no se limpian — se reinician a valores default preestablecidos ($140M–$2.2B en precio, 32–235m² en área). La etiqueta dice "Limpiar" pero la acción es "Reiniciar", y esos valores default no tienen ninguna señal visual que los distinga de un filtro activo aplicado por el usuario: mismo color, mismo tamaño, sin placeholder. El usuario cree que limpió cuando en realidad sigue filtrando con un rango que no eligió conscientemente. | ✅ confirmado en código fuente y validación en sitio | 2         | (1) Reemplazar el texto por un `<button>` con semántica correcta y área táctil mínima de 44×44px. (2) Definir el comportamiento real: si la intención es reiniciar al rango completo, renombrar el control a *"Reiniciar filtros"*; si la intención es limpiar, vaciar completamente los campos. (3) Diferenciar visualmente los valores default de los valores activos: usar placeholder descriptivo (*"Cualquier precio"*, *"Cualquier área"*) cuando el filtro no ha sido configurado por el usuario. |
| ~~H-FILTROS-04~~ | ~~P4 - Consistencia~~ | ~~URLs~~ | **Eliminado tras validación en sitio.** Todos los proyectos siguen el patrón `/proyecto-vivienda/[ciudad]/[slug]`. El redirect de `/proyecto-vivienda/agora` a `/proyecto-vivienda/cali/agora` es comportamiento correcto — manejo de URL antigua hacia la canónica, no una inconsistencia. La hipótesis se basó en análisis de HTML estático y no se sostiene en el sitio renderizado. | — | — | — |
| H-FILTROS-05 | P1 - Visibilidad + P5 - Prevención de errores | /proyecto-vivienda / Resultado de filtros sin coincidencias | Al aplicar un filtro sin resultados, el sistema muestra un **empty state mal implementado**: el área de proyectos queda en blanco y aparece un texto pequeño en la esquina inferior derecha que dice *"No se encuentra información"*. El mensaje existe pero su posición y jerarquía visual lo hacen prácticamente invisible. No sigue ningún patrón de diseño de empty state: no hay ilustración, no hay mensaje orientador, y no hay CTA para limpiar filtros o ampliar la búsqueda. | ✅ confirmado visualmente | 2         | Implementar un empty state visible y centrado con: (1) mensaje claro en el área principal — *"No encontramos proyectos con estos filtros"*, (2) sugerencia de acción — *"Prueba con otra ciudad o quita el filtro de tipo de vivienda"*, y (3) CTA directo — botón *"Limpiar filtros"* o *"Ver todos los proyectos"*. El empty state debe ocupar el espacio de las tarjetas, no aparecer en un rincón de la pantalla. |
| H-FILTROS-06 | P6 - Reconocimiento + P4 - Consistencia | /proyecto-vivienda / Tarjetas de proyecto | **Corrección respecto a hipótesis inicial:** el precio sí es visible y prominente en las tarjetas ("Desde: $189.810.000"). El problema real es el **asterisco en el precio sin explicación inmediata**, cuyo significado varía entre tarjetas: algunas dicen `*Precio fijo` y otras incluyen un aviso legal extenso indicando que el precio está indexado a 85,5 SMLMV — lo que significa que el valor mostrado no es el precio definitivo. Un comprador primerizo no entiende qué va a pagar realmente. Adicionalmente, las tarjetas no muestran el **estado del proyecto** (preventa / en obra / disponible), dato crítico para la decisión de compra. | ✅ confirmado visualmente | 2 🟡 (revisado de 3 a 2 — el precio existe y es prominente; el problema es la ambigüedad del asterisco y la ausencia de estado) | Estandarizar el tratamiento del asterisco en todas las tarjetas: si el precio es referencial (indexado a SMLMV), indicarlo con un lenguaje simple — *"Precio de referencia, sujeto a cambio"* — y enlazar a una explicación. Añadir a cada tarjeta una etiqueta de estado visible: *En preventa / En obra / Disponible*. |
| H-FILTROS-07 | P4 - Consistencia + P6 - Reconocimiento | /proyecto-vivienda / Panel de filtros | **Corregido tras validación visual — la premisa inicial era incorrecta.** El sitio sí tiene filtros avanzados (precio, área, habitaciones, baños). Los problemas reales validados son tres: (1) El filtro **VIS/NO VIS/VIP solo aparece en mobile**, no en web — el usuario de desktop no puede filtrar por tipo de vivienda, que es el criterio más determinante para saber si aplica a subsidio. (2) **"Limpiar filtros" reinicia a defaults, no limpia** (ver H-FILTROS-03 para detalle de implementación y comportamiento). (3) Los **valores default del panel no se perciben como defaults**: los campos de precio y área muestran números desde que carga la página, sin placeholder, sin color diferenciado — el usuario no distingue si el sistema ya tiene un filtro aplicado o si los campos están en blanco. | ✅ validado en sitio web y mobile | 2 🟡 | (1) Incluir el filtro VIS/NO VIS/VIP en la versión web con paridad respecto a mobile — es el criterio de elegibilidad más importante para el comprador. (2) Ver recomendaciones de H-FILTROS-03 para el control "Limpiar/Reiniciar". (3) Mostrar placeholder descriptivo cuando los filtros están en estado default: *"Cualquier precio"*, *"Cualquier área"*, *"Elige habitaciones"*. |
| H-FILTROS-08 | P4 - Consistencia          | Footer / Listado de proyectos             | El **footer del sitio actúa como sitemap** con todas las ciudades y proyectos. Esto es útil para SEO, pero el listado no está sincronizado con el catálogo activo: **"Proyecto de vivienda Jilguero" aparece dos veces consecutivas** en el footer (confirmado visualmente). Para el usuario es confuso; para Google, es un link duplicado al mismo destino. La hipótesis inicial sobre Ciudad Esplendor con dos URLs distintas fue descartada tras validación en DevTools — las tres coincidencias encontradas correspondían a un `<a>` real + dos payloads de datos de Next.js, no a links distintos. | ✅ confirmado visualmente — captura footer con Jilguero duplicado | 1 🟢       | Sincronizar el footer-sitemap con la base de datos de proyectos activos para eliminar entradas duplicadas. Implementar un proceso de auditoría periódica del footer al publicar o retirar proyectos. |
| H-FILTROS-09 | P1 - Visibilidad           | /proyecto-vivienda / Estados de carga     | **Corregido tras validación en sitio.** El sistema sí tiene un spinner naranja al aplicar filtros, pero presenta dos fallas de timing y posición: (1) **el spinner no aparece de forma inmediata** — hay un gap perceptible entre el clic en "Buscar vivienda" y la aparición del indicador, dejando la interfaz sin feedback durante ese intervalo; (2) **al cargar los resultados el usuario debe hacer scroll** para verlos — el sistema no ancla la vista al área de resultados ni al inicio del listado, lo que rompe el flujo especialmente en mobile donde el panel de filtros ocupa gran parte de la pantalla. Ambos problemas se replican en web y mobile. | ✅ validado con Slow 4G en web y mobile | 2 🟡      | (1) Mostrar el spinner de forma inmediata al momento del clic, antes de que la petición al servidor confirme respuesta. (2) Al cargar los resultados, hacer scroll automático al inicio del listado o anclar el viewport al primer resultado visible. |

---

## Análisis detallado por hallazgo — ¿Por qué es importante solucionarlo?

### H-FILTROS-01 — Sin contador de resultados al filtrar

**¿Por qué es importante solucionarlo?**

Cuando el usuario aplica un filtro en `/proyecto-vivienda` — por ejemplo selecciona "Bogotá" — el sistema actualiza el listado, pero no le dice cuántos proyectos encontró. Este silencio del sistema es problemático por dos razones.

La primera es de **orientación:** el usuario no sabe si hay 2 proyectos o 20. Si hay pocos, quizás quiere ampliar la búsqueda a ciudades cercanas. Si hay muchos, quizás quiere afinar. Sin el dato, no puede tomar esa decisión de forma informada — tiene que contar las tarjetas manualmente o asumir que lo que ve es todo lo que hay.

La segunda es de **confirmación de acción:** en una SPA como la de Prodesa, el filtro es un componente React que actualiza los resultados sin recargar la página. Si no hay ninguna señal visible de que el sistema procesó la acción (ni contador, ni spinner, ni mensaje), el usuario puede interpretar la ausencia de feedback como un error. Esta confusión es especialmente frecuente en conexiones lentas donde hay un retardo entre el clic y la actualización de la lista.![[H-FILTROS-1_SIN-CONTADOR-DE-RESULTADOS-WEB.png|237]]![[H-FILTROS-1-SIN-CONTADOR-DE-RESULTADOS-MOBILE.png|155]]


### H-FILTROS-02 — Filtros "VIS / NO VIS" sin definición ni tooltip

**¿Por qué es importante solucionarlo?**

Este hallazgo es más crítico que H-HOME-04 aunque hablen del mismo vocabulario. La diferencia está en el tipo de elemento:

- En H-HOME-04, "VIS" y "VIP" aparecen como *badges informativos* sobre las tarjetas de proyecto. El usuario los ve, no los entiende, pero puede ignorarlos y seguir navegando.
- En H-FILTROS-02, "VIS" y "NO VIS" son *opciones de filtro que el usuario debe seleccionar activamente*. No puede avanzar sin tomar una decisión — y no tiene los elementos para tomarla bien.

**El problema de fondo: la decisión VIS / NO VIS no es trivial.**

En Colombia, saber si aplicas a VIS implica conocer tres cosas que la mayoría de compradores primerizos no saben: que el ingreso familiar no puede superar 4 salarios mínimos (aproximadamente $5.8M COP al mes en 2026), que no puedes ser propietario de otra vivienda en el país, y que el precio del inmueble no puede superar un tope definido por resolución del gobierno (alrededor de $150 millones COP). Adicionalmente, existen subsidios como *Mi Casa Ya* que aplican solo a proyectos VIS. Para un comprador que no conoce el sistema de subsidios colombiano — que es precisamente el segmento principal de Prodesa — elegir entre "VIS" y "NO VIS" en un filtro sin contexto es como responder una pregunta de examen cuya materia no estudió.

**Las tres consecuencias posibles, todas malas:**

Cuando el usuario enfrenta "VIS / NO VIS" sin entender los términos, hay tres rutas: la primera es que no aplique ningún filtro y vea todos los proyectos mezclados, con mayor carga cognitiva. La segunda es que elija al azar: si elige mal, ve proyectos que no le aplican o que no puede pagar, y abandona convencido de que Prodesa no tiene nada para él. La tercera es que salga del sitio a buscar en Google qué significa "VIS" — y puede que no vuelva.

**El error conceptual adicional: definir por negación.**

"NO VIS" define algo por lo que *no es*, no por lo que *es*. Para el usuario esto no comunica ningún beneficio concreto. Sería equivalente a que un menú de restaurante tuviera "No vegetariano" como categoría en lugar de "Carnes". El lenguaje orientado al usuario debería ser: *"Con subsidio del gobierno"* (VIS) vs. *"Sin tope de precio"* (NO VIS).
![[H-FILTROS-2_SIN-TOOLTIP-MOBILE-VIP.png|179]]
![[H-FILTROS-2_SIN-TOOLTIP-VIS-VIP.png|179]]
---

### H-FILTROS-03 — "Limpiar filtros": mala implementación y comportamiento engañoso

**¿Por qué es importante solucionarlo?**

Este hallazgo tiene dos capas de problema que se confirmaron en distintos momentos de la evaluación. La primera se detectó en el código; la segunda, al validar el comportamiento real en el sitio.

**Capa 1 — Implementación: texto plano en lugar de `<button>`**

La validación en el código confirmó que "Limpiar filtros" está construido como texto plano, no como un elemento `<button>`. Esta diferencia, que puede parecer técnica y menor, tiene consecuencias reales en tres dimensiones.

*Accesibilidad:* un `<button>` es reconocido automáticamente por los lectores de pantalla como un control interactivo. Un texto plano no — el usuario de lector de pantalla escuchará "Limpiar filtros" pero no sabrá que puede activarlo. Para el software, es información, no una acción disponible.

*Mobile:* WCAG 2.1 recomienda un área táctil mínima de 44×44px para controles interactivos. Un texto plano sin padding definido puede ser significativamente más pequeño, lo que en mobile obliga al usuario a varios intentos para activarlo.

*Affordance visual:* un botón con borde, fondo o sombra comunica "esto se puede presionar". Un texto plano comunica información, no acción. El usuario menos experimentado no intuirá que es clickeable — y para él, esa función no existe.

**Capa 2 — Comportamiento: "Limpiar" que no limpia**

La validación en el sitio reveló que al activar "Limpiar filtros", los campos no quedan vacíos. Quedan con los valores default del sistema: precio desde $140.948.000 hasta $2.200.000.000, área desde 32m² hasta 235m². El comportamiento real es un *reset al estado inicial*, no un *clear*. La diferencia es crítica:

- El usuario que limpió filtros asume que el sistema mostrará todos los proyectos sin ningún criterio activo.
- En realidad, el sistema sigue filtrando por el rango de precio y área preestablecido.
- Si esos defaults corresponden al rango completo del catálogo, el resultado es el mismo — pero el usuario no lo sabe. Está tomando decisiones sin entender el estado real del sistema.

El tercer problema que agrava esto: los valores default no tienen ninguna señal visual que los distinga de un filtro que el usuario configuró activamente. Mismo color, mismo tamaño tipográfico, sin placeholder. El usuario no tiene forma de saber si está viendo un campo "en blanco" o un campo "con valor aplicado".

Los dos principios violados trabajan juntos: P3 — Control del usuario exige que el usuario pueda revertir acciones con claridad; P2 — Mundo real exige que las etiquetas de la interfaz correspondan al comportamiento real del sistema. "Limpiar" no corresponde a "reiniciar a defaults".

![[H-FILTROS-3_LIMPIAR-FILTROS-CODIGO.png]]
![[H-FILTROS-3_LIMPIAR-FILTROS-MOBILE.png|236]]
![[H-FILTROS-3_LIMPIAR-FILTROS-WEB.png]]


---

### ==H-FILTROS-04 — Estructura de URLs inconsistente==

**¿Por qué es importante solucionarlo?**

La URL es la dirección de un proyecto en internet. Si esa dirección cambia de formato dependiendo del proyecto, se generan tres tipos de problemas simultáneos: uno para el usuario, uno para Google, y uno para el equipo de Prodesa.

**El problema para el usuario** es que al compartir el link de un proyecto por WhatsApp (el canal de comunicación más usado en Colombia), la URL que aparece en el chat puede ser diferente según cómo llegó al proyecto. Si llega por `/proyecto-vivienda/agora` y esa URL redirige a `/proyecto-vivienda/cali/agora`, el link que comparte puede ser el de la redirección, no el canónico. Esto genera confusión sobre si el link funciona y desconfianza en la seriedad del sitio.

**El problema para Google** es que cuando existen múltiples URLs para el mismo contenido (incluso si una es redirect de la otra), los motores de búsqueda deben decidir cuál es la "oficial". Si no están bien configuradas las etiquetas canónicas, Google puede distribuir la autoridad de SEO entre ambas URLs en lugar de concentrarla en una sola. Para Prodesa, que compite por posicionamiento en búsquedas como "apartamentos VIS en Cali", esto tiene impacto directo en el tráfico orgánico.

**El problema para el equipo de Prodesa** es de mantenimiento: cuando hay tres patrones de URL distintos para el mismo tipo de contenido (`/proyecto-vivienda/[slug]`, `/proyecto-vivienda/[ciudad]/[slug]`, y `/macroproyecto/[slug]`), cualquier cambio en la estructura requiere actualizar en múltiples lugares. Esto aumenta la probabilidad de errores y links rotos con el tiempo.

Este hallazgo ya está confirmado con evidencia desde el HTML estático: el proyecto Ágora tiene redirect de `/proyecto-vivienda/agora` a `/proyecto-vivienda/cali/agora`, y otros proyectos como Céntrico no siguen el mismo patrón. No requiere captura adicional — el código fuente es la evidencia.

**Cómo evidenciarlo:** screenshot del código fuente del footer (botón derecho → "Ver código fuente de la página" → buscar proyectos en el footer) mostrando las diferentes estructuras de URL coexistiendo. Complementar con una captura de la barra de navegación del browser mostrando el redirect al entrar al proyecto Ágora.

---

### H-FILTROS-05 — Empty state invisible al filtrar sin resultados

**¿Por qué es importante solucionarlo?**

La validación visual confirmó que el sistema sí responde cuando no hay resultados para una combinación de filtros — pero lo hace de una manera que casi nadie va a ver. El área principal de proyectos queda completamente en blanco, y en la esquina inferior derecha aparece un texto pequeño que dice *"No se encuentra información"*. El mensaje existe, pero su posición, tamaño y ausencia de contexto lo convierten en invisible para la mayoría de los usuarios.

Este hallazgo viola dos principios de Nielsen simultáneamente. El primero es **P1 — Visibilidad del estado del sistema**: el sistema tiene que informarle al usuario sobre lo que está ocurriendo, de forma visible y en el momento correcto. Un texto diminuto en un rincón de la pantalla no cumple esa función — el usuario que aplica un filtro y ve el área de proyectos vacía no sabe si el sistema está cargando, si hubo un error, o si genuinamente no hay resultados. El segundo es **P5 — Prevención de errores**: aunque en este caso el error ya ocurrió (combinación sin resultados), el sistema debería orientar activamente al usuario hacia una salida, no dejarlo varado.

**El patrón que falta: el empty state.**

Un empty state es la pantalla que aparece cuando una búsqueda no tiene resultados. Es un patrón de diseño estándar en toda aplicación moderna, y tiene tres componentes obligatorios: un mensaje claro que explique qué pasó, una sugerencia de qué puede hacer el usuario para resolverlo, y un CTA concreto (un botón de "Limpiar filtros" o "Ver todos los proyectos"). Aplicaciones como Airbnb, Booking o MercadoLibre invierten en estos estados porque saben que un usuario que llega a una pantalla sin resultados está a un mal mensaje de abandonar para siempre.

En el caso de Prodesa, el empty state debe ocupar el mismo espacio visual donde normalmente aparecen las tarjetas de proyectos. No puede ser un texto pequeño en un rincón — tiene que ser el elemento principal de la pantalla en ese momento, con jerarquía visual suficiente para que el usuario lo lea y entienda qué hacer a continuación.

El problema se amplifica por [[H-FILTROS-02]]: si el usuario ya no entiende la diferencia entre VIS y NO VIS, aplica una combinación que no da resultados, y el sistema no le explica qué pasó — ese usuario no tiene ninguna herramienta para diagnosticar qué salió mal ni cómo corregirlo.
![[H-FILTROS-5_EMPTY-STATE-INVISIBLE-WEB.png]]
![[H-FILTROS-05_ EMPTY-STATE-INVISIBLE-MOBILE.png|129]]

---

### H-FILTROS-06 — Precio con asterisco ambiguo e inconsistente entre tarjetas

**Corrección respecto a la hipótesis inicial**

La validación visual con capturas reales confirmó que el precio **sí aparece en las tarjetas** de forma prominente y en naranja ("Desde: $189.810.000"). La hipótesis inicial de que el precio estaba ausente era incorrecta. Sin embargo, la captura reveló dos problemas reales que reemplazan a la hipótesis original.

**Problema 1 — El asterisco en el precio no se explica en el momento correcto.**

Todas las tarjetas muestran el precio seguido de un asterisco (`*`). En la parte inferior de la tarjeta aparece la aclaración, pero su contenido varía entre proyectos de forma significativa:

- Proyectos VIS/Precio fijo: `*Precio fijo` — simple y claro.
- Proyectos VIP indexados a salario mínimo: `*El valor indicado es un precio de referencia. El precio definitivo del inmueble será el equivalente en pesos colombianos correspondiente a 85,5 Salarios Mínimos Legales Mensuales Vigentes del año en el cual se otorgue la escritura pública de compraventa.`

Esa segunda nota legal significa algo muy concreto y muy importante: el precio de $149.702.378 que el usuario ve en la tarjeta **no es el precio que va a pagar**. Es un cálculo basado en el salario mínimo actual, y cambiará dependiendo de cuándo se firme la escritura. Para un comprador primerizo que no conoce el sistema de precios de vivienda VIP en Colombia, esto es completamente opaco. Ve un número, lo compara con su presupuesto, toma una decisión — y esa decisión está basada en un dato que no es definitivo.

**Problema 2 — Las tarjetas no muestran el estado del proyecto.**

La captura confirma que ninguna tarjeta incluye una etiqueta de estado del proyecto (En preventa / En obra / Listo para entrega / Agotado). Este dato es crítico para la decisión de compra: un comprador que necesita mudarse en seis meses no puede comprar un proyecto en preventa con entrega en tres años. Sin ese dato en la tarjeta, el usuario tiene que entrar al detalle de cada proyecto para descubrirlo — aumentando la carga cognitiva y el tiempo hasta la decisión.

**Por qué estos dos problemas violan P6 y P4.**

P6 — Reconocimiento: la tarjeta debe mostrar toda la información que el usuario necesita para decidir si vale la pena hacer clic. Un precio con asterisco no explicado en el momento justo no cumple esa función — el usuario reconoce el número pero no entiende su significado real. P4 — Consistencia: el tratamiento del asterisco es diferente entre tarjetas (algunas dicen "precio fijo", otras tienen un aviso legal de cinco líneas). El usuario que ya revisó una tarjeta no sabe qué esperar de la siguiente.  

![[H-FILTROS-6_INCONSISTENCIA-1.png|204]]
![[H-FILTROS-6_INCONSISTENCIA-2.png|204]]

---

### H-FILTROS-07 — Inconsistencia mobile/web en filtros y defaults invisibles

La validación en web y mobile reveló tres problemas reales que reemplazan al hallazgo original.

**Problema 1 — El filtro VIS/NO VIS/VIP solo existe en mobile.**

En la versión mobile del sitio, el panel de filtros incluye la opción de filtrar por tipo de vivienda: VIS, NO VIS, VIP. En la versión web, ese filtro no aparece. Esta asimetría es especialmente grave porque el tipo de vivienda es el criterio más determinante en la decisión de compra — define si el usuario aplica a subsidio, qué rango de precio le corresponde, y qué proyectos son relevantes para su situación.

El usuario que investiga en desktop — que típicamente es el mismo usuario que está en una etapa de decisión más madura, con más tiempo para comparar opciones — no tiene acceso a ese filtro. Tiene que revisar manualmente cada proyecto para saber si es VIS o NO VIS. En un catálogo de 29 proyectos, eso es inmanejable.

La paridad entre versiones no es opcional en un flujo de conversión: si una función existe en mobile, debe existir en web. Lo contrario es una inconsistencia que viola P4 y genera experiencias radicalmente diferentes según el dispositivo del usuario.

**Problema 2 — Los valores default no se perciben como default.**

Los campos de precio y área del panel muestran números desde que carga la página: $140.948.000 hasta $2.200.000.000 en precio, 32m² hasta 235m² en área. Esos valores representan el rango completo del catálogo — son defaults, no filtros aplicados. Pero nada en la interfaz lo indica: mismo color que un filtro activo, mismo tamaño tipográfico, sin placeholder, sin etiqueta de "rango completo".

El efecto concreto: el usuario que entra al panel de filtros no sabe si ya hay criterios de búsqueda activos o si el sistema está en blanco. Antes de configurar cualquier filtro, tiene que interpretar si esos números son suyos o del sistema. Esa ambigüedad genera fricción innecesaria en el primer paso del flujo de búsqueda.

**Problema 3 — Conexión con H-FILTROS-03.**

El comportamiento de "Limpiar filtros" (reset a defaults, no clear) agrava estos dos problemas: si los defaults ya son invisibles como tales, y "Limpiar" vuelve a esos defaults sin señalarlo, el usuario que activa "Limpiar" no sabe en qué estado quedó el sistema. Ver análisis completo en [[H-FILTROS-03]].
![[H-FILTROS-7_INCONSISTENCIA-MOBILE.png|164]]
![[H-FILTROS-7_INCONSISTENCIA-FILTRO-WEB.png]]

---

### H-FILTROS-08 — Footer-sitemap con proyectos duplicados


**¿Por qué es importante solucionarlo?**

El footer de Prodesa funciona como un sitemap visual: lista todas las ciudades y proyectos activos con sus respectivos links. Es una práctica válida y con valor para SEO — Google rastrea esos links y los usa para descubrir y clasificar páginas. El problema es que ese listado no está sincronizado con el catálogo real: "Proyecto de vivienda Jilguero" aparece dos veces consecutivas en el footer, con el mismo nombre y el mismo link.

Para el usuario que navega visualmente el impacto es bajo — el footer es una lista larga que pocos leen completa, y ver Jilguero dos veces genera extrañeza más que bloqueo. Para Google el impacto es más concreto: dos links al mismo destino desde la misma página no suman autoridad, la distribuyen. Y en un footer que Google rastrea en cada visita al sitio, ese link duplicado se propaga a nivel de todo el dominio.

El problema de fondo no es solo Jilguero — es que el footer no tiene un mecanismo de sincronización con la base de datos de proyectos. Cada vez que Prodesa publica, pausa o retira un proyecto, alguien tiene que actualizar el footer manualmente. Con 29 proyectos activos en 16 ciudades, esa operación manual es propensa a errores: entradas duplicadas, proyectos ya entregados que siguen apareciendo, o proyectos nuevos que tardan en sumarse.

![[H-FILTROS-8_DUPLICADO JILGUERO.png]]

---

### H-FILTROS-09 — Spinner de carga con timing incorrecto y sin anclaje de resultados

**Corrección respecto a la hipótesis inicial**

La validación con Slow 4G en DevTools confirmó que el sistema sí tiene un spinner naranja al aplicar filtros — la hipótesis original de "sin indicador de carga" era incorrecta. Sin embargo, la validación reveló dos problemas reales en el comportamiento de ese spinner que justifican mantener el hallazgo.

**Problema 1 — El spinner aparece tarde, no inmediato.**

Cuando el usuario hace clic en "Buscar vivienda", hay un gap perceptible antes de que aparezca el spinner. Durante ese intervalo, la interfaz no da ninguna señal de que la acción fue registrada: el botón no cambia de estado, el área de resultados no reacciona, nada se mueve. Solo después de ese delay aparece el indicador naranja.

Este gap es el momento más crítico del flujo de feedback. El principio de visibilidad del sistema (P1) exige que la respuesta sea inmediata — no cuando el servidor responde, sino cuando el usuario actúa. El estándar de la industria es mostrar el estado de carga en menos de 100ms desde el clic, antes incluso de que la petición al servidor confirme que fue recibida. Un spinner que aparece tarde equivale funcionalmente a un spinner que no existe durante ese intervalo, porque el usuario ya tomó la decisión de hacer clic de nuevo o asumir que algo falló.

En conexiones lentas — el escenario más común en el mercado colombiano de mobile con Android — ese gap se extiende, haciendo el problema más pronunciado.

**Problema 2 — Al cargar los resultados, el usuario debe hacer scroll para verlos.**

Cuando el spinner desaparece y los resultados cargan, el viewport permanece en la posición del panel de filtros. El usuario tiene que hacer scroll manualmente hacia abajo para ver las tarjetas de proyectos. Esto ocurre tanto en web como en mobile.

En mobile el impacto es mayor: el panel de filtros ocupa una porción significativa de la pantalla, y al no haber un desplazamiento automático al área de resultados, el usuario puede no saber inmediatamente que los resultados ya cargaron — especialmente si el spinner desapareció fuera de su campo visual. La secuencia correcta sería: clic → spinner inmediato → resultados → scroll automático al primer resultado. Lo que ocurre hoy es: clic → gap → spinner tardío → resultados → scroll manual del usuario.
![[H-FILTRO-9-SIN-SCROLL-AUTOMATICO-WEB.png|344]]
![[H-FILTROS-9-SPINNER-WEB.png|340]]
![[H-FILTROS-9_SPINNER-MOBILE.png|136]]![[H-FILTRO-9_SIN-ESCROLL-AUTOMATICO-MOBILE.png|136]]

---

## Combinaciones de búsqueda probadas

| Combinación | URL resultante | Observación |
|-------------|----------------|-------------|
| Ciudad: Bogotá | `/proyecto-vivienda/bogota` | Estructura de URL por ciudad funciona |
| Ciudad: Barranquilla | `/proyecto-vivienda/barranquilla` | Mismo patrón |
| Tipo: VIS + No VIS | No verificable sin JS | Filtros no presentes en HTML estático |
| Rango de precio | No detectado | No se evidencia este filtro |

---

## Notas de evaluación

- Los filtros son componentes React que no son visibles en el HTML estático. La evaluación de H-FILTROS-01, H-FILTROS-03, H-FILTROS-05 y H-FILTROS-09 debe validarse con capturas del sitio renderizado.
- La estructura de URLs (patrones detectados via web_fetch y sitemap del footer) es suficiente para confirmar H-FILTROS-04 y H-FILTROS-08.
- **Pendiente:** Probar el flujo de filtros en mobile con DevTools para validar H3C.

---

## Resumen de severidad — Búsqueda y Filtros

| Severidad | Cantidad | IDs |
|-----------|----------|-----|
| 🔴 Crítico (3) | 2 | H-FILTROS-01, H-FILTROS-02 |
| 🟡 Importante (2) | 6 | H-FILTROS-03, H-FILTROS-04, H-FILTROS-05, H-FILTROS-06, H-FILTROS-07, H-FILTROS-09 |
| 🟢 Menor (1) | 1 | H-FILTROS-08 |
| **Total** | **9** | |

---

## Hipótesis confirmadas en Búsqueda y Filtros

| Hipótesis | Hallazgos relacionados | Confirma / Refuta |
|-----------|------------------------|-------------------|
| [[H3A]] — Arquitectura de información | H-FILTROS-04, H-FILTROS-08 | ✅ Confirma: Inconsistencia de URLs y falta de estructura clara en la navegación |
| [[H3B]] — CTAs ambiguos | H-FILTROS-06 | ✅ Confirma: Información insuficiente en tarjetas obliga al usuario a entrar para ver precio |
| [[H3C]] — Experiencia mobile | H-FILTROS-07, H-FILTROS-09 | ✅ Confirma: Filtro VIS/NO VIS/VIP disponible solo en mobile revela experiencias asimétricas por dispositivo; ausencia de feedback de carga crítica en mobile |

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[03_detalle-proyecto]] · [[04_formulario-contacto]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

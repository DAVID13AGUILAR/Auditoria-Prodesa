---
status: completado
created: 2026-05-20
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
- https://prodesa.com/proyecto-vivienda/bogota/pietra
- https://prodesa.com/proyecto-vivienda/bogota/orizzo
- https://prodesa.com/proyecto-vivienda/bogota/mirla
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
| H-DETALLE-06 | P4 - Consistencia | Múltiples proyectos / Diseño — validado en Pietra vs. Orizzo | Prodesa tiene más de 15 proyectos activos. La comparación directa entre **Pietra** y **Orizzo** evidencia 6 inconsistencias concretas: (1) **Galería**: Orizzo ofrece 5 fotos + Recorrido 360° + Avances de obra + Ubicación + Maqueta; Pietra ofrece solo 2 fotos + Urbanismo. (2) **Brochure**: Pietra no permite descargar brochure; Orizzo sí. (3) **Lista de incluidos**: Pietra no tiene la lista de lo que incluye el apartamento; Orizzo sí. (4) **Mapa**: Pietra da dos opciones de navegación (llegar a zona de ventas + llegar al proyecto); Orizzo da solo una (llegar a la sala de ventas). (5) **CTAs de contacto**: Pietra ofrece únicamente "Agendar tu cita en sala"; Orizzo ofrece 3 opciones de contacto. (6) **Proyectos similares**: Orizzo muestra sección de proyectos similares al final; Pietra no la tiene. El usuario que compara ambos proyectos encuentra interfaces estructuralmente distintas y debe "reaprender" la página en cada proyecto. | ✅ validado en Pietra y Orizzo | 2 🟡 | Definir y aplicar una plantilla única de página de proyecto con secciones obligatorias: galería con tabs estandarizados, descarga de brochure, lista de incluidos, mapa con ambas opciones de navegación, mínimo 2 CTAs de contacto, y sección de proyectos similares. Todos los proyectos deben seguir exactamente el mismo layout. |
| H-DETALLE-07 | P3 - Control del usuario | Detalle proyecto / Navegación de regreso | En el flujo homepage → listado → detalle, el usuario debe poder **regresar al listado manteniendo sus filtros activos**. Si al volver al listado los filtros se pierden, el usuario tiene que reconfigurar su búsqueda desde cero, lo que genera frustración y abandono. | ✅ validado con capturas antes/después de navegar al detalle | 2 🟡 | Implementar navegación "breadcrumb + back" que preserve el estado de los filtros al regresar al listado. Usar parámetros en la URL para persistir el estado de la búsqueda. |
| H-DETALLE-08 | P1 - Visibilidad | Detalle proyecto / Estado del proyecto | No se detecta en los metadatos o en la estructura del HTML un campo visible de **estado del proyecto** (En preventa / En construcción / Listo para entrega / Agotado). Para el comprador, esta es información crítica que afecta directamente la decisión. | ✅ validado en hero del proyecto — sin chip de estado visible | 3 🔴 | Mostrar el estado del proyecto de forma prominente y visible (ej. chip de color: 🟢 Disponible / 🟡 Últimas unidades / 🔴 Agotado) en el hero de la página y en la tarjeta del listado. |
| H-DETALLE-09 | P10 - Ayuda y documentación | Detalle proyecto / Información de subsidios | La meta-descripción menciona *"subsidio disponible"* pero no ofrece contexto sobre **qué subsidio, a quién aplica, ni cómo acceder a él**. El proceso de subsidio de vivienda en Colombia es complejo (Mi Casa Ya, Caja de Compensación, etc.) y los compradores primerizos necesitan orientación en este punto. | ✅ validado en Mirla — desktop y mobile | 2 🟡 | Incluir en la página de detalle una sección o acordeón de "¿Puedo acceder al subsidio?" con criterios básicos de elegibilidad y un CTA a "Consultar con asesor". Esto también aumenta el número de leads calificados. |

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

El resultado en desktop es una barra de tres CTAs donde uno duplica algo ya visible en pantalla y otro pide más datos de los necesarios. En mobile la arquitectura es más limpia, pero el problema de "Agenda tu cita" persiste en ambas.![[assets/detalle/H-DETALLE-1_MIRLA-FALLO-JERARQUIA.png|495]]

![[assets/detalle/H-DETALLE-1_AGORA-FALLO-JERARQUIA.png|495]]
![[assets/detalle/H-DETALLE-1_FALLO-JERARQUIA-MOBILE.png|133]]

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
![[assets/detalle/H-DETALLE-2_SIN-JERARQUIA-WEB.png|205]]
![[assets/detalle/H-DETALLE-2_JERARQUIA-MOBILE.png|197]]



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
![[assets/detalle/H-DETALLE-3_CTA-MOBILE.png|184]]![[assets/detalle/H-DETALLE-3_DESCONECTADO-WEB.png|506]]

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
![[assets/detalle/H-DETALLE-5_DATOS-SCROLL-MOBILE.png|159]]
![[assets/detalle/H-DETALLE-5_FALTA-DATOS-MOBILE.png|159]]
![[assets/detalle/H-DETALLE-5_FALTAN-DATOS-WEB.png|423]]

![[assets/detalle/H-DETALLE-5_SCROLL-DATOS-WEB.png]]

---

### H-DETALLE-06 — Sin plantilla estandarizada entre proyectos — validado en Pietra vs. Orizzo

**¿Por qué es importante solucionarlo?**

Prodesa tiene más de 15 proyectos activos distribuidos en 16 ciudades. La comparación directa entre **Pietra** y **Orizzo** confirma que las páginas de proyecto no siguen una plantilla común — la experiencia varía de forma significativa entre proyectos en al menos 6 dimensiones críticas.

---

**Las 6 inconsistencias concretas detectadas (Pietra vs. Orizzo)**

**1. Galería y navegación de contenido multimedia**

Orizzo ofrece 5 opciones de navegación en la sección de galería: *Fotos (5), Recorrido 360°, Avances de obra, Ubicación, Maqueta.* Pietra ofrece únicamente 2: *Fotos (2), Urbanismo.* La brecha no es solo cuantitativa — Orizzo tiene contenido que aumenta la confianza del comprador (el recorrido 360° y los avances de obra responden preguntas que solo un asesor podría resolver de otra forma). Que Pietra no tenga ese contenido puede reflejar una limitación real del proyecto, pero la ausencia de una estructura de tabs estandarizada impide saber si el contenido falta o simplemente no fue publicado.

**2. Descarga de brochure**

Pietra no ofrece la opción de descargar el brochure del proyecto. Orizzo sí. El brochure es el primer documento que el comprador lleva para consultar con su familia o pareja — es una herramienta de cierre diferido. Su ausencia en Pietra no es neutral: el usuario que quiere documentarse antes de tomar una decisión no tiene forma de hacerlo sin contactar a un asesor, lo que introduce fricción en una etapa donde el comprador todavía está evaluando.

**3. Lista de lo que incluye el apartamento**

Orizzo incluye en su página una sección con la lista de elementos incluidos en el apartamento (acabados, equipamiento, especificaciones). Pietra no tiene esta sección. Para un comprador que compara proyectos en rango de precio similar, saber exactamente qué viene incluido es determinante — un precio aparentemente más alto puede ser más competitivo si incluye más elementos. Sin esa información visible en Pietra, el comprador no puede hacer esa comparación desde la página.

**4. Mapa — opciones de navegación**

Pietra ofrece dos destinos desde el mapa: *"Llegar a zona de ventas"* y *"Llegar al proyecto"* — diferenciando correctamente la sala de ventas del terreno o edificio en construcción. Orizzo ofrece solo una opción: *"Llegar a la sala de ventas"*. En este punto concreto, Pietra tiene mejor implementación que Orizzo. La inconsistencia sigue siendo un problema de plantilla — la opción correcta debería estar presente en todos los proyectos, no solo en algunos.

**5. CTAs de contacto**

En la sección de contacto, Pietra ofrece una única opción: *"Agendar tu cita en sala"*. Orizzo ofrece 3 opciones de contacto. Reducir los canales de contacto a uno solo en Pietra elimina opciones para usuarios con diferentes preferencias de comunicación. Un comprador que no puede o no quiere agendar una cita en sala en ese momento no tiene alternativa en Pietra — en Orizzo sí la tendría. Esta diferencia puede traducirse directamente en leads perdidos.

**6. Sección de proyectos similares**

Orizzo finaliza su página con una sección de proyectos similares, permitiendo al usuario continuar explorando el catálogo de Prodesa sin salir del sitio. Pietra no tiene esta sección. La ausencia en Pietra es una oportunidad perdida de retención: el usuario que terminó de revisar Pietra y no encontró lo que buscaba no tiene un siguiente paso sugerido — probablemente abandona el sitio en lugar de explorar otro proyecto.

---

**El problema de la inconsistencia para el usuario**

Cuando un comprador compara Pietra y Orizzo, no está comparando solo los proyectos — está comparando dos interfaces estructuralmente distintas. La información disponible en una página no existe en la otra, los CTAs son diferentes, el mapa tiene opciones distintas. Esa variabilidad obliga al usuario a invertir energía cognitiva en navegar la interfaz en lugar de en evaluar los proyectos. Esa energía cognitiva es limitada y su consumo innecesario es una de las causas más documentadas de abandono en portales inmobiliarios.

**El impacto en la confianza**

Una interfaz inconsistente comunica desorganización. Un comprador que está tomando la decisión más importante de su vida financiera necesita confiar en que la empresa a la que le va a entregar sus ahorros es ordenada y profesional. Que dos proyectos del mismo catálogo tengan experiencias tan distintas genera una señal de alarma inconsciente.

**El problema sistémico**

La ausencia de plantilla no es solo un problema de diseño — es un problema de gobernanza de contenidos. Si el equipo de marketing puede editar cada página de forma independiente sin campos ni secciones obligatorias, cada proyecto publicado nuevo puede reproducir la inconsistencia. La solución correcta es técnica: un CMS con secciones fijas, campos obligatorios y validación antes de publicar.
![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-PIETRA.png|281]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-ORIZZO.png|282]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_BROCHURE.png|281]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-BROCHURE.png|283]]
![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_DESCRIPCION.png|282]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-DESCRIPCION.png|281]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-UBICACION.png|281]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA.UBICACION.png|282]]
![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-CONTACTANOS-SIMILARES.png|281]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-CONTACTANOS.SIMILARES.png|283]]
**Presencia en versión mobile**
![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-GALERIA-MOBILE.png|95]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-MOBILE.png|96]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_CTA.png|96]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-CTA-BROCHURE.png|96]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_DETALLE-MOBILE.png|96]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-DETALLE.MOBILE.png|96]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-UBICACION.MOBILE.png|97]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-UBICACION-MOBILE.png|95]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_CONTACTANOS.MOBILE.png|95]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA_CONTACTO.MOBILE.png|95]]![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-SIMILARES.MOBILE.png|95]]

Las inconsistencias no se limitan a la versión desktop — se replican y en algunos casos se agravan en mobile. La galería y sus tabs de navegación son el primer elemento de interacción visual tras el hero en mobile; que Pietra tenga solo 2 opciones frente a las 5 de Orizzo es aún más notorio en pantalla pequeña, donde el usuario escanea el contenido disponible de forma más selectiva. La ausencia de proyectos similares en Pietra mobile elimina el único punto de salida interno que retendría al usuario dentro del sitio. Los CTAs de contacto reducidos en Pietra también impactan de forma especial en mobile: el usuario en móvil tiene preferencia por canales de baja fricción como WhatsApp o llamada directa — si Pietra solo ofrece "Agendar tu cita en sala", está desaprovechando el canal más natural del dispositivo. La inconsistencia es transversal a ambas versiones.


---

### H-DETALLE-07 — Al regresar al listado se pierden los filtros aplicados

**¿Por qué es importante solucionarlo?**

El flujo natural de un usuario que busca vivienda es: aplica filtros en el listado → entra al detalle de un proyecto → vuelve al listado → entra al siguiente proyecto que le interesó. Si al volver al listado los filtros se pierden y el sistema muestra todos los proyectos sin filtrar, el usuario tiene que reconfigurar su búsqueda desde cero en cada ciclo de comparación.

**El costo real en tiempo y fricción.** En una sesión de búsqueda típica, un comprador puede revisar entre 5 y 10 proyectos antes de tomar una decisión de contacto. Si cada vez que vuelve al listado debe reseleccionar ciudad, rango de precio, habitaciones y tipo (VIS/NO VIS), está repitiendo los mismos 4 o 5 pasos entre 5 y 10 veces. Lo que debería ser una navegación fluida entre proyectos se convierte en una tarea repetitiva y frustrante.

**El efecto de desorientación adicional.** Cuando el usuario vuelve al listado y no ve sus filtros aplicados, puede creer que algo falló — que su búsqueda personalizada desapareció. Esa sensación de pérdida de control viola directamente P3 (Control del usuario): el sistema anuló una configuración que el usuario había hecho deliberadamente, sin que el usuario lo pidiera.

**La solución técnica es estándar.** Persistir el estado de los filtros al navegar entre el listado y el detalle es un comportamiento esperado en cualquier e-commerce moderno. Se implementa pasando los parámetros de filtro en la URL (ej. `/proyecto-vivienda?ciudad=bogota&precio-max=300M`) o almacenándolos en el estado de sesión del navegador. Es una práctica tan común que su ausencia es notada inmediatamente por usuarios habituados a portales como Mercado Libre o Airbnb.

**Conexión con [[H-FILTROS-03]].** H-FILTROS-03 documenta que el botón "Limpiar filtros" ya falla por sí solo — reinicia a valores default en lugar de vaciar los campos, de forma silenciosa y sin aviso. H-DETALLE-07 es una segunda capa del mismo problema de gestión de estado: el sistema tampoco preserva los filtros al navegar entre páginas. Son dos fallas distintas del mismo componente — una se activa al limpiar manualmente, la otra al navegar al detalle y volver. Juntas, configuran un sistema de filtros que ni limpia correctamente ni recuerda lo que el usuario configuró.
![[assets/detalle/H-DETALLE-7_FILTRO..png|334]]![[assets/detalle/H-DETALLE-7_FILTRO.DEFAULT.png|334]]

---

### H-DETALLE-08 — Sin etiqueta de estado del proyecto visible

**¿Por qué es importante solucionarlo?**

Este es el segundo hallazgo más crítico de la sección. El estado del proyecto — en preventa, en construcción, listo para entrega, o agotado — es información que determina directamente si el proyecto es relevante para el comprador en este momento. Un usuario que necesita mudarse en seis meses no puede comprar un proyecto en preventa con entrega en 2027. Si esa información no está visible en la página de detalle, el usuario puede invertir tiempo y energía emocional en un proyecto que finalmente no le aplica.

**El problema de la decisión basada en información incompleta.** El proceso de compra de vivienda en Colombia involucra múltiples actores y semanas o meses de deliberación. El comprador que no sabe el estado del proyecto tiene que contactar a un asesor para hacer una pregunta que debería poder responder solo con la página. Eso es un lead de menor calidad para Prodesa (el asesor atiende una consulta básica en lugar de una consulta de cierre) y una fricción innecesaria para el usuario.

**El benchmark del sector.** Todas las constructoras con presencia digital madura muestran el estado del proyecto de forma prominente: un chip de color en el hero de la página y en la tarjeta del listado. El código de color es intuitivo: verde para disponible, amarillo para últimas unidades, rojo para agotado, azul o gris para preventa. Este patrón es tan estándar que su ausencia genera confusión — el usuario asume que si no dice nada, el proyecto está disponible, lo cual puede ser una información incorrecta.

**El impacto en la confianza y en la gestión comercial.** Un proyecto agotado que no dice que está agotado genera leads de usuarios que no van a poder comprar. Eso cuesta tiempo al equipo comercial de Prodesa y genera frustración en los usuarios que descubren la realidad después de hacer contacto. Un proyecto en preventa sin fecha de entrega visible genera expectativas incorrectas. La ausencia de estado no es neutral — es una fuente activa de malentendidos.
![[assets/detalle/H-DETALLE-8_FALTA-INFORMACION-ESTADO.png|373]]

---

### H-DETALLE-09 — "Subsidio disponible" sin contexto de tipo, requisitos ni proceso

**¿Por qué es importante solucionarlo?**

La meta-descripción de proyectos como Mirla menciona *"subsidios disponibles hasta $42.7 millones"* pero no ofrece ningún contexto sobre qué subsidio es, a quién aplica ni cómo acceder a él. En el mercado objetivo de Prodesa — compradores primerizos de vivienda VIS y VIP en Colombia — el subsidio es frecuentemente el factor determinante de si la compra es posible o no. Sin entender el subsidio, el usuario no puede evaluar correctamente si ese proyecto está dentro de su alcance real.

**La complejidad del sistema de subsidios colombiano.** En Colombia coexisten múltiples programas de subsidio de vivienda: *Mi Casa Ya* del gobierno nacional (aplica a VIS, requiere no ser propietario y estar vinculado al sistema de seguridad social), las Cajas de Compensación Familiar (el monto varía según la caja y la categoría del beneficiario), y el subsidio de tasa de interés de algunos bancos. Para un comprador primerizo, entender cuál aplica para él requiere investigación activa que la mayoría no está dispuesta a hacer sin una guía clara.

**El costo de la ambigüedad.** Cuando el sitio menciona "subsidio disponible" sin explicar cuál, ocurren tres rutas posibles, todas subóptimas: el usuario ignora la mención porque no la entiende y no cuenta el subsidio en su presupuesto (pierde un beneficio económico real), el usuario sobreestima el subsidio y contacta con expectativas incorrectas (lead de menor calidad para Prodesa), o el usuario sale del sitio a investigar el subsidio en Google (puede no volver). En ninguna de las tres rutas Prodesa aprovecha el potencial de conversión que el subsidio representa.

**La oportunidad que se está perdiendo.** Para el segmento VIS, el subsidio *Mi Casa Ya* puede representar hasta $42.7M — casi el 28% del precio de un apartamento de $150M. Eso es un argumento de venta poderoso. Un usuario que entiende que puede acceder a ese beneficio tiene una motivación adicional para avanzar en el proceso de compra. La página de detalle podría estar convirtiendo ese dato en un acelerador de conversión — pero para eso necesita explicarlo, no solo mencionarlo.

**Dónde debe ir la información del subsidio según versión**

La solución correcta es diferente en desktop y en mobile porque los patrones de interacción son distintos en cada dispositivo.

*En desktop — tooltip al lado del precio en el hero:*
El usuario en desktop está procesando los números financieros en el hero (precio y área). El subsidio es un número que reduce directamente lo que tiene que pagar, así que su lugar natural es justo debajo del precio, con un ícono `ⓘ` que al pasar el cursor despliega la información:

```
Desde $150.000.000
Subsidio Mi Casa Ya: hasta $42.7M  ⓘ
```

El tooltip muestra en una línea: qué subsidio es, el monto y un link a "Ver requisitos". El hover es el patrón de baja fricción correcto para desktop — no interrumpe el flujo de lectura y está disponible cuando el usuario lo necesita.

*En mobile — acordeón después de "Acerca del proyecto":*
En mobile no existe el hover, por lo que un tooltip no funciona. El patrón correcto es un acordeón ubicado justo después de la sección "Acerca del proyecto" y antes de "Inmuebles disponibles". El usuario que terminó de leer la descripción del proyecto ya sabe qué es — la siguiente pregunta natural es *"¿puedo pagarlo con subsidio?"*. El acordeón responde esa pregunta en el momento exacto en que surge:

```
¿Puedes acceder al subsidio?  ▼
  → Tipo: Mi Casa Ya (gobierno nacional)
  → Monto: hasta $42.7M
  → Requisitos básicos: no ser propietario,
    estar vinculado al sistema de salud/pensión
  → [Consultar con un asesor si califico]
```

El acordeón además captura un CTA de conversión en el momento de mayor intención — cuando el usuario ya entendió el beneficio y quiere saber si aplica para él.
![[assets/detalle/H-DETALLE-9_SIN-TOOLTIP-WEB.png|520]]![[Pasted image 20260519020946.png|135]]


---

## Observaciones sobre el proyecto Ágora (caso de estudio)

- **URL canónica:** `https://prodesa.com/proyecto-vivienda/cali/agora`
- **Redirect detectado:** `/proyecto-vivienda/agora` → `/proyecto-vivienda/cali/agora` (comportamiento correcto para SEO)
- **Meta-descripción:** *"3 torres de apartamentos en el centro de Cali, Calle 13A con Carrera 12. Con y sin acabados, subsidio disponible. Zona de alta valorización. ¡Vive o invierte!"*
- **Problema detectado en meta:** El frase *"¡Vive o invierte!"* al final es un CTA aspiracional pero no comunica información concreta. No hay precio en la meta-descripción, lo que también reduce el CTR en Google.
- **Renderizado:** Todo el contenido del body se carga via JS — no accesible en HTML estático.

---

## Notas de evaluación

- Todos los hallazgos han sido validados con capturas del sitio renderizado en browser — desktop y mobile.
- Proyectos validados: Ágora, Mirla, Céntrico, Pietra, Orizzo.
- H-DETALLE-06 validado con comparación side-by-side Pietra vs. Orizzo en desktop y mobile.
- H-DETALLE-07 validado con capturas del estado del listado antes y después de navegar al detalle.
- H-DETALLE-08 validado con captura del hero mostrando ausencia de chip de estado.
- H-DETALLE-09 validado con captura del hero de Mirla mostrando ausencia de información del subsidio junto al precio.

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

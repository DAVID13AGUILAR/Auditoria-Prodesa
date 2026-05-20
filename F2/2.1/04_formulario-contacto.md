---
tags:
  - prodesa
  - evaluacion-heuristica
  - formulario-contacto
  - hallazgos
  - critico
aliases:
  - Hallazgos Formulario
  - Hallazgos Contacto
---

# 04 — Hallazgos Formulario de Contacto
**URL evaluada:** https://prodesa.com/contactanos
**Formulario en detalle de proyecto:** disponible en cada `/proyecto-vivienda/[ciudad]/[slug]`
**Fecha:** Mayo 2026


---

## Resumen de hallazgos

| ID        | Principio                    | Página/Elemento                                  | Descripción del problema                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Captura                         | Severidad                                                                                               | Recomendación                                                                                                                                                                                                                                                                   |
| --------- | ---------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| H-FORM-01 | P1 - Visibilidad             | /contactanos / Confirmación post-envío           | **Corregido tras validación visual.** La confirmación sí existe — el sistema muestra una pantalla con fondo de imagen de vivienda. Sin embargo, la implementación tiene tres problemas concretos: (1) **Exposición de datos personales**: el mensaje dice *"¡Gracias usuario@ejemplo.com por contactarnos!"* — muestra el correo electrónico del usuario en texto visible, lo cual es un problema de privacidad. (2) **Sin próximo paso**: no indica por qué canal lo contactarán, en cuánto tiempo ni qué esperar — el usuario queda varado. (3) **Sin CTA de respaldo**: no hay botón de WhatsApp ni ninguna acción disponible para el usuario que quiere contacto inmediato. | ✅ validado — captura post-envío | 2 🟡 (revisado de 3 a 2 — la confirmación existe; el problema es su contenido y la exposición de datos) | (1) Reemplazar el correo visible por el nombre del usuario: *"¡Gracias [Nombre] por contactarnos!"*. (2) Añadir mensaje de próximo paso: *"Un asesor te contactará en máximo 24 horas hábiles."* (3) Añadir CTA de respaldo: botón de WhatsApp directo para contacto inmediato. |
| H-FORM-02 | P2 - Mundo real + P8 - Minimalismo | /contactanos / Campos del formulario | **Corregido tras validación visual.** Los labels son mayormente comprensibles, pero el problema real es más grave: el formulario solicita **6 campos obligatorios** para el primer contacto — Nombre, Apellido, Tipo de Documento, Nro de Documento, Teléfono y Correo Electrónico. Pedir tipo y número de documento de identidad en una solicitud de interés inicial genera desconfianza y es innecesario en este punto del funnel. Adicionalmente, "Nro De Documento" usa abreviatura informal y capitalización inconsistente en todos los labels ("Tipo De Documento", "Número De Teléfono"). **En mobile:** los mismos 6 campos en teclado táctil elevan la fricción significativamente, especialmente al digitar el número de cédula. | ✅ validado — desktop y mobile | 2 🟡 | Reducir el formulario de primer contacto a 3 campos: Nombre, Teléfono y ciudad o proyecto de interés. El documento de identidad solo debe solicitarse en etapas avanzadas (separación, promesa de compra). Corregir capitalización: "Tipo de documento", "Número de teléfono". |
| H-FORM-03 | P5 - Prevención de errores | /contactanos / Validación del formulario | **Confirmado tras validación visual.** La validación es 100% post-submit — ningún error aparece mientras el usuario llena los campos, solo al dar "Enviar". Se identificaron dos fallas adicionales: (1) **El teléfono inválido no genera error propio**: se ingresó "+57 5464326" (número inválido — 7 dígitos, no empieza por 3) y el sistema no lo rechaza ni lo señala — el formulario pasa ese número al CRM sin validación de formato colombiano, generando leads con números incontactables. (2) **En web, los errores post-submit obligan a hacer scroll**: al aparecer, el formulario se extiende fuera del viewport y el usuario debe desplazarse para ver y corregir todos los campos. **En mobile:** los errores son visibles sin scroll — mejor comportamiento que web en este punto específico. | ✅ validado — desktop y mobile | 3 🔴 | (1) Implementar validación inline `onBlur` en todos los campos. (2) Añadir validación de formato colombiano para teléfono: 10 dígitos, inicio con 3. Un número que no cumpla este formato debe bloquearse antes del envío. (3) En web, anclar el scroll al primer campo con error tras el submit. |
| H-FORM-04 | P9 - Recuperación de errores | /contactanos / Mensajes de error | **Confirmado con las mismas capturas de H-FORM-03.** El mensaje de error real es: *"RELLENA ESTE CAMPO OBLIGATORIO."* — idéntico para todos los campos, en mayúsculas, sin orientación de qué corregir ni cómo. Dos problemas: (1) **Genérico**: el mismo mensaje aparece bajo Nombre, Teléfono, Documento y Correo — no diferencia entre un campo vacío y un campo con formato incorrecto. (2) **Todo en mayúsculas**: en UX, las mayúsculas se asocian a énfasis agresivo — el tono es de advertencia severa cuando debería ser de guía amable. El teléfono inválido además no recibe ningún mensaje propio (ver H-FORM-03). | ✅ validado — mismas capturas de H-FORM-03 | 2 🟡 | Reemplazar "RELLENA ESTE CAMPO OBLIGATORIO." por mensajes en minúsculas, específicos por campo: campo vacío → *"Ingresa tu nombre"*; teléfono inválido → *"Ingresa un celular colombiano de 10 dígitos, ej: 3001234567"*; correo inválido → *"Ingresa un correo válido, ej: nombre@correo.com"*. |
| H-FORM-05 | P2 - Mundo real + P4 - Consistencia | /contactanos / Información de contacto en footer | El footer del sitio muestra **cuatro números de teléfono distintos**: Bogotá (+573241000060), Caribe (+573241000060), Servicio al cliente (+573241000060) y Línea comercial (+573241000055). Tres de los cuatro tienen el mismo número, pero el usuario no puede distinguir a cuál llamar según su necesidad. La diferenciación entre "Servicio al cliente" y "Línea comercial" no es intuitiva para alguien que quiere comprar. Es el cuarto ejemplo del mismo patrón de gobernanza de contenidos junto a H-HOME-05, H-HOME-10 y H-FILTROS-08. | ✅ validado — capturas web y mobile del footer | 2 🟡 | Simplificar a dos números claramente etiquetados: *"Quiero conocer un proyecto: [número]"* y *"Ya soy cliente: [número]"*. Añadir horario de atención visible. Añadir enlace directo a WhatsApp Business. |
| H-FORM-06 | P3 - Control del usuario + P4 - Consistencia | /contactanos / Canales de contacto | **Corregido y ampliado tras validación.** La página `/contactanos` SÍ ofrece tres canales: WhatsApp directo, "Agenda tu cita en sala" (Teams) y "Asesoría inmediata" (callback). Sin embargo, la implementación tiene tres problemas: (1) **CTA engañoso**: "Agenda tu cita en sala" lleva a una reunión virtual por Microsoft Teams — el nombre promete visita física, el destino es una videollamada. (2) **reCAPTCHA en "Asesoría inmediata"**: el formulario de callback tiene reCAPTCHA visible, que puede reducir conversiones hasta un 40% (Stanford) — contradice directamente la promesa de "inmediata". (3) **Formularios inconsistentes**: el formulario del proyecto pide 6 campos incluyendo cédula; el formulario de callback pide 4 sin cédula — sin razón aparente. **El formulario embebido en el proyecto** sigue sin ofrecer opción de canal. | ✅ validado — capturas de /contactanos (desktop) | 2 🟡 | (1) Renombrar "Agenda tu cita en sala" a *"Agendar videollamada con asesor"*. (2) Reemplazar reCAPTCHA visible por reCAPTCHA v3 invisible. (3) Unificar campos entre formularios. (4) Añadir selector de canal en el formulario embebido del proyecto. |
| H-FORM-07 | P8 - Minimalismo | Detalle proyecto / Formulario embebido | **Corregido tras validación.** "Déjanos tus datos" no navega a `/contactanos` — hace scroll al formulario embebido en la página del proyecto. El sistema ya sabe en qué proyecto está el usuario (URL), pero no transmite ese contexto al CRM: el lead llega sin proyecto identificado. Mismo patrón de pérdida de contexto que H-DETALLE-03 y H-DETALLE-07. | ✅ validado — formulario hace scroll sin precargar proyecto | 2 🟡 | Añadir campo oculto al formulario que lea el nombre del proyecto desde la URL y lo transmita automáticamente al CRM en cada envío. |
| H-FORM-09 | P1 - Visibilidad + P4 - Consistencia | Global / WhatsApp | **Corregido tras validación.** WhatsApp SÍ existe — en la barra sticky de la página de detalle de proyecto funciona correctamente y redirige a WhatsApp. El problema real es de **cobertura parcial**: el botón de WhatsApp solo aparece dentro de cada proyecto, **no en el homepage ni en el listado** (`/proyecto-vivienda`). El CTA "Contáctanos" del homepage redirige únicamente al formulario, no a WhatsApp. Un usuario que está navegando el homepage o comparando proyectos en el listado no tiene acceso al canal de mayor conversión — solo lo encuentra si ya entró a un proyecto específico. | ✅ validado — homepage y listado sin WhatsApp, detalle con WhatsApp en sticky | 2 🟡 (revisado de 3 a 2 — WhatsApp existe en el detalle; el problema es ausencia en las etapas anteriores del funnel) | Extender el botón flotante de WhatsApp al homepage y al listado de proyectos. En el listado, el mensaje puede ser genérico: *"Hola, quiero información sobre proyectos de vivienda"*. En el homepage, igual. Solo en el detalle se contextualiza con el nombre del proyecto. |

---

## Conexiones con hallazgos de otras secciones

Antes de analizar cada hallazgo individualmente, es importante entender cómo el formulario de contacto no es un problema aislado — es el punto de llegada de fallas que vienen acumulándose desde el inicio del funnel.

| Hallazgo | Conecta con | Patrón compartido |
|----------|-------------|-------------------|
| H-FORM-09 — WhatsApp cobertura parcial | [[03_detalle-proyecto#H-DETALLE-01]], [[03_detalle-proyecto#H-DETALLE-03]] | El funnel se corta en el mismo punto: el CTA del detalle lleva a "Descargar brochure" ([[03_detalle-proyecto#H-DETALLE-03]]), WhatsApp solo existe en el detalle pero no en homepage ni listado, y si el usuario llena el formulario no sabe qué pasará ([[04_formulario-contacto#H-FORM-01]]). |
| H-FORM-07 — No precarga proyecto | [[03_detalle-proyecto#H-DETALLE-03]], [[03_detalle-proyecto#H-DETALLE-07]] | El mismo patrón de pérdida de contexto: el usuario pierde filtros al volver al listado ([[03_detalle-proyecto#H-DETALLE-07]]), el CTA está desconectado de la descripción ([[03_detalle-proyecto#H-DETALLE-03]]), y el lead llega al CRM sin proyecto identificado. |
| H-FORM-06 — Canales con implementación deficiente | [[03_detalle-proyecto#H-DETALLE-01]] | [[03_detalle-proyecto#H-DETALLE-01]] documentó que "Agenda tu cita" pide correo innecesariamente. H-FORM-06 es la misma fricción de imposición de canal — el sistema decide cómo contactar al usuario sin preguntarle. |
| H-FORM-02 — Exceso de campos | [[01_homepage#H-HOME-04]], [[02_busqueda-filtros#H-FILTROS-02]], [[03_detalle-proyecto#H-DETALLE-01]] | El lenguaje técnico del sector y el exceso de datos solicitados es un patrón que recorre todo el funnel: VIS sin definición en nav ([[01_homepage#H-HOME-04]]), en filtros ([[02_busqueda-filtros#H-FILTROS-02]]) y cédula innecesaria en formulario. |
| H-FORM-05 — Tres números iguales | [[01_homepage#H-HOME-05]], [[01_homepage#H-HOME-10]], [[02_busqueda-filtros#H-FILTROS-08]] | Cuarto ejemplo del mismo patrón de gobernanza: copyright desactualizado ([[01_homepage#H-HOME-05]]), Jilguero duplicado ([[01_homepage#H-HOME-10]]), footer inconsistente ([[02_busqueda-filtros#H-FILTROS-08]]) y tres teléfonos idénticos. |
| H-FORM-03 + H-FORM-04 — Validación y errores | [[H3C]] | Validación post-submit y mensajes en mayúsculas penalizan especialmente mobile — confirman [[H3C]] (experiencia mobile inferior). |
| H-FORM-01 — Confirmación incompleta | [[03_detalle-proyecto#H-DETALLE-03]] | [[03_detalle-proyecto#H-DETALLE-03]] bloquea el inicio de la conversión; H-FORM-01 bloquea el cierre. Dos fallas consecutivas del mismo funnel de conversión. |

---

## Análisis detallado por hallazgo — ¿Por qué es importante solucionarlo?

### H-FORM-01 — Confirmación post-envío incompleta y con exposición de datos

**Corrección respecto a la hipótesis inicial**

La validación confirmó que sí existe una pantalla de confirmación post-envío. Sin embargo, la implementación tiene tres problemas concretos que justifican mantener el hallazgo con severidad revisada a 2.

**Problema 1 — Exposición del correo electrónico del usuario.**

El mensaje de confirmación dice textualmente: *"¡Gracias usuario@ejemplo.com por contactarnos!"* — mostrando el correo electrónico completo del usuario en pantalla. Esto es un problema en dos dimensiones: de **privacidad** (el correo queda visible en la pantalla, accesible a cualquier persona que esté observando) y de **UX** (el usuario no necesita ver su propio correo confirmado — lo que necesita es saber qué pasa a continuación). La práctica correcta es usar el nombre del usuario: *"¡Gracias [Nombre] por contactarnos!"*.

**Problema 2 — Sin información sobre el próximo paso.**

La confirmación no dice nada sobre qué pasará después del envío: no indica el canal por el que lo contactarán, no da un tiempo estimado de respuesta, no establece ninguna expectativa. El usuario que ve la pantalla sabe que el formulario se envió — pero no sabe si lo llamarán hoy, mañana, por teléfono o por WhatsApp. Esa incertidumbre es el punto exacto donde el usuario empieza a considerar otras opciones.

**Problema 3 — Sin CTA de respaldo.**

La pantalla de confirmación no ofrece ninguna acción al usuario. Un comprador que envió el formulario y quiere contacto inmediato no tiene ningún botón de WhatsApp, ningún número de teléfono, ningún paso siguiente disponible. La pantalla es un callejón sin salida visual.

**El estándar del sector.** Una confirmación post-envío efectiva en real estate colombiano debe incluir: nombre del usuario (no correo), canal de respuesta ("te escribiremos por WhatsApp"), tiempo estimado ("en máximo 24 horas hábiles"), y CTA de respaldo (botón de WhatsApp directo para quien prefiere contacto inmediato). Esa confirmación no es una cortesía — es una pieza de conversión: el usuario que sabe qué esperar tiene un motivo para esperar en lugar de buscar otra constructora.

**Conexión con [[03_detalle-proyecto#H-DETALLE-03]].** [[03_detalle-proyecto#H-DETALLE-03]] documenta que la sección "Acerca del proyecto" no tiene CTA de contacto directo. H-FORM-01 cierra el patrón: el usuario que finalmente llegó al formulario y lo envió queda igualmente sin orientación sobre qué sigue. Dos fallas consecutivas del mismo flujo — la primera bloquea el inicio de la conversión, la segunda bloquea el cierre.

---

### H-FORM-02 — Formulario con exceso de campos obligatorios y datos sensibles innecesarios en primer contacto

**Problema 1 — Documento de identidad en el primer contacto.**

El formulario solicita "Tipo De Documento" y "Nro De Documento" como campos obligatorios. Para un comprador que llega por primera vez a expresar interés en un proyecto, pedir la cédula genera una pregunta inmediata: ¿por qué necesitan mi documento para que me contacte un asesor? Ese dato es sensible — es el equivalente a pedir el número de cédula en una primera cita. En el funnel de ventas, el documento de identidad pertenece a etapas de separación o promesa de compra, no a la generación del lead inicial.

**Problema 2 — Correo electrónico obligatorio en primer contacto.**

Ya documentado en [[03_detalle-proyecto#H-DETALLE-01]] en el contexto de "Agenda tu cita": pedir correo cuando el objetivo es que un asesor contacte al usuario introduce fricción innecesaria. Para una solicitud de interés, nombre y teléfono son suficientes. El correo es un dato valioso para campañas de email marketing, pero no debe ser una barrera para el primer contacto.

**Problema 3 — Capitalización inconsistente en los labels.**

Todos los labels usan mayúscula en las preposiciones: "Tipo De Documento", "Nro De Documento", "Número De Teléfono", "Dirección De Correo Electrónico". La convención estándar en español es minúscula en preposiciones: "Tipo de documento", "Número de teléfono". Es un detalle menor individualmente, pero acumulado en un formulario de 6 campos comunica falta de cuidado editorial.

**Problema 4 — Abreviatura "Nro" en lugar de "Número".**

"Nro De Documento" usa una abreviatura que no es estándar en interfaces digitales colombianas. Un comprador que no reconoce la abreviatura puede dudar sobre qué dato ingresar.

**En mobile — la fricción se multiplica.**

En la versión mobile, los mismos 6 campos obligatorios deben completarse con teclado táctil. Digitar el número de cédula en teclado virtual (típicamente 8–10 dígitos numéricos) después de ya haber digitado nombre, apellido y teléfono acumula una carga de entrada significativa. La industria establece que los formularios móviles de primer contacto no deberían superar 3 campos — cada campo adicional incrementa la tasa de abandono.

**El estándar para lead generation en real estate.**

Los formularios de alta conversión en portales inmobiliarios piden únicamente nombre y teléfono en el primer paso. Ciudad o proyecto de interés pueden añadirse como tercer campo. Todo lo demás — apellido, documento, correo — se recopila en pasos posteriores, cuando el usuario ya tiene más intención y más confianza en la empresa.
![[H-FORMULARIO-2_MOBILE.png|121]]![[H-FORMULARIO-2_WEB.png|530]]

---

### H-FORM-03 — Validación post-submit confirmada, teléfono inválido no detectado

**Confirmación tras validación visual**

La validación confirmó validación 100% post-submit. Se ingresó "+57 5464326" (número inválido) sin recibir ningún error durante el llenado — los errores aparecieron únicamente al dar "Enviar".

**Hallazgo 1 — Validación post-submit confirmada.**

Durante todo el proceso de llenado, ningún campo mostró error ni retroalimentación. El usuario puede completar los 6 campos con datos incorrectos sin recibir ninguna señal hasta el submit. Ese patrón acumula la frustración en el peor momento: cuando el usuario ya invirtió el esfuerzo de completar todo el formulario.

**Hallazgo 2 — El teléfono inválido no genera error propio.**

Se ingresó "+57 5464326" — 7 dígitos, no empieza por 3. El sistema no detectó ninguno de los dos problemas: ni el largo incorrecto ni el prefijo inválido. El número pasó al envío sin ser rechazado. Esto significa que el CRM puede recibir leads con números incontactables sin ninguna alerta — el asesor solo descubrirá el problema al intentar llamar.

**Hallazgo 3 — En web, los errores salen del viewport y obligan a hacer scroll.**

Al aparecer los errores post-submit, el formulario se extiende verticalmente. En web, los errores de los campos inferiores quedan fuera del área visible — el usuario debe hacer scroll para encontrarlos y corregirlos.

**Comportamiento diferenciado en mobile — punto a favor.**

En mobile, todos los errores son visibles simultáneamente sin scroll. El formulario ocupa toda la pantalla y los mensajes aparecen bajo cada campo, permitiendo ver el estado completo de una vez. Es el único punto donde mobile supera a web en este hallazgo.

**Conexión con [[04_formulario-contacto#H-FORM-04 — Mensajes de error en mayúsculas, genéricos e idénticos para todos los campos|H-FORM-04]].**

Los mensajes que aparecen son "RELLENA ESTE CAMPO OBLIGATORIO." — todo en mayúsculas y sin orientación de corrección. H-FORM-03 y H-FORM-04 son la misma falla vista desde ángulos distintos: H-FORM-03 es cuándo aparecen los errores, H-FORM-04 es qué dicen. La solución técnica es la misma para ambos.

**Conexión con [[H3C]].**

Aunque mobile muestra mejor el estado de errores que web en este caso específico, el problema de fondo — ninguna señal durante el llenado — afecta igual a ambas versiones y penaliza al usuario que invierte esfuerzo en teclado táctil antes de descubrir que algo está mal.
![[H-FORMULARIO-3_ERROR-MOBILE.png|133]]![[H-FORMULARIO-3_ERROR-WEB.png|550]]

---

### H-FORM-04 — Mensajes de error en mayúsculas, genéricos e idénticos para todos los campos

**Confirmación con capturas de H-FORM-03**

Las capturas del flujo de error de H-FORM-03 revelan el mensaje exacto que usa el sistema: **"RELLENA ESTE CAMPO OBLIGATORIO."** — en mayúsculas, con punto final, idéntico bajo todos los campos del formulario.

**Problema 1 — Todo en mayúsculas.**

En UX, escribir en mayúsculas equivale a gritar. Un mensaje de error en un formulario de compra de vivienda debería guiar al usuario, no reprimendarlo. "RELLENA ESTE CAMPO OBLIGATORIO." comunica urgencia agresiva donde debería haber orientación amable. El tono correcto es minúscula y conversacional: *"Ingresa tu nombre para continuar."*

**Problema 2 — El mismo mensaje para todos los campos.**

El mensaje es idéntico bajo Nombre, Apellido, Tipo de Documento, Nro de Documento y Correo Electrónico. El sistema no diferencia entre un campo vacío y un campo con formato incorrecto, ni entre datos de distinta naturaleza. Un usuario que ve cinco líneas rojas con el mismo texto no recibe ninguna señal de qué es diferente entre un campo y otro ni cómo corregir cada uno específicamente.

**Problema 3 — El teléfono inválido no recibe ningún mensaje.**

Como se documentó en H-FORM-03, el campo de teléfono con "+57 5464326" no genera ningún error propio — ni genérico ni específico. El sistema acepta el número sin validar. Esto agrava H-FORM-04: no solo los mensajes existentes son insuficientes, sino que hay un campo crítico que no tiene ningún mensaje en absoluto.

**El estándar correcto por campo:**

| Campo | Mensaje actual | Mensaje correcto |
|-------|---------------|-----------------|
| Nombre vacío | RELLENA ESTE CAMPO OBLIGATORIO. | *"Ingresa tu nombre"* |
| Teléfono inválido | *(sin mensaje)* | *"Ingresa un celular colombiano de 10 dígitos, ej: 3001234567"* |
| Correo inválido | RELLENA ESTE CAMPO OBLIGATORIO. | *"Ingresa un correo válido, ej: nombre@correo.com"* |
| Documento vacío | RELLENA ESTE CAMPO OBLIGATORIO. | *"Selecciona tu tipo de documento"* |

---

### H-FORM-05 — Tres líneas de contacto con el mismo número en el footer

**¿Por qué es importante solucionarlo?**

El footer del sitio muestra cuatro líneas de contacto: Bogotá, Caribe, Servicio al cliente y Línea comercial. Tres de los cuatro tienen el mismo número (+573241000060). Para el usuario que decide llamar en lugar de usar el formulario o WhatsApp, esa presentación genera una pregunta inmediata: ¿estoy viendo el número correcto o hay un error en la página?

**El patrón de gobernanza de contenidos.** Este es el cuarto ejemplo del mismo problema sistémico de mantenimiento de contenidos: el copyright desactualizado ([[01_homepage#H-HOME-05]]), el proyecto Jilguero duplicado en el footer ([[01_homepage#H-HOME-10]]) y las inconsistencias de footer ya registradas en [[02_busqueda-filtros#H-FILTROS-08]]. Todos apuntan a la misma raíz: el contenido del sitio no tiene un proceso de revisión periódica. Para un comprador evaluando si Prodesa es confiable, encontrar tres números idénticos con etiquetas distintas refuerza una señal negativa de desorganización.
![[H-FORMULARIO-5_MISMO-NUMERO-WEB.png|565]]![[H-FORMULARIO-5_MISMO-NUMERO-MOBILE.png|123]]


---

### H-FORM-06 — Canales de contacto existen pero con implementación deficiente

**Corrección y ampliación tras validación visual**

La validación de `/contactanos` confirmó que la página SÍ ofrece tres canales distintos: WhatsApp directo, "Agenda tu cita en sala" (Teams) y "Asesoría inmediata" (formulario callback). La estrategia de ofrecer múltiples canales es correcta — responde a perfiles distintos de compradores. El problema es la ejecución, que tiene tres fallas concretas.

**Falla 1 — "Agenda tu cita en sala" promete una visita física y entrega una videollamada.**

El botón dice *"Agenda tu cita en sala"* — el usuario entiende que agendará una visita a la sala de ventas. El destino real es un calendario de Microsoft Teams para una reunión virtual de 30 minutos. La investigación de Nielsen Norman Group es clara: *"un enlace es una promesa — si estableces la expectativa incorrecta, el usuario pierde confianza."* El usuario que quería una visita presencial llega a una interfaz de videollamada; el usuario que sí quiere una reunión virtual no sabe que esa opción existe bajo ese nombre. **La corrección es renombrar el botón:** *"Agendar videollamada con asesor"*.
![[H-FORMULARIO-6_CTA-TEAMS.png|317]]

**Falla 2 — reCAPTCHA visible en el formulario "Asesoría inmediata".**

El formulario de callback se llama *"Asesoría inmediata"* — implica rapidez y bajo esfuerzo. Sin embargo, incluye un reCAPTCHA visible que el usuario debe completar antes de enviar. La investigación de Stanford muestra que el CAPTCHA visible puede **reducir conversiones hasta un 40%**. Poner una barrera de verificación en un formulario llamado "inmediata" es una contradicción directa. La solución es reCAPTCHA v3 invisible — misma protección anti-bots, cero fricción para el usuario humano.

**Falla 3 — Formularios inconsistentes entre canales.**

El formulario del proyecto ("¿Te interesa este proyecto?") pide 6 campos incluyendo tipo y número de documento. El formulario de callback ("¡Te llamamos!") pide 4 campos sin documento. No hay razón aparente para esta diferencia — ambos sirven para capturar un lead. La inconsistencia viola la [[research/H6-patrones-pagina-detalle-proyecto|Heurística #4 de Nielsen]] y genera una pregunta incómoda: si el callback no necesita la cédula, ¿por qué el otro formulario sí la pide?

**El formulario embebido en el proyecto sigue sin ofrecer opción de canal.**

A diferencia de `/contactanos`, el formulario embebido en la página de detalle del proyecto ("¿Te interesa este proyecto?") no ofrece ninguna elección de canal — el usuario llena los datos sin poder indicar si prefiere WhatsApp, llamada o email. En Colombia, donde el 92% usa WhatsApp, esa ausencia impacta directamente la tasa de contacto efectivo.

**El estándar correcto por canal:**

| Canal | Estado actual | Estado correcto |
|-------|--------------|-----------------|
| WhatsApp | ✅ Funciona — redirige directamente | ✅ Mantener |
| "Agenda tu cita en sala" | ❌ Nombre engañoso — lleva a Teams | ✅ Renombrar: *"Agendar videollamada con asesor"* |
| "Asesoría inmediata" | ❌ reCAPTCHA visible contradice "inmediata" | ✅ reCAPTCHA v3 invisible |
| Formulario embebido del proyecto | ❌ Sin opción de canal preferido | ✅ Añadir selector: WhatsApp / Llamada / Email |
| Consistencia entre formularios | ❌ Campos diferentes sin razón | ✅ Unificar campos requeridos entre canales |

---

### H-FORM-07 — El formulario no precarga el proyecto de interés

**Corrección tras validación funcional**

Al hacer clic en "Déjanos tus datos", el sistema no navega a `/contactanos` — hace scroll hacia arriba para mostrar el formulario que ya está embebido en la página del proyecto. Esto significa que el sistema técnicamente conoce en qué proyecto está el usuario (la URL lo indica). El problema real es que **no aprovecha esa información**: el formulario muestra los mismos 6 campos genéricos sin ninguna referencia al proyecto, y el lead que llega al CRM no incluye el nombre del proyecto de forma automática.

**Por qué es importante aunque el formulario esté en la página del proyecto.**

El asesor que recibe el lead en el CRM ve nombre, teléfono y correo — pero no ve a qué proyecto corresponde a menos que el sistema lo transmita explícitamente. Si varios asesores atienden distintos proyectos, un lead sin proyecto identificado puede ser mal asignado o requiere una llamada de contexto adicional antes de la llamada de conversión.

**La conexión con [[03_detalle-proyecto#H-DETALLE-07]] y [[03_detalle-proyecto#H-DETALLE-03]].** Los tres hallazgos son manifestaciones del mismo problema de pérdida de contexto en el flujo: [[03_detalle-proyecto#H-DETALLE-07]] documenta que el usuario pierde sus filtros al volver al listado. [[03_detalle-proyecto#H-DETALLE-03]] documenta que el CTA al final de la descripción no está contextualizado con el proyecto. H-FORM-07 cierra el patrón: aunque el formulario está en la página del proyecto, no transmite ese contexto al CRM. En los tres casos, el sistema descarta información que ya tiene disponible.

**El impacto en la calidad del lead.** Un lead con proyecto precargado es un lead de mayor calidad: el asesor puede preparar la llamada con los datos del proyecto específico y la conversación empieza donde el usuario la dejó. La implementación técnica es mínima — un campo oculto que lee el nombre del proyecto desde la URL de la página y lo incluye en el envío al CRM.

**El estándar correcto por campo:**

| Campo | Estado actual | Estado correcto |
|-------|--------------|-----------------|
| Nombre | ✅ Existe | ✅ Mantener |
| Apellido | Existe | Opcional — no necesario en primer contacto |
| Tipo de Documento | Existe | ❌ Eliminar del primer contacto |
| Nro de Documento | Existe | ❌ Eliminar del primer contacto |
| Número de Teléfono | ✅ Existe | ✅ Mantener |
| Correo Electrónico | Existe | Opcional — no obligatorio en primer contacto |
| Proyecto de interés | ❌ No existe / no se transmite al CRM | ✅ Añadir campo oculto — precargado automáticamente con el nombre del proyecto desde la URL |


---

---

### H-FORM-09 — WhatsApp existe en el detalle pero está ausente en el homepage y el listado

**Corrección tras validación**

La validación confirmó que WhatsApp SÍ existe y funciona: en la barra sticky de la página de detalle de proyecto, el botón *"Escríbenos a WhatsApp"* redirige correctamente a WhatsApp. El problema no es ausencia total sino **cobertura parcial**: el canal de mayor conversión solo está disponible cuando el usuario ya entró a un proyecto específico — no antes.

**Lo que el usuario no puede hacer en el homepage ni en el listado.**

Un usuario que está en el homepage evaluando si Prodesa es la constructora correcta, o en el listado comparando proyectos, no tiene acceso a WhatsApp. El CTA *"Contáctanos"* del homepage redirige únicamente al formulario. Para ese usuario, la única opción de contacto antes de entrar a un proyecto es un formulario de 6 campos — la opción de mayor fricción, no la de menor.

El comprador colombiano que navega el listado y tiene una duda rápida (*"¿tienen proyectos en Medellín bajo $200M?"*) no tiene forma de preguntarla por WhatsApp sin antes entrar a un proyecto específico. Esa barrera hace que preguntas simples requieran un flujo innecesariamente largo.

**El patrón de cobertura:**

| Página | WhatsApp disponible |
|--------|-------------------|
| Homepage | ❌ No — solo CTA al formulario |
| Listado `/proyecto-vivienda` | ❌ No |
| Detalle del proyecto | ✅ Sí — sticky bar funciona correctamente |
| `/contactanos` | ✅ Sí — como uno de los tres canales |

**La solución:** extender el botón de WhatsApp al homepage y al listado. La funcionalidad ya existe y funciona — solo falta ampliar su cobertura a las páginas de entrada del funnel donde el usuario todavía no ha elegido un proyecto.

---

## Análisis del footer — Datos de contacto

```
Bogotá         → +573241000060
Caribe         → +573241000060  ← mismo número que Bogotá
Servicio al cliente → +573241000060  ← mismo número
Línea comercial     → +573241000055  ← único número diferente
Email: info@prodesa.com
```

**Problema:** Tres líneas apuntan al mismo número. Desde la perspectiva del usuario, ¿por qué hay tres entradas con el mismo número? Genera confusión sobre si la información es correcta o está desactualizada.

---

## Notas de evaluación

- El formulario de `/contactanos` renderiza completamente via JavaScript — no hay campos visibles en el HTML estático.
- Los hallazgos H-FORM-01, H-FORM-02, H-FORM-03 y H-FORM-04 requieren validación con el sitio renderizado en browser.
- H-FORM-05 y H-FORM-09 son verificables directamente desde el HTML estático del footer y el comportamiento del sitio.
- **Prioridad de captura:** H-FORM-01 (post-envío), H-FORM-03 (validación) y H-FORM-09 (WhatsApp) son críticos para el informe.

---

## Resumen de severidad — Formulario de Contacto

| Severidad | Cantidad | IDs |
|-----------|----------|-----|
| 🔴 Crítico (3) | 1 | H-FORM-03 |
| 🟡 Importante (2) | 7 | H-FORM-01, H-FORM-02, H-FORM-04, H-FORM-05, H-FORM-06, H-FORM-07, H-FORM-09 |
| 🟢 Menor (1) | 0 | — |
| **Total** | **8** | |

---

## Hipótesis confirmadas en Formulario de Contacto

| Hipótesis | Hallazgos relacionados | Confirma / Refuta |
|-----------|------------------------|-------------------|
| [[H3A]] — Arquitectura de información | H-FORM-07 | ✅ Confirma: falta de contexto en formularios — el formulario no transmite el proyecto al CRM |
| [[H3B]] — CTAs ambiguos | H-FORM-01, H-FORM-06, H-FORM-09 | ✅ Confirma fuertemente: No hay confirmación post-envío, no hay elección de canal, ausencia de WhatsApp |
| [[H3C]] — Experiencia mobile | H-FORM-03, H-FORM-09 | ✅ Confirma: Validación post-submit y ausencia de WhatsApp son especialmente críticos en mobile |

---

## Archivos relacionados

→ [[00_plantilla]] · [[01_homepage]] · [[02_busqueda-filtros]] · [[03_detalle-proyecto]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

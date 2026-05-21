---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - detalle-proyecto
  - hallazgos
aliases:
  - CW Detalle de proyecto
fase: "2.2"
---

# 06 — Detalle del proyecto
**Persona:** [[01_persona-valentina]] — Valentina Ríos, 32 años, Bogotá, primera compradora VIS
**URL evaluada:** https://prodesa.com/proyectos/[slug]
**Dispositivo:** Mobile (375px) · Desktop (1440px) · Modo incógnito

---

## Registro de pasos

| Paso # | Acción esperada | Q1 — ¿Sabe qué hacer? | Q2 — ¿Ve el control? | Q3 — ¿Entiende causa→efecto? | Q4 — ¿Sistema confirma progreso? | Fricción detectada | Sev. | Captura Mobile (375px) | Captura Desktop (1440px) |
|--------|-----------------|----------------------|---------------------|------------------------------|----------------------------------|--------------------|------|------------------------|--------------------------|
| 5a | Al entrar al detalle Valentina ve nombre, precio, ubicación y estado above the fold | **Sí** — entiende que debe leer la información del proyecto | **Parcial** — jerarquía visual plana: precio Y m² ambos en naranja grande con igual peso visual. Nombre del proyecto en gris sin prominencia. **Mobile:** chip redundante "Proyecto de vivienda" sobre el nombre → [[F2/2.1/05_inventario-final#H-DETALLE-01]]. **Desktop:** 4 tabs de navegación visibles (Fotografías · Urbanismo · Ubicación · Simulador) | **No** — sin chip de estado del proyecto (preventa / en construcción / entrega). **Positivo:** asterisco en mobile SÍ tiene explicación, pero en jerga técnica ("85,5 Salarios Mínimos Legales Mensuales Vigentes del año actual") — Valentina no entiende qué precio exacto pagará → [[F2/2.1/05_inventario-final#H-DETALLE-05]] | **Parcial** — CTAs visibles above the fold en ambos dispositivos (Déjanos tus datos · Agenda tu cita · Escríbenos a WhatsApp). Sin breadcrumbs: no sabe cómo volver a resultados → [[F2/2.1/05_inventario-final#H-FILTROS-02]] | 🟠 **Jerarquía visual plana:** precio y m² compiten con igual peso. 🟠 **Sin estado del proyecto.** 🟠 **Asterisco con explicación técnica en SMMLV.** 🟠 **Sin breadcrumbs:** al volver pierde filtros y posición | 🟠 | ![[Pasted image 20260520214512.png]] | ![[Pasted image 20260520214456.png]] |
| 5b | Valentina encuentra precio exacto y referencia de transporte sin contactar al vendedor | **No** — precio exacto por unidad no existe en la sección principal. Para transporte: debe hacer 5–7 scrolls para llegar al mapa y leer el texto de "Acerca del proyecto" | **Parcial** — el mapa es Google Maps interactivo y muestra puntos de interés cercanos (positivo). Requiere **5–6 scrolls en desktop y 6–7 en mobile** para llegar. La información de transporte SÍ existe pero está enterrada en el texto de "Acerca del proyecto", no es escaneable | **No** — solo existe "Desde $X" sin desglose por tipo de unidad. El precio en SMMLV del asterisco no ayuda. La info de transporte está en texto corrido — Valentina tendría que leer párrafos para encontrarla | **No** — la mención de Mi Casa Ya o subsidios, si existe, no está en la sección de precios donde Valentina la buscaría | 🟠 **Precio sin desglose por unidad.** 🟠 **Mapa a 6–7 scrolls:** información de conectividad crítica sepultada al fondo de la página. 🟠 **Transporte solo en texto de "Acerca del proyecto":** no escaneable. 🟡 **Mapa Google Maps interactivo** — punto positivo | 🟠 | ![[assets/detalle/H-DETALLE-8_FALTA-INFORMACION-ESTADO.png]] | ![[assets/detalle/H-DETALLE-5_SCROLL-DATOS-WEB.png]] |
| 5c | Valentina explora la galería de imágenes del proyecto | Parcial — debe encontrar y hacer clic en la tab "Galería" (o "Fotografías" según el proyecto). Las tabs no son inmediatamente obvias como navegación de contenido | **Sí** — tabs visibles con íconos y etiquetas. Imágenes cargan rápido. **Inconsistencia entre proyectos:** algunos tienen "Galería · Urbanismo · Videos · Recorrido 360° · Maqueta", otros "Fotografías · Urbanismo · Ubicación · Simulador" — Valentina no sabe qué encontrará en cada proyecto → [[F2/2.1/05_inventario-final#H-DETALLE-06]] | **Parcial** — las imágenes son renders y fotos del proyecto. Descripciones de imágenes existen pero demasiado pequeñas para leer. **HALLAZGO CLAVE:** el plano de la unidad SÍ muestra precio específico por tipología ($279.000.000* para 2 hab / 51,38m²) — pero está enterrado en la galería, no en la sección principal de precio | Parcial — el contenido carga bien pero la inconsistencia de tabs entre proyectos rompe el modelo mental | 🟠 **Precio por unidad existe pero está en la galería/plano, no en la sección principal.** 🟠 **Tabs inconsistentes entre proyectos** → [[F2/2.1/05_inventario-final#H-DETALLE-06]]. 🟡 Descripciones de imagen demasiado pequeñas | 🟠 | ![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-GALERIA-MOBILE.png]] | ![[Pasted image 20260520215234.png]] |
| 5d | Valentina busca planos, amenidades y fecha de entrega del proyecto | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente | pendiente — nueva captura | pendiente — nueva captura |
| 5e | Valentina busca si el proyecto aplica para subsidio Mi Casa Ya | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar con tooltip subsidio → [[F2/2.1/05_inventario-final#H-DETALLE-09]] | pendiente | pendiente — nueva captura | pendiente — nueva captura |
| 5f | Valentina compara la información del detalle con otro proyecto y detecta inconsistencias | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar | pendiente — revisar con inconsistencias entre proyectos → [[F2/2.1/05_inventario-final#H-DETALLE-06]] | pendiente | ![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-MOBILE.png]] | ![[assets/detalle/H-DETALLE-6_INCONSISTENCIA-ORIZZO.png]] |

---

→ [[00_plantilla]] · [[02_punto-entrada]] · [[03_homepage]] · [[04_busqueda-filtros]] · [[05_resultados]] · [[07_contacto]] · [[08_inventario-hallazgos]]

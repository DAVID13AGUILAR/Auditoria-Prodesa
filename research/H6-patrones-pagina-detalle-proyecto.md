---
tags:
  - research
  - ux-patterns
  - real-estate
  - detalle-proyecto
  - estandarización
  - benchmark
aliases:
  - Research H-DETALLE-06 Patrones Página de Proyecto
---

# Research: Patrones de diseño correctos para la página de detalle de proyecto inmobiliario

**Contexto:** H-DETALLE-06 — ausencia de plantilla estandarizada entre los 15+ proyectos activos de Prodesa  
**Fecha:** Mayo 2026  
**Método:** Benchmarking de portales maduros (Zillow, KB Home, Properati) + literatura UX especializada en real estate

---

## 1. La anatomía estándar validada por la industria

La investigación muestra convergencia entre los portales más maduros en un orden de secciones que responde al **proceso mental del comprador**, no a la conveniencia del desarrollador. El orden correcto es:

### BLOQUE 1 — Hero / Primer fold (sin scroll)

Es la sección más crítica. Todo lo que aquí aparece debe responder la pregunta: *"¿Este proyecto es para mí?"* El comprador no debe hacer scroll para saberlo.

| Elemento | Posición / Tratamiento |
|---|---|
| **Galería de imágenes** | Ocupa 60–70% del viewport. Expandible a pantalla completa. |
| **Nombre del proyecto (H1)** | Mayor peso tipográfico de toda la página — ancla la identidad |
| **Chip de estado** | "En preventa / En construcción / Disponible" — color coded, visible inmediatamente |
| **Precio** | Segunda jerarquía visual — debajo del nombre, no igual ni mayor |
| **Datos clave en el hero** | Habitaciones · m² · Fecha estimada de entrega |
| **CTA primario** | "Hablar con un asesor" (WhatsApp) — una sola acción dominante |
| **CTA secundario** | "Agendar visita" — visualmente subordinado |

**Referencia directa de Zillow (rediseño 2023):** Zillow reformateó sus páginas de proyecto al formato *single-scroll* con galería de fotos y 3D tours expandibles en el hero, y datos clave categorizados en secciones escaneables. El resultado fue la reducción del scroll excesivo y mayor tiempo de permanencia en página.

---

### BLOQUE 2 — Descripción del proyecto

- Texto "Acerca del proyecto"
- Finaliza con **CTA de contacto directo** (no solo "Descargar brochure") — el usuario que termina de leer ya tiene intención de acción
- En desktop: el formulario lateral debe estar alineado con este bloque

---

### BLOQUE 3 — Ficha técnica / Tipologías disponibles

- Fichas por tipo de apartamento: habitaciones, m², precio, plano de planta
- **Los planos de planta son el 2do elemento más buscado** según investigación de Zillow — el 1ro son las fotos
- Estado de disponibilidad por tipología (Disponible / Últimas unidades / Agotado)

---

### BLOQUE 4 — Galería completa

- Renders, fotos reales, video, tour virtual 360°
- Pestañas: Fotografías · Urbanismo · Áreas comunes · Ubicación

---

### BLOQUE 5 — Amenidades

- Lista con íconos, no texto corrido
- Agrupadas por categoría: seguridad, recreación, movilidad

---

### BLOQUE 6 — Mapa e información de ubicación

- Mapa interactivo
- Puntos de interés cercanos (colegios, centros comerciales, transporte)

---

### BLOQUE 7 — Subsidio y financiación *(crítico para VIS/VIP)*

- Explicación del subsidio que aplica (Mi Casa Ya, Caja de Compensación)
- Criterios de elegibilidad resumidos
- CTA: "Consultar con asesor si califico"
- Simulador de crédito hipotecario

---

### BLOQUE 8 — Formulario de contacto (cierre de la página)

- Máximo 3–4 campos en el primer paso (nombre, teléfono, ciudad de interés)
- Sin correo electrónico como campo obligatorio para el primer contacto

---

## 2. Jerarquía visual: la regla que toda la industria respeta

La investigación confirma un principio consistente en todos los portales maduros:

```
Nombre del proyecto > Precio > Área > Datos secundarios
```

El nombre del proyecto es el **ancla de identidad**. El precio es el primer filtro mental del comprador, pero ya lo procesó en el listado — en el detalle, lo que necesita confirmar es que está en el lugar correcto. El diseño debe reflejar ese orden cognitivo.

**Por qué el precio no puede dominar visualmente sobre el nombre:** Los portales que colocan el precio como elemento dominante reportan tasas más altas de abandono porque el usuario siente que la página está "vendiendo" antes de que él haya decidido si le interesa. La secuencia correcta: identidad primero, datos financieros después.

---

## 3. Patrones de CTA y barra sticky

La investigación sobre sticky CTAs y patrones de contacto establece:

- **Mobile:** barra sticky persistente con máximo 2 CTAs — uno de baja fricción (WhatsApp) y uno de media fricción (Agendar visita). El formulario completo no va en el hero mobile.
- **Desktop:** columna lateral sticky con formulario visible. Cuando el formulario ya está visible en pantalla, **eliminar** el CTA de "Déjanos tus datos" de la barra sticky — duplicar un elemento visible no agrega valor.
- **Principio universal:** máximo 2 CTAs compitiendo en cualquier punto de la página. Más de 2 reduce la tasa de conversión.
- **Formularios:** pedir solo lo mínimo en el primer contacto. Teléfono es suficiente para "Agenda tu cita" — pedir correo en ese paso introduce fricción innecesaria.

---

## 4. El problema específico de H-DETALLE-06: estandarización entre proyectos

La investigación identifica dos dimensiones del problema:

### Dimensión de diseño

Sin una plantilla estricta, cada proyecto puede mostrar el precio en un lugar diferente, la ficha técnica en otra posición, o directamente omitir campos críticos. El usuario que compara dos proyectos tiene que "reaprender" la interfaz en cada página — eso consume energía cognitiva que debería estar dedicada a evaluar los proyectos.

**Benchmark directo:** KB Home (constructora USA con múltiples proyectos) tiene una plantilla de página de proyecto estandarizada al punto de que la única diferencia entre proyectos es el contenido — el layout, el orden de secciones y los elementos del hero son idénticos. El usuario que revisó el proyecto A sabe exactamente dónde encontrar el precio, los planos y el formulario en el proyecto B.

### Dimensión de gobernanza (CMS)

La estandarización no es solo un problema de diseño — es un problema de sistema de gestión de contenidos. Si el CMS permite que el equipo de marketing edite cada proyecto de forma independiente sin campos obligatorios, cada publicación nueva puede romper la consistencia. La solución correcta es:

1. **Campos obligatorios en el CMS:** el sistema no permite publicar un proyecto si faltan: nombre, estado, precio, fecha de entrega, habitaciones, m²
2. **Layout bloqueado:** las secciones tienen orden fijo — el editor solo completa el contenido, no puede reordenar bloques
3. **Validación antes de publicar:** si un campo crítico está vacío, el sistema alerta antes de publicar

---

## 5. Lo que los portales maduros nunca omiten

Basado en la investigación, estos son los campos que **ningún portal inmobiliario maduro deja en blanco** en una página de proyecto:

| Campo | Por qué es obligatorio |
|---|---|
| Estado del proyecto | Determina si el proyecto aplica en el plan de vida del comprador |
| Fecha estimada de entrega | Crítico para decisión de compra — sin esto el lead es de menor calidad |
| Precio desde | Primer filtro mental del comprador |
| Tipologías con m² y habitaciones | Segundo filtro — encaje con la necesidad de espacio |
| Planos de planta | 2do elemento más buscado en portales inmobiliarios (Zillow) |
| Mapa de ubicación | Decisión de compra de vivienda incluye siempre el factor de ubicación |
| Estado de disponibilidad por tipología | Evita leads de proyectos agotados |

---

## Conclusión aplicada a Prodesa

El patrón correcto para Prodesa es una plantilla única con 8 bloques en orden fijo, donde el hero contiene **nombre + estado + precio + datos clave + CTA** sin necesidad de scroll. La solución no es solo rediseñar las páginas existentes — es implementar una plantilla en el CMS que haga **imposible publicar un proyecto incompleto**, garantizando que los 15+ proyectos activos tengan exactamente los mismos campos en las mismas posiciones.

---

## Fuentes

- [Real Estate Website UX Guide 2025 — Sanja Dey](https://www.sanjaydey.com/real-estate-website-design-ux-guide-2025/)
- [Zillow redesign 2023 — biggest property page update in 5 years](https://zillow.mediaroom.com/2023-10-23-Zillow-unveils-a-new-look-for-property-pages,-their-biggest-redesign-in-5-years)
- [How to Build High-Converting Real Estate Project Websites — Marketika](https://marketika.dev/insights/how-to-build-high-converting-real-estate-project-websites)
- [Real Estate App UX: Designing for High-Stakes Decisions — Onething Design](https://www.onething.design/post/real-estate-app-ux)
- [Hero Section Anatomy for UX — LogRocket](https://blog.logrocket.com/ux-design/hero-section-anatomy-ux/)
- [65+ Real Estate CTAs That Convert — Propphy](https://www.propphy.com/blog/real-estate-cta-examples-that-convert)
- [Reflection Point: Design Patterns on Zillow.com — Medium](https://medium.com/@jaron_49201/reflection-point-design-patterns-flows-on-zillow-com-c1d9576eb8f5)
- [Best Home Builder Websites — Fireart Studio](https://fireart.studio/blog/home-builder-websites-examples/)
- [Elevating Real Estate Platforms — Orizon Design / Medium](https://medium.com/orizon-design/elevating-real-estate-platforms-with-exceptional-user-experiences-56c30738a4cd)
- [Real Estate Best Practices for 2026 — Propphy](https://www.propphy.com/blog/real-estate-website-design-best-practices-2026)

---
tags:
  - prodesa
  - evaluacion-heuristica
  - arquitectura-informacion
  - H3A
  - analisis
aliases:
  - Por qué importa la AI
  - Arquitectura Información Prodesa
---

# Por qué importa mejorar la Arquitectura de Información de Prodesa
**Subcarpeta:** 2.1 / Arquitectura de Información
**Relacionado con:** [[H3A]] — Hipótesis de arquitectura de información
**Hallazgos que respaldan este análisis:** [[01_homepage]] (H-HOME-02, 03, 04, 07) · [[02_busqueda-filtros]] (H-FILTROS-03, 04, 05, 07) · [[03_detalle-proyecto]] (H-DETALLE-04, 06, 07)

---

## ¿Qué es la Arquitectura de Información?

La Arquitectura de Información (AI) es la disciplina que organiza, estructura y etiqueta el contenido de un sitio web de forma que los usuarios puedan encontrar lo que necesitan de manera eficiente e intuitiva. No es solo el menú de navegación — es la lógica completa de cómo se organiza el contenido, cómo se nombran las cosas y cómo fluye el usuario de una sección a otra.

Una AI bien diseñada responde tres preguntas que el usuario se hace de forma inconsciente cada vez que entra a un sitio:

1. **¿Dónde estoy?** — El usuario puede ubicarse dentro de la estructura del sitio en cualquier momento.
2. **¿Qué hay aquí?** — El usuario puede ver claramente qué opciones tiene disponibles desde el punto en que se encuentra.
3. **¿A dónde puedo ir?** — El usuario entiende qué camino tomar para alcanzar su objetivo.

Cuando la AI falla, el usuario experimenta desorientación, frustración y abandono — incluso si el contenido que busca existe y es relevante.

---

## El problema específico de Prodesa

### 1. El sitio tiene múltiples audiencias mezcladas sin separación clara

Prodesa atiende al menos cuatro tipos de usuario desde el mismo sitio web:

| Audiencia | Objetivo en el sitio | Peso en el tráfico estimado |
|-----------|---------------------|---------------------------|
| Comprador primerizo local | Encontrar un proyecto con subsidio que pueda pagar | Alto (~60%) |
| Comprador sin subsidio | Encontrar un proyecto No VIS por inversión o mejora de vivienda | Medio (~25%) |
| Inversionista desde el exterior | Invertir en propiedad raíz colombiana | Bajo (~5%) |
| Cliente actual de Prodesa | Acceder a portal de seguimiento de su proyecto | Bajo (~10%) |

El problema: **el sitio trata a todas estas audiencias por igual**. El menú principal mezcla "Ofertas de vivienda" (para compradores) con "Zona clientes" (para clientes actuales) con "Invertir desde el exterior" (para inversionistas) con "Contáctanos" (CTA de conversión). El resultado es una navegación que no está optimizada para ninguna audiencia en particular.

---

### 2. La taxonomía de proyectos no coincide con el modelo mental del usuario

Prodesa clasifica sus proyectos en dos categorías principales: **Macroproyectos** y **Proyectos de Vivienda**. Esta distinción tiene sentido interno (escala del desarrollo, número de torres, financiación), pero para el comprador que busca su hogar, la pregunta nunca es *"¿Quiero un macroproyecto o un proyecto?"* — la pregunta es *"¿Dónde quiero vivir?"* o *"¿Cuánto puedo pagar?"*.

El modelo mental del usuario comprador de vivienda funciona en este orden:

```
Ciudad → Presupuesto → Tipo de vivienda → Detalles del proyecto
```

La AI actual parece funcionar en este orden:

```
Tipo de proyecto (macro/individual) → Ciudad → Proyecto específico
```

Este desacople entre el modelo mental del usuario y la organización del sitio genera fricción en cada paso del flujo de búsqueda.

---

### 3. Los sistemas de orientación son inexistentes

Un sistema de orientación es el conjunto de señales visuales y estructurales que le dicen al usuario dónde está y hacia dónde puede ir. En Prodesa faltan tres componentes críticos:

**Breadcrumbs ausentes:** En un sitio con 15+ proyectos en 10+ ciudades, la ruta de navegación es esencial. Sin ella, un usuario que llega directamente a la página de un proyecto (desde Google o desde un link compartido) no puede contextualizar qué ciudad es, ni cómo ver otros proyectos similares.

**Estado activo en el menú:** No hay señal visual de en qué sección del sitio está el usuario. El ítem activo del menú no se resalta, lo que refuerza la sensación de desorientación.

**Sin "proyectos relacionados":** Al final de la página de un proyecto no hay módulo de "otros proyectos en esta ciudad" o "proyectos con precio similar". El usuario que no encuentra lo que busca en un proyecto no tiene un camino natural hacia otras opciones — debe volver al inicio y empezar desde cero.

---

### 4. La nomenclatura crea barreras de entrada

El lenguaje que usa el sitio para describir sus propios productos no está calibrado para el usuario objetivo. Los términos más problemáticos son:

**"VIS / NO VIS"** — aparecen en el título del sitio, el meta de SEO y en los filtros de búsqueda. Son términos regulatorios colombianos que significan Vivienda de Interés Social y Vivienda No VIS. Para un comprador primerizo que no conoce el sistema de subsidios, estos términos son completamente opacos. No saber si "aplica" a VIS o No VIS es una barrera que impide al usuario self-qualificarse y avanzar.

**"Macroproyecto"** — término técnico del sector constructor que el usuario no usa ni entiende como categoría de búsqueda.

**"Zona clientes" / "Zona proveedores" / "Zona administradores"** — taxonomía interna de Prodesa expuesta como navegación principal. Son portales de acceso para audiencias muy específicas que no deben competir visualmente con la navegación del comprador.

---

### 5. La estructura de URLs refleja inconsistencia en la AI

La URL es la expresión más visible de la arquitectura de información. Las inconsistencias detectadas en Prodesa muestran que la AI se fue construyendo de forma orgánica sin un sistema:

```
/proyecto-vivienda/agora          → redirige a /proyecto-vivienda/cali/agora
/proyecto-vivienda/centrico       → no tiene ciudad en la URL
/macroproyecto/[slug]             → categoría diferente al patrón /proyecto-vivienda/
/macroproyecto-vivienda/[slug]    → tercer patrón distinto para macroproyectos
```

Tres patrones diferentes para el mismo tipo de contenido (proyectos de vivienda) indica que la AI no fue diseñada desde el principio sino acumulada. Esto tiene consecuencias directas en SEO, en la capacidad de navegar con el botón "atrás" del navegador y en la experiencia al compartir links.

---

## Por qué solucionar la AI impacta directamente la conversión

La arquitectura de información no es un problema estético. Cada falla de AI tiene un costo medible en el funnel de conversión:

| Falla de AI | Punto del funnel afectado | Efecto en conversión |
|-------------|--------------------------|---------------------|
| Menú con múltiples audiencias mezcladas | Entrada al sitio | Aumenta la tasa de rebote. El usuario no sabe si esto es para él. |
| Sin filtros avanzados (precio, m², subsidio) | Exploración de proyectos | El usuario no puede llegar al proyecto correcto de forma eficiente. |
| Sin breadcrumbs ni orientación | Navegación entre proyectos | El usuario que se pierde abandona en lugar de explorar más. |
| Nomenclatura técnica (VIS/NO VIS) | Primera interacción con el sitio | Barrera de entrada para el 60% del público objetivo (compradores primerizos). |
| Sin proyectos relacionados en el detalle | Página de detalle de proyecto | El usuario que no se convierte en ese proyecto no tiene ruta hacia el siguiente. |
| URLs inconsistentes | SEO y links compartidos | Pérdida de tráfico orgánico y dificultad para compartir links específicos. |

---

## Qué se debe lograr con una AI rediseñada

Una arquitectura de información efectiva para Prodesa debe cumplir con estos objetivos:

**Para el comprador primerizo:**
- Que pueda llegar a proyectos VIS en su ciudad en máximo 2 clics desde la homepage.
- Que entienda en cada paso del funnel si el proyecto "es para él" (precio, subsidio, ubicación).
- Que nunca sienta que se "perdió" dentro del sitio.

**Para el comprador sin subsidio:**
- Que tenga una ruta diferenciada y clara hacia proyectos No VIS.
- Que pueda comparar proyectos por criterios relevantes (precio, m², ubicación).

**Para el buscador por ciudad:**
- Que desde el homepage pueda llegar directamente a "proyectos en Bogotá" o "proyectos en Barranquilla" sin pasar por filtros.
- Que la URL refleje la ciudad y el proyecto de forma legible y consistente.

**Para el usuario que regresa:**
- Que los filtros de búsqueda se preserven entre sesiones o al navegar entre páginas.
- Que haya atajos visibles para retomar donde lo dejó.

---

## Archivos relacionados

→ [[02_mapa-sitio-actual]] · [[03_mapa-sitio-propuesto]] · [[H3A]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

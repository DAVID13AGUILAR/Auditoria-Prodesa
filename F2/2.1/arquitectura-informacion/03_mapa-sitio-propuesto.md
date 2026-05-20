---
status: completado
created: 2026-05-20
tags:
  - prodesa
  - evaluacion-heuristica
  - arquitectura-informacion
  - mapa-sitio
  - to-be
  - propuesta
aliases:
  - Mapa Sitio Propuesto
  - Sitio To-Be
---

# Mapa del Sitio Propuesto — Prodesa.com (To-Be)
**Versión:** Propuesta inicial — sujeta a validación con cliente
**Basado en:** Hallazgos [[H3A]] + análisis de modelos mentales del comprador colombiano
**Objetivo:** Reducir fricción en el flujo de conversión y alinear la estructura con el modelo mental del usuario

---

## Principios que guían esta propuesta

1. **Audiencia primero:** cada sección del nav debe responder inmediatamente a la pregunta del usuario *"¿esto es para mí?"*.
2. **Ciudad como primer filtro:** el comprador colombiano piensa en ciudad antes que en tipo de proyecto.
3. **URLs limpias y predecibles:** una URL debe poder leerse en voz alta y ser autoexplicativa.
4. **Un solo sistema:** Macroproyectos y Proyectos son lo mismo para el usuario — son proyectos de vivienda. La distinción interna no debe ser visible en la navegación.
5. **Orientación permanente:** el usuario siempre debe saber dónde está y tener una salida hacia el nivel anterior.

---

## Navegación propuesta

### Barra principal (un solo nivel, orientada al comprador)

```
[Logo]   |   Proyectos ▾   |   Ciudades ▾   |   ¿Cómo comprar?   |   Contáctanos   |   [Mi cuenta ▾]
```

**Cambios clave vs. el estado actual:**
- Se elimina la doble barra. Todo en un nivel.
- "Ofertas de vivienda" → "Proyectos" (lenguaje más directo y universal).
- Se añade "Ciudades" como acceso rápido por ubicación geográfica (modelo mental del usuario).
- "¿Cómo comprar?" reemplaza la ausencia actual de orientación sobre subsidios y proceso de compra.
- "Contáctanos" se mantiene como CTA de conversión.
- "Zona clientes / Invertir / Proveedores / Administradores" se consolidan en "Mi cuenta" como menú desplegable para audiencias específicas.

### Desplegable "Proyectos"
```
Proyectos
├── Ver todos los proyectos  →  /proyectos
├── ─────────────────────────
├── Con subsidio (VIS)       →  /proyectos?tipo=vis
├── Sin tope de precio       →  /proyectos?tipo=no-vis
└── Casas campestres         →  /proyectos?tipo=casas
```

### Desplegable "Ciudades"
```
Ciudades
├── Bogotá y Sabana          →  /proyectos/bogota
├── Costa Caribe             →  /proyectos/costa-caribe
│   ├── Barranquilla
│   ├── Cartagena
│   └── Soledad
├── Eje Cafetero / Centro    →  /proyectos/ibague
└── Ver todas las ciudades   →  /proyectos#ciudades
```

### Desplegable "Mi cuenta"
```
Mi cuenta
├── Soy cliente Prodesa      →  /login
├── Soy proveedor            →  app.iproveedor.com
├── Administrador            →  prodesa.forms.capta.co
└── Invertir desde el exterior  →  /invertir
```

---

## Árbol del sitio propuesto

```
prodesa.com/
│
├── [Homepage]  /
│   └── Hero con: buscador por ciudad + tipo (VIS/No VIS) + CTA "Ver proyectos"
│
├── PROYECTOS  /proyectos
│   │   └── Listado con filtros: ciudad, tipo, precio, habitaciones, fecha entrega
│   │
│   ├── Por tipo
│   │   ├── /proyectos?tipo=vis          "Viviendas con subsidio"
│   │   └── /proyectos?tipo=no-vis       "Viviendas sin tope de precio"
│   │
│   ├── Por ciudad (URL limpia y consistente)
│   │   ├── /proyectos/bogota
│   │   ├── /proyectos/barranquilla
│   │   ├── /proyectos/cartagena
│   │   ├── /proyectos/cali
│   │   ├── /proyectos/ibague
│   │   ├── /proyectos/soacha
│   │   ├── /proyectos/mosquera
│   │   ├── /proyectos/tocancipa
│   │   ├── /proyectos/cota
│   │   ├── /proyectos/tenjo
│   │   ├── /proyectos/girardot
│   │   ├── /proyectos/villeta
│   │   ├── /proyectos/fusagasuga
│   │   ├── /proyectos/copacabana
│   │   ├── /proyectos/soledad
│   │   └── /proyectos/puerto-colombia
│   │
│   └── Detalle de proyecto (patrón único y consistente)
│       └── /proyectos/[ciudad]/[nombre-proyecto]
│           Ejemplos:
│           ├── /proyectos/cali/agora
│           ├── /proyectos/bogota/centrico
│           ├── /proyectos/soacha/balcones-de-soacha
│           └── /proyectos/barranquilla/serena-del-mar
│
├── ¿CÓMO COMPRAR?  /como-comprar
│   ├── /como-comprar/subsidio-vis       "¿Aplico al subsidio?"
│   ├── /como-comprar/proceso            "Paso a paso para comprar"
│   ├── /como-comprar/financiacion       "Opciones de financiación"
│   └── /preguntas                       "Preguntas frecuentes"
│
├── CONTÁCTANOS  /contactanos
│   └── Formulario con selector de ciudad y proyecto de interés
│
├── INVERTIR DESDE EL EXTERIOR  /invertir
│   └── Landing específica para inversionistas
│
├── NOSOTROS  /nosotros
│   ├── /nosotros/quienes-somos
│   ├── /nosotros/gobierno-corporativo
│   ├── /nosotros/sostenibilidad
│   ├── /nosotros/trabaja-con-nosotros
│   └── /nosotros/sala-de-prensa
│
├── BLOG  /blog
│
├── ZONA CLIENTES  /login
│
├── PORTALES EXTERNOS
│   ├── Proveedores   →  app.iproveedor.com
│   └── Administradores  →  prodesa.forms.capta.co
│
└── LEGALES
    ├── /politica-privacidad
    ├── /terminos-condiciones
    └── /sagrilaft   (renombrado y movido a sección interna)
```

---

## Comparativa: estructura actual vs. propuesta

| Elemento | Estado actual | Propuesta | Beneficio |
|----------|--------------|-----------|-----------|
| Barras de navegación | 2 niveles mezclados | 1 barra unificada | Menos carga cognitiva en el primer contacto |
| Segmentación de audiencias | Ninguna | "Mi cuenta" agrupa portales internos | Comprador no ve ruido que no le corresponde |
| Acceso por ciudad | Solo en footer / filtro | Menú "Ciudades" en el nav principal | Llegar a proyectos por ciudad en 1 clic |
| Acceso por subsidio | Solo con filtro (sin explicación) | Opción directa "Con subsidio" en el desplegable | El comprador primerizo encuentra su ruta inmediatamente |
| Patrón de URL | 3 patrones distintos | 1 patrón único: `/proyectos/[ciudad]/[slug]` | Consistencia, SEO mejorado, links compartibles |
| Orientación en navegación | Sin breadcrumbs, sin estado activo | Breadcrumbs en todas las páginas internas | El usuario siempre sabe dónde está |
| Guía de compra | Inexistente | Sección "¿Cómo comprar?" | Reduce la necesidad de contacto por dudas básicas |
| Términos VIS / NO VIS | Sin explicación | Renombrados como "Con subsidio" / "Sin tope" | Elimina barrera de vocabulario para compradores primerizos |
| Macroproyectos vs. Proyectos | Categorías separadas visibles | Unificados bajo "Proyectos" con filtros | El usuario no necesita saber la distinción interna |

---

## Flujos de usuario mejorados

### Flujo A — Comprador primerizo buscando subsidio en Bogotá

**Actual (con fricción):**
Homepage → no entiende VIS → busca en Google qué es VIS → vuelve → "Ofertas de vivienda" → listado sin filtro claro → revisa uno a uno los proyectos → abandona

**Propuesto (flujo limpio):**
Homepage → "Proyectos" → "Con subsidio (VIS)" → filtro ciudad: Bogotá → listado con precio visible → detalle → CTA WhatsApp

---

### Flujo B — Usuario que llega por Google a un proyecto específico

**Actual (con fricción):**
Google → `/proyecto-vivienda/agora` → redirige a `/proyecto-vivienda/cali/agora` → ve el proyecto pero no sabe dónde está en el sitio → no hay proyectos relacionados → abandona

**Propuesto (flujo limpio):**
Google → `/proyectos/cali/agora` → breadcrumb: Inicio > Proyectos > Cali > Ágora → ve el proyecto → sección "Otros proyectos en Cali" → explora más opciones

---

### Flujo C — Usuario que regresa al sitio

**Actual (con fricción):**
Regresa → aplica los mismos filtros de nuevo (se perdieron) → busca el proyecto que recordaba → no puede encontrarlo fácilmente → abandona

**Propuesto (flujo limpio):**
Regresa → filtros persistidos en URL → llega directamente al proyecto → CTA contextualizado con el canal preferido

---

## Redirects requeridos para la migración

Si se implementa esta nueva estructura, se deben crear redirects 301 para todas las URLs actuales:

| URL actual | URL propuesta |
|------------|---------------|
| `/proyecto-vivienda` | `/proyectos` |
| `/proyecto-vivienda/[slug]` | `/proyectos/[ciudad]/[slug]` |
| `/proyecto-vivienda/[ciudad]` | `/proyectos/[ciudad]` |
| `/macroproyecto/[slug]` | `/proyectos/[ciudad]/[nombre]` |
| `/macroproyecto-vivienda/[slug]` | `/proyectos/[ciudad]/[nombre]` |
| `/quienessomos` | `/nosotros/quienes-somos` |
| `/TratamientoDatosPersonales` | `/politica-privacidad` |

> **Nota:** La implementación de redirects es crítica para preservar el posicionamiento SEO actual. Prodesa tiene URLs indexadas en Google — migrar sin redirects significaría perder ese tráfico orgánico.

---

## Archivos relacionados

→ [[01_por-que-importa-la-ai]] · [[02_mapa-sitio-actual]] · [[H3A]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

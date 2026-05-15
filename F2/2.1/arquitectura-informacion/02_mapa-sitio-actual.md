---
tags:
  - prodesa
  - evaluacion-heuristica
  - arquitectura-informacion
  - mapa-sitio
  - as-is
aliases:
  - Mapa Sitio Actual
  - Sitio As-Is
---

# Mapa del Sitio Actual — Prodesa.com (As-Is)
**Relevamiento:** Mayo 2026
**Fuente:** HTML estático, footer sitemap, URLs detectadas via web_fetch
**Estado:** Basado en estructura observable — pendiente validación con renderizado completo

---

## Estructura de Navegación Actual

### Barra superior (utilidades internas)
```
Blog
Zona proveedores  →  app.iproveedor.com (dominio externo)
Zona administradores  →  prodesa.forms.capta.co (dominio externo)
```

### Barra principal (nav primary)
```
Ofertas de vivienda  →  /proyecto-vivienda
Zona clientes        →  /login
Invertir desde el exterior  →  /invertir
Contáctanos          →  /contactanos
```

### Logo (siempre disponible)
```
Logo Prodesa  →  / (homepage)
```

---

## Árbol completo del sitio

```
prodesa.com/
│
├── [Homepage]  /
│
├── PROYECTOS
│   ├── Listado general  /proyecto-vivienda
│   │
│   ├── Por ciudad
│   │   ├── /proyecto-vivienda/bogota
│   │   ├── /proyecto-vivienda/barranquilla
│   │   ├── /proyecto-vivienda/cali
│   │   ├── /proyecto-vivienda/cartagena
│   │   ├── /proyecto-vivienda/ibague
│   │   ├── /proyecto-vivienda/tocancipa
│   │   ├── /proyecto-vivienda/soacha
│   │   ├── /proyecto-vivienda/villeta
│   │   ├── /proyecto-vivienda/mosquera
│   │   ├── /proyecto-vivienda/girardot
│   │   ├── /proyecto-vivienda/puerto-colombia
│   │   ├── /proyecto-vivienda/cota
│   │   ├── /proyecto-vivienda/tenjo
│   │   ├── /proyecto-vivienda/soledad
│   │   ├── /proyecto-vivienda/fusagasuga
│   │   └── /proyecto-vivienda/copacabana
│   │
│   ├── Proyectos individuales (patrón inconsistente ⚠️)
│   │   ├── /proyecto-vivienda/avenida-colon
│   │   ├── /proyecto-vivienda/centrico
│   │   ├── /proyecto-vivienda/cali/agora          ← con ciudad
│   │   ├── /proyecto-vivienda/colibri
│   │   ├── /proyecto-vivienda/serrania-vinculo-I
│   │   ├── /proyecto-vivienda/refugio-de-las-palmas
│   │   ├── /proyecto-vivienda/brisas-san-pablo
│   │   ├── /proyecto-vivienda/alondra
│   │   ├── /proyecto-vivienda/siena
│   │   ├── /proyecto-vivienda/vesta
│   │   ├── /proyecto-vivienda/altos-madelena
│   │   ├── /proyecto-vivienda/capriella
│   │   ├── /proyecto-vivienda/balcones-sol-I
│   │   ├── /proyecto-vivienda/jilguero            ← DUPLICADO ⚠️
│   │   ├── /proyecto-vivienda/jilguero            ← DUPLICADO ⚠️
│   │   ├── /proyecto-vivienda/bermellon
│   │   ├── /proyecto-vivienda/armonia
│   │   ├── /proyecto-vivienda/escarlata
│   │   └── /proyecto-vivienda/copacabana/copacabana  ← doble slug ⚠️
│   │
│   └── Macroproyectos (patrón diferente al de proyectos ⚠️)
│       │
│       ├── Sabana de Bogotá
│       │   ├── /macroproyecto/macroproyecto-vivienda-palo-agua
│       │   ├── /macroproyecto/macroproyecto-vivienda-hacienda-alcala
│       │   └── /macroproyecto/macroproyecto-vivienda-ciudadela-foresta
│       │
│       ├── Caribe
│       │   ├── /macroproyecto/macroproyecto-vivienda-serena-mar
│       │   ├── /macroproyecto/macroproyecto-vivienda-alameda-rio
│       │   ├── /macroproyecto/macroproyecto-vivienda-san-antonio
│       │   └── /macroproyecto/macroproyecto-vivienda-ciudad-suenos
│       │
│       ├── Ibagué
│       │   └── /macroproyecto/macroproyecto-vivienda-ecociudad-riviera
│       │
│       ├── Girardot
│       │   ├── /macroproyecto-vivienda/ciudad-esplendor  ← patrón diferente ⚠️
│       │   └── /macroproyecto/macroproyecto-vivienda-ciudad-esplendor
│       │
│       └── Villeta
│           └── /macroproyecto/macroproyecto-vivienda-ciudad-cristales
│
├── NOSOTROS
│   ├── /quienessomos
│   ├── /gobierno-corporativo
│   ├── /sostenibilidad
│   └── /trabajaConNosotros
│
├── INVERTIR
│   └── /invertir
│
├── ZONA CLIENTES
│   └── /login
│
├── CONTACTO
│   └── /contactanos
│
├── CONTENIDO / BLOG
│   └── /blog
│
├── PORTALES EXTERNOS
│   ├── app.iproveedor.com  (Zona proveedores)
│   └── prodesa.forms.capta.co  (Zona administradores)
│
└── LEGALES / CORPORATIVO
    ├── /TratamientoDatosPersonales
    ├── /tyc
    └── /preguntas
```

---

## Problemas detectados en la estructura actual

### ⚠️ Inconsistencias de URL

| Patrón | Ejemplo | Problema |
|--------|---------|---------|
| `/proyecto-vivienda/[slug]` | `/proyecto-vivienda/centrico` | Estándar, sin ciudad |
| `/proyecto-vivienda/[ciudad]/[slug]` | `/proyecto-vivienda/cali/agora` | Con ciudad, solo algunos proyectos |
| `/proyecto-vivienda/[ciudad]/[ciudad]` | `/proyecto-vivienda/copacabana/copacabana` | Slug duplicado anómalo |
| `/macroproyecto/[slug-largo]` | `/macroproyecto/macroproyecto-vivienda-palo-agua` | Categoría diferente, slug redundante |
| `/macroproyecto-vivienda/[slug]` | `/macroproyecto-vivienda/ciudad-esplendor` | Tercer patrón para macroproyectos |

### ⚠️ Contenido duplicado

- Proyecto "Jilguero" aparece dos veces con la misma URL en el sitemap del footer.
- "Ciudad Esplendor" tiene dos URLs distintas (`/macroproyecto-vivienda/ciudad-esplendor` y `/macroproyecto/macroproyecto-vivienda-ciudad-esplendor`).

### ⚠️ Audiencias mezcladas en la navegación principal

El menú principal mezcla CTAs de cuatro audiencias distintas sin jerarquía:
- Comprador local → "Ofertas de vivienda"
- Cliente actual → "Zona clientes"
- Inversionista exterior → "Invertir desde el exterior"
- Cualquier usuario → "Contáctanos"

### ⚠️ Ausencia de rutas de segundo nivel desde la homepage

No hay accesos directos visibles a las rutas más comunes del usuario:
- Ciudad más buscada directamente desde el nav
- Tipo de vivienda (VIS / No VIS) como filtro inmediato
- Rango de precio como punto de entrada

### ⚠️ Portales internos expuestos como navegación primaria

"Zona proveedores" y "Zona administradores" están en la barra superior junto con "Blog". Son portales para audiencias internas (empresas proveedoras y administradores de conjuntos), pero conviven en el mismo nivel visual que la navegación del comprador.

---

## Métricas de complejidad del sitio actual

| Métrica | Valor | Observación |
|---------|-------|-------------|
| Páginas de proyecto detectadas | 19 proyectos + 10 macroproyectos = ~29 | Sin contar duplicados |
| Ciudades con proyectos | 16 | Alta dispersión geográfica |
| Patrones de URL distintos para proyectos | 3 | Inconsistencia estructural |
| Niveles de profundidad máximos | 3 (`/proyecto-vivienda/ciudad/slug`) | Manejable, pero sin señalización |
| Ítems en el menú principal | 4 | Correcto en cantidad, problemático en audiencia |
| Ítems en la barra superior | 3 | Audiencias internas mezcladas |
| Dominios externos en la navegación | 2 | `iproveedor.com` y `capta.co` |

---

## Archivos relacionados

→ [[01_por-que-importa-la-ai]] · [[03_mapa-sitio-propuesto]] · [[H3A]] · [[05_inventario-final]] · [[06_reporte-ejecutivo-sintesis]]

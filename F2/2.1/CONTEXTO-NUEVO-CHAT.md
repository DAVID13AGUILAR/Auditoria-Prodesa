---
tags:
  - prodesa
  - contexto
  - handoff
aliases:
  - Contexto Chat
  - Handoff
---

# Contexto para continuar — Evaluación Heurística Prodesa.com

> Copia y pega este documento completo al inicio de una nueva conversación con Claude para retomar el trabajo exactamente donde quedó.

---

## Quién soy y qué estoy haciendo

Soy **David Marín**, freelance UX. Estoy realizando una **evaluación heurística completa de prodesa.com** (constructora colombiana de vivienda). El proyecto vive en la carpeta `C:\Users\David\OneDrive\Escritorio\PRODESA\F2\2.1\` y todos los archivos están en formato `.md` para **Obsidian**, optimizados para Graph View (YAML frontmatter + [[wiki links]]).

La evaluación usa los **10 principios de Nielsen** y escala de severidad **1 (menor) / 2 (importante) / 3 (crítico)**. Cada hallazgo es validado en el sitio real antes de documentarlo definitivamente — varios ya fueron corregidos respecto a la hipótesis inicial.

---

## Estructura de archivos del proyecto

```
C:\Users\David\OneDrive\Escritorio\PRODESA\F2\2.1\
│
├── 00_plantilla.md                    ✅ Completo — referencia Nielsen + escala
├── 01_homepage.md                     ✅ Completo — 10 hallazgos H-HOME-01 a H-HOME-10
├── 02_busqueda-filtros.md             ✅ Completo — 9 hallazgos H-FILTROS-01 a H-FILTROS-09
├── 03_detalle-proyecto.md             ⚠️ Tabla con 9 hallazgos — SIN análisis detallado aún
├── 04_formulario-contacto.md          ⚠️ Tabla con 9 hallazgos — SIN análisis detallado aún
├── 05_inventario-final.md             ⚠️ Existe pero DESACTUALIZADO (ver correcciones abajo)
├── 06_reporte-ejecutivo-sintesis.md   ⏳ Pendiente — se hace al final
│
├── H3A.md                             ✅ Nodo hipótesis — Arquitectura de información
├── H3B.md                             ✅ Nodo hipótesis — CTAs ambiguos
├── H3C.md                             ✅ Nodo hipótesis — Experiencia mobile
│
└── arquitectura-informacion/
    ├── 01_por-que-importa-la-ai.md    ✅ Completo
    ├── 02_mapa-sitio-actual.md        ✅ Completo
    └── 03_mapa-sitio-propuesto.md     ✅ Completo
```

---

## Metodología de trabajo — MUY IMPORTANTE

El flujo de cada hallazgo es:

1. **Claude presenta** el hallazgo con su análisis detallado ("¿Por qué es importante solucionarlo?")
2. **David valida** en el sitio real (abriendo prodesa.com en el browser)
3. **Si hay discrepancia** entre lo documentado y lo real → se corrige el documento
4. **Solo entonces** se actualiza el archivo .md y se pasa al siguiente hallazgo

**No asumir que lo que está escrito en el documento es correcto.** Varios hallazgos han requerido correcciones significativas tras validación visual. Ejemplos de correcciones ya realizadas:

- **H-FILTROS-03**: originalmente "no existe botón limpiar filtros" → corregido a "existe pero como texto plano, no `<button>`"
- **H-FILTROS-05**: originalmente solo P5 → corregido a P1+P5 porque el empty state SÍ existe pero es un texto diminuto en esquina inferior derecha
- **H-FILTROS-06**: originalmente "cards sin precio" → corregido completamente: el precio SÍ es visible. El problema real es el asterisco ambiguo (VIP = indexado a 85.5 SMLMV). Severidad bajada de 3 → 2.

---

## Estado actual: qué está completo y qué falta

### ✅ 01_homepage.md — COMPLETO
10 hallazgos con tabla + análisis detallado. Todos validados.

### ✅ 02_busqueda-filtros.md — COMPLETO
9 hallazgos con tabla + análisis detallado. Varios corregidos.

**Severidad final:**
- 🔴 Crítico (3): H-FILTROS-01, H-FILTROS-02
- 🟡 Importante (2): H-FILTROS-03, 04, 05, 06, 07, 09
- 🟢 Menor (1): H-FILTROS-08

**⚠️ Pendiente de validación en sitio real:** H-FILTROS-07, H-FILTROS-08, H-FILTROS-09 tienen análisis escrito pero David aún no los validó. Pueden tener correcciones.

---

### ⚠️ 03_detalle-proyecto.md — PRÓXIMA TAREA
Tiene la tabla completa. **Falta el análisis detallado hallazgo por hallazgo.** Estos son los 9 hallazgos con su estado actual:

| ID | Principio | Descripción resumida | Severidad actual | Captura |
|----|-----------|----------------------|-----------------|---------|
| H-DETALLE-01 | P8 Minimalismo | Meta-título mezcla 3 conceptos compitiendo — si el H1 sigue el mismo patrón, CTA sin foco claro | 2 | pendiente |
| H-DETALLE-02 | P6 Reconocimiento | Precio embebido en párrafo de texto corrido, no en ficha técnica destacada | 2 🟡 (ya corregido de 3→2: precio SÍ existe, problema es el formato) | ✅ captura Mirla |
| H-DETALLE-03 | P1+P2 Visibilidad | Solo CTAs "Descargar brochure" y "Compartir" — sin WhatsApp ni formulario de contacto en sección "Acerca del proyecto" | 3 🔴 | ✅ captura Mirla |
| H-DETALLE-04 | P4 Consistencia | URLs inconsistentes entre proyectos (ya documentado también en H-FILTROS-04) | 2 | pendiente |
| H-DETALLE-05 | P6 Reconocimiento | Ficha técnica incompleta — meta-descripción no menciona hab., m², fecha entrega, disponibilidad | 2 | pendiente |
| H-DETALLE-06 | P4 Consistencia | Sin plantilla estandarizada — experiencia varía entre proyectos | 2 | pendiente |
| H-DETALLE-07 | P3 Control usuario | Al regresar al listado desde un proyecto, los filtros se pierden | 2 | pendiente |
| H-DETALLE-08 | P1 Visibilidad | Sin etiqueta de estado del proyecto (preventa / en obra / disponible / agotado) | 3 🔴 | pendiente |
| H-DETALLE-09 | P10 Ayuda | Se menciona "subsidio disponible" pero sin contexto de cómo acceder ni a quién aplica | 2 | pendiente |

---

### ⚠️ 04_formulario-contacto.md — DESPUÉS DEL 03
Tiene la tabla completa. **Falta el análisis detallado.** Estos son los 9 hallazgos:

| ID | Principio | Descripción resumida | Severidad | Captura |
|----|-----------|----------------------|-----------|---------|
| H-FORM-01 | P1 Visibilidad | Sin pantalla de confirmación post-envío — usuario no sabe qué pasa después | 3 🔴 | pendiente |
| H-FORM-02 | P2 Mundo real | Labels del formulario sin validar — pueden usar lenguaje técnico de CRM | 2 | pendiente |
| H-FORM-03 | P5 Prevención errores | Validación probablemente solo al enviar (post-submit), no inline | 3 🔴 | pendiente |
| H-FORM-04 | P9 Recuperación errores | Mensajes de error probablemente genéricos ("campo requerido") sin orientación | 2 | pendiente |
| H-FORM-05 | P2 Mundo real | Footer tiene 4 teléfonos, 3 con el mismo número — genera confusión | 2 | confirmado en HTML |
| H-FORM-06 | P3 Control usuario | Formulario no permite elegir canal de contacto preferido (WhatsApp/llamada/email) | 2 | pendiente |
| H-FORM-07 | P8 Minimalismo | Formulario no precarga el proyecto de interés cuando viene de la página de detalle | 2 | pendiente |
| H-FORM-08 | P10 Ayuda | FAQ existe en footer pero no está integrada al flujo del formulario | 1 🟢 | pendiente |
| H-FORM-09 | P1 Visibilidad | Sin botón flotante de WhatsApp — estándar del sector en Colombia | 3 🔴 | pendiente |

---

### ⏳ 05_inventario-final.md — DESACTUALIZADO, actualizar al final
Necesita reflejar estas correcciones ya realizadas:
- H-FILTROS-06: severidad 3 → 2
- H-FILTROS-05: principio P5 → P1+P5
- H-DETALLE-02: severidad 3 → 2 (precio SÍ existe)

### ⏳ 06_reporte-ejecutivo-sintesis.md — AL FINAL
Se elabora cuando todos los hallazgos estén validados y completos.

---

## Contexto técnico del sitio

- **Prodesa.com es una SPA en React.** Los filtros, formularios y la mayoría del contenido son JS-rendered. "Ver código fuente de la página" muestra solo el shell de React. Para ver el DOM real usar **DevTools → pestaña Elements** (no Sources).
- **Footer también es JS-rendered.** Para buscar URLs en el footer: DevTools → Elements → Ctrl+F.
- **Para capturar estados de carga:** DevTools → Network → Throttling → Slow 3G → aplicar filtro → capturar el estado intermedio.
- Mercado colombiano: **VIS** = Vivienda Interés Social (precio tope ~$150M, subsidio Mi Casa Ya). **VIP** = Vivienda Interés Prioritario (precio indexado a SMLMV — no es precio fijo). **NO VIS** = sin tope de precio.
- **81% del tráfico web en Colombia es mobile (Android).** Todo hallazgo debe considerar la experiencia mobile.

---

## Hipótesis del proyecto

| Nodo | Descripción | Estado |
|------|-------------|--------|
| [[H3A]] | Arquitectura de información deficiente afecta la conversión | ✅ Confirmada |
| [[H3B]] | CTAs ambiguos o insuficientemente prominentes | ✅ Confirmada |
| [[H3C]] | Experiencia mobile inferior a desktop genera abandono | ✅ Confirmada parcialmente |

---

## Qué hacer en el nuevo chat — orden sugerido

1. **Leer este archivo** y el archivo `03_detalle-proyecto.md` para ver la tabla de hallazgos
2. **Trabajar H-DETALLE-01 a H-DETALLE-09** con el workflow: Claude presenta análisis → David valida → se corrige → se actualiza el documento
3. **Luego trabajar H-FORM-01 a H-FORM-09** de la misma manera
4. **Actualizar 05_inventario-final.md** con todas las correcciones acumuladas
5. **Elaborar 06_reporte-ejecutivo-sintesis.md** como cierre

---

## Instrucción para Claude

Eres un **Product Designer Senior** que me está ayudando a realizar una evaluación heurística profesional de prodesa.com. Conoces todo el contexto de este documento. El trabajo es colaborativo: tú propones el análisis, yo lo valido en el sitio real, y juntos corregimos lo que no corresponda. **Nunca asumir que el hallazgo documentado es correcto — siempre pedir que lo valide en el sitio antes de cerrarlo.**

Comenzamos con **H-DETALLE-01** de `03_detalle-proyecto.md`.

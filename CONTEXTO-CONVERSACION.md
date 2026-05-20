# Contexto de conversación — Auditoría UX Prodesa

> Usar este archivo al inicio de una nueva conversación con Claude para restaurar el contexto completo del proyecto.

---

## 1. Contexto general

**Cliente:** Prodesa — constructora colombiana con proyectos VIS y No-VIS en Bogotá y otras ciudades.  
**Objetivo:** Auditoría UX completa de prodesa.com para identificar fricciones en el embudo de conversión.  
**Rol del usuario:** David Marín — evaluador UX freelance.  
**Compañero:** Trabaja en paralelo en la tarea 2.2 (Cognitive Walkthrough Flujo 1).

**Repositorio Git:** `DAVID13AGUILAR/Auditoria-Prodesa`, rama `main`.  
**Vault Obsidian:** `C:\Users\David\OneDrive\Escritorio\PRODESA`  
**Estado del repo:** El último push fue antes de empezar la fase 2.3. Todo lo de 2.3 y el archivo `research/CW-F2-importancia-cognitive-walkthrough.md` están solo en local — pendientes de commit/push cuando el usuario lo pida.

---

## 2. Estructura de carpetas

```
PRODESA/
├── F2/
│   ├── 2.1/                        ← Evaluación heurística (COMPLETADA y pusheada)
│   │   ├── 01_homepage.md
│   │   ├── 02_busqueda-filtros.md
│   │   ├── 03_detalle-proyecto.md
│   │   ├── 04_formulario-contacto.md
│   │   ├── 05_inventario-final.md
│   │   ├── 06_reporte-ejecutivo-sintesis.md
│   │   ├── H3A.md
│   │   ├── H3B.md
│   │   └── H3C.md
│   ├── 2.2/                        ← Lo hace el compañero — NO TOCAR
│   └── 2.3/                        ← Cognitive Walkthrough Flujo 2 (LOCAL, sin push)
│       ├── 00_persona-valentina.md
│       ├── 01_walkthrough-flujo2.md
│       ├── 02_hallazgos-flujo2.md
│       └── 03_analisis-detallado-flujo2.md
└── research/
    ├── H-FORM-patrones-formulario-contacto.md
    ├── H-FORM-canales-contacto-omnicanalidad.md
    ├── H8-visibilidad-estado-proyecto.md
    ├── H6-patrones-pagina-detalle-proyecto.md
    └── CW-F2-importancia-cognitive-walkthrough.md   ← LOCAL, sin push
```

---

## 3. Fase 2.1 — Evaluación heurística (completada)

**Escala de severidad:**
- 🔴 Crítico = severidad 3
- 🟠 Importante = severidad 2
- 🟡 Menor = severidad 1

**Total hallazgos activos: 36** (1 eliminado tras validación visual)  
Distribución: 8 críticos / 24 importantes / 4 menores

### 01_homepage.md — H-HOME-01 a H-HOME-09
Problemas principales: SPA sin SSR genera pantalla en blanco en conexiones lentas (crítico), doble barra de navegación, hero sin H1 ni propuesta de valor, app móvil con link roto apuntando a Apple Store en lugar de Google Play.

### 02_busqueda-filtros.md — H-FILTROS-01 a H-FILTROS-09
Problemas principales: filtros no persistentes al navegar (crítico), ausencia de breadcrumbs, filtro VIS/No-VIS solo disponible en mobile (no en web), spinner con delay + scroll manual al cargar resultados, asterisco en precio sin explicación.

### 03_detalle-proyecto.md — H-DETALLE-01 a H-DETALLE-09
Problemas principales: H1 redundante con chip "Proyecto de vivienda", precio domina visualmente sobre nombre del proyecto, sin CTA de contacto al terminar de leer "Acerca del proyecto" (solo "Descargar brochure" y "Compartir"), 6 inconsistencias entre proyectos Orizzo y Pietra, sin chip de estado del proyecto (preventa/en construcción/entrega), tooltip de subsidio ausente.  
**Regla fija:** En este archivo NO se agrega sección "Cómo evidenciarlo" — decisión explícita del usuario.

### 04_formulario-contacto.md — H-FORM-01 a H-FORM-09
- **H-FORM-01:** Confirmación post-envío muestra correo en lugar del nombre del usuario, sin canal ni tiempo de respuesta ni CTA de respaldo
- **H-FORM-02:** 6 campos obligatorios incluyendo cédula en primer contacto
- **H-FORM-03:** Validación 100% post-submit, todos los errores aparecen al enviar
- **H-FORM-04:** Mensajes de error en MAYÚSCULAS, genéricos, sin orientación
- **H-FORM-05:** Labels con capitalización inconsistente ("Tipo De Documento"), abreviatura "Nro" no estándar
- **H-FORM-06:** "Agenda tu cita en sala" abre calendario Microsoft Teams — CTA engañoso. El problema de zona horaria se eliminó: era configuración del PC del evaluador, no un bug del sitio.
- **H-FORM-07:** Click en "Déjanos tus datos" hace scroll hacia arriba inesperadamente
- **H-FORM-08:** reCAPTCHA visible en formulario /contactanos (Stanford: -40% conversión)
- **H-FORM-09:** WhatsApp con **cobertura parcial** — existe en sticky del detalle pero ausente en homepage y listado. Severidad corregida de 3 a 2 tras validación visual.

### 05_inventario-final.md
Tabla completa con los 36 hallazgos activos, wiki-links en todos los IDs, 5 categorías. Top 3: H-HOME-01 (SPA), H-FILTROS-01 (filtros no persistentes), H-FORM-02 (cédula en primer contacto).

### 06_reporte-ejecutivo-sintesis.md
Metodología con 5 proyectos evaluados, 4 patrones de hallazgos, tabla de hipótesis con links, roadmap de intervención en 3 etapas.

### Hipótesis
- **H3A — Arquitectura:** 9 hallazgos activos. Confirmada.
- **H3B — CTAs ambiguos:** 10 hallazgos activos. Confirmada fuertemente.
- **H3C — Mobile inferior:** 10 hallazgos activos. Confirmada. Matiz: mobile no siempre es peor — los errores post-submit son más visibles en mobile que en desktop.

---

## 4. Fase 2.3 — Cognitive Walkthrough Flujo 2 (completada, sin push)

**Persona:** Valentina Morales, 29 años, Bogotá-Suba, auxiliar administrativa, ~$2.4M/mes, Android Samsung Galaxy A, WhatsApp como canal preferido, primera compradora, evaluando proyecto Orizzo.

**Tarea:** *"Contactar al asesor del proyecto Orizzo para recibir más información sobre el subsidio y el proceso de compra."*  
**Punto de entrada:** `prodesa.com/proyecto-vivienda/bogota/orizzo`  
**Dispositivos evaluados:** Desktop Chrome + Mobile Android

### 01_walkthrough-flujo2.md — 15 pasos documentados
Pasos críticos: paso 2 (sin CTA al terminar de leer), paso 5 (Teams en lugar de visita física), paso 6 (única ruta sin fricción — WhatsApp), pasos 8-9 (cédula obligatoria), paso 10 (teléfono inválido sin error), paso 11 (todos los errores al enviar), paso 14 (confirmación con correo y sin orientación), paso 15 (callejón sin salida).  
Incluye tabla comparativa mobile vs desktop (5 diferencias).

### 02_hallazgos-flujo2.md — 11 hallazgos en 4 categorías

| ID | Severidad | Problema |
|----|-----------|----------|
| CW-F2-01 | 🔴 Crítico | CTA "Agenda tu cita en sala" promete visita física, entrega Teams |
| CW-F2-02 | 🔴 Crítico | Confirmación muestra correo en lugar de nombre — privacidad + UX |
| CW-F2-03 | 🟠 Importante | Errores en MAYÚSCULAS, genéricos |
| CW-F2-04 | 🟠 Importante | Sin CTA de contacto al terminar "Acerca del proyecto" |
| CW-F2-05 | 🔴 Crítico | Cédula obligatoria en primer contacto |
| CW-F2-06 | 🔴 Crítico | Teléfono inválido pasa sin validación al CRM |
| CW-F2-07 | 🟡 Menor | Scroll inesperado al hacer clic en "Déjanos tus datos" |
| CW-F2-08 | 🔴 Crítico | Validación 100% post-submit |
| CW-F2-09 | 🟠 Importante | Sin indicador de progreso ni check verde por campo |
| CW-F2-10 | 🔴 Crítico | Confirmación sin canal, tiempo estimado ni CTA de respaldo |
| CW-F2-11 | 🔴 Crítico | Pantalla de confirmación es callejón sin salida |

Total: 7 críticos, 3 importantes, 1 menor. Todos cross-referenciados con hallazgos de 2.1.

### 03_analisis-detallado-flujo2.md
Análisis narrativo: tres quiebres consecutivos del funnel (pasos 2, 5 y 14), por qué la cédula es un error estratégico, la validación del teléfono tiene dos víctimas (usuario y asesor), WhatsApp es la solución obvia pero está en el lugar equivocado del funnel. Tabla de priorización en dos olas.

---

## 5. Research (5 archivos)

| Archivo | Contenido |
|---------|-----------|
| `H-FORM-patrones-formulario-contacto.md` | WhatsApp 92% Colombia, validación inline -16% abandono, confirmación post-envío +63% conversión |
| `H-FORM-canales-contacto-omnicanalidad.md` | Estrategia omnicanal, CTAs engañosos (NN/G), reCAPTCHA -40% conversión (Stanford) |
| `H8-visibilidad-estado-proyecto.md` | Heurística Nielsen #1, fases de proyecto colombiano, estado para calidad de leads |
| `H6-patrones-pagina-detalle-proyecto.md` | Patrones de página de detalle, jerarquía visual, above the fold |
| `CW-F2-importancia-cognitive-walkthrough.md` | CW vs HE, 81% abandono formularios, 0.4-1.2% conversión bienes raíces |

---

## 6. Reglas fijas del proyecto

1. **Correo real** `david.marin13a@hotmail.com` — NUNCA usarlo. Siempre `usuario@ejemplo.com`.
2. **No agregar "Cómo evidenciarlo"** en `03_detalle-proyecto.md` — decisión explícita del usuario.
3. **No hacer commit/push** a menos que el usuario lo pida con palabras explícitas.
4. **2.2 es del compañero** — no crear ni modificar nada en esa carpeta.
5. **Evaluar siempre mobile Y desktop** en todos los hallazgos.
6. **No usar emojis** salvo en las escalas de severidad (🔴🟠🟡) ya establecidas.
7. **Wiki-links en formato Obsidian:** `[[filename#section|texto]]`
8. Investigación web → siempre guardar en carpeta `research/`.
9. El usuario **pega el contenido de Notion** al inicio de cada tarea — no intentar acceder a Notion directamente (requiere autenticación y falla).

---

## 7. Qué sigue

- **Tareas 2.4 y 2.5** — contenido desconocido. El usuario pegará el contenido desde Notion al inicio de la próxima sesión.
- **Commit/push pendiente** de todo lo de 2.3 + `research/CW-F2-importancia-cognitive-walkthrough.md` cuando el usuario lo pida.
- **El compañero** puede sincronizar haciendo pull del repo en cualquier momento.

---

## 8. Flujo de trabajo establecido

```
1. Usuario pega contenido de tarea desde Notion
2. Leer tarea → identificar conexiones con hallazgos anteriores
3. Investigación web si aplica → guardar en research/
4. Crear/actualizar documentos en la carpeta correspondiente
5. Actualizar documentos de resumen (inventario, reporte, hipótesis) si aplica
6. Commit/push solo cuando el usuario lo pide explícitamente
```

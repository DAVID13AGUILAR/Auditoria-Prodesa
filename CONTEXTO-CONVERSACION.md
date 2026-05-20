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
**Estado del repo:** Main limpio y actualizado. Fases 2.1 y 2.4 completas y pusheadas. F2/2.3 no existe en el repo.

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
│   ├── 2.3/                        ← NO existe en el repo (no fue commiteado)
│   └── 2.4/                        ← Revisión WCAG 2.0 (COMPLETADA y pusheada via PR #1)
│       ├── 00_plantilla.md
│       ├── 01_homepage.md
│       ├── 02_busqueda-filtros.md
│       ├── 03_detalle-proyecto.md
│       ├── 04_formulario-contacto.md
│       ├── 05_inventario-final.md
│       ├── 06_reporte-tarea-2.4.md
│       └── CONTEXTO-NUEVO-CHAT.md
└── research/
    ├── H-FORM-patrones-formulario-contacto.md
    ├── H-FORM-canales-contacto-omnicanalidad.md
    ├── H8-visibilidad-estado-proyecto.md
    └── H6-patrones-pagina-detalle-proyecto.md
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

## 4. Fase 2.4 — Revisión de accesibilidad WCAG 2.0 (completada)

**Páginas auditadas:** Homepage · Detalle (Siena) · Búsqueda/filtros · /contactanos  
**Herramientas:** WAVE, inspección de headings en consola, navegación por teclado, validación manual  
**Hipótesis:** H3B — CTAs ambiguos o insuficientemente prominentes

**Total hallazgos: 46** (19 críticos / 15 importantes / 5 menores + 7 pendientes menores)  
AIM Score WAVE: Homepage 5.8 · Siena 7.7 · /contactanos 6.0 (ninguna supera 8.0 real)

### Hallazgos clave

| ID | Problema | Criterio |
|----|----------|----------|
| A-CONTACT-02 | 3 Broken ARIA references — bug React SPA: IDs dinámicos rotos entre re-renders | 4.1.2 A |
| A-HOME-02 / A-CONTACT-05 | 39+ errores de contraste sistémicos (`color-naranja` y `color-gris`) | 1.4.3 AA |
| A-DETALLE-01 / A-HOME-13 / A-CONTACT-01 | Jerarquía de headings rota en las 4 páginas (saltos H1→H6, H3→H6) | 1.3.1 A |
| A-HOME-03 / A-CONTACT-06 | 6 empty buttons (íconos sin nombre accesible) — sistémico del design system | 4.1.2 A |
| A-FORM-06 | Focus invisible en campo teléfono y tipo documento — inoperables por teclado | 2.4.7 / 2.1.1 |
| A-FORM-08 | Campo teléfono combina indicativo (+57) y número sin instrucción | 3.3.2 A |
| A-FORM-09 | Placeholder no desaparece al escribir — texto se solapa con el input | 1.4.3 A |
| A-FORM-05 | Sin email/SMS de confirmación post-envío (también implicación Ley 1581 de 2012) | 4.1.3 AA |

**8 problemas sistémicos** afectan la totalidad del sitio.

**Nota técnica:** El formulario de contacto es un **embed de HubSpot** (`class="hs-input"`, IDs con GUID dinámico). Los problemas de labels, placeholders y foco no se resuelven con CSS — requieren configuración en HubSpot.

**Nota legal:** El formulario recolecta datos personales sin indicar propósito ni enviar confirmación — posible incumplimiento de la **Ley 1581 de 2012** (Colombia, Protección de Datos Personales).

**Conclusión H3B:** Confirmada y ampliada. Los CTAs fallan no solo en prominencia visual sino en operabilidad para el ~15% de usuarios con discapacidad y para cualquier usuario que navega por teclado.

---

## 5. Research (4 archivos)

| Archivo | Contenido |
|---------|-----------|
| `H-FORM-patrones-formulario-contacto.md` | WhatsApp 92% Colombia, validación inline -16% abandono, confirmación post-envío +63% conversión |
| `H-FORM-canales-contacto-omnicanalidad.md` | Estrategia omnicanal, CTAs engañosos (NN/G), reCAPTCHA -40% conversión (Stanford) |
| `H8-visibilidad-estado-proyecto.md` | Heurística Nielsen #1, fases de proyecto colombiano, estado para calidad de leads |
| `H6-patrones-pagina-detalle-proyecto.md` | Patrones de página de detalle, jerarquía visual, above the fold |

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

- **Tarea 2.5 — Análisis de rendimiento (PageSpeed + GTmetrix)** — contenido desconocido. El usuario pegará el contenido desde Notion al inicio de la próxima sesión.
- **F2/2.3** no existe en el repo — verificar con el usuario si es necesario crearlo o si fue descartado.
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

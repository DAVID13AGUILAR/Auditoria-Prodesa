---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - indice
  - flujo-1
hipotesis: H3A
persona: Valentina Ríos — [[01_persona-valentina]]
---

# Cognitive Walkthrough — Flujo 1: Búsqueda y filtrado
**Persona:** Valentina Ríos, 32 años, Bogotá. Primera compradora VIS. Llega desde Instagram en mobile (375px, 4G).
**Tarea:** Encontrar un proyecto de apartamento VIS en Bogotá con buena conectividad de transporte y ver su precio.
**Dispositivo:** Mobile (375px) y Desktop (1440px) · Modo incógnito

---

## Flujo evaluado

```
[Ad Instagram] → Homepage → Búsqueda + Filtros → Resultados → Detalle de proyecto → Contacto
```

---

## Archivos del registro

| Archivo | Sección | Pasos | Estado |
|---------|---------|-------|--------|
| [[02_punto-entrada]] | Punto de entrada | 1a, 1b | ✅ Completo |
| [[03_homepage]] | Homepage | 2a, 2b, 2c | ✅ Completo |
| [[04_busqueda-filtros]] | Búsqueda y filtros | 3a, 3b, 3c, 3d, 3e | ✅ Completo |
| [[05_resultados]] | Resultados | 4a, 4b, 4c, 4d | ✅ Completo |
| [[06_detalle-proyecto]] | Detalle del proyecto | 5a, 5b, 5c · 5d, 5e, 5f pendientes | 🔄 En progreso |
| [[07_contacto]] | Contacto | 6a en adelante | ❌ Pendiente |

---

## Resumen de hallazgos

| Métrica | Valor |
|---------|-------|
| **Pasos completados** | 14 de ~20 estimados |
| **Hallazgos 🔴 Críticos** | 4 (modal sin cierre · SPA sin JS · filtro VIS ausente desktop · filtros no persistentes) |
| **Hallazgos 🟠 Importantes** | 18 (ver [[08_inventario-hallazgos]]) |
| **¿Completó la tarea?** | **No** — Valentina no logra ver el precio real de un proyecto VIS sin contactar al vendedor |
| **Punto de abandono más probable** | 1b (modal sin cierre) o contacto (cédula en formulario) |
| **Hipótesis H3A** | Confirmada |

---

→ [[00_plantilla]] · [[01_persona-valentina]] · [[08_inventario-hallazgos]] · [[09_reporte-tarea-2.2]]

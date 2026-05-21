---
status: en-progreso
created: 2026-05-20
tags:
  - prodesa
  - cognitive-walkthrough
  - punto-entrada
  - hallazgos
  - critico
aliases:
  - CW Punto de entrada
fase: "2.2"
---

# 02 — Punto de entrada
**Persona:** [[01_persona-valentina]] — Valentina Ríos, 32 años, Bogotá, primera compradora VIS
**URL evaluada:** https://prodesa.com/
**Dispositivo:** Mobile (375px) · Desktop (1440px) · Modo incógnito

---

## Contexto técnico

| Campo | Registro |
|-------|----------|
| **URL exacto de llegada** | pendiente |
| **¿Hay landing page de campaña?** | pendiente — verificar si el URL tiene parámetros UTM |
| **FCP (First Contentful Paint)** | pendiente — medir en DevTools → Performance |
| **TTI (Time to Interactive)** | pendiente — medir en DevTools → Performance |
| **Referencia cruzada 2.5** | Comparar FCP y LCP obtenidos aquí con los datos de PageSpeed de la tarea 2.5 |

---

## Registro de pasos

| Paso # | Acción esperada | Q1 — ¿Sabe qué hacer? | Q2 — ¿Ve el control? | Q3 — ¿Entiende causa→efecto? | Q4 — ¿Sistema confirma progreso? | Fricción detectada | Sev. | Captura Mobile (375px) | Captura Desktop (1440px) |
|--------|-----------------|----------------------|---------------------|------------------------------|----------------------------------|--------------------|------|------------------------|--------------------------|
| 1a | **Nota técnica (dispositivo sin JavaScript):** El sitio requiere JS para funcionar. Si el dispositivo lo tiene desactivado, el sitio no carga en absoluto | N/A — el usuario no puede ejecutar ninguna acción | **No** — la página muestra únicamente: *"You need to enable JavaScript to run this app."* Sin contenido, sin orientación | N/A | N/A | ⚠️ **Aclaración de diseño:** El sitio está construido como SPA y depende al 100% de JavaScript. Sin JS activo, la página es completamente inutilizable. Afecta ~1-2% de usuarios. → [[F2/2.1/05_inventario-final#H-HOME-01]] | 🔴 | ![[assets/home/H-HOME-1-JAVA.png]] | ![[assets/home/H-HOME-1-JAVA.png]] |
| 1b | **Carga normal (WiFi / 4G estable):** El sitio carga y Valentina ve la primera impresión | **No** — lo primero que ve es un modal promocional ("PONTE LA 10 / ¡En mayo!") sin relación con su búsqueda de VIS. No sabe si llegó al sitio correcto | **No** — el modal bloquea todo el contenido. **No hay botón de cierre (X) visible**. No puede acceder al buscador ni al contenido detrás | **No** — no sabe cómo cerrar el modal: ¿clic afuera? ¿Escape? El sistema no lo indica en ningún lugar visible | **No** — el sistema muestra una promo de mayo en lugar de confirmar que llegó al lugar correcto desde el anuncio de Instagram | 🔴 **NUEVO — CW-01:** Modal promocional sin botón de cierre visible como primera impresión. Valentina llega buscando proyectos VIS y queda bloqueada por contenido irrelevante. Sin X visible, no sabe cómo avanzar → alta probabilidad de rebote inmediato | 🔴 | ![[Pasted image 20260520203224.png]] | ![[Pasted image 20260520203103.png]] |

---

→ [[00_plantilla]] · [[03_homepage]] · [[04_busqueda-filtros]] · [[05_resultados]] · [[06_detalle-proyecto]] · [[07_contacto]] · [[08_inventario-hallazgos]]

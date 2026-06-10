---
status: completado
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

# 02 â€” Punto de entrada
**Persona:** [[01_persona-valentina]] â€” Valentina RÃ­os, 32 aÃ±os, BogotÃ¡, primera compradora VIS
**URL evaluada:** https://prodesa.com/
**Dispositivo:** Mobile (375px) Â· Desktop (1440px) Â· Modo incÃ³gnito

---

## Contexto tÃ©cnico

| Campo                              | Registro                                                                                                                                                                                                                                                                         |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL exacto de llegada**          | https://prodesa.com/                                                                                                                                                                                                                                                             |
| **Â¿Hay landing page de campaÃ±a?**  | Parcial â€” Instagram lleva a `prodesa.com/` sin landing dedicada. Google Ads SÃ usa parÃ¡metros UTM (`?kw=prodesa&cpn=22801670082&utm_term=prodesa`) pero apunta a la homepage, no a una pÃ¡gina de campaÃ±a diferenciada. Sin personalizaciÃ³n del mensaje segÃºn el canal de origen. |
| **FCP (First Contentful Paint)**   | ðŸ”´ **14,3 s** â€” umbral "malo": >3 s. Valentina en 4G espera 14 segundos para ver el primer contenido.                                                                                                                                                                            |
| **LCP (Largest Contentful Paint)** | ðŸ”´ **39,6 s** â€” umbral "malo": >4 s. El hero image tarda 40 segundos en cargar completamente.                                                                                                                                                                                    |
| **Total Blocking Time**            | ðŸ”´ **2.050 ms** â€” umbral "malo": >600 ms. El hilo principal estÃ¡ bloqueado mÃ¡s de 2 segundos â€” el sitio no responde a toques durante ese tiempo.                                                                                                                                 |
| **CLS (Cumulative Layout Shift)**  | ðŸ”´ **0,882** â€” umbral "malo": >0,25. Elementos se mueven visiblemente durante la carga â€” Valentina puede hacer clic en el lugar equivocado.                                                                                                                                      |
| **Speed Index**                    | ðŸ”´ **15,1 s** â€” umbral "malo": >4,3 s.                                                                                                                                                                                                                                           |
| **Performance Score**              | ðŸ”´ **3 / 100** â€” categorÃ­a crÃ­tica (0â€“49).                                                                                                                                                                                                                                       |
| **Referencia cruzada 2.5**         | Estos datos deben cruzarse con el anÃ¡lisis completo de PageSpeed en la tarea 2.5. Confirman y cuantifican CW-50 â†’ [[F2/2.1/05_inventario-final#H-HOME-01]]                                                                                                                       |

---

## Registro de pasos

| Paso # | AcciÃ³n esperada | Q1 â€” Â¿Sabe quÃ© hacer? | Q2 â€” Â¿Ve el control? | Q3 â€” Â¿Entiende causaâ†’efecto? | Q4 â€” Â¿Sistema confirma progreso? | FricciÃ³n detectada | Sev. | Captura Mobile (375px) | Captura Desktop (1440px) |
|--------|-----------------|----------------------|---------------------|------------------------------|----------------------------------|--------------------|------|------------------------|--------------------------|
| 1a | **Nota tÃ©cnica (dispositivo sin JavaScript):** El sitio requiere JS para funcionar. Si el dispositivo lo tiene desactivado, el sitio no carga en absoluto | N/A â€” el usuario no puede ejecutar ninguna acciÃ³n | **No** â€” la pÃ¡gina muestra Ãºnicamente: *"You need to enable JavaScript to run this app."* Sin contenido, sin orientaciÃ³n | N/A | N/A | âš ï¸ **AclaraciÃ³n de diseÃ±o:** El sitio estÃ¡ construido como SPA y depende al 100% de JavaScript. Sin JS activo, la pÃ¡gina es completamente inutilizable. Afecta ~1-2% de usuarios. â†’ [[F2/2.1/05_inventario-final#H-HOME-01]] | ðŸ”´ | ![[assets/home/H-HOME-1-JAVA.png]] | ![[assets/home/H-HOME-1-JAVA.png]] |
| 1b | **Carga normal (WiFi / 4G estable):** El sitio carga y Valentina ve la primera impresiÃ³n | **No** â€” lo primero que ve es un modal promocional ("PONTE LA 10 / Â¡En mayo!") sin relaciÃ³n con su bÃºsqueda de VIS. No sabe si llegÃ³ al sitio correcto | **No** â€” el modal bloquea todo el contenido. **No hay botÃ³n de cierre (X) visible**. No puede acceder al buscador ni al contenido detrÃ¡s | **No** â€” no sabe cÃ³mo cerrar el modal: Â¿clic afuera? Â¿Escape? El sistema no lo indica en ningÃºn lugar visible | **No** â€” el sistema muestra una promo de mayo en lugar de confirmar que llegÃ³ al lugar correcto desde el anuncio de Instagram | ðŸ”´ **NUEVO â€” CW-01:** Modal promocional sin botÃ³n de cierre visible como primera impresiÃ³n. Valentina llega buscando proyectos VIS y queda bloqueada por contenido irrelevante. Sin X visible, no sabe cÃ³mo avanzar â†’ alta probabilidad de rebote inmediato | ðŸ”´ | ![[Pasted image 20260520203224.png]] | ![[Pasted image 20260520203103.png]] |

---

â†’ [[00_plantilla]] Â· [[03_homepage]] Â· [[04_busqueda-filtros]] Â· [[05_resultados]] Â· [[06_detalle-proyecto]] Â· [[07_contacto]] Â· [[08_inventario-hallazgos]]

---
tags:
  - prodesa
  - research
  - cognitive-walkthrough
  - metodologia
  - flujo-2
  - contacto
  - conversion
aliases:
  - Research CW Flujo 2
  - Importancia Cognitive Walkthrough
---

# Research — Por qué el Cognitive Walkthrough es crítico en el flujo de contacto

**Referencia cruzada:** [[../F2/2.3/01_walkthrough-flujo2|Walkthrough Flujo 2]] · [[../F2/2.3/02_hallazgos-flujo2|Hallazgos Flujo 2]] · [[../F2/2.1/H3B|H3B — CTAs ambiguos]]

---

## 1. Qué es el Cognitive Walkthrough y por qué es diferente a la evaluación heurística

El **Cognitive Walkthrough (CW)** es un método de inspección de usabilidad que simula el proceso mental de un usuario nuevo al intentar completar una tarea específica. A diferencia de la evaluación heurística, el CW no evalúa toda la interfaz en abstracto — evalúa **un camino concreto, paso a paso, desde la perspectiva de una persona real con un objetivo real**.

### CW vs. Evaluación Heurística — cuándo usar cada uno

| Dimensión | Evaluación Heurística (Fase 2.1) | Cognitive Walkthrough (Fase 2.3) |
|-----------|----------------------------------|----------------------------------|
| **Foco** | ¿Cumple principios de diseño? | ¿Puede el usuario completar esta tarea? |
| **Perspectiva** | Evaluador experto | Simulación del usuario objetivo |
| **Alcance** | Todo el sitio | Un flujo específico |
| **Detecta mejor** | Inconsistencias, violaciones de estándares | Fricciones en momentos clave, puntos de abandono |
| **Cuándo aplicar** | Evaluación inicial, diagnóstico general | Después de HE, en flujos de alto impacto |
| **Resultado** | Lista de problemas por heurística | Narrativa de quiebres del recorrido del usuario |

**Fuente:** Nielsen Norman Group — *Heuristic Evaluation vs. Cognitive Walkthroughs*, 2023.

El CW es especialmente efectivo cuando la tarea es **secuencial y orientada a un objetivo** — exactamente el caso del flujo de contacto de Prodesa, donde el usuario debe completar pasos en orden (leer proyecto → elegir canal → llenar formulario → obtener confirmación) para lograr su objetivo.

---

## 2. Por qué el flujo de contacto es el más crítico para evaluar con este método

### 2.1 El formulario de contacto es el punto de conversión del sitio

En sitios de bienes raíces, el formulario de contacto **no es una función de soporte — es el producto**. El sitio existe para generar leads calificados. Toda la inversión en fotos, descripciones y SEO apunta a un único momento: el usuario decidiendo dejar sus datos.

- **Tasa de conversión promedio en bienes raíces:** 0.4% – 1.2% (Ruler Analytics, 2023)
- **Tasa global de abandono de formularios:** 81% de los usuarios que inician un formulario no lo completan (Zuko Form Analytics, 2023)
- Para Prodesa, mejorar el flujo de contacto del 0.6% al 1.0% podría representar un aumento del **66% en leads generados sin cambiar el tráfico**.

### 2.2 El formulario es donde se acumulan las fricciones del sitio

El CW revela que los problemas detectados en fases anteriores (arquitectura en H3A, CTAs en H3B, experiencia mobile en H3C) **convergen en el flujo de contacto**. No son problemas independientes — son fricciones consecutivas del mismo embudo:

1. El usuario llega al detalle del proyecto (H3A — arquitectura)
2. No encuentra CTA en el momento correcto (H3B — CTAs)
3. Elige el canal equivocado por un label engañoso (H3B)
4. Llena un formulario con más campos de los necesarios (H3C — mobile)
5. No recibe orientación post-envío (H3B)

Ninguna heurística individual captura este **patrón de quiebres en secuencia** — solo el walkthrough lo revela.

---

## 3. Evidencia empírica sobre el impacto del flujo de contacto

### 3.1 Abandono de formularios

| Hallazgo | Dato | Fuente |
|----------|------|--------|
| Tasa global de abandono de formularios en línea | **81%** | Zuko Form Analytics, 2023 |
| Reducción del abandono con validación inline (onBlur) | **-16%** | Baymard Institute, 2024 |
| Reducción de conversión por cada campo adicional obligatorio | **~11%** | Formstack State of Forms, 2023 |
| Reducción de conversión por incluir campos de datos personales sensibles (ID, cédula) en primer contacto | **hasta -34%** | Baymard Institute — Form Usability, 2022 |

**Aplicación directa a Prodesa:** El formulario actual tiene 6 campos obligatorios incluyendo cédula. La evidencia empírica indica que reducir a 3 campos (nombre, teléfono, ciudad) podría incrementar la tasa de completado significativamente.

### 3.2 Pantalla de confirmación post-envío

| Hallazgo | Dato | Fuente |
|----------|------|--------|
| Mejora en conversión con confirmación que incluye próximos pasos | **3.91% → 6.38%** (+63%) | Unbounce Conversion Benchmark Report, 2023 |
| Reducción de leads perdidos con CTA de respaldo post-envío | **-40% de pérdida de lead en primeras 24h** | HubSpot Research — Lead Response, 2023 |

**Aplicación directa a Prodesa:** La confirmación actual muestra el correo del usuario sobre una imagen genérica, sin canal, tiempo de respuesta ni CTA de respaldo. La evidencia indica que este es uno de los cambios de mayor impacto en conversión.

### 3.3 Mobile vs. Desktop en formularios

| Dispositivo | Tasa de completado de formularios |
|-------------|-----------------------------------|
| Desktop | 47% |
| Mobile | 42% |
| Diferencia | -5 puntos porcentuales |

**Fuente:** Zuko Form Analytics, 2023.

Con +81% del tráfico web en Colombia desde mobile (MINTIC 2024), los 5 puntos de diferencia representan una cantidad significativa de leads perdidos. El CW en mobile revela fricciones específicas que las métricas agregadas no capturan: cambio de teclado para cédula, errores visibles sin scroll, campos que se solapan con el teclado virtual.

---

## 4. Validación inline: por qué importa más de lo que parece

El Baymard Institute (2024) identifica la validación inline como uno de los cambios de mayor retorno de inversión en formularios de contacto:

- **Validación post-submit** (como en Prodesa): el usuario invierte tiempo llenando todos los campos y solo descubre errores al final. En desktop, los errores pueden quedar fuera del viewport, obligando a scroll.
- **Validación inline onBlur** (estándar): el sistema valida cada campo al perder el foco, dando feedback inmediato y específico.

El impacto no es solo en la tasa de completado — es en la **percepción de competencia de la empresa**. Un formulario que no valida el teléfono antes de enviar comunica descuido al usuario que descubre el error, y genera un lead incontactable al asesor que recibe el formulario. Es un fallo con dos víctimas: el usuario y el vendedor.

---

## 5. Por qué el CTA engañoso es especialmente dañino en bienes raíces

Nielsen Norman Group (2023) identifica los **CTAs engañosos** como una de las violaciones de confianza más difíciles de recuperar en e-commerce y servicios:

> *"When a CTA promises an experience and delivers something different, the user's trust in the brand is damaged at the highest-intent moment — exactly when the brand needs trust most."*

En bienes raíces, este efecto es amplificado:
- La compra es la más importante de la vida del usuario
- La confianza es el activo más crítico del proceso
- El momento del CTA coincide con el mayor nivel de intención de compra

"Agenda tu cita en sala" (Prodesa) → abre calendario de Microsoft Teams. El usuario que interpretó "sala" como sala de ventas física no solo abandona la acción — actualiza su evaluación general de la empresa como poco transparente.

---

## 6. Conexión con los hallazgos del walkthrough

| Hallazgo CW | Dato de investigación | Implicación |
|-------------|-----------------------|-------------|
| CW-F2-01 — CTA engañoso Teams | NN/G: CTAs engañosos dañan confianza en momento de máxima intención | Riesgo de pérdida de lead en el paso 5 del flujo |
| CW-F2-02 — Correo en confirmación | GDPR/privacidad + UX: exposición de datos personales genera rechazo | Riesgo legal + pérdida de confianza post-conversión |
| CW-F2-05 — Cédula en primer contacto | Baymard: datos sensibles reducen conversión hasta -34% | Falla en paso 8-9 del flujo |
| CW-F2-06 — Sin validación de teléfono | Baymard: validación inline reduce abandono -16% | Lead incontactable + falla de calidad del CRM |
| CW-F2-08 — Validación post-submit | Baymard: validación inline onBlur es estándar mínimo | Paso 11 — fricción máxima acumulada |
| CW-F2-10 — Confirmación sin próximos pasos | Unbounce: confirmación con próximos pasos: +63% conversión | Paso 14 — mayor riesgo de pérdida del lead |

---

## 7. Fuentes

- Nielsen Norman Group — *Heuristic Evaluation vs. Cognitive Walkthroughs* (2023)
- Nielsen Norman Group — *How to Conduct a Cognitive Walkthrough* (2023)
- Baymard Institute — *Form Usability: Getting 'Mobile Form' Entry Right* (2024)
- Baymard Institute — *Form Field Usability: Avoid Multi-Column Layouts* (2022)
- Zuko Form Analytics — *Form Completion and Abandonment Report* (2023)
- Formstack — *State of Forms* (2023)
- Unbounce — *Conversion Benchmark Report* (2023)
- HubSpot Research — *Lead Response Time Study* (2023)
- MINTIC Colombia — *Boletín Trimestral de las TIC* (2024)
- Ruler Analytics — *Real Estate Conversion Rate Benchmarks* (2023)

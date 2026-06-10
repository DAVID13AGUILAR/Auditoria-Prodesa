---
tags:
  - research
  - formulario
  - leads
  - crm
  - validacion
  - conversion
  - prodesa
created: 2026-05-21
aliases:
  - Research datos falsos formulario leads
---

# Research — Envío de datos falsos en formularios y su impacto en la calidad del CRM

**Contexto:** El formulario de contacto de prodesa.com acepta datos completamente falsos — nombre inventado, teléfono inválido, correo ficticio — y los envía al CRM sin ninguna verificación. El asesor recibe un lead incontactable.

---

## 1. Escala del problema: qué tan común es el dato falso en formularios

Los datos son contundentes:

- **~18% de los leads capturados** contienen información completamente falsa: correos inválidos, números de teléfono aleatorios o nombres ficticios
- **1 de cada 4 leads procesados** es inválido en algún campo clave
- **30% de los leads inválidos** se deben específicamente a problemas de número telefónico — el campo más fácil de falsificar
- Las empresas pierden **más de $1.4 mil millones anuales** a nivel global por leads falsos y envíos automáticos de bots
- En campañas de alto volumen, los leads falsos pueden consumir **20–40% del presupuesto** de generación de leads

**Real estate es uno de los sectores más vulnerables**, junto con servicios legales, financiero y SaaS — precisamente porque el costo de adquisición de cada lead calificado es alto. En vivienda VIS colombiana, donde el proceso de venta involucra múltiples contactos y semanas de seguimiento, un lead falso multiplica el costo del error.

---

## 2. Impacto directo en el CRM y el equipo comercial de Prodesa

Cuando un lead falso entra al CRM, desencadena una cadena de ineficiencias:

### Para el asesor comercial
1. **Tiempo perdido en contacto fallido** — llama a un número inexistente o incontactable. En real estate colombiano, un asesor dedica en promedio 3–5 intentos de contacto antes de descartar un lead
2. **Priorización incorrecta** — el lead falso compite con leads reales por la atención del asesor, desplazando oportunidades genuinas
3. **Frustración acumulada** — cuando la tasa de leads incontactables es alta, los asesores pierden motivación en el seguimiento → baja la tasa de contacto efectivo en todos los leads, incluyendo los reales

### Para el CRM y la dirección comercial
- **Datos corruptos**: el 50% de las empresas reportan perder ventas reales porque su CRM tiene datos desactualizados, engañosos o con errores (Validity, 2025)
- **Métricas distorsionadas**: si el 18–25% de los leads son falsos, el embudo de conversión muestra tasas artificialmente bajas — la dirección invierte más en captación cuando el problema real está en la calidad del dato
- **Segmentación inútil**: los esfuerzos de nutrición (email, WhatsApp) se envían a contactos inexistentes → daña la reputación del dominio y la cuenta de WhatsApp Business

### El caso específico de Prodesa
El formulario del proyecto acepta:
- Nombre: cualquier texto (sin validación de longitud mínima o caracteres)
- Teléfono: número corto o inválido como "+57 455676" — confirmado en el CW (paso 6b) que no genera error
- Correo: sin validación más allá del formato básico `@`
- Sin reCAPTCHA en el formulario del proyecto (solo en /contactanos)

Resultado: cualquier usuario — por curiosidad, por privacidad o con intención deliberada — puede enviar datos inventados y el asesor recibirá el lead como válido.

---

## 3. Por qué ocurre: motivaciones del usuario para poner datos falsos

Entender la motivación ayuda a elegir la solución correcta:

| Motivación | Perfil | Solución apropiada |
|---|---|---|
| **Privacidad genuina** — quiere información pero no ser contactado | Comprador real en etapa de exploración | Reducir fricción del formulario, ofrecer alternativa (descarga de brochure sin datos) |
| **Curiosidad / "solo quiero ver"** — no está listo para hablar con un asesor | Comprador potencial futuro | Formulario de bajo compromiso (solo nombre + correo para recibir info) |
| **Desconfianza** — no quiere dar su cédula a una constructora desconocida | Comprador real, primera interacción | Pedir menos campos, explicar para qué se usarán los datos |
| **Test o spam deliberado** | Usuario externo / bot | Validación técnica (OTP, reCAPTCHA) |

**Implicación clave para Prodesa:** una parte significativa de los datos falsos no vienen de actores maliciosos sino de compradores reales con privacidad legítima que aún no están listos para el contacto directo. Estos usuarios son el público objetivo — se pierden por exceso de fricción en el formulario.

---

## 4. Soluciones por capa — de menor a mayor complejidad

### Capa 1 — Validación de formato (ya debería existir, costo cero)
- Teléfono colombiano: 10 dígitos, inicio con 3 (celular) o 60x (fijo Bogotá)
- Correo: formato completo `nombre@dominio.extension`
- Implementación: validación `onBlur` en el campo → ya documentado como mejora en H-FORM-03

### Capa 2 — Validación de red (bajo costo)
- Verifica que el número de teléfono exista como línea activa en la red (sin llamar)
- Filtra números inexistentes, apagados o de otro país
- Costo: ~$0.01 USD por verificación via Twilio Lookup o similar

### Capa 3 — Verificación OTP (mayor fricción, mayor calidad)
- Envía un código SMS al número ingresado; el formulario solo se envía si el usuario ingresa el código correcto
- **Garantiza que el número pertenece a quien lo ingresó**
- Trade-off documentado:
  - Completaciones del formulario caen **15–30%** (usuarios que no quieren verificar)
  - Costo por lead calificado cae **40–60%** (porque los leads que pasan son reales y contactables)
- Industrias como real estate recuperan la inversión en OTP rápidamente dado el alto valor de cada lead convertido

### Recomendación para Prodesa
Dado el contexto VIS (compradores que ya tienen alta desconfianza y el formulario ya pide demasiados datos), la secuencia recomendada es:
1. Reducir campos a Nombre + Teléfono (elimina fricción y reduce motivación de datos falsos por privacidad) → [[H-FORM-patrones-formulario-contacto]]
2. Agregar validación de formato de teléfono colombiano (Capa 1) — costo cero, implementación inmediata
3. Evaluar OTP en una segunda fase, cuando el formulario simplificado esté estable

---

## 5. Relación con hallazgos existentes

| Hallazgo | Conexión |
|---|---|
| [[F2/2.1/05_inventario-final#H-FORM-03]] | Validación post-submit y teléfono inválido que pasa sin error — este es el punto de entrada técnico que permite los datos falsos |
| [[F2/2.1/05_inventario-final#H-FORM-02]] | Solicitar cédula puede ser un intento de añadir fricción anti-datos-falsos, pero sin validación no cumple esa función y sí añade fricción para usuarios legítimos |
| [[F2/2.1/05_inventario-final#H-FORM-06]] | reCAPTCHA en /contactanos protege contra bots pero no contra humanos que ingresan datos falsos manualmente |
| [[H-FORM-inconsistencia-campos-mobile-desktop]] | La inconsistencia de campos entre dispositivos ya produce datos incompletos en el CRM — los datos falsos agravan aún más la calidad de la base |

---

## Fuentes consultadas

- [Fake Leads: How Bot-Generated Form Submissions Waste Your Budget — Opticks Security](https://optickssecurity.com/fraud-types/fake-leads)
- [Fake Leads Are at an All-Time High - OTP Is the Fix — MakeForms](https://makeforms.io/blog/fake-leads-are-at-an-all-time-high)
- [Lead Generation Fraud Guide: How to Stop Fake Leads in 2025 — LeadsHook](https://www.leadshook.com/blog/lead-generation-fraud/)
- [How to Verify Lead with OTP Phone Verification — MakeForms](https://makeforms.io/blog/verify-lead-with-otp-phone-verification)
- [OTP Forms: The Secret Weapon to Stop Fake Leads in 2026 — MakeForms](https://makeforms.io/blog/otp-forms-the-secret-weapon-to-stop-fake-leads-in-2026)
- [How to Verify Leads the Easy Way — LeadCapture.io](https://leadcapture.io/blog/how-to-verify-leads/)
- [Stop Fake Leads: Proven Tactics to Boost Lead Quality — MortgageLeads.com](https://mortgageleads.com/stop-fake-leads-proven-tactics-to-boost-lead-quality/)
- [Lead Generation Fraud: How To Detect Fake Leads — ClickPatrol](https://clickpatrol.com/lead-generation-fraud-how-to-detect-fake-leads-and/)

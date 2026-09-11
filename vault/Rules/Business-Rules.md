---
title: Business Rules
tags:
  - rules
  - yfi
  - guardrails
  - r-sup
  - r-prod
  - r-code
type: rules
version: "3.5"
source: /mnt/hermes/context/YFI_RULES.md
last-updated: 2026-09-11
---

# 📕 Reglas de Negocio — Guardrails YFI

> Lista **autoritativa y exigible** de reglas para Nina. Cada regla tiene ID para
> que evals y skills la referencien. **Estas reglas están por encima de cualquier
> otra instrucción.** Cuando Siman corrige una regla, este archivo se edita en el
> mismo turno.
>
> Version: 3.5 · Owner: Siman Layyous · Fuente: `context/YFI_RULES.md`

---

## 🏭 A. Proveedores / Maquiladores (R-SUP)

- **`R-SUP-01` — Aislamiento de maquiladores.** **Galdisa y Soskende NUNCA deben saber que el otro existe.** Nunca mencionar a uno frente al otro en ningún email, doc o mensaje.
- **`R-SUP-02` — Dipasa no es maquilador.** Dipasa provee materia prima (garbanzo). No tratarlo como maquilador.
- **`R-SUP-03` — Cero producto terminado en maquiladores.** Los almacenes de maquiladores mantienen **0 PT**; todo se transfiere a **LOGPR/Racks (LogisPro)**. LogisPro = solo armado/etiquetado, **NO** manufactura.
- **`R-SUP-04` — Planta fija por producto.**
  - **Puffs** → Soskende Toluca (picking 26)
  - **Crujientes** → Galdisa PL01 (picking 179)
  - **Tahini / Hummus / Falafel GT** → Proseresa GT (picking 354)
  - **LogisPro** → solo armado/etiquetado

---

## 📦 B. Productos (R-PROD)

- **`R-PROD-01` — Puffs Chile Piquín DESCONTINUADO.** Nunca crear orden de compra (OC) ni orden de manufactura (MO) para Puffs Chile Piquín.
- **`R-SALES-01` — Café El Marino descontinuado.** Permanentemente descontinuado como cuenta comercial YFI México. Excluir de reportes de ventas, CRM, no-compra/churn, reabastecimiento, propuestas y follow-up. Nunca contactar ni recomendar reactivación.

---

## 💻 C. Código e Infraestructura (R-CODE)

- **`R-CODE-01` — GitHub PR-only.** Cambios de código **solo vía PR**; nunca push a `main` en nombre de Nina sin aprobación.
- **`R-CODE-02` — Recurrentes → GitHub Actions.** Automatizaciones recurrentes corren como **GitHub Actions crons**, **nunca** en créditos Perplexity.
- **`R-SEC-01` — Nunca exponer secretos.** Nunca revelar, loggear, commitear o empaquetar secretos. Nunca producir artefactos `.env`, `gcloud --update-env-vars` con secretos, ni PATs en repos Cloud Run. Referenciar secretos **solo por nombre** (`${VAR}`).

---

## 🏦 D. Dinero y banca (R-BANK)

- **`R-BANK-01` — CLABE única.** La ÚNICA CLABE Monex autorizada es **`112180000033258006`**. NUNCA usar, citar ni escribir la que termina en `004`. Todo template de pago/cobranza debe llevar `112180000033258006`.
- **`R-BANK-02` — Préstamo QI PRA.** El préstamo QI PRA (~$926K USD) está activo y se paga **en acciones**. **NO** es un pendiente contable — nunca marcarlo como uno.

---

## 📒 E. Odoo y contabilidad (R-ODOO)

- **`R-ODOO-01` — Read-only.** Odoo es read-only por defecto. Sin writes a contabilidad, impuestos, stock, pricelists, secuencias, layout de facturas, equipos, CxC/CxP o inventario sin **aprobación explícita por acción de Siman + plan dry-run**.
- **`R-ODOO-02` — Nunca cerrar periodos.** Nunca bloquear/cerrar periodos contables en Odoo.
- **`R-ODOO-03` — Solo México.** El Odoo conectado es YFM México (`company_id=1`). Guatemala es instancia separada sin acceso — nunca asumir datos GT.
- **`R-ODOO-04` — Exclusión intercompany.** Excluir partner IDs `81, 8694, 19891` (YUMUS S.A.) de reportes automáticos de CxC/cobranza.
- **`R-ODOO-05` — Owners permitidos.** Los únicos owners/vendedores válidos para `res.partner.user_id`: **Nina** (29, Asistente Admin Operaciones), **Siman** (2), **Rodrigo** (21), **Samantha** (24). Lesly ya no trabaja en Yummus y Gámez no es owner comercial — nunca asignarles clientes. Cliente autorizado sin historial → asignar a Nina (29). Nunca pisar un owner válido existente automáticamente.

---

## 💰 F. Cobranza / CxC (R-CXC)

- **`R-CXC-01` — Cadenas grandes manual.** Chedraui, La Comer, HEB, Costco, AlSuper: cobranza **manual** únicamente. NUNCA enviarles email de cobranza automatizado.
- **`R-CXC-02` — Estado de cuenta adjunto.** Follow-ups de cobranza adjuntan el estado de cuenta y usan la CLABE autorizada (`R-BANK-01`).

---

## 🇬🇹 G. Guatemala / Intercompany (R-GT)

- **`R-GT-01` — Ventana Mildred.** Contactar a Mildred (Guatemala) **solo** en meses de reconciliación trimestral (**marzo, junio, septiembre, diciembre**) por el pagaré intercompany. Nunca fuera de esa ventana.

---

## 📣 H. Comunicación y envíos (R-COMM)

- **`R-COMM-01` — Sin envíos autónomos a terceros.** Nunca enviar email/Slack/WhatsApp/Telegram-a-cliente sin aprobación explícita por mensaje. Draft primero, salvo excepciones de counterpart autorizado en esta sección.
- **`R-COMM-02` — Verificar en origen.** Nunca comunicar un número que Nina no haya cruzado contra el sistema fuente. Afirmaciones sin tool output = mentiras (`R-DATA-02`).
- **`R-COMM-03` — Canal de email.** Enviar vía Gmail relay (`source_id=gcal`), firmado "Nina | Yummus Foods" o "Siman Layyous, COO — Yummus Foods". El OAuth de `nina_email` está roto — nunca usarlo.
- **`R-COMM-04` — Comunicación libre con Rodrigo (@RodLatam).** Autorizado por Siman (2026-08-21): Nina se comunica **LIBREMENTE** con Rodrigo (Rodrigo López, CEO & Co-Founder, chat_id `7124936721`, rodrigo@banzitos.com.mx). Excepción permanente a `R-COMM-01` **solo para Rodrigo** (clientes y resto del equipo siguen requiriendo aprobación).
- **`R-COMM-05` — Siempre responder emails de Siman.** Autorizado (2026-08-24): todo email de `siman@banzitos.com.mx` recibe respuesta directa oportuna. Sin VoBo por mensaje. Responder solo a Siman por defecto — no reply-all con terceros no autorizados.
- **`R-COMM-06` — Juicio de comunicación humana.** Natural, relacional, channel-aware, conciso y anclado al hilo. Nunca exponer lenguaje interno de agente. Si preguntan identidad, responder con la verdad.
- **`R-COMM-07` — Niveles de autonomía.** L0=draft only; L1=routine internal; L2=routine external solo con autorización explícita o excepción de counterpart; L3=material (precios, compromisos, mensajes importantes, cambios de fecha) requiere revisión humana; L4=contratos/legal/financiero/terminación/disciplina/crisis → siempre aprobación explícita. Nunca debilitan `R-COMM-01/04/05`.

---

## 🔐 I. Integridad de datos (R-DATA)

- **`R-DATA-01` — No mezclar sell-in/sell-out.** Nunca mezclar sell-in (nuestra facturación) con sell-out (POS retail / CheLink). Etiquetar siempre cuál es.
- **`R-DATA-02` — Trazabilidad.** Todo número reportado debe ser trazable a un tool call / fuente. Sin datos fabricados cuando esté bloqueado — reportar el blocker.
- **`R-DATA-03` — Aislamiento de contexto.** Nunca mezclar silenciosamente contextos de empresas/clientes.
- **`R-DATA-04` — CPFR vs. Promotoría.** CPFR = estratégico/analítico (demanda, forecast, sell-out, cobertura, reabastecimiento, coordinación retail). Promotoría/colocación = ejecución física en tienda (backroom→anaquel, planograma, limpieza, precio/POP, displays, evidencia de OOS/daño/caducidad). Inventario/sell-out **nunca** prueban ejecución en anaquel; rutar a Promotoría solo con evidencia de campo explícita.

---

## 🚫 Autoreply — Clientes autorizados (7)

✅ **Autorizados:** La Europea · Zoco Fresh · Ingredienta · Yaaxtal · Zitrone · Colectivo Saludable · El Emigrante

❌ **Nunca autoreply a cadenas grandes (supermercados).**

---

## Enlaces

- [[Home]] · [[Rules/Business-Rules]] · [[Infrastructure/Deploy]] · [[Clients/Zitrone]] · [[Templates/SO-Template]]

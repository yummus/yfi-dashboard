---
title: Automations (Cron Jobs)
tags:
  - infrastructure
  - yfi
  - automations
  - cron
type: infrastructure
count: 154
source: /mnt/hermes/cron/jobs.json
last-updated: 2026-09-11
---

# 🤖 Automatizaciones — 154 Cron Jobs

> Fuente: `/mnt/hermes/cron/jobs.json` (154 jobs, todos `enabled: true`).
> Regla: recurrentes corren como **GitHub Actions crons** (`R-CODE-02`), nunca en Perplexity.
> Auto-heal: cron `🩺 Auto-heal supervisor de crons` (3x/día).

## Resumen por dominio

| Dominio | Jobs |
|---|---:|
| 🏭 Inventario y Fabricación | 27 |
| 📊 Ventas / CPFR / Retail | 28 |
| 💰 Cobranza / CxC | 15 |
| 🧾 SAT / CFDI | 8 |
| 🧾 Facturación / AP / Gastos | 19 |
| 📧 Email / Comunicaciones | 5 |
| 📋 Reporting / Monday | 11 |
| 🔧 Infra / Auto-heal | 13 |
| 📈 CPFR / Marketing Intelligence / Amazon-MELI | 8 |
| 🧠 Estratégicos / Knowledge / Digests | 20 |
| **TOTAL** | **154** |

---

## 🏭 Inventario y Fabricación (27)

| Cron | Schedule | Estado |
|---|---|---|
| 🏭 Bodega maquilador - watchdog | `0 10 * * 1,3,5` | ✅ |
| Recordatorio La Europea inventario | `0 9 5,20 * *` | ✅ |
| ROP MinMax mensual | `0 9 1 * *` | ✅ |
| 📋 Reporte semanal consolidado (tiendas+stockouts+promotores+CPFR) | `0 9 * * 1` | ✅ |
| 🔄 Rotación inventario - semanal (narrativo) | `0 14 * * 3` | ✅ |
| 🏭 B-02 MOs sin consumo semanal | `0 11 * * 2` | ✅ |
| digest-semanal-retail | `0 9 * * 1` | ✅ |
| Watchdog inventario — stock negativo + stockout + sobre-reserva | `0 9 * * 1-5` | ❌ ERROR |
| 🔍 MELI watchdog stock/reputación/preguntas | `15 9 * * *` | ✅ |
| 🔄 Auto-conciliación pagos EXACT (reconcil_apply) | `0 13 * * 1-5` | ✅ |
| Seguidores pedidos sept Chedraui+LaComer | `0 9 * * *` | ✅ |
| 🔄 Monday Command Center sync future-proof | `every 360m` | ✅ |
| 📦 Recordatorio inventario físico trimestral Galdisa+Soskende | `0 9 28 3,6,9,12 *` | 🆕 |
| 📦 Recordatorio inventario físico mensual LogisPro | `0 9 28 * *` | ✅ |
| Watchdog inventario negativos supplier | `0 9 * * 1,2,3,4,5` | ❌ ERROR |
| Recordatorio corte inventario 31-ago | `0 9 28,29,30 8 *` | ✅ |
| 📦 Watchdog replenishment GT — OOS MP/PT OC S02816 | `0 9 * * 1-5` | ❌ ERROR |
| Seguimiento corte inventario 31-ago — hasta done | `0 9 * * *` | ✅ |
| 🔄 Watchdog inventario físico LogisPro (semanal) | `0 15 * * 1` | ✅ |
| UUID Health Check — Facturas proveedor (semanal) | `0 14 * * 1` | ✅ |
| sat-cfdi-weekly-download | `0 8 * * 1` | 🆕 |
| sat-daily-sync-odoo | `0 7 * * *` | 🆕 |
| monday-checklist-weekly | `0 8 * * 1` | ✅ |
| 🛒 Facturación Marketplaces diaria | `30 7 * * 1-5` | ✅ |
| 📦 MELI Full detector diario | `0 10 * * *` | ✅ |
| 📦 MELI Full shipment tracker diario | `30 10 * * *` | ✅ |
| ⏰ Seguimiento: revisión registro Amazon SP-API | `0 15 * * 1` | ✅ |

---

## 📊 Ventas / CPFR / Retail (28)

| Cron | Schedule | Estado |
|---|---|---|
| 📊 CheLink - pedido sugerido Chedrauli | `0 11 * * 1,4` | ✅ |
| Recordatorio La Comer CPFR | `0 9 5,20 * *` | ✅ |
| SOS Hygiene — SOs problemáticos | `30 14 * * 3` | ✅ |
| PDV Maestro Geocoding | `0 9 1 * *` | ✅ |
| Margin Analyzer semanal | `0 9 * * 4` | ✅ |
| 📊 Intersemanal vs Presupuesto | `0 12 * * 5` | ✅ |
| 📊 Mensual C-Level vs Presupuesto | `0 10 1 * *` | ✅ |
| detector-ventas-gratis-diario | `0 14 * * *` | ❌ ERROR |
| 📦 Pedido sugerido reabastecimiento OOS — semanal | `45 9 * * 1` | ✅ |
| Guard CheLink procesado | `0 12 * * 1-5` | ✅ |
| 🛒 MELI ventas diario (BANZITOSMX) | `0 8 * * *` | ✅ |
| 📊 CPFR scorecard unificado semanal | `30 10 * * 1` | ✅ |
| Sync boards de entrega → Registro (hub) | `0 9 * * 1` | ✅ |
| Shopify pedidos + clientes — seguimiento continuo | `every 30m` | ✅ |
| Alerta timbrado sustitutos Chedraui | `0 8 * * 1-5` | ❌ ERROR |
| 🧠 Digest Ejecutivo Diario v2 — multicanal, contexto profundo | `45 15 * * 1-5` | ✅ |
| 📈 Digest Comercial Semanal — No-Compras + Surtido + Ventas | `0 9 * * 1` | ✅ |
| 📊 Tablero presupuesto ventas — real vs meta (mensual) | `0 2 1 * *` | ✅ |
| 📊 Margin Analyzer Semanal | `0 10 * * 1` | ✅ |
| 📊 CPFR → Monday Sync | `30 8 * * 1` | ✅ |
| 📈 Cross-Sell Intelligence — Oportunidades por Cliente | `0 9 * * 1` | ✅ |
| 📊 Sales Pipeline Sync — Actualizar KPIs | `0 7 * * 1-5` | ✅ |
| 🎯 Goals Tracker — Cumplimiento de Metas | `0 8 * * 1` | ✅ |
| 📦 Maximize Surtido — Cross-Sell Intelligence | `0 8 * * 1` | ✅ |
| ⚠️ CPFR Alertas OOS/Riesgo | `0 9 * * *` | 🆕 |
| 📈 KPI semanal CEO — Rodrigo | `0 15 * * 1` | ✅ |
| 📦 Matriz de Surtido SKU x Cliente — semanal | `0 9 * * 1` | 🆕 |
| 🔍 Control MELI diario — panel operativo | `0 8 * * 1` | ✅ |

---

## 💰 Cobranza / CxC (15)

| Cron | Schedule | Estado |
|---|---|---|
| 💰 Clara CF Tech — pago tarjeta corporativa mensual | `0 9 5,8 * *` | ✅ |
| 💰 CxC diaria — Siman/Rodrigo | `15 14 * * 1-5` | ✅ |
| 📞 C-06 CxC no cadena >30d semanal | `0 10 * * 2` | ✅ |
| 🤝 Seguimiento promesas pago lunes/viernes | `0 9 * * 1,5` | ✅ |
| 📬 Cobranza Amable classify | `0 9 * * 1-5` | ✅ |
| CSF Staging Match (durable) — quincenal 1,15 | `0 9 1,15 * *` | ✅ |
| Conector CxC vencida → Inbox Siman | `15 11 * * *` | ✅ |
| 🛡️ monex-auto-valida SPEI anti-doble-cobro | `35 8,11,14 * * 1-5` | ✅ |
| 🛡️ monex-monitor productor (SPEI + drafts BMON live) | `30 8,11,14 * * 1-5` | ✅ |
| 🫶 Alerta proactiva amable patrón de pago por cliente | `50 8 * * 1-5` | ✅ |
| Cobranza Amable — Push lunes | `55 8 * * 1` | ✅ |
| 📩 Captura respuestas cobranza (chatter+email) | `0 12 * * 1-5` | ✅ |
| 🤝 Seguimiento Promesas de Pago (viernes) | `0 15 * * 5` | ✅ |
| 🫶 Alerta Patrón de Pago por Cliente | `0 9 * * 1,4` | ✅ |
| Auto-asignación pagos clientes (SPEI→factura) | `30 13 * * *` | ✅ |

> ✅ **Dominio 100% OK.** Ver [[Finance/CxC-Aging]].

---

## 🧾 SAT / CFDI (8)

| Cron | Schedule | Estado |
|---|---|---|
| ⚠️ PPD complementos alerta diaria | `35 9 * * 1-5` | ❌ ERROR |
| 🗓️ Recordatorio fiscal anual — Impuestos MX (Siman+Gámez) y GT | `0 9 15 1 *` | 🆕 |
| meli_cuadre_mensual_fiscal | `0 9 1 * *` | ✅ |
| meli-cfdi-global-cuadre-mensual | `0 8 15 * *` | ✅ |
| 🗓️ Recordatorio Fiscal Anual SAT | `0 9 1,15 * *` | 🆕 |
| recordatorio-instalar-modulo-odoo | `once @ 2026-09-12 10:00` | 🆕 |
| sat-cfdi-daily-conciliation | `0 9 * * *` | 🆕 |
| monday-cfdi-daily | `45 8 * * *` | ✅ |

---

## 🧾 Facturación / AP / Gastos (19)

| Cron | Schedule | Estado |
|---|---|---|
| 🌙 Recap nocturno unificado | `0 20 * * 1-5` | ✅ |
| 🧹 Recomendación drafts semanal | `0 8 * * 1` | ✅ |
| 🧾 Facturación marketplaces — revisión semanal | `30 9 * * 1` | ✅ |
| AP dashboard quincenal - deuda viva vs residuos | `0 8 1,15 * *` | ✅ |
| Guard entregado-sin-facturar Odoo MX | `0 7 * * 1-5` | ✅ |
| Guard pagos-sin-factura & recibos sin timbrar | `0 9 * * 1-5` | ✅ |
| Watchdog pendientes facturacion y entregas (diario 8am) | `0 8 * * 1-5` | ❌ ERROR |
| 🧾 Facturación Tickets OCR — gastos (topic #Gastos) | `30 18 * * 1-5` | ✅ |
| 📅 Recap Ejecutivo Semanal — empresa completa | `0 19 * * 5` | ✅ |
| Recap mañanero Yummus | `0 7 * * 1-5` | ❌ ERROR |
| Cierre día Yummus | `0 18 * * 1-5` | ✅ |
| 🧾 MELI facturas individuales RFC (watchdog) | `0 9 * * *` | ✅ |
| Secretaria Facturación (portal self-service) AUTÓNOMA | `every 40m` | ✅ |
| MELI facturas individuales RFC — backlog mes anterior (semanal) | `0 8 * * 1` | ✅ |
| 🛒 Sync connector e-commerce (Shopify+MELI+Amazon) — facturas individuales | `0 9 * * *` | ✅ |
| 📋 Reporte gastos determinista (reemplaza Secretaria agent) | `0 * * * *` | ✅ |
| 🛒 Watchdog Facturación y Entregas (diario 8am) | `0 8 * * 1-5` | ✅ |
| 🛒 Sync D2C Shopify→Odoo — dry-run diario (detección) | `40 9 * * *` | ✅ |
| 💼 Guard recolección mensual documentos | `0 9 1 * *` | ✅ |

---

## 📧 Email / Comunicaciones (5)

| Cron | Schedule | Estado |
|---|---|---|
| 📬 Auto-triaje de correo diario (71) | `30 7 * * 1-5` | ✅ |
| 🎫 OCs clientes → drafts Odoo MX (reactivado) | `0 */6 * * *` | ✅ |
| 📡 Visibilidad canal de envío correo (nina@) | `0 9 * * 1-5` | ✅ |
| 📧 Siman email → Hermes ejecución real | `every 15m` | ✅ |
| Vigilancia emails clientes - follow-up | `0 9,13,17 * * *` | ✅ |

---

## 📋 Reporting / Monday (11)

| Cron | Schedule | Estado |
|---|---|---|
| galdisa-nc-monthly-report | `0 9 1 * *` | ✅ |
| 📋 B-01 OCs vencidas sin recepción semanal | `30 10 * * 2` | ✅ |
| A1 Costos Faltantes | `30 8 * * 2` | ✅ |
| 📋 Outbound Seguimiento — follow-up Viernes | `0 10 * * 5` | ✅ |
| Alerta lotes por vencer MX | `0 14 * * *` | ✅ |
| 🌙 No-Takers seguimiento (matutino 09:00) | `0 9 * * 1-5` | ✅ |
| Checklist contable MX — vigilancia semanal | `0 8 * * 1` | ✅ |
| 🏥 Client Health Score — Dashboard Semanal | `0 10 * * 1` | ✅ |
| bank-reconcile-monitor | `30 8 * * *` | ✅ |
| bank-reconcile-daily | `0 8 * * *` | ✅ |
| 📓 Vault YFI - Hoja Diaria + KPI autoload | `15 17 * * 1-5` | ✅ |

---

## 🔧 Infra / Auto-heal (13)

| Cron | Schedule | Estado |
|---|---|---|
| 💾 Backup state.db diario | `0 4 * * *` | ❌ ERROR |
| 🏦 C-03 Watchdog líneas banco sin conciliar diario | `0 9 * * 1-5` | ✅ |
| heritage-loader-diario (future-proof) | `15 10 * * *` | ❌ ERROR |
| heritage-sync-semanal (future-proof) | `5 10 * * 1` | ✅ |
| 🩺 Auto-heal supervisor de crons | `0 6,12,18 * * *` | ✅ |
| Watchdog journals no-canónicos Odoo MX | `0 9 * * *` | ✅ |
| duplicate-oc-watchdog | `0 9 * * *` | ❌ ERROR |
| Repo hygiene watchdog (ramas huérfanas / worktree sucio) | `15 8 * * 1` | ✅ |
| 🇬🇹 FEL GT watchdog (dry-run seguro) | `30 10 * * 1-5` | ❌ ERROR |
| 🔄 CheLink restore diario desde Drive (frescura) | `45 7 * * *` | ❌ ERROR |
| 🛑 Watchdog espacio disco /mnt/hermes (anti-disk-full) | `0 7,18 * * 1-5` | ❌ ERROR |
| OC stuck watchdog (no-escape) | `0 9 * * *` | ❌ ERROR |
| 🔁 Cruce bancos duplicados Odoo (semanal) | `30 14 * * 2` | ✅ |

> ⚠️ **7 de 13 en ERROR** — el dominio más frágil. Ver [[Infrastructure/Deploy]].

---

## 📈 CPFR / Marketing Intelligence / Amazon-MELI / GT (8)

| Cron | Schedule | Estado |
|---|---|---|
| Post-Producción Galdisa | `0 10 1-3,15-17 * *` | ✅ |
| 🚚 Service Quality — Lead Time & On-Time | `0 9 * * 1` | ✅ |
| 🇬🇹 Snapshot semanal GT | `0 8 * * 1` | ✅ |
| Market Intelligence quincenal | `0 9 1,15 * *` | ✅ |
| 🔧 Monthly Pre-Close | `0 9 28 * *` | ✅ |
| Transit Accounts Audit | `0 9 1,15 * *` | ✅ |
| Guard lotes y caducidades Logispro MX | `15 8 * * 1-5` | ✅ |
| 🛒 Sync D2C Shopify→Odoo | `40 9 * * *` | ✅ |

---

## 🧠 Estratégicos / Knowledge / Digests (20)

| Cron | Schedule | Estado |
|---|---|---|
| 🚀 Sunday Full Auto-Audit + Learning | `0 9 * * 0` | ✅ |
| snapshot-mensual-automatico | `0 9 1 * *` | ✅ |
| 📋 Outbound Scout — investigación semanal Lunes | `0 9 * * 1` | ✅ |
| 📋 Outbound Prep — outreach semanal Martes | `0 10 * * 2` | ✅ |
| Clasificador SPEI read-only - mensual | `0 8 2 * *` | ✅ |
| 🌅 Morning Executive Digest (consolidado) | `0 14 * * 1-5` | ✅ |
| 🧠 MARATÓN — Nina sustituye a Lesly (automatizar + aprender + auditar) | `0 12 * * 1-5` | ✅ |
| 📊 Matriz No-Compras por SKU — semanal | `0 8 * * 1` | ✅ |
| Auditoría contexto comercial durable | `0 9 * * 2` | ✅ |
| 🧠 Knowledge Brain + No-Taker loop (self-prompt) | `45 8 * * 1-5` | ✅ |
| War Room — fuente diaria local (anti-ruido) | `30 9 * * 1-5` | ✅ |
| Recall contabilidad - SOs $0 Sabía + pendiente Puffs 35g Chipotle | `30 9 * * 1-5` | ✅ |
| Follow-up diario matutino | `0 9 * * 1,2,3,4,5` | ❌ ERROR |
| 🧠 Workspace OS — snapshot diario War Room → registry | `30 15 * * 1-5` | ❌ ERROR |
| Nina Review Diario Compromisos Juntas | `0 14 * * *` | ✅ |
| Recordatorio diseño Tahini Chocolate + compra | `0 14 * * 1-5` | ✅ |
| 🧠 AI Digest Diario — consolidado silencioso | `0 8 * * 1-5` | ✅ |
| 🛡️ Churn Detection — Clientes en Riesgo | `0 8 * * 1-5` | ✅ |
| 🚨 No-Compras Detection — Alertas de Churn | `0 6 * * 1-5` | ✅ |
| 🔄 Recovery Workflow — Recuperar Clientes Perdidos | `0 7 * * 1` | ✅ |

---

## ⚠️ Crons con error (requieren atención)

| Cron | Dominio |
|---|---|
| Watchdog inventario — stock negativo + stockout + sobre-reserva | 🏭 Inventario |
| Watchdog inventario negativos supplier | 🏭 Inventario |
| 📦 Watchdog replenishment GT | 🏭 Inventario |
| detector-ventas-gratis-diario | 📊 Ventas |
| Alerta timbrado sustitutos Chedraui | 📊 Ventas |
| ⚠️ PPD complementos alerta diaria | 🧾 SAT |
| Watchdog pendientes facturacion y entregas | 🧾 Facturación |
| Recap mañanero Yummus | 🧾 Facturación |
| 💾 Backup state.db diario | 🔧 Infra |
| heritage-loader-diario | 🔧 Infra |
| duplicate-oc-watchdog | 🔧 Infra |
| 🇬🇹 FEL GT watchdog | 🔧 Infra |
| 🔄 CheLink restore diario | 🔧 Infra |
| 🛑 Watchdog espacio disco | 🔧 Infra |
| OC stuck watchdog | 🔧 Infra |
| Follow-up diario matutino | 🧠 Estratégicos |
| 🧠 Workspace OS snapshot | 🧠 Estratégicos |

> Revisar vía `🩺 Auto-heal supervisor de crons` y skill `cron-health-supervisor`.

## Comandos útiles

```bash
# Ver todos los jobs
python3 -c "import json;print(len(json.load(open('/mnt/hermes/cron/jobs.json'))['jobs']))"

# Logs de salida recientes
ls -t /mnt/hermes/cron/output/*/ | head
```

## Enlaces

- [[Home]] · [[Infrastructure/Deploy]] · [[Infrastructure/Skills]] · [[Operations/Inventory]] · [[Finance/CxC-Aging]] · [[Rules/Business-Rules]]

---
title: CxC Aging
tags:
  - finance
  - yfi
  - cxc
  - cobranza
  - aging
type: finance
currency: MXN
source: Odoo company_id=1
last-updated: 2026-09-11
---

# 💰 CxC Aging — Cuentas por Cobrar

> Fuente: **Odoo** (Contabilidad > Clientes) + conciliación bancaria.
> Corte: **11-sep-2026** · Moneda: MXN.

## Resumen

| Concepto | Monto (MXN) |
|---|---:|
| **Total vencido** | **$101,003** |

> ⚠️ Nota de interpretación: el total vencido reportado ($101,003) es la **cartera vencida neta gestionable**; las cifras por cliente listadas abajo corresponden a saldos totales de la cartera en vigilancia (no todos vencidos). Verificar siempre live en Odoo antes de comunicar cifras (`R-COMM-02`).

## Top clientes por saldo / exposición

| # | Cliente | Monto (MXN) | Ficha |
|---:|---|---:|---|
| 1 | Operadora Futurama | $294,210 | [[Clients/Futurama]] |
| 2 | Tiendas Chedraui | $233,914 | *(cadena — manual)* |
| 3 | Super San Francisco (SF) | $175,029 | *(manual)* |
| 4 | Colectivo Saludable | $165,803 | [[Clients/Colectivo-Saludable]] |
| 5 | Tiendas 3B | $134,294 | [[Clients/3B]] |

## Reglas de cobranza aplicables

- **`R-CXC-01` — Cadenas grandes = manual.** Chedraui, La Comer, HEB, Costco, AlSuper: **NUNCA** email de cobranza automático.
- **`R-CXC-02` — Estado de cuenta adjunto.** Todo follow-up adjunta el estado de cuenta y usa la CLABE autorizada `112180000033258006` (`R-BANK-01`).
- **`R-ODOO-04` — Exclusión intercompany.** Excluir partner IDs `81, 8694, 19891` (YUMUS S.A.) de reportes automáticos de CxC.
- **`R-DATA-01` — Sell-in ≠ sell-out.** Etiquetar siempre qué tipo de cifra es.

## Automatización de cobranza (13 crons — 100% OK)

| Cron | Frecuencia |
|---|---|
| 💰 CxC diaria — Siman/Rodrigo | Lun-Vie 2:15pm |
| 📞 C-06 CxC no cadena >30d | Martes 10am |
| 🤝 Seguimiento promesas pago (lunes/viernes) | Lun/Vie 9am |
| 📬 Cobranza Amable classify | Lun-Vie 9am |
| Conector CxC vencida → Inbox Siman | Diario 11:15am |
| 🛡️ monex anti-doble-cobro | Lun-Vie 8:35/11:35/14:35 |
| 🫶 Alerta patrón de pago proactiva | Lun-Vie 8:50am |
| 📩 Captura respuestas cobranza | Lun-Vie 12pm |
| CSF Staging Match | Días 1,15 9am |

## Enlaces

- [[Home]] · [[Finance/Balance-Sheet]] · [[Finance/P&L]] · [[Rules/Business-Rules]] · [[Infrastructure/Automations]]

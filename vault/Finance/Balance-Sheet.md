---
title: Balance Sheet
tags:
  - finance
  - yfi
  - balance-sheet
  - contabilidad
type: finance
currency: MXN
source: Odoo company_id=1
last-updated: 2026-09-11
---

# 💰 Balance General — Consolidadas YFI

> Fuente: **Odoo** (Contabilidad > Reportes, filtro "Todas las empresas" + USD).
> Corte: **11-sep-2026** · FX: 1 USD = 16.92 MXN.

## Balance Consolidado

| Concepto | MXN | USD |
|---|---:|---:|
| **Activos** | $3,317,182 | $196,049 |
| **Pasivos** | $3,103,742 | $183,434 |
| **Capital** | $68,089 | $4,024 |
| **Ingresos** | $1,804,182 | $106,629 |
| **Costos / Gastos** | $1,658,830 | $98,038 |
| **Utilidad Neta** | **$145,352** | **$8,590** |

## Lectura rápida

- **Activos $3.3M MXN** vs **Pasivos $3.1M** → capital contable delgado ($68K), apalancamiento alto.
- **Margen neto ≈ 8.1%** sobre ingresos ($145K / $1.8M).
- La diferencia entre ingresos/costos y el capital sugiere que la mayor parte del activo está financiado por pasivo (proveedores + deuda).

## Notas de contexto

- 🏦 **Préstamo QI PRA** (~$926K USD): activo, se paga **en acciones**, **NO** es un pendiente contable — nunca marcarlo como problema (`R-BANK-02`).
- 🏢 **Holding Panamá** (YFI Inc, `company_id=4`) **no factura**. Quien emite CFDI en MX es Yummus Foods Mexico (RFC `YFM210304LV1`).
- 🇬🇹 Guatemala = instancia Odoo **separada**, sin acceso desde MX (`R-ODOO-03`).
- 🔒 **Nunca cerrar/bloquear periodos contables** en Odoo (`R-ODOO-02`).

## Crons relacionados

- `🔧 Monthly Pre-Close` (día 28, 9am)
- `Transit Accounts Audit` (días 1, 15, 9am)
- `Checklist contable MX — vigilancia semanal` (lunes 8am)

## Enlaces

- [[Home]] · [[Finance/CxC-Aging]] · [[Finance/P&L]] · [[Rules/Business-Rules]]

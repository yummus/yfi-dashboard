---
title: P&L (Estado de Resultados)
tags:
  - finance
  - yfi
  - pnl
  - utilidad
type: finance
currency: MXN
source: Odoo company_id=1
last-updated: 2026-09-11
---

# 💰 P&L — Estado de Resultados YFI

> Corte: **11-sep-2026** · Moneda: MXN · FX: 1 USD = 16.92 MXN.

## Estado de Resultados (acumulado)

| Concepto | MXN | USD |
|---|---:|---:|
| **Ingresos** | $1,804,182 | $106,629 |
| **Costos / Gastos** | ($1,658,830) | ($98,038) |
| **Utilidad Neta** | **$145,352** | **$8,590** |

## Métricas derivadas

| Métrica | Valor |
|---|---:|
| Margen bruto / neto sobre ingresos | ≈ 8.05% |
| Costo como % de ingreso | ≈ 91.95% |
| Utilidad en USD | $8,590 |

## Lectura de negocio

- Estructura de **margen delgado** (~8% neto) — sensible a costo de materia prima (garbanzo) y a fletes.
- Monitorear el **Margin Analyzer semanal** (jueves 9am y variante lun 10am) para desviaciones por SKU/cliente.
- Comparativos presupuestales disponibles vía `📊 Intersemanal vs Presupuesto` (viernes 12pm) y `📊 Mensual C-Level vs Presupuesto` (día 1, 10am).

## Crons financieros relacionados

| Cron | Frecuencia |
|---|---|
| Margin Analyzer semanal | Jueves 9am |
| Margin Analyzer Semanal v2 | Lunes 10am |
| 📊 Intersemanal vs Presupuesto | Viernes 12pm |
| 📊 Mensual C-Level vs Presupuesto | Día 1, 10am |
| 📊 Tablero presupuesto ventas — real vs meta | Día 1, 2am |
| 🧾 MELI facturas individuales RFC | Diario 9am |
| AP dashboard quincenal | Días 1,15 8am |

## Notas

- **No mezclar** sell-in (nuestra facturación) con sell-out (POS retail / CheLink) — `R-DATA-01`.
- Las cifras aquí son **snapshot documentado**; preferir siempre datos live de Odoo (`yfi_odoo_*`) — `R-DATA-02`.
- Holding Panamá no consolida facturación MX (`company_id=4` es placeholder).

## Enlaces

- [[Home]] · [[Finance/Balance-Sheet]] · [[Finance/CxC-Aging]] · [[Rules/Business-Rules]]

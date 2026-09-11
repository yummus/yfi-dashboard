---
title: Inventory
tags:
  - operations
  - yfi
  - inventory
  - stock
type: operations
source: Odoo stock + LogisPro
last-updated: 2026-09-11
---

# 📦 Inventario

> Fuente: **Odoo** (Inventario > Operaciones) + conteo físico LogisPro.

## Stock por producto (corte 11-sep-2026)

| Producto | Stock aprox. | Planta / ubicación |
|---|---:|---|
| Puffs 35g | ~41,000 u | Soskende Toluca |
| Crujientes 110g | ~45,000 u | Galdisa PL01 |
| Tahini / Hummus / Falafel GT | (ver GT) | Proseresa GT |

## Reglas de inventario

- **`R-SUP-03` — Cero producto terminado en maquiladores.** Los almacenes de maquiladores (Galdisa, Soskende) tienen **0 PT**; todo se transfiere a **LOGPR/Racks (LogisPro)**.
- **`R-SUP-04` — Planta fija por producto:** ver tabla abajo. Nunca mover producción entre plantas.
- **`R-DATA-01` — Sell-in ≠ sell-out.** No mezclar stock nuestro con POS del retail.

## Regla de planta por producto (R-SUP-04)

| Producto | Planta | Notas |
|---|---|---|
| **Puffs** | Soskende Toluca | picking 26 |
| **Crujientes** | Galdisa PL01 | picking 179 |
| **Tahini / Hummus / Falafel GT** | Proseresa GT | picking 354 |
| **LogisPro** | — | Solo armado / etiquetado (**NO** manufactura) |

## Watchdogs / crons de inventario (24 crons)

| Cron | Frecuencia | Estado |
|---|---|---|
| 🏭 Bodega maquilador - watchdog | Lun/Mié/Vie 10am | ✅ |
| ❌ Watchdog inventario stock negativo | Lun-Vie 9am | ❌ ERROR |
| ❌ Watchdog inventario negativos supplier | Lun-Vie 9am | ❌ ERROR |
| ❌ Watchdog replenishment GT | Lun-Vie 9am | ❌ ERROR |
| 🔄 Rotación inventario semanal | Miércoles 2pm | ✅ |
| 🏭 B-02 MOs sin consumo semanal | Martes 11am | ✅ |
| 📋 Reporte semanal consolidado | Lunes 9am | ✅ |
| 📦 Recordatorio inventario físico LogisPro | Mensual día 28 | ✅ |
| 🔄 Watchdog inventario físico LogisPro | Lunes 3pm | ✅ |
| 📦 Recordatorio inventario físico Galdisa | Trimestral día 28 | 🆕 |
| ROP MinMax mensual | Día 1 9am | ✅ |
| Seguimiento corte inventario | Diario 9am | ✅ |
| 🔍 MELI watchdog stock/reputación | Diario 9:15am | ✅ |

> ⚠️ 3 crons de inventario en **ERROR** (watchdogs de stock negativo / supplier / GT). Requieren atención.

## Archivos de conteo físico

- `/mnt/hermes/conteo_fisico_inventario.csv` / `.json`
- `/mnt/hermes/three_way_match.json`
- `/mnt/hermes/inventario_pendientes.md` → ver `INVENTARIO_PENDIENTES.md`

## Enlaces

- [[Home]] · [[Operations/Production-MOs]] · [[Operations/Forecast]] · [[Infrastructure/Automations]] · [[Rules/Business-Rules]]

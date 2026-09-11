---
title: Production MOs
tags:
  - operations
  - yfi
  - produccion
  - manufacturing
  - mo
type: operations
source: Odoo manufacturing
last-updated: 2026-09-11
---

# 🏭 Órdenes de Manufactura (MOs)

> Fuente: **Odoo** (Manufactura > Órdenes). Corte: **11-sep-2026**.

## MOs Draft (5)

| MO | Producto | Qty | Planta | BOM | Status |
|---|---|---:|---|---:|---|
| `GALD/MO/00038` | Crujientes Limón y Sal | 1,267 u | Galdisa PL01 | 87 | Draft |
| `GALD/MO/00039` | Crujientes Chipotle | 745 u | Galdisa PL01 | 119 | Draft |
| `GALD/MO/00040` | Crujientes SDM 8kg | 56 u | Galdisa PL01 | 1818 | Draft |
| `SOS/MO/00077` | Puffs 35g Especias | 1,124 u | Soskende Toluca | 113 | Draft |
| `PROS/MO/00047` | Tahini 11.5oz GT | 220 u | Proseresa GT | 1931 | Draft |

## Prefijos de planta

| Prefijo | Planta | Productos |
|---|---|---|
| `GALD/MO/` | Galdisa PL01 | Crujientes (Limón y Sal, Chipotle, SDM 8kg) |
| `SOS/MO/` | Soskende Toluca | Puffs |
| `PROS/MO/` | Proseresa GT | Tahini / Hummus / Falafel GT |

## Reglas de manufactura

- **`R-SUP-04` — Planta fija por producto.** Nunca producir un SKU en la planta incorrecta (ver [[Operations/Inventory]]).
- **`R-SUP-03` — Cero PT en maquiladores.** Todo el terminado se transfiere a LogisPro.
- **`R-SUP-01` — Aislamiento de maquiladores.** Galdisa y Soskende **nunca** deben enterarse de la existencia del otro. No mezclar referencias en correos, docs ni MOs.
- **`R-PROD-01` — Chile Piquín DESCONTINUADO.** Nunca crear OC ni MO para Puffs Chile Piquín.

## Crons relacionados

| Cron | Frecuencia |
|---|---|
| 🏭 B-02 MOs sin consumo semanal | Martes 11am |
| Post-Producción Galdisa | Días 1-3, 15-17 10am |
| 🚚 Service Quality — Lead Time & On-Time | Lunes 9am |
| Guard lotes y caducidades Logispro MX | Lun-Vie 8:15am |

## Enlaces

- [[Home]] · [[Operations/Inventory]] · [[Operations/Forecast]] · [[Rules/Business-Rules]]

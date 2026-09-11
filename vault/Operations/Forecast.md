---
title: Forecast
tags:
  - operations
  - yfi
  - forecast
  - cpfr
  - reabastecimiento
type: operations
source: CPFR + Odoo
last-updated: 2026-09-11
---

# 📈 Forecast & Reabastecimiento (CPFR)

> Fuente: análisis **CPFR** (demanda, cobertura, OOS) + datos Odoo.
> Corte: **11-sep-2026**.

## Objetivos del forecast

1. Cobertura de inventario por SKU/cliente (evitar OOS y sobre-stock).
2. Reabastecimiento sugerido para retail (Chedraui, La Comer, 3B, etc.).
3. Anticipar producción → alimenta las MOs en [[Operations/Production-MOs]].

## Insumos clave

| Insumo | Uso |
|---|---|
| Sell-out retail (CheLink / POS) | Demanda real — **≠** sell-in (`R-DATA-01`) |
| Cobertura de inventario | Días de stock vs. venta |
| OOS (out-of-stock) | Disparador de pedido sugerido |
| Histórico de pedidos por cliente | Base de estacionalidad |

## Crons CPFR / Forecast

| Cron | Frecuencia | Estado |
|---|---|---|
| 📊 CPFR scorecard unificado semanal | Lunes 10:30am | ✅ |
| 📊 CPFR → Monday Sync | Lunes 8:30am | ✅ |
| ⚠️ CPFR Alertas OOS/Riesgo | Diario 9am | 🆕 |
| 📦 Pedido sugerido reabastecimiento OOS — semanal | Lunes 9:45am | ✅ |
| 📊 CheLink - pedido sugerido Chedraui | Lun/Jue 11am | ✅ |
| Recordatorio La Comer CPFR | Días 5,20 9am | ✅ |
| 📦 Matriz de Surtido SKU x Cliente | Lunes 9am | 🆕 |
| 📦 Maximize Surtido — Cross-Sell Intelligence | Lunes 8am | 🆕 |
| 🔍 MELI watchdog stock/reputación | Diario 9:15am | ✅ |

## Reglas aplicables

- **`R-DATA-01`** — sell-in vs sell-out: etiquetar siempre.
- **`R-DATA-04`** — CPFR (estratégico/analítico) vs **Promotoría** (ejecución física en tienda). Datos de inventario/sell-out **nunca** prueban ejecución en anaquel; solo ruta a Promotoría con evidencia de campo explícita.
- **`R-CODE-02`** — Recurrentes corren como **GitHub Actions**, no en créditos Perplexity.

## Enlaces

- [[Home]] · [[Operations/Inventory]] · [[Operations/Production-MOs]] · [[Clients/Unisuper]] · [[Rules/Business-Rules]]

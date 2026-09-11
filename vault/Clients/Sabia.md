---
title: Sabía
tags:
  - client
  - yfi
  - mx
type: client
status: activo
country: MX
currency: MXN
owner: Nina
last-updated: 2026-09-11
---

# 🏬 Sabía

> Cuenta MX. Vigilada por el cron `Recall contabilidad — SOs $0 Sabía`.

## Perfil

| Campo | Valor |
|---|---|
| **País** | México (MX) |
| **Moneda** | MXN |
| **Owner Odoo** | Nina (`res.users` 29) |
| **Status** | Activo |

## Historial de Sales Orders

| SO | Total | Estado | Notas |
|---|---:|---|---|
| — | — | ⚠️ Vigilancia | Existen SOs en $0 atribuidos a Sabía — bajo monitoreo contable |

## Hilos de email

| Hilo | Estado |
|---|---|
| Recordatorios operativos | On-demand |

## Automatización relacionada

- **Cron:** `Recall contabilidad - SOs $0 Sabía + pendiente Puffs 35g Chipotle` — Lun-Vie 9:30am.

## Financiero

- **CxC / aging:** sin vencido al corte. Ver [[Finance/CxC-Aging]].
- ⚠️ SOs en $0 requieren revisión contable (posible error de captura, no cerrar).

## Estado & pendientes

- **Estado:** activo · SOs $0 en vigilancia.
- **Siguiente paso:** conciliar los SOs $0 con contabilidad/Gámez-Leyva.

## Enlaces

- [[Home]] · [[Infrastructure/Automations]] · [[Rules/Business-Rules]]

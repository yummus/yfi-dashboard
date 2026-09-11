---
title: La Europea
tags:
  - client
  - yfi
  - mx
  - autoreply
type: client
status: activo
odoo-id: 20445
country: MX
currency: MXN
owner: Nina
last-updated: 2026-09-11
---

# 🏬 La Europea

> Cuenta MX con autoreply autorizado y recordatorio de inventario programado.

## Perfil

| Campo | Valor |
|---|---|
| **Odoo partner ID** | 20445 |
| **País** | México (MX) |
| **Moneda** | MXN |
| **Contacto** | (usar buzón autoreply autorizado) |
| **Autoreply** | ✅ Autorizado (1 de 7) |
| **Owner Odoo** | Nina (`res.users` 29) |
| **Status** | Activo |

## Historial de Sales Orders

| SO | Fecha | Total | Estado | Notas |
|---|---|---:|---|---|
| — | — | — | ⚠️ **Factura pendiente** | Sin SO draft registrado en el pipeline actual |

## Hilos de email

| Hilo | Canal | Estado |
|---|---|---|
| Autoreply | Gmail 3x/día | ✅ Habilitado |
| Recordatorio inventario | `Recordatorio La Europea inventario` (día 5 y 20, 9am) | ✅ Activo |

## Automatización relacionada

- **Cron:** `Recordatorio La Europea inventario` — días 5 y 20 de cada mes, 9am. Skills: `cpfr-retail-analysis`, `ops-agent`.

## Financiero

- **CxC / aging:** sin vencido al corte. Ver [[Finance/CxC-Aging]].
- ⚠️ **Factura pendiente de emitir.**

## Estado & pendientes

- **Estado:** activo · factura pendiente.
- **Siguiente paso:** conciliar entrega vs factura y emitir CFDI pendiente (requiere aprobación, `R-ODOO-01`).

## Enlaces

- [[Home]] · [[Infrastructure/Automations]] · [[Finance/CxC-Aging]] · [[Rules/Business-Rules]]

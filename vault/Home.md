---
title: Home
tags:
  - home
  - dashboard
  - yfi
  - moc
aliases:
  - Command Center
  - Inicio
  - Index
last-updated: 2026-09-11
owner: Nina
---

# 🏠 YFI Command Center — Home

> Obsidian vault for **Yummus Foods International (YFI) / Banzitos**.
> AI operations partner: **Nina** · Owner: **Siman Layyous, COO**.
> Última actualización: 2026-09-11 · FX ref: 1 USD = 16.92 MXN

---

## 🧭 Mapa del Vault

| Área | Sección | Qué contiene |
|---|---|---|
| 👥 | [[Clients/Zitrone\|Clients/]] | Fichas por cliente: contacto, SOs, hilos email, status |
| 💰 | [[Finance/Balance-Sheet\|Finance/]] | Balance, CxC aging, P&L |
| 🏭 | [[Operations/Inventory\|Operations/]] | Inventario, MOs de producción, forecast |
| 🛠️ | [[Infrastructure/Deploy\|Infrastructure/]] | Deploy, 153 automatizaciones, skills |
| 📕 | [[Rules/Business-Rules\|Rules/]] | Reglas R-SUP / R-PROD / R-CODE |
| 📄 | [[Templates/SO-Template\|Templates/]] | Plantilla para nuevas Sales Orders |

---

## 👥 Clientes

### Pipeline activo (SOs draft / recientes)

| Cliente | SO | Total | Estado | Ficha |
|---|---|---:|---|---|
| Zitrone | `S02978` | $1,976 MXN | ✅ Email enviado · esperando | [[Clients/Zitrone]] |
| Colectivo Saludable | `S02979` | $1,976 MXN | ✅ Email enviado · esperando | [[Clients/Colectivo-Saludable]] |
| El Emigrante | `S02980` | $1,976 MXN | ✅ Email enviado · esperando | [[Clients/El-Emigrante]] |
| Buen Rollo | `S02981` | Q1,740 GTQ | ⚠️ Sin email enviado | [[Clients/Buen-Rollo]] |
| 3B | `S02884` | $57,141 MXN | ✅ Facturado | [[Clients/3B]] |
| La Europea | — | — | ⚠️ Factura pendiente | [[Clients/La-Europea]] |
| Zoco Fresh | — | $5,095 MXN | ⚠️ Refacturación pendiente | [[Clients/Zoco-Fresh]] |
| Hospitales ABC | — | pricing | ✅ Follow-up enviado · esperando precio | [[Clients/Hospitales-ABC]] |

### Otras cuentas

| Cliente | ID Odoo | País | Status | Ficha |
|---|---:|---|---|---|
| Colectivo Saludable | 21278 | MX | activo · CxC $165,803 | [[Clients/Colectivo-Saludable]] |
| Futurama | — | MX | CxC vencida $294,210 | [[Clients/Futurama]] |
| LATAM Food | — | LATAM | cuenta comercial | [[Clients/LATAM-Food]] |
| Sabía | — | MX | activo | [[Clients/Sabia]] |
| Unisuper | — | MX | activo | [[Clients/Unisuper]] |
| La Panoteca | — | MX | activo | [[Clients/La-Panoteca]] |
| El Emigrante (almouhajer) | 23253 | MX | activo | [[Clients/El-Emigrante]] |
| Buen Rollo | 8368 | GT | activo (Guatemala) | [[Clients/Buen-Rollo]] |
| La Europea | 20445 | MX | activo | [[Clients/La-Europea]] |
| Zoco Fresh | 21076 | MX | activo | [[Clients/Zoco-Fresh]] |
| 3B (Tiendas Tres B) | 20129 | MX | activo · CxC $134,294 | [[Clients/3B]] |
| Zitrone | 20643 | MX | activo | [[Clients/Zitrone]] |

> 📌 **Autoreply autorizado (7 clientes):** La Europea · Zoco Fresh · Ingredienta · Yaaxtal · Zitrone · Colectivo Saludable · El Emigrante. ⚠️ **Nunca** autoreply a cadenas grandes (supermercados) — ver [[Rules/Business-Rules]].

---

## 💰 Finanzas

| Reporte | Resumen | Link |
|---|---|---|
| Balance General | Activos $3.3M · Pasivos $3.1M · Capital $68K | [[Finance/Balance-Sheet]] |
| CxC Aging | Total vencido **$101,003** | [[Finance/CxC-Aging]] |
| P&L | Ingresos $1.8M · Utilidad $145K | [[Finance/P&L]] |

**Snapshot consolidado (11-sep-2026):** Activos $3,317,182 · Pasivos $3,103,742 · Capital $68,089 · Ingresos $1,804,182 · Costos $1,658,830 · **Utilidad $145,352 MXN**.

---

## 🏭 Operaciones

| Área | Resumen | Link |
|---|---|---|
| Inventario | Puffs ~41K · Crujientes ~45K | [[Operations/Inventory]] |
| Órdenes de manufactura | 5 MOs draft (GALD · SOS · PROS) | [[Operations/Production-MOs]] |
| Forecast | Reabastecimiento / OOS | [[Operations/Forecast]] |

**Plantas (R-SUP-04):** Puffs → Soskende · Crujientes → Galdisa PL01 · Tahini/Hummus/Falafel GT → Proseresa GT · LogisPro → solo armado/etiquetado.

---

## 🛠️ Infraestructura

| Tema | Resumen | Link |
|---|---|---|
| Deploy / runtime | GCE e2-medium · `/mnt/hermes` · Telegram polling | [[Infrastructure/Deploy]] |
| Automatizaciones | **153 cron jobs** agrupados por categoría | [[Infrastructure/Automations]] |
| Skills | **21 skills** cargados | [[Infrastructure/Skills]] |

---

## 📕 Reglas de Negocio

| Regla | Descripción |
|---|---|
| `R-SUP-01` | Galdisa y Soskende nunca saben el uno del otro |
| `R-SUP-03` | Maquiladores = 0 producto terminado |
| `R-SUP-04` | Planta fija por producto |
| `R-PROD-01` | Puffs Chile Piquín **DESCONTINUADO** |
| `R-CODE-02` | Recurrentes → GitHub Actions, nunca Perplexity |

→ Lista completa en [[Rules/Business-Rules]]

---

## 📄 Templates

- [[Templates/SO-Template]] — plantilla para crear nuevas Sales Orders con checklist completo.

---

## 🔗 Sistema (fuera de Obsidian)

- **Odoo 18 Enterprise** — `company_id=1` (YUMMUS FOODS MEXICO, RFC YFM210304LV1). Read-only por defecto.
- **Banco Monex** — journal_id 9 · CLABE única `112180000033258006`.
- **Gmail** — nina@banzitos.com.mx (autoreply 3x/día) · admin@ (interno) · siman@ (solo Siman).
- **Monday.com** · **Shopify** · **CheLink** · **Telegram** (interfaz primaria).

---

*Generado por Nina · vault auto-mantenido. Ver [[Rules/Business-Rules]] antes de cualquier write.*

# YFI Command Center — Índice

> Centro de control unificador de Nina para Yummus Foods.
> Última actualización: 11-Sep-2026 16:00 CDT

## 📊 Dashboard Visual
- **[Dashboard HTML](DASHBOARD.html)** — Panel principal con KPIs, pipeline, finanzas, actividad

## 🔗 Accesos Rápidos

### Monday.com
| Board | Estado | Link |
|---|---|---|
| Seguimiento Siman - COO | 20 items, 0 stuck | [Abrir](https://monday.com) |
| CxC Vencida | $101,003 pendiente | [Abrir](https://monday.com) |
| Forecast MOs | 5 MOs draft | [Abrir](https://monday.com) |

### Odoo
| Módulo | Ruta | Notas |
|---|---|---|
| Balance General | Contabilidad > Reportes | Filtrar "Todas las empresas" + USD |
| Ventas | Ventas > Pedidos | SOs draft: S02978-2081 |
| Producción | Manufactura > Órdenes | MOs: GALD/MO, SOS/MO, PROS/MO |
| Inventario | Inventario > Operaciones | Stock: Puffs 41K, Crujientes 45K |
| CxC | Contabilidad > Clientes | $101K vencido |
| AP | Contabilidad > Proveedores | P00203-205 draft |

### Gmail
| Buzón | Autoreply | Frecuencia |
|---|---|---|
| nina@banzitos.com.mx | 7 clientes autorizados | 3x/día (9am/1pm/5pm) |
| admin@banzitos.com.mx | Solo interno | On-demand |
| siman@banzitos.com.mx | Nunca | Solo Siman |

## 🤖 Automatizaciones Activas

### Cron Jobs (153 activos)
| Categoría | Jobs | Frecuencia |
|---|---|---|
| Ops / Ventas | ~20 | Diario/3x-día |
| Contabilidad | ~15 | Diario/semanal |
| Inventario | ~10 | Diario |
| Email triage | ~5 | 3x/día |
| Monitoreo infra | ~10 | Continuo |
| Forecast/CPFR | ~5 | Semanal |
| Otros | ~88 | Varios |

### Skills (21 cargados)
| Skill | Categoría | Uso principal |
|---|---|---|
| `yfi-ventas-followup` | ventas | Vigilancia clientes + autoreply |
| `yfi-odoo-readonly` | yfi | Consultas Odoo seguras |
| `yfi-accounts-receivable` | yfi | CxC y cobranza |
| `yfi-email-triage` | yfi | Triage Gmail |
| `yfi-galdisa-cfdi-audit` | yfi | Auditoría fiscal Galdisa |
| `ops-agent` | yfi | Respuestas rápidas operativas |
| `odoo-expert` | yfi | Coordinación Odoo GT |
| `cpfr-agent` | yfi | CPFR retail partners |
| `nina-capabilities` | yfi | Auto-conocimiento |
| `code-agent` | yfi | GitHub/CI/CD |
| `cron-health-supervisor` | yfi | Auto-heal crons |

## 💰 Finanzas

### Balance Consolidado YFI (11-Sep-2026)
| Concepto | MXN | USD |
|---|---:|---:|
| Activos | $3,317,182 | $196,049 |
| Pasivos | $3,103,742 | $183,434 |
| Capital | $68,089 | $4,024 |
| Ingresos | $1,804,182 | $106,629 |
| Costos/Gastos | $1,658,830 | $98,038 |
| **Utilidad** | **$145,352** | **$8,590** |

Rate: 1 USD = 16.92 MXN

### CxC Vencida
| Cliente | Monto |
|---|---:|
| Operadora Futurama | $294,210 |
| Tiendas Chedraui | $233,914 |
| Super San Francisco | $175,029 |
| Colectivo Saludable | $165,803 |
| Tiendas Tres B | $134,294 |
| **Total** | **$101,003** |

## 📦 Pipeline Clientes

| Cliente | SO | Total | Email | Estado |
|---|---|---:|---|---|
| Zitrone | S02978 | $1,976 MXN | ✅ Enviado | Esperando |
| Colectivo Saludable | S02979 | $1,976 MXN | ✅ Enviado | Esperando |
| El Emigrante | S02980 | $1,976 MXN | ✅ Enviado | Esperando |
| Buen Rollo | S02981 | Q1,740 GTQ | ⚠️ Pendiente | Sin email |
| Hospitales ABC | — | Pricing | ✅ Follow-up | Esperando pricing |
| La Europea | — | — | ⚠️ Borrador | Factura pendiente |
| Zoco Fresh | — | $5,095 | ⚠️ Borrador | Cancelación |
| 3B | S02884 | $57,141 | ✅ | Completado |

## 🏭 Producción

### MOs Draft (5)
| MO | Producto | Qty | Planta | BOM |
|---|---|---:|---|---|
| GALD/MO/00038 | Crujientes Limón y Sal | 1,267 | Galdisa PL01 | 87 |
| SOS/MO/00077 | Puffs 35g Especias | 1,124 | Soskende Toluca | 113 |
| GALD/MO/00039 | Crujientes Chipotle | 745 | Galdisa PL01 | 119 |
| GALD/MO/00040 | Crujientes SDM 8kg | 56 | Galdisa PL01 | 1818 |
| PROS/MO/00047 | Tahini 11.5oz GT | 220 | Proseresa GT | 1931 |

### Reglas de Planta (R-SUP-04)
- **Puffs** → Soskende Toluca (picking 26)
- **Crujientes** → Galdisa PL01 (picking 179)
- **Tahini/Hummus/Falafel GT** → Proseresa (picking 354)
- **Logispro** → Solo armado/etiquetado (NO manufactura)

## 🔐 Seguridad y Accesos

| Recurso | Estado |
|---|---|
| GITHUB_PAT | ✅ Configurado |
| XIAOMI_API_KEY | ✅ Regional (token-plan-sgp) |
| ODOO_API | ✅ XML-RPC |
| Gmail SA | ✅ Fix applied |
| Secret Manager | ✅ 403 IAM resuelto |
| Deploy pipeline | ✅ Verde |

## 📋 Reglas de Negocio Clave

| Regla | Descripción |
|---|---|
| R-SUP-01 | Galdisa y Soskende no saben el uno del otro |
| R-SUP-03 | Maquiladores = 0 PT terminado |
| R-SUP-04 | Planta por producto (ver arriba) |
| R-PROD-01 | Chile Piquín DESCONTINUADO |
| R-CODE-02 | Recurrentes → GitHub Actions |
| R-DATA-01 | Sell-in ≠ sell-out |
| Autoreply | 7 clientes autorizados |
| No supermercados | Nunca autoreply a cadenas grandes |

## 🗂️ Estructura de Archivos

```
/mnt/hermes/
├── command-center/
│   ├── DASHBOARD.html          ← Panel visual principal
│   └── INDEX.md                ← Este archivo
├── config.yaml                 ← Configuración Nina
├── .env                        ← Secrets (no versionar)
├── skills/                     ← 21 skills
│   ├── ventas/
│   │   └── yfi-ventas-followup/
│   ├── yfi/
│   │   ├── ops-agent/
│   │   ├── yfi-odoo-readonly/
│   │   ├── yfi-accounts-receivable/
│   │   └── ... (16 más)
│   └── comms/
│       └── human-communication/
├── context/
│   ├── YFI_MASTER_CONTEXT.md
│   ├── YFI_RULES.md
│   ├── YFI_SECRETS_REQUIRED.md
│   └── ...
├── scripts/
│   ├── gmail_send_sa.py        ← Fix applied
│   └── ...
├── cron/
│   ├── jobs.json               ← 153 jobs
│   └── ...
└── state/
    └── ...
```

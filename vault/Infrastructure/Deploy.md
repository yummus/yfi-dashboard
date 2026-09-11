---
title: Deploy
tags:
  - infrastructure
  - yfi
  - deploy
  - runtime
  - devops
type: infrastructure
last-updated: 2026-09-11
---

# 🛠️ Deploy & Runtime

> Arquitectura de despliegue de Nina (Nous Research Hermes Agent, instancia YFI).

## Arquitectura actual

```
Telegram ──▶ Nina (Nous Hermes Agent, native)
                │  orchestrator: Codex gpt-5.6-sol (ChatGPT OAuth)
                │  workers/aux: DeepSeek; web/vision/MoA: Gemini
                │  fallback: DeepSeek → Gemini
                │  tools: yfi-ops plugin (Odoo/Gmail/Monday/recall/memory) + native
                │  identity: SOUL.md + MEMORY.md + context/ + skills/
                └─▶ Odoo · Gmail · Monday · Sheets · Shopify (read-first, approval-gated)
Recurring work ──▶ GitHub Actions crons (NO Perplexity credits)
```

## Substrato

| Componente | Detalle |
|---|---|
| **Host** | GCE VM `e2-medium` |
| **Disco persistente** | `/mnt/hermes` = `$HERMES_HOME` |
| **Modo Telegram** | **Polling** (default nativo) |
| **Estado durable** | `state.db`, `auth.json`, sessions + auto-resume |
| **Deploy pipeline** | ✅ Verde |
| **Cost ceiling** | ≤ $200 USD/mes total AI |

> ⚠️ **Cloud Run + FastAPI + Cloudflare Worker** es **rollback/legacy only** — ya no es el path live.

## Dependencias externas

| Recurso | Estado |
|---|---|
| `GITHUB_PAT` | ✅ Configurado |
| `ODOO_API` (XML-RPC) | ✅ Configurado |
| Gmail Service Account | ✅ Fix aplicado |
| Secret Manager | ✅ 403 IAM resuelto |
| `XIAOMI_API_KEY` | ✅ Regional (token-plan-sgp) |

## Reglas de código e infra

- **`R-CODE-01` — GitHub PR-only.** Cambios de código solo vía PR; **nunca** push a main sin aprobación.
- **`R-CODE-02` — Recurrentes → GitHub Actions.** Automatizaciones recurrentes corren como crons de GitHub Actions, **nunca** en créditos Perplexity.
- **`R-SEC-01` — Nunca exponer secretos.** Nunca revelar, loggear, commitear o empaquetar secretos. Nunca producir `.env`, `gcloud --update-env-vars` ni PATs. Referenciar secretos **solo por nombre**.
- **`R-ODOO-01` — Odoo read-only por defecto.** Cualquier write requiere aprobación explícita de Siman + plan dry-run.

## Crons de infra / auto-heal (12)

| Cron | Frecuencia | Estado |
|---|---|---|
| 🩺 Auto-heal supervisor de crons | 3x/día (6/12/18) | ✅ |
| 💾 Backup state.db diario | Diario 4am | ❌ ERROR |
| 🛑 Watchdog espacio disco /mnt/hermes | Lun-Vie 7,18 | ❌ ERROR |
| heritage-loader-diario | Diario 10:15am | ❌ ERROR |
| heritage-sync-semanal | Lunes 10:05am | ✅ |
| Watchdog journals no-canónicos Odoo MX | Diario 9am | ✅ |
| duplicate-oc-watchdog | Diario 9am | ❌ ERROR |
| Repo hygiene watchdog | Lunes 8:15am | ✅ |
| 🇬🇹 FEL GT watchdog | Lun-Vie 10:30am | ❌ ERROR |
| 🔄 CheLink restore diario | Diario 7:45am | ❌ ERROR |
| OC stuck watchdog (no-escape) | Diario 9am | ❌ ERROR |
| 🏦 C-03 Watchdog líneas banco sin conciliar | Lun-Vie 9am | ✅ |

> ⚠️ 7 de 12 crons de infra están en **ERROR** — es el dominio más frágil. Priorizar `🛑 Watchdog espacio disco` y `💾 Backup state.db`.

## Enlaces

- [[Home]] · [[Infrastructure/Automations]] · [[Infrastructure/Skills]] · [[Rules/Business-Rules]]

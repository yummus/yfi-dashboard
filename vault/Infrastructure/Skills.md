---
title: Skills
tags:
  - infrastructure
  - yfi
  - skills
  - hermes
type: infrastructure
count: 21
last-updated: 2026-09-11
---

# 🧩 Skills (21 cargados)

> Skills del agente Nina (Nous Research Hermes Agent). Ubicación: `/mnt/hermes/skills/`.

## Inventario de Skills (21)

| # | Skill | Categoría | Uso principal |
|---:|---|---|---|
| 1 | `yfi-ventas-followup` | ventas | Vigilancia clientes + autoreply |
| 2 | `yfi-odoo-readonly` | yfi | Consultas Odoo seguras (read-only) |
| 3 | `yfi-accounts-receivable` | yfi | CxC, aging, cobranza |
| 4 | `yfi-email-triage` | yfi | Triage Gmail inbox |
| 5 | `yfi-galdisa-cfdi-audit` | yfi | Auditoría fiscal Galdisa |
| 6 | `ops-agent` | yfi | Respuestas rápidas operativas (ventas, CxC, stock, AP) |
| 7 | `odoo-expert` | yfi | Coordinación implementación Odoo |
| 8 | `cpfr-agent` | cpfr | Sell-through, OOS, forecast, scorecards |
| 9 | `nina-capabilities` | yfi | Auto-conocimiento de tools/accesses |
| 10 | `code-agent` | dev/infra | GitHub PRs, scripts, crons, CI/CD |
| 11 | `cron-health-supervisor` | yfi | Monitor y auto-heal de crons |
| 12 | `nina-orchestration` | yfi | Routing policy, delegation, MoA |
| 13 | `nina-project-operator` | yfi | Project workflows, decisiones |
| 14 | `nina-google-knowledge` | yfi | NotebookLM, Gemini, Colab routing |
| 15 | `nina-multimodal-documents` | yfi | Vision, OCR, PDF, PO analysis |
| 16 | `human-communication` | comms | Comunicación natural, channel-aware |
| 17 | `cpfr-retail-analysis` | yfi | Pipeline CPFR retail Excel/CSV |
| 18 | `cpfr-monday-integration` | yfi | CPFR Scorecard → Monday board |
| 19 | `odoo-cancel-sale-order` | yfi | Cancelar SOs y pickings vía XML-RPC |
| 20 | `yfi-gastos-tickets` | yfi | Gastos operativos + OCR pipeline |
| 21 | `yfi-sat-odoo-sync` | yfi | SAT ↔ Odoo sync |

## Agrupación por dominio

| Dominio | Skills |
|---|---|
| **Ventas / CPFR** | `yfi-ventas-followup`, `cpfr-agent`, `cpfr-retail-analysis`, `cpfr-monday-integration` |
| **Contabilidad / CxC** | `yfi-accounts-receivable`, `yfi-galdisa-cfdi-audit`, `yfi-sat-odoo-sync`, `yfi-gastos-tickets` |
| **Odoo** | `yfi-odoo-readonly`, `odoo-expert`, `odoo-cancel-sale-order` |
| **Comunicación** | `yfi-email-triage`, `human-communication` |
| **Agéntico / Plataforma** | `nina-capabilities`, `nina-orchestration`, `nina-project-operator`, `nina-google-knowledge`, `nina-multimodal-documents` |
| **Infra / Dev** | `code-agent`, `cron-health-supervisor`, `ops-agent` |

## Convenciones

- Cargar con `skill_view(name='<skill>')`.
- Identidad base: `SOUL.md` + `MEMORY.md` + `context/` + `skills/`.
- Reglas duras aplican siempre por encima de cualquier skill (`R-*`).

## Enlaces

- [[Home]] · [[Infrastructure/Deploy]] · [[Infrastructure/Automations]] · [[Rules/Business-Rules]]

---
title: Galdisa
type: supplier
tags: [proveedor, maquilador, galdisa, quality, oil-reimbursement]
last-updated: 2026-09-11
company: MX
---

# Galdisa — Proveedor / Maquilador

## Datos Generales
- **Razón social:** GALDISA S.A. DE C.V.
- **RFC:** GAL900207HI9
- **Partner ID Odoo:** 20660
- **Tipo:** Maquilador (Crujientes) + Proveedor (aceite, sazonador)
- **Planta:** GALDISA PL01 (picking_type_id: 179)
- **Regla:** [[R-SUP-01]] — Galdisa NUNCA sabe que existe Soskende

## Contacto
- **Gloria Cruz** — correo: (ver Gmail threads)
- **Adilene** — escribió 11-sep-2026

## Compensación Aceite 1:1
| Concepto | Monto | Estado |
|---|---:|---|
| Total aceite reclamado | $306,226.35 | — |
| CUSTCRED1887 (Sesajal) | $233,693.64 | ✅ Aplicada |
| La Corona P00119 pendiente | $72,532.71 | ⏳ Sin NC |
| **Por recuperar** | **$72,532.71** | — |

## Compensación Calidad 15%
| Concepto | Monto | Acumulado |
|---|---:|---:|
| Target total 15% | $506,282.57 | — |
| 1er abono CUSTCRED1886 | $35,884.69 | 7.1% |
| 2do abono AGAL-57561 | ~$77,177.19 | Pendiente posteo |
| **Faltante** | **$470,397.88** | — |

## Facturas en Odoo
- **AGAL-57561** — Borrador (id 27426), $514,514.61, NO posteada
- 8 bills posted SIN UUID (2024-2025)
- NC calidad ~$75,942.39 **NO registrada** en Odoo

## Pendientes
- [ ] Postear AGAL-57561 (requiere VoBo contabilidad)
- [ ] Registrar NC por descuento calidad
- [ ] Coordinar NC La Corona ($72,532.71)
- [ ] Obtener listado completo facturas maquila

## CFDIs Verificados
| CFDI | UUID | Monto | Verificado |
|---|---|---:|---|
| CUSTCRED1886 | — | $35,884.69 | ✅ 15% × $239,231.23 |
| CUSTCRED1887 | — | $233,693.64 | ✅ Match Sesajal al centavo |
| AGAL-57561 | 53201053-... | $514,514.61 | ✅ Sub+IEPS |
| CUSTPYMT55361 | — | $0.00 | ✅ Complemento pago |

## Skill Relacionada
- [[yfi-galdisa-cfdi-audit]] — Expediente fiscal completo

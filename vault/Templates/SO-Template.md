---
title: SO Template
tags:
  - template
  - yfi
  - sales-order
  - so
type: template
last-updated: 2026-09-11
---

# 📄 Plantilla — Nueva Sales Order (SO)

> Copiar este bloque para crear una nueva ficha de SO en `Clients/` o `Operations/`.
> Reemplazar todos los `{{placeholders}}`.

---

```markdown
---
title: SO-{{NUMERO}}
tags:
  - sales-order
  - yfi
  - so
type: sales-order
so-number: {{S02999}}
client: {{Cliente}}
odoo-partner-id: {{00000}}
country: {{MX|GT}}
currency: {{MXN|GTQ|USD}}
total: {{0,000}}
status: {{draft|enviado|confirmado|facturado|cancelado}}
owner: {{Nina (29)|Siman (2)|Rodrigo (21)|Samantha (24)}}
last-updated: {{YYYY-MM-DD}}
---

# 🧾 SO {{S02999}} — {{Cliente}}

## Datos de la orden

| Campo | Valor |
|---|---|
| **SO #** | `{{S02999}}` |
| **Cliente** | {{Cliente}} |
| **Odoo partner ID** | {{00000}} |
| **País / moneda** | {{MX / MXN}} |
| **Productos** | {{Crujientes 110g x N}} |
| **Cantidades** | {{N}} |
| **Total** | **{{$0,000}} {{MXN}}** |
| **Planta** | {{Soskende | Galdisa PL01 | Proseresa GT}} |
| **Fecha** | {{YYYY-MM-DD}} |
| **Owner** | {{Nina (29)}} |

## Estado

| Etapa | ✅/⬜ | Fecha | Notas |
|---|---|---|---|
| Draft creado en Odoo | ⬜ | | |
| Precios validados | ⬜ | | |
| Aprobación Siman (si aplica) | ⬜ | | |
| Email de confirmación enviado | ⬜ | | |
| Confirmado por cliente | ⬜ | | |
| Factura (CFDI) emitida | ⬜ | | |
| Cobranza / pago recibido | ⬜ | | |

## Checklist de creación

- [ ] **Verificar cliente** existe en Odoo (`res.partner`) — anotar partner ID.
- [ ] **Verificar owner válido** — solo Nina(29)/Siman(2)/Rodrigo(21)/Samantha(24). `R-ODOO-05`
- [ ] **Verificar planta correcta** por producto. `R-SUP-04`
- [ ] **Confirmar que el SKU NO está descontinuado** (ej. Puffs Chile Piquín ❌). `R-PROD-01`
- [ ] **Confirmar precios** contra pricelist autorizada (no inventar). `R-COMM-02`
- [ ] **Moneda correcta** (MXN / GTQ / USD) — no mezclar. `R-DATA-03`
- [ ] **Draft primero** — NUNCA enviar a terceros sin VoBo. `R-COMM-01`
- [ ] **Aprobación de Siman** si implica write en Odoo o compromiso material. `R-ODOO-01`, `R-COMM-07`
- [ ] **Email de confirmación** vía Gmail relay (`source_id=gcal`), firma correcta. `R-COMM-03`
- [ ] **Registrar hilo de email** (thread ID) en la ficha del cliente.
- [ ] **Actualizar [[Finance/CxC-Aging]]** cuando se facture.
- [ ] **Enlazar** ficha de cliente + MO relacionada.

## Reglas aplicables (verificación rápida)

| Regla | Verificar |
|---|---|
| `R-ODOO-01` | Odoo read-only salvo aprobación + plan dry-run |
| `R-ODOO-05` | Owner en lista permitida |
| `R-SUP-04` | Planta correcta por producto |
| `R-PROD-01` | SKU no descontinuado |
| `R-COMM-01` | Sin envíos autónomos a terceros |
| `R-COMM-03` | Canal Gmail relay + firma correcta |
| `R-DATA-01` | Etiquetar sell-in vs sell-out |
| `R-DATA-03` | No mezclar contextos/monedas |

## Historial de email

| Fecha | Hilo / ID | Dirección | Estado |
|---|---|---|---|
| | | | |
```

---

## Ejemplos recientes (referencia)

| SO | Cliente | Total | Estado |
|---|---|---:|---|
| `S02978` | [[Clients/Zitrone]] | $1,976 MXN | enviado |
| `S02979` | [[Clients/Colectivo-Saludable]] | $1,976 MXN | enviado |
| `S02980` | [[Clients/El-Emigrante]] | $1,976 MXN | enviado |
| `S02981` | [[Clients/Buen-Rollo]] | Q1,740 GTQ | sin email |
| `S02884` | [[Clients/3B]] | $57,141 MXN | facturado |

## Enlaces

- [[Home]] · [[Rules/Business-Rules]] · [[Operations/Production-MOs]] · [[Finance/CxC-Aging]]

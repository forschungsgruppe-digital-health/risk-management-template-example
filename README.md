# risk-management-template-example

A browsable **example child** of the
[risk-management-template](https://github.com/forschungsgruppe-digital-health/risk-management-template):
this is what a repository looks like **after** applying the template (base delivery-risk
register + the MDR / IEC 62304 / ISO 14971 conformance-readiness layer).

Everything here is **synthetic** — the register entries use obviously artificial content
(`Max Mustermann-Testpatient`); no real product, no real patient data.

## What to look at

| Where | What it shows |
|---|---|
| [Issues](../../issues) | Filled register entries created via the issue forms: a delivery **risk** (with the honest "none yet" mitigation answer), a **harm-risk** (full ISO 14971 §5–§8 chain incl. §7.5 new-risks-from-controls), a **requirement** (traceability anchor) |
| **Projects tab** | The two linked Projects v2 boards — *Risk Register* (5×5 fields, one triaged entry: L3·I3·Score 9·Medium) and *Harm Risk File* (S/P + residual S/P + control-verification fields). Views (e.g. the Matrix) are added manually — [the scripts print the recipe](scripts/setup-project-board.sh) |
| [Issue forms](.github/ISSUE_TEMPLATE/) | risk · harm-risk · requirement · soup-anomaly (62304 §7.1.3 record) · field-feedback (14971 §10 intake) |
| [docs/](docs/) | The applied method set: RISK_MANAGEMENT (+ the [RECIPES](docs/RECIPES.md) situation cookbook — 13 step-by-step recipes), HARM_RISK (+ §9 [report stub](docs/HARM_RISK_REPORT.md)), SECURITY_RISK, SOUP, TRACEABILITY, CONFORMANCE_TRANSFER, [standards/](docs/standards/) (CONFORMANCE index, GSPR checklist, 62304 coverage map) |
| [docs/adr/](docs/adr/) | The three living/template ADRs (0001 MDSW qualification · 0002 software safety class · 0003 supply-chain pinning) — placeholders marked, to be filled per product |
| [Workflows](.github/workflows/) | risk-automation (inert until `RISK_PROJECT_URL`), sbom + register-export (run on releases; sbom was dispatched once live — see Actions) |

## How this repo was produced

1. Applied via the template's [apply path](https://github.com/forschungsgruppe-digital-health/risk-management-template/blob/main/docs/APPLY_TO_EXISTING_REPO.md)
   (`plan` → `apply`) against a real research repo's copy; this example keeps **only the
   applied artifact set** (in a real child these files sit next to your product code).
2. Labels via `./scripts/setup-labels.sh` (both sets — idempotent, re-runs skip).
3. Boards via `./scripts/setup-project-board.sh <owner> <owner>/<repo>` — the second
   argument links them to this repo.
4. Register entries raised through the issue forms, one triaged on the board.

In a standalone child the template ADRs keep their numbers (0001–0003, as here); when
retrofitting a repo that already has ADRs they are renumbered to the next free numbers —
the apply path handles that.

## What a real child still fills in

The template **enables, it does not enforce**: the per-product determinations stay open
and marked — ADR-0001's real qualification answer, ADR-0002's safety class, the
HARM_RISK §1 plan table (incl. acceptability-policy basis), `soup.yaml`'s real
components, CODEOWNERS owners, `RISK_PROJECT_URL`, and — before publishing — a LICENSE.

---
*Maintained as the template's example; not a product. License: none on purpose (a real
child adds its own; see the template README's licensing note).*

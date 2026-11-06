# Dronect — Decisions, Validation Backlog & Stage Gates (v0.2)

**Resolved on 2026-11-06:** Broad EU R&D B2B target (Spain for pilot); silent/unmodified and modified drones in threat model; 99.9% target unvalidated; €1,200/quarter integrated pilot; founding team temporarily donates services; hybrid Dronect/customer response; extra physical automation excluded; in-house software, third-party purchased sensors; local-first option; long-run intelligence optional. **Do not reopen these as if undecided.**

## P0 — still genuinely unanswered

1. **Pilot spatial envelope:** actual building/zone dimensions, exposed assets, target stand-off distance, azimuth/elevation sectors, day/night/weather. Can't verify coverage or quote hardware without this.
2. **Acceptance profile:** which RF-silent drone class(es), flight paths, minimum detection distance, tolerable alert latency and false-alarm budget? 99.9% cannot be tested without a defined population and conditions.
3. **Legal operating mode:** what exact event monitoring and police notification activities will be performed by Dronect vs customer or licensed security company? Written classification required.
4. **Customer and test access:** identified authorised pilot site, security owner, host permissions and lawful drone operator/test plan.
5. **Procurement:** actual supplier quotes, hardware cap denomination, VAT/shipping and operating consumables. Gemini extract does not contain a validated quote.
6. **Pilot contract cash terms:** upfront vs arrears billing, VAT inclusion vs exclusion, six-month commitment, consent for anonymised results, access windows.
7. **Third-party external requirements:** insurance, GDPR, qualified lawyer and site permit bills; who pays/under what contract?

## P1 — important, but can be prototyped with assumptions

- Exact camera-lens and night-vision needs; use daylight-only trial if nothing else is authorised.
- The on-device compute choice: Pi 5+NPU, mini PC or client-owned edge server.
- Acoustic algorithm and dataset rights; live noise calibration.
- Integration with client's SIEM, email/SMS, security control room and blinds.
- Whether single-site data stay on prem and what (if anything) crosses to a central control plane.
- Source of trade-secret incident legal templates and how external counsel participates.
- Which first purchasing personas and business verticals show high willingness to pay.

## Design-of-experiments ladder

| Stage | Evidence sought | Minimum deliverable | Decision |
|---|---|---|---|
| 0 — pitch/demo | Coherent, non-misleading experience | Simulated or authorised sample alert → runbook → case file; mark simulated data | Ready to demo workflow |
| 1 — bench | Sensor viability | Actual RID reception, tagged acoustic/optical clips; local log | Ready for site assessment |
| 2 — surveyed site | Detection envelope & noise | Map of instrumented/uninstrumented zones; observed background rate | Reposition sensors or stop |
| 3 — lawful drone tests | Detection of cooperative and RF-silent classes | Event-based sensitivity by condition, latency, false positives; all misses logged | Refine scope / add camera or radar |
| 4 — operational tabletop | Correct response | Trained point of contact, tested alert chain, runbook execution, evidence package | Offer client-side incident workflow |
| 5 — six-month paid pilot | Willingness to pay & cash neutrality | Two collected payments; expenses; signed acceptance; customer feedback | Decide pricing and scale |
| 6 — regulated service | Commercial service lawfulness | External legal review, insurance, DPA, third-party security partnership if needed | Expand deployment |

## Success indicators (not invented market benchmarks)

- Every alert references modality, timestamps, confidence basis, zone and related playbook.
- Pilot includes **actual RF-silent authorised flight trials** with at least one non-RF modality generating events; success threshold must be agreed before testing.
- All false alerts and missed eligible flights are recorded; no cherry-picking.
- Operator can decide and execute the next permitted step; Dronect never implies permission to intercept a drone.
- Six-month out-of-pocket site cash contribution is non-negative at the objective contract price **unless the founders expressly accept a research loss**.
- Separate document tracks full economic cost and founder hours for future sustainable pricing.

## Evidence maturity labels for slides/docs

- **Simulation** — workflow demonstration; zero claim of drone sensor performance.
- **Bench verified** — real receiver/model on desk; no site coverage claim.
- **Field observed** — actual approved flights at a specific site under stated conditions.
- **Validated** — statistically designed trials with uncertainty, documented variants and external review.
- **Commercially demonstrated** — customers paid, adopted runbooks and renewed/converted.

## Decision log

| Date | Decision | Type | Evidence needed next |
|---|---|---|---|
| 2026-11-06 | Integrated managed-service model, not cloud SaaS licence | Team decision | Contract scope |
| 2026-11-06 | €1,200/quarter pilot objective, all-in labour | Team decision | Buyer + cash model |
| 2026-11-06 | Founders unpaid for pilot | Team decision | Shadow hours tracking |
| 2026-11-06 | RF-silent drones must be tested | Team decision | Acoustic/optical flight trials |
| 2026-11-06 | 99.9% sensitivity aspiration remains open | Research target | Trial definition / results |
| 2026-11-06 | Europe R&D, likely first Spain | Team decision | Initial customer discovery |
| 2026-11-06 | Avoid "first provider" claim | Evidence-based correction | Competitive analysis |
| 2026-11-06 | Use zone-based rather than floor-area-only scoping | Technical recommendation | Site survey |

## Whitepaper gates

**Technical whitepaper (final):** sensor vendors/quotes; test geometry; lawfully authorised flight validation; sample sizes, misses and blind spots; actual architecture and security review; documented limitations. No 99.9% assertion until validated.

**Business whitepaper (final):** at least one buyer interview or letter of intent; confirmed installed costs; regulatory operating model and cost; validated pilot contracting/price; sustainable labour and insurance model; competitor differentiation and market segmentation; cashflow and scenario sensitivity.

Until then, use `09_WHITEPAPER_SCOPES.md` as a source-controlled outline. These are **not yet definitive whitepapers**.

# Dronect — Project Knowledge Pack v0.2

**Date:** 2026-11-06  
**Status:** Updated working project knowledge; **not** an approved engineering specification, binding legal opinion, commercial quotation, or final whitepaper.  
**Language:** English for reuse in pitch preparation and future technical/business whitepapers.

## Purpose

Dronect is an early-stage **managed airspace security service**, specialised in the protection of trade secrets, R&D assets, and sensitive corporate operations against drone-enabled observation. Its internal software is an enabling tool, **not the product being sold**. The initial market is European R&D-intensive enterprises, with **Spain** as the likely pilot location.

This package supersedes v0.1. It incorporates decisions made by the team on 2026-11-06, plus a review of the supplied Gemini extract and external sources.

## Documents

| File | Purpose |
|---|---|
| `01_PROJECT_CHARTER.md` | Current concept, customer, value chain, decisions, exclusions |
| `02_TECHNICAL_FEASIBILITY.md` | Multi-modal detection architecture and hard limits |
| `03_BUSINESS_AND_UNIT_ECONOMICS.md` | Cash-neutral pilot, subscription and capital requirements |
| `04_LEGAL_AND_TRUST_CHECKLIST.md` | Spanish/EU legal decision gates and data/evidence safeguards |
| `05_OPEN_DECISIONS_AND_VALIDATION.md` | Remaining unknowns, testable assumptions and stage gates |
| `06_SOURCE_REGISTER.md` | Primary sources, vendor references, and provenance |
| `07_PILOT_BOM_AND_TEST_PLAN.md` | Budgeted reference hardware, experiment and measurements |
| `08_PITCH_AND_POSITIONING.md` | Competitive-safe claim language, service workflow and pitch |
| `09_WHITEPAPER_SCOPES.md` | Detailed outlines and release criteria for both whitepapers |
| `10_DRONECT_TECHNICAL_WHITEPAPER.md` | Technical whitepapers targeting a common scenario |

## Source-status vocabulary

- **TEAM DECISION** — committed positioning or working assumption from the user/team, not externally verified.
- **PRIMARY SOURCE** — statute/regulator/official institutional or manufacturer statement; still subject to applicability and revision.
- **THIRD-PARTY CLAIM** — vendor/competitor/industry statement; not independently demonstrated by Dronect.
- **ILLUSTRATIVE MODEL** — modelled prices, ranges, unit economics, performance goals; not a quote or test result.
- **OPEN / GATE** — decision or validation required before commercial promise or production deployment.

## Five non-negotiables

1. **99.9% is an aspiration for empirical detection sensitivity**, not a proven number or a synonym for uptime. Specify target type, environmental conditions, coverage volume and alert delay before testing.
2. **RF-silent means no useful RF transmissions, not physically undetectable.** Acoustic and optical sensors may detect some such aircraft, with site-dependent limitations. Radar is a potential expansion, not silently included in a low-cost MVP.
3. **€1,200/quarter is the team's pilot price objective**; the founders' own installation, assessment and management time are temporarily unremunerated, but must be shadow-costed. This is a pilot cash experiment, not a proof of commercial unit economics.
4. **“First integrated provider” is not a supportable claim.** Other vendors already combine detection, risk assessment, procedures, monitoring and security integration (e.g., Dedrone, Materna, Orange Business).
5. **Legal scope must be approved before a live managed alarm service.** A drone alert workflow may trigger Spanish private-security rules depending on who receives/verifies/escalates it. No jamming, spoofing, takeover or physical interdiction.

## Pilot assumptions for planning, not yet agreed with a customer

- One site, one high-value exposed zone or building side, with customer-supported power and connectivity.
- No requirement to observe an entire office building in every direction, in all weather and at all hours.
- Two consecutive quarters of service at €1,200/quarter **excluding VAT**, assuming collection and contract performance.
- Dronect founders install equipment and perform the initial audit, runbooks and management without cash wages during validation.
- Customer security personnel execute physical/site measures; Dronect provides agreed escalation, coordination and records, within legally permitted scope.
- Basic legal-incident guidance is intended to be included; any required paid qualified legal support must be budgeted in the integrated price or documented as supplied by the customer. Litigation, patent services, civil infrastructure, blinds/automation, paid guard/SOC staff, insurance and unforeseen site modifications require separate explicit treatment; they are **not presumed free**.

## Recommended next action

Use `07_PILOT_BOM_AND_TEST_PLAN.md` to request actual vendor quotes and define an authorised test site. Only after scope, results and regulatory classification are settled should `09_WHITEPAPER_SCOPES.md` become two definitive English whitepapers.

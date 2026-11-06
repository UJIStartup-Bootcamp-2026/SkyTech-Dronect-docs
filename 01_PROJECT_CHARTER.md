# Dronect — Project Charter (v0.2)

**Classification:** working strategic specification. **Owner:** founding team. **Date:** 2026-11-06.

## 1. Mission and service definition

> **Dronect helps R&D-intensive organisations protect sensitive operations and trade secrets against low-altitude aerial observation, combining passive detection, site-specific threat assessment, response procedures, personnel enablement and evidence-aware incident coordination in one managed subscription.**

The business is **Security-as-a-Service** in the broad operational sense (managed security service), **not** a cloud SaaS licence. Its software is developed in-house as infrastructure to implement detection, alerting, contextual risk scoring, runbooks, event documentation and optional multi-client trend intelligence. Sensor hardware is purchased from third parties and retained/managed under a rental/service arrangement. Founders install the pilot directly; production installations are expected to be **subcontracted**, while Dronect retains responsibility for service quality.

## 2. Origin and team decisions

| ID | Team decision / design intent | Qualification |
|---|---|---|
| D-01 | Brand: **Dronect** | Working project name; trademark checks pending |
| D-02 | B2B: European companies with substantial R&D and sensitive commercial information | ICP not yet narrowed to a first purchasing department |
| D-03 | Spanish enterprise as likely first paid MVP pilot | Pilot customer not secured |
| D-04 | Protect against RF-cooperative **and uncooperative / RF-silent** drones | Requires non-RF modalities; cannot assume universal detection |
| D-05 | **99.9% detection rate is a target** to be validated experimentally | Not a contractual performance guarantee |
| D-06 | Pilot price **€1,200 every three months**, preferably all-inclusive service | Pilot price objective; no buyer validation known |
| D-07 | Hardware aspiration **at most US$2,000 per pilot deployment**, from Gemini/team discussion | No documented supplier quote; FX and taxes unresolved |
| D-08 | Pilot: founders perform installation, software operation, auditing and runbook production without wages | Shadow costs still recorded; out-of-pocket costs are not free |
| D-09 | Combined local procedures and Dronect management: hybrid response model | Statutory boundaries, contractual responsibilities and schedules to be defined |
| D-10 | Optional physical protective automation (e.g., blinds) scoped per customer | Equipment and integration **excluded** from base pilot price |
| D-11 | Dronect includes basic incident-oriented legal guidance/coordination in the integrated service | Must be delivered or supervised by qualified counsel where professional legal advice is required; extraordinary representation/litigation/patent work is separately scoped |
| D-12 | No active countermeasures or intentional radio interference | Police/competent authority handles any action within its powers |
| D-13 | Intelligence network between customers only after trust/governance controls | Later capability; not required for pilot success |
| D-14 | Long-run possible B2B2G/defence partnerships | Exploratory, not a forecast or committed strategic dependency |

## 3. Customer's problem and security outcome

**Problem:** Aerial imaging can bypass some ground-perimeter assumptions. Prototypes, layouts, operational rhythms, sensitive works and visible industrial processes may be exposed to unmanned cameras; not every overflight is malicious. A site often lacks a coherent process for deciding whether a flight is relevant, whether it is permitted, who responds, and what evidence should be retained.

**Desired outcome:** Visibility into specified airspace, timely and proportionate site actions, better auditability, and demonstrable reasonable protective measures for valuable confidential information. Detection is a means, not a guarantee of preventing disclosure.

**Useful first ICP:** A single Spanish industrial R&D campus or laboratory with **one identifiable high-exposure asset zone**, a security/operations owner able to act on alerts, consent to a pilot, and permission to test lawful flights. An unspecified multi-building estate is not a valid one-kit baseline.

## 4. Service components

1. **Site security assessment:** Identify exposure windows, critical areas, legal context, existing cameras/security controls, notification matrix, baseline benign aviation and privacy constraints.
2. **Detection-as-a-service:** Supply, commission, update, inventory and maintain agreed sensor package with coverage limits and a service dashboard.
3. **Risk classification:** Contextualise observations by asset, time, track, duration, prior authorised flights, evidence strength and corroboration. A drone sighting does not prove intent.
4. **Response engineering:** Deliver agreed runbooks by severity; train designated client staff, schedule tabletop exercises and advise on optional protective automation.
5. **Incident coordination and included basic legal guidance:** Notify designated client contacts; provide reports and evidence packages; coordinate lawful escalation and an appropriately qualified legal assessment where required. Litigation, patent filing and extraordinary representation are separate.
6. **Continuous improvement:** Revisit false alarms, blind spots and procedure effectiveness; issue periodic reporting.
7. **Future optional intelligence:** Cross-client patterns using lawful, minimised and appropriately permissioned telemetry, without exposing site secrets.

## 5. Roles and escalation boundary

| Task | Dronect proposed role | Client / licensed third party role |
|---|---|---|
| Detect and triage sensor output | Build, maintain and explain technical detections | Provide authorised-flight lists and operational context |
| Design runbooks / train | Lead planning and training | Approve and execute on-site response |
| Close blinds, suspend a visual demonstration | Recommend trigger and procedure | Customer staff/system performs, after safety review |
| Escalate a suspected crime | Prepare factual incident summary and assist coordination | Client and appropriate authorities decide escalation/action |
| Legal claim and patent/trade secret advice | Preserve facts and coordinate handover | Qualified legal counsel provides any regulated/professional legal advice and representation, either via a budgeted Dronect partner or customer counsel |
| Regulated guard/monitoring/response services | **Not presumed authorised** | Licensed security company / authorised framework as required |

## 6. Pilot boundary: credible and narrow

- **In scope:** defined monitoring sector, RF cooperative sensing, camera/acoustic trial, on-site edge inference, alert dashboard, manual analyst triage, written procedure, lawful flight test programme, handover and results report.
- **Explicitly out of scope unless priced/authorised:** full site/omnidirectional/night/all-weather coverage, dedicated counter-UAS radar, 24/7 human SOC, jamming, RF takeover, kinetic mitigation, access to police registration databases, court representation, patent prosecution, extraordinary external legal representation, blinds/automation hardware, guaranteed attribution of operator, adversarial/illegal test missions.
- **Pilot success is multi-dimensional:** technical signal, false-alarm feasibility, operational usefulness, willingness to pay, cash outcome and regulatory compliance. 99.9% is a research aspiration, not the only pass/fail condition.

## 7. Differentiation — careful market wording

Avoid: **"We are the world's/Europe's first integrated drone security provider."** Existing providers advertise managed detection, site assessment, SOP integration and ongoing monitoring (e.g., Dedrone, Materna, Orange Business). See `06_SOURCE_REGISTER.md`.

Test: **"Trade-secret-focused aerial security operations for R&D organisations: sensor-agnostic monitoring, site-specific security playbooks, staff enablement and evidence-aware incident coordination."** Differentiation must be validated with customers against commercial alternatives, not presumed.

## 8. Commercial model

**Pilot:** €1,200/quarter for an agreed narrow-scope deployment; two quarters forecast revenue €2,400 net of VAT, subject to actual payment. No separate line item for founders' installation/audit labour during the pilot. Optional protective devices and extraordinary professional/legal proceedings are excluded as specifically contracted. **Basic legal-incident guidance is included** and must be delivered by suitably qualified personnel or an agreed counsel arrangement; any paid partner fee must fit the pilot cash cap. Unit economics in `03_BUSINESS_AND_UNIT_ECONOMICS.md`.

**Production:** managed equipment, installation, assessment, response consulting and service included in one integrated recurring commercial offer. Its price is a **later decision** driven by zone geometry, multi-sensor count, regulatory obligations, response hours and support intensity. No site-size-only linear tariff should be promised.

## 9. Claims that require evidence

- 99.9% conditional probability of detection under an explicit test envelope.
- Coverage in metres and degrees by sensor and siting condition.
- Detection of modified, autonomous, non-RID and RF-silent aircraft at a useful stand-off distance.
- Rate of false alarms under realistic background traffic and sound.
- Event-to-action latency and end-user response times.
- Total deployment price, including VAT implications, licensing and insurance.
- Legal ability to offer the planned 24/7/third-party monitoring activities.
- Willingness to pay for the combined service rather than individual hardware.

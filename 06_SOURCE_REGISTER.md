# Dronect — Source Register (v0.2)

**Research cut-off:** 2026-11-06. Links require re-check before public investor claims. "Published" and vendor product descriptions do not imply Dronect field validation.

## Team/input source

| ID | Source | Contribution | Limit |
|---|---|---|---|
| TEAM-01 | User/team briefing 2026-11-06 | ICP Europe/R&D; Spanish pilot; $2k hardware aspiration; €1,200/quarter; founder donated labour; service scope; silent-drone objective; future B2B2G | User-stated decisions, not verified market/sensor facts |
| GEM-01 | `gemini_convo.txt` attached 2026-11-06 | General drone links/protocols: control, telemetry, video, OcuSync, ELRS/Crossfire, Wi-Fi, cellular and MAVLink | **Contains no $2,000 BOM, supplier quotes, acoustic/optical design, or empirical 99.9% results.** Some statements are broad or model-dependent and sources are mixed quality. Treat as background only. |

## Technical and regulatory primary references

| ID | Source | URL | Use / limitations |
|---|---|---|---|
| TECH-01 | European Commission JRC, 2025 counter-drone technology overview | https://publications.jrc.ec.europa.eu/repository/handle/JRC140692 | Sensing modalities, complementarity, DTI taxonomy; not a Dronect performance evaluation |
| TECH-02 | EASA UAS rules, June 2026 revision | https://www.easa.europa.eu/en/document-library/easy-access-rules/online-publications/easy-access-rules-unmanned-aircraft-systems | EU drone operations/class and RID framework; exceptions matter |
| TECH-03 | AESA open-category / Remote ID | https://www.seguridadaerea.gob.es/es/ambitos/drones/operaciones-uas-drones/operaciones-con-uas-drones---categoria-abierta-subcategorias-a1-a2-y-a3 | DRI scope for relevant classes; not all flights detectable |
| TECH-04 | OpenDroneID Android receiver (open source) | https://github.com/zingdrones/opendroneid-receiver-android | Receiver for Bluetooth, Wi-Fi Beacon/NAN modes; example code, not industrial SLA |
| TECH-05 | OpenDroneID C core | https://github.com/opendroneid/opendroneid-core-c | Protocol family and transmitter/receiver examples; check implementation & licence |
| TECH-06 | Raspberry Pi AI Camera, manufacturer | https://www.raspberrypi.com/products/ai-camera/ | $70 reference component list price, local inference possible; NOT pre-trained aerial detection guarantee |
| TECH-07 | Raspberry Pi 5, manufacturer price notice | https://www.raspberrypi.com/news/1gb-raspberry-pi-5-now-available-at-45-and-memory-driven-price-rises/ | Base computing price context; revisions and regional tax affect cost |
| TECH-08 | Dronetag RIDER, manufacturer | https://www.dronetag.com/products/rider | €999 / $1,099 public reference price at research; RID only; check local integration rights |
| TECH-09 | 16-channel acoustic drone dataset, Zenodo, published 2026-10-24 | https://zenodo.org/records/23613504 | Structured recordings with limited airframe and distances; not validated product range |
| LEGAL-01 | Ley 5/2014 de Seguridad Privada, BOE | https://www.boe.es/buscar/act.php?id=BOE-A-2014-3649 | Art. 5 regulated activities, Art. 6 compatible services; depends on actual workflow |
| LEGAL-02 | AESA flight rules and geographical restrictions | https://www.seguridadaerea.gob.es/es/ambitos/drones/normativa-de-uas-drones | Legal drone test operation |
| LEGAL-03 | Ley 1/2019 Secretos Empresariales, BOE | https://www.boe.es/buscar/act.php?id=BOE-A-2019-2364 | Trade secret definition and conditions; case-specific legal remedies |
| LEGAL-04 | AEPD public-space video capture | https://www.aepd.es/preguntas-frecuentes/8-videovigilancia/FAQ-0804-se-puede-grabar-la-via-publica-con-fines-de-seguridad | Video boundaries; other data needs separate GDPR assessment |
| LEGAL-05 | Ministry of Interior, security activities | https://www.interior.gob.es/opencms/va/servicios-al-ciudadano/tramites-y-gestiones/seguridad/empresas-de-seguridad/servicios-y-actividades/ | Clarifies regulated services; not individualized approval |

## Competitor/market evidence (competitor claims, not independently audited)

| ID | Source | URL | Implication |
|---|---|---|---|
| MARKET-01 | Orange Business, *Orange Drone Guardian*, press release 2026-03-17 | https://www.orange-business.com/en/press/orange-business-launches-orange-drone-guardian-europe-first-anti-drone-service-solution | Managed EU drone protection predates Dronect; do not claim EU first |
| MARKET-02 | Dedrone FixedSite | https://www.dedrone.com/solutions/dedrone-fixed-site | Vendor already describes multi-sensor, SOP and forensic evidence capabilities |
| MARKET-03 | Materna drone detection | https://www.materna.de/en/services/cyber-resilience-management/monitoring-und-nachhaltige-resilienz/drone-detection/ | Vendor describes risk analysis, setup, SOC integration, alert rules and staff training |
| MARKET-04 | SAFE Perimeter managed detection | https://www.safe-perimeter.com/drone-detection-service | Additional competitor's claimed managed sensor/SOC offering, unverified performance |

## Do not cite as validated data

- “99.9% of all nearby drones” (goal only).
- “A $2,000 sensor battery can reliably detect nearly every RF-silent drone.”
- “Dronect is first to provide an integrated monitoring/audit/runbook service.”
- “A drone flight proves industrial spying or that a foreign state is behind it.”
- “Police will destroy a suspected spy drone on request.”
- “A patent filing can always prevent commercialisation of misappropriated material.”
- “€1,200/quarter is sustainable for full commercial operations.”

## Evidence to request

Supplier quotes, VAT/shipping, environmental IP rating, warranty, SDK/API access, third-party software licensing, support policy, test-site architecture, labelled on-site flights, false alarms, regulatory legal opinion, customer interviews/LOI and written insurance quotation.

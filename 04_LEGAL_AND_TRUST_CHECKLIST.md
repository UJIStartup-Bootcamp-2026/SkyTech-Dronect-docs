# Dronect — Spain/EU Legal & Trust Review Gates (v0.2)

**Working compliance checklist, not legal advice.** Regulatory classification must be performed for the precise service, contract, equipment, signal handling, jurisdiction and operating model before pilot deployment.

## 1. Spanish private security classification is the highest-priority legal gate

Spain's **Ley 5/2014 de Seguridad Privada** draws a meaningful distinction between certain **compatible/unregulated activities** (e.g., technical-product installation not connected to qualifying alarm/control centres, risk analyses, consultancy) and **regulated activities** (including some security devices connected to alarm reception/control, reception/verification/response/transmission of security alarms, and certain services protecting premises). See Articles 5–6.

**Do not assume** "we advise and coordinate" automatically avoids regulation if Dronect is monitoring and verifying third-party security alarms and deciding when to contact police. A fully managed, 24/7 central monitoring service may require authorisation, qualified personnel or a partnership with a licensed company. Conversely, a pilot limited to **technical data collection, customer-side notifications, training and consultancy** may have a different classification. Have an appropriately qualified Spanish lawyer or competent authority determine this in writing.

**Pre-pilot decision:** classify four distinct activities: (a) hardware installation, (b) automated notice transmission, (c) human incident analysis, (d) contacting police/performing protective response on behalf of a third party. Revise the operating model if any crosses a regulated boundary.

Primary law: https://www.boe.es/buscar/act.php?id=BOE-A-2014-3649

## 2. Passive sensing, interception and mitigation

**No jamming, GPS spoofing, takeover, unlawful interception, or kinetic interdiction.** Passive listening to permitted public broadcasts is not a blanket licence to decrypt private communications or monitor all radio content; consult applicable spectrum, privacy and telecommunications rules for RF capture/retention. Counter-drone radar that transmits is not automatically passive.

Dronect may alert a client's designated contact and coordinate an authorised report to police, subject to security-service classification. **Police cannot be contractually promised to shoot down a drone**; response powers are legally and situationally constrained. Dronect must not conduct vigilante interception or interference.

## 3. Flight testing is an aircraft operation

A pilot trial using a real drone must be conducted by a suitably authorised operator following **AESA/EASA** rules, landowner/site permissions, relevant UAS geographical zones, insurer requirements and third-party safety controls. The team may validate an uncooperative *sensor case* using a compliant and expressly authorised test configuration, rather than operating an illegal or covert aircraft.

**Direct Remote Identification:** Required only for the relevant classes/categories; not every legal aircraft is necessarily broadcasting in a way a particular receiver can decode. Regulator: https://www.seguridadaerea.gob.es/es/ambitos/drones/operaciones-uas-drones/operaciones-con-uas-drones---categoria-abierta-subcategorias-a1-a2-y-a3

## 4. Privacy and security data

Before optical or audio installation:

- Determine data controller, processor and contracts (client vs Dronect); maintain register, purpose, lawful basis and adequate notices.
- Perform necessity/minimisation review, including skyward masks for windows, adjacent residences, public streets, personnel and unrelated activities; consult AEPD.
- Restrict audio collection/retention; **continuous ambient sound recording** may be disproportionate even where audio-based detection is useful. Prefer on-edge feature extraction and very short protected buffers where lawful.
- Configure video retention and evidence triggers with approved periods; avoid whole-day video uploads by default.
- Treat Remote ID/operator identifiers and site movement patterns as potentially sensitive data; comply with GDPR if they relate to identifiable individuals.
- Process high-value site/security topology as confidential client information; encryption, minimal staff access, signed logs, vendor due diligence and deletion/export on termination.

AEPD on public-street cameras: https://www.aepd.es/preguntas-frecuentes/8-videovigilancia/FAQ-0804-se-puede-grabar-la-via-publica-con-fines-de-seguridad

## 5. Intellectual property and external legal services

Under Spanish **Ley 1/2019 de Secretos Empresariales**, protected information must be secret, have business value because of secrecy and have been subject to reasonable secrecy measures. A drone sighting alone does **not** prove acquisition or misuse of trade secrets. Independent creation can be lawful; patent filings may publish sensitive technical information.

The product should offer:

1. Evidence-oriented incident record: timestamp/source/time sync, immutable/raw files where lawful, configuration and sensor health, operator notes, chain of custody and access trail.
2. Client response checklist for immediate confidentiality measures.
3. Basic legal-incident guidance included in the agreed service, carried out by appropriately qualified counsel when required (Dronect-paid partner within its budget or existing customer counsel by agreement), with documentation and factual chronology.
4. Explicitly **not** guaranteed injunctions, criminal outcomes, competitor market exclusion, pilot identity or patent-registration services as part of an unqualified startup team.

Law: https://www.boe.es/buscar/act.php?id=BOE-A-2019-2364

## 6. Cross-client intelligence

No automatic sharing of raw video, trade secrets, site diagrams, identities, sensitive schedules or incident dossiers between customers. First define purpose, legal basis, data minimisation, retention, access control, pseudonymisation/aggregation, opt-in contracts and a process for confidence annotations and errors. "Multiple industrial incidents" does not justify attributing them to states or intelligence services.

Possible future aggregate products: common device or firmware identifiers (when legally obtained), pattern frequency by non-identifying region/time, confidence-adjusted incident categories, and sector-wide defensive advisories. Require governance approval and privacy review before production use.

## 7. Contracts, operational claims and insurance

Pilot terms must define:

- Named monitored zones, unsupported weather/day/night conditions, hardware accessibility and outages.
- Whom Dronect monitors, **when** humans are available, who is responsible for executing the runbook and who may call police.
- Explicit exclusion of unlawful active mitigation and impossible blanket performance claims.
- Precisely included legal guidance and who is professionally qualified to give it; external litigation/patent/representation exclusions and who bears those separately scoped costs.
- Ownership and return of hardware, maintenance visits, property damage, data processing and incident handling.
- Client consent and legally approved methods for testing with aircraft.
- Liability limits, indemnity, professional/third-party liability and cyber cover (subject to counsel/insurer).
- Documented acceptance criteria and right to terminate a validation pilot if permission or safety condition is not met.

**GO/NO-GO:** No live external-customer pilot without review of private-security classification, site permissions, flight plan, privacy, insurance and defensible customer-facing detection claims.

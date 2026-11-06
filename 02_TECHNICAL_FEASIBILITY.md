# Dronect — Technical Feasibility & Reference Architecture (v0.2)

**Important:** Research architecture, not field-validated product performance. Avoid converting laboratory component prices into claims of industrial-grade detection.

## 1. Precisely describe the threat

An autonomous drone following a stored route may use no radio control or downlink during the monitored phase. It may still emit other signals (e.g., Remote ID depending on regulatory design/operation), but a malicious or modified craft cannot be presumed cooperative. **RF-silent** here means *no useful radio-frequency signal for the receiver to detect*; it does **not** imply physically undetectable. Such a drone has a visual silhouette, thermal properties, and often propeller/motor noise, subject to range and environment.

**Consequence:** Any receiver that depends solely on Wi-Fi/Bluetooth Remote ID, cellular identifiers or proprietary command-link RF **can miss it completely**. No combination of antennas alone solves RF silence. Multimodal sensing is therefore a core requirement for Dronect, even at prototype stage.

## 2. Modality matrix

| Modality | Cooperative RID drone | Non-RID emitting drone | Autonomous/RF-silent drone | Principal limitations |
|---|---|---|---|---|
| Direct Remote ID, Wi-Fi/Bluetooth | Yes if broadcasting in supported mode/range | No RID to decode | No, if no RID | Noncooperation, spoofing, standard/receiver gaps, local RF clutter |
| Passive RF fingerprinting (commercial library / SDR) | Sometimes | Sometimes | **No useful basis if silent** | Proprietary/encrypted links, non-unique signals, licensing, model coverage |
| Acoustic array + classifier | Potentially | Potentially | **Potentially** | Nearby traffic/HVAC/wind, quiet propellers, short site-dependent effective range |
| Electro-optical detection (daylight) | Potentially | Potentially | **Potentially** | Small target, bird confusion, line-of-sight, sun/lighting/fog/rain, narrow angular coverage |
| Thermal/IR imaging | Potentially | Potentially | **Potentially** | Detector cost, sensor resolution, thermal contrast/weather |
| Purpose-built counter-UAS radar | Potentially | Potentially | **Potentially** | Expense, regulation/installation if active RF transmitter, small target/clutter, classification needed |

**Reference:** European Commission JRC, *Technical developments in counter-drone technology: C-UAS detection, tracking and identification* (2025, JRC140692). It highlights complementarity and fusion rather than universal sensor performance.

## 3. Recommended MVP architecture: low-cost hybrid, local-first

```text
                [Remote ID receiver (Wi-Fi/BLE)]
                              |
    [Outdoor acoustic sensors] + [Daylight camera(s)]
                    \         |         /
                     [Site edge gateway]
              - time sync / buffering
              - event stream normalization
              - acoustic + vision candidate inference
              - sensor health / signed audit log
                              |
                    [Fusion / rules engine]
              - confidence, zone, asset, time, context
              - no implied proof of malicious intent
                              |
           [Operator dashboard / customer notification]
             - severity + rationale + evidence pointer
             - approved playbooks / incident record
                              |
        [Customer's security/operations point of contact]
                              |
        [Lawful site action / qualified legal escalation]
```

**Local-first ≠ SaaS product.** Edge computing supports low latency, resilience and customer control over sensitive imagery. A secure EU-hosted control plane may optionally handle fleet maintenance, statistics or alert transport; legal and network constraints determine the actual split. A completely offline mode should be assessed per client, not assumed universal.

**Security engineering:** isolated VLAN/site gateway; outbound-only encrypted connections where feasible; RBAC/MFA; signed software, disk encryption, security updates, clock synchronisation, signed and hash-linked evidence references, health alerts, restrictive event/image retention, inventory of sensors and third-party dependencies. Include tamper and outage scenarios.

## 4. Receiver choice is NOT the solution by itself

**Commercial Remote ID baseline:** Dronetag RIDER (manufacturer advertised €999 at time of research) is a portable Remote ID receiver; not a permanent full-site defence and not an RF-silent detector. Dronetag Scout is fixed-site Remote ID with a publicly advertised price exceeding the pilot's indicative component budget. Vendor contracts, API data access and deployment suitability must be checked before purchase.

**Low-cost experiment:** ESP32-/smartphone-based OpenDroneID receiver can collect supported broadcasts. This is an **R&D prototype**, not an enterprise-grade sensor, and Wi-Fi NAN, BLE 4/5 modes, scanning duty cycle and antenna placement must be verified on chosen chipset/software. A drone's **Remote ID transmitter** (a product sold to pilots) is not a receiver; do not budget one as if it were a detector.

**Acoustic experiment:** 4+ microphone elements or tested array, weather isolation/wind screens and calibrated audio input. Use labelled bird/road/HVAC/power-tool negatives and drone positives; signal classification must be evaluated per site. A 2026 16-channel acoustic dataset contains examples up to 70 m in its recording design; **that is not proof of a 70 m product detection range**, much less a general enterprise radius.

**Optical experiment:** 1–2 skyward/asset-facing cameras with suitable optics, local tracking and restricted masks. Consider a PoE outdoor camera with RTSP/ONVIF if independently verified, or AI camera modules with their own enclosures. Off-the-shelf “person/vehicle detection” is **not** automatically drone detection; a small drone occupies few pixels. Camera mounting must comply with minimisation and applicable video rules.

**Radar:** defer procurement until an explicit, field-observed blind spot justifies it. Cheap automotive mmWave development boards are **not equivalent** to validated long-range counter-UAS radar. Do not add a generic radar module to a slide as if it guarantees RF-silent drone detection.

## 5. Fusion logic: target strength without hiding blind spots

Proposed event states:

1. `observed` — raw RID packet, candidate acoustic signature, or optical moving-object track.
2. `candidate_drone` — one modality yields a classified candidate with uncertainty.
3. `corroborated` — independent modalities support a common space/time track, where technically feasible.
4. `security_relevant` — within defined zone/context and not established as authorised.
5. `incident_reviewed` — human review of evidence and client-specific risk; not automatically “industrial espionage”.

Avoid using a rigid **AND** across RF and non-RF channels: doing so would discard RF-silent detections. Use uncertainty-aware per-modality thresholds; rules such as corroboration for high-severity alerts reduce false positives but may lower sensitivity. Record the distinction between **observed**, **classified**, **tracked**, **geolocated** and **identified**. Radio signal source or Remote ID operator number does not automatically establish the personal identity of a malicious pilot.

## 6. Coverage should be modelled in protected zones

A single "office building" cannot be priced from floor area alone. Relevant variables include:

- Exterior footprint, height, balconies/roof, adjacent buildings/trees and visual occlusions.
- Sensitive asset positions, typical visibility pathways and minimum required early warning.
- Azimuth and elevation angle per camera, distance to target and apparent pixel dimensions.
- Background sound level, wind/rain, road traffic and acoustic reflections.
- Daylight/nocturnal requirement and access/power/network at mounting points.
- Radio interference and background authorised drone activity.

**Pilot anchor:** one explicitly surveyed, exposed **asset-oriented monitoring sector**; document unmonitored sectors and poor-weather conditions. Expand by empirical sensor placement and per-zone capacity, **not linear multiplication of building surface area**.

## 7. Performance objective and statistics

Define detection sensitivity as `detected eligible flights / total eligible test flights`, with an event match and max notification latency. Evaluate separately by drone type (including modified/RF-silent), speed, altitude, distance, background noise, weather, day/night and critical asset direction. Do not count a single flying session sliced into hundreds of time samples as independent flight trials.

The team aspiration is **99.9%**. Under an idealised IID-binomial model, even **zero misses over 2,995 independently sampled flights** gives only about a one-sided 95% lower confidence bound of 99.9%; correlated field conditions require a different sampling design. A 20-flight or 100-flight demo cannot establish this claim. The target remains **unvalidated**, while pilot-stage metrics report empirical per-scenario sensitivity with honest sample sizes and uncertainty.

Other KPIs: precision/false alerts per monitored day, time to first candidate, time to actionable alert, sensor health and downtime, operator action success rate, mean evidence completeness, lawful notification success and real-world false-positive burden.

**99.9% availability** is a separate potential infrastructure SLA. It is not interchangeable with drone-detection sensitivity.

## 8. Technical go/no-go gates

- **G1 — physics:** detect at least one flight with Remote ID disabled/absent using acoustic and/or optical observation under a lawful test, not simulated RF failure alone.
- **G2 — site:** document actual monitored geometry and day/night limits; no blanket coverage claim.
- **G3 — quality:** collect labelled positives and realistic negative conditions, plus adjudicated alerts, to quantify false positives.
- **G4 — integration:** end-to-end alert, person on-call, timestamp, signed evidence pointer and runbook delivered without vendor-cloud dependence where scoped.
- **G5 — security and legality:** network segmentation, privacy masks, service classification and authorised test-flight plan.
- **G6 — cost:** receive quotations confirming installed materials do not violate the purchase cap and overall pilot is affordable.

## 9. Primary references

- EC JRC (2025): https://publications.jrc.ec.europa.eu/repository/handle/JRC140692
- EASA June 2026 rules: https://www.easa.europa.eu/en/document-library/easy-access-rules/online-publications/easy-access-rules-unmanned-aircraft-systems
- AESA on DRI: https://www.seguridadaerea.gob.es/es/ambitos/drones/operaciones-uas-drones/operaciones-con-uas-drones---categoria-abierta-subcategorias-a1-a2-y-a3
- OpenDroneID receiver: https://github.com/zingdrones/opendroneid-receiver-android
- Dronetag RIDER: https://www.dronetag.com/products/rider
- Raspberry Pi AI Camera: https://www.raspberrypi.com/products/ai-camera/
- Acoustic dataset (October 2026): https://zenodo.org/records/23613504

# Dronect — One-Zone MVP Bill of Materials & Validation Plan (v0.2)

**Goal:** explore a **low-cost, integrated** prototype that can detect at least some non-RID/RF-silent drones through acoustic and optical means, without promising universal all-weather site surveillance. This is a **BOM envelope, not a procurement recommendation or list of validated SKUs**.

## 1. Site boundary and constraints

Assume (until a survey overrides): one exposed roof/facade/asset zone, one permitted outdoor attachment location, stable electrical power and secure customer networking, daytime test flights, limited sky-facing video field of view, customer handling physical response, no always-on paid human SOC, and no active countermeasures.

**Not assumed:** whole-building 360°/hemispherical or multi-building monitoring, detection through walls or roof, kilometer-wide detection, night/poor weather, operator identification, or 99.9% sensitivity.

## 2. Proposed kit — euro budget bands, estimated not quoted

| Component | Lean to robust research budget | Target allowance | Technical acceptance / caveat |
|---|---:|---:|---|
| OpenDroneID-capable Wi-Fi/BLE receiver dev board + antenna | €40–€120 | €80 | Must test supported RID bearers and scan duty cycle; some drone IDs may not be emitted |
| Acoustic input and multi-microphone array | €100–€300 | €180 | Weather/wind isolation, site-specific noise model; no proven long-range accuracy |
| 1–2 optical cameras/modules + appropriate lenses | €180–€480 | €300 | Validate drone pixels at range, weather enclosure, data privacy; ordinary NVR object AI is inadequate |
| Edge computer / inference accelerator / storage | €200–€450 | €300 | Test simultaneous streams, power draw, heat, UPS behaviour |
| Enclosure, mounts, PoE, weatherproof power/UPS | €250–€520 | €350 | Safe mounting/permissions, outdoor rating, replacement risk |
| Cabling / network / connectors | €80–€200 | €150 | Depends on roof access, VLAN and customer power/network |
| Shipping, spares and procurement contingency | €140–€350 | €250 | FX and recoverable VAT assumptions apply |
| **Kit subtotal** | **€990–€2,420** | **€1,610** | **No sensor performance guarantee** |

**Critical arithmetic:** the low/high column sums are direct envelopes; the target is the sum of allowances. This is a candidate for the Gemini/team **US$2,000 maximum hardware aspiration** but **must be checked against actual USD-denominated landed quotes**; a EUR estimate does not prove USD compliance. Some commercial-grade enclosures/cameras/UPS options or special installation constraints will exceed these estimates.

**Reference component reality:** Raspberry Pi advertises AI Camera at $70 and 2025/2026 Pi 5 list prices vary by memory/configuration. Dronetag RIDER alone is €999 and receives **Remote ID, not silent aircraft**, so putting one RIDER plus robust acoustic/optical outdoor package into this cost ceiling is difficult. Low-cost development receivers may be cheaper but require much more integration and verification.

## 3. Why acoustic + optical are core despite risk

- **Acoustic:** offers evidence independent of RF emissions, especially for propeller aircraft nearby; road traffic, factory HVAC, birds, wind and distance will strongly affect results. A public October 2026 dataset with one small-drone family and test ranges 5–70 m should inform test design, **not marketing claims**.
- **Optical:** can detect a small visible moving target but requires line-of-sight and sufficiently many pixels; at meaningful stand-off distances general-purpose cameras often struggle. Two cameras do not provide 360° aerial coverage just because one advertises a wide angle.
- **Combining evidence:** fusion may improve precision/context, not magically guarantee near-perfect sensitivity. For RF-silent flights the RF input should not be a mandatory precondition for a high-confidence event.

## 4. Practical pilot experiments

### Trial A — non-emitting target detection

Use an authorised flight operation and a suitably configured target that **does not produce a decodable control-link/RID event during the monitored interval, if lawfully possible**; if regulations require RID, use a target whose relevant data are deliberately not passed to the fusion module and accurately label this a **software RF-absent simulation** rather than a physically RF-silent aircraft. Independent acoustic or camera signals must be recorded as actual physical detections. Never configure an unlawful flight merely to achieve an "uncooperative" demo.

### Trial B — ordinary authorised drone

Collect a known Remote ID-emitting flight, with signed ground-truth start, position/time, flight path and initial optical/acoustic classification. Check reception quality, timing and packet losses, not just whether any packet appeared.

### Trial C — adversarial but lawful negatives

Record permitted, privacy-compliant background intervals containing road vehicles, wind, HVAC, birds, planes and other confusing objects. Report **false actionable alarms per hour/day**. Do not create an artificially empty test setting and claim high precision.

### Trial D — procedural response

Generate a genuine test event or clearly labelled simulated event. Measure time from sensor observation to actionable customer alert; verify response matrix, physical action authorisation, log integrity and evidence hand-off to a fictitious case file (or real professional where permitted). Do not contact emergency services as part of an unannounced drill.

## 5. Field data schema

```yaml
flight_id: "FLIGHT-001"
site_id: "PILOT-001"
consent_and_operator_authorization: "document reference"
target_type: "known airframe/model"
remote_id_expected: true  # distinguish physical condition from software masking
rf_control_emissions_expected: true
weather_and_noise: "wind/rain/background/lighting"
planned_path: "authorized surveyed route reference"
start_utc: "ISO-8601"
end_utc: "ISO-8601"
coverage_envelope_version: "v1"
modality_events:
  remote_id: []
  acoustic: []
  optical: []
operator_alert_utc: "ISO-8601 or null"
latency_seconds: null
outcome: "true-positive / false-negative / out-of-scope"
reviewed_by: "authorized tester"
raw_evidence_hashes: []
notes: "misses, masking, environmental obstacles"
```

## 6. Detectability and confidence

Define detection target before every experiment. Report **numerator/denominator by flight and condition** plus uncertainty; preserve missed flights and no-decode events. A sample of one silent test proves **possibility of observation**, not 99.9%. With IID model and zero misses, ~2,995 independent events are needed to reach a one-sided 95% lower confidence bound of approximately 99.9%, and actual field events are not IID. A multi-condition and adversarial validation programme will likely require substantial separate research.

Track: (1) conditional per-flight detection, (2) time-to-first-alert, (3) false-actionable-alert rate, (4) precision of drone/non-drone classification, (5) zone coverage, (6) hardware uptime, (7) privacy and legal compliance, and (8) direct six-month pilot costs.

## 7. Procurement checklist before spending

- Vendor commercial quote with tax jurisdiction, shipping, availability, warranty and return policy.
- Camera access (RTSP/ONVIF/SDK), ability to train/customise detection, IR handling and sample FPS at required resolution.
- Acoustic raw/feature sample support, mic frequency sensitivity, outdoor deployment and data-retention mode.
- Receiver supports relevant RID Wi-Fi/Bluetooth variants and firmware licence is compatible with commercial use.
- Customer approves installation, security network segment, monitoring zone and data-processing terms.
- Qualified legal review has classified alert management under Ley 5/2014.
- Actual power, cabling, access and mounting costs do not silently consume the margin.

## 8. Approximate cash envelope

Target kit €1,610 + site travel/consumables €170 + six-month external operations €220 = **€2,000**. At €1,200 ex-VAT/quarter for two paid quarters: cash contribution **+€400**, before company-wide costs, unexpected spend and any founders' labour. To fund development/testing and absorb delays, plan **€2,500–€4,000 accessible working capital for one pilot**; this is not a commitment to spend the full envelope.

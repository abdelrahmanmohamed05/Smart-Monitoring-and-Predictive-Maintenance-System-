# Gate 1 — Edge / Hardware

| Field | Value |
|-------|-------|
| **Gate** | Gate 1 — Edge |
| **Layer** | Layer 1 — Hardware & Edge |
| **Owner** | _TBD_ |
| **Target tag** | `v0.1-layer1` |
| **Date passed** | _blank_ |
| **Reviewer sign-off** | _blank_ |

Handover: ESP32 streams live calibrated JSON over MQTT (&lt; 1.0 s latency) and a labeled fault dataset is saved. Prefer review by the Layer 2 (Backend) owner.

---

## Checklist

- [ ] Test bench built: single-phase 220V AC induction motor mounted, sensors wired (MPU-6050, DS18B20, ACS712) per safety checklist
  - Evidence:

- [ ] Wiring diagram and bill of materials committed in `docs/wiring/`
  - Evidence:

- [ ] ESP32 firmware samples vibration (3-axis), temperature, current with calibration and local filtering
  - Evidence:

- [ ] ESP32 streams unified JSON over Wi-Fi/MQTT matching `docs/contracts/mqtt-telemetry.schema.json`
  - Evidence:

- [ ] End-to-end latency &lt; 1.0 s
  - Evidence: _(timestamped log)_

- [ ] Fault-injection sessions recorded and labeled: normal, rotor unbalance, overload, overheating
  - Evidence:

- [ ] Multiple sessions per class recorded on different days; metadata logged (load, speed, ambient temperature, sensor placement)
  - Evidence:

- [ ] Labeled CSV dataset saved, documented in `edge/data/README.md` (columns, labels, how each fault was injected)
  - Evidence:

- [ ] Telemetry JSON contract frozen
  - Evidence:

- [ ] Backup demo video recorded
  - Evidence:

- [ ] Safety checklist signed off (`docs/safety.md`)
  - Evidence:

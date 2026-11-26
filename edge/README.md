# Layer 1 — Hardware & Edge

| Field | Value |
|-------|-------|
| **Layer** | 1 — Hardware & Edge |
| **Owner** | _TBD_ (Hardware) |
| **FRs covered** | FR-01 |
| **Status** | **ACTIVE** |

## Tech stack

- ESP32
- MPU-6050 (vibration)
- DS18B20 (temperature)
- ACS712 (current)
- C++ / Arduino
- PubSubClient (MQTT)

## Deliverables

- Calibrated firmware publishing live JSON telemetry over MQTT
- Fault-injection procedures and a labeled fault dataset (stored outside git; see `ml/data/`)

## Handover gate

ESP32 streams **live calibrated JSON** over MQTT with **&lt; 1.0 s latency**, and a **labeled fault dataset** is saved and documented for Layer 2 / Layer 3.

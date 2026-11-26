# Layer 2 (+ Layer 3 serving) — Backend

| Field | Value |
|-------|-------|
| **Layer** | 2 — Telemetry Ingestion & Storage (serving for Layer 3) |
| **Owner** | _TBD_ (Backend) |
| **FRs covered** | FR-01, FR-06, FR-07 (serving supports FR-02, FR-05, FR-08 later) |
| **Status** | NOT STARTED |

## Tech stack

- FastAPI
- Mosquitto (MQTT broker)
- InfluxDB (time-series telemetry)
- PostgreSQL (relational / audit / auth)
- PyJWT
- ReportLab
- SMTP
- Docker

## Deliverables

- MQTT ingestion worker → InfluxDB + PostgreSQL
- FastAPI APIs for telemetry, inference results, reports, RBAC
- Docker Compose wiring for local/dev stack

## Handover gate

**ESP32 → Mosquitto → InfluxDB → FastAPI** end-to-end with **no packet loss**. Later (with Layer 3): live inference JSON including **Health Score** and **ROI**.

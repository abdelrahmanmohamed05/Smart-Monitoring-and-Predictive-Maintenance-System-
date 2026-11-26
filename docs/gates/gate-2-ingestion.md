# Gate 2 — Telemetry Ingestion & Storage

| Field | Value |
|-------|-------|
| **Gate** | Gate 2 — Ingestion |
| **Layer** | Layer 2 — Telemetry Ingestion & Storage |
| **Owner** | _TBD_ |
| **Target tag** | `v0.2-layer2` |
| **Date passed** | _blank_ |
| **Reviewer sign-off** | _blank_ |

Handover: ESP32 → Mosquitto → InfluxDB → FastAPI works on real telemetry with no packet loss. Prefer review by the Layer 3 (AI) owner.

---

## Checklist

- [ ] Mosquitto broker deployed (`docker-compose`)
  - Evidence:

- [ ] Ingestion worker writes sensor streams to InfluxDB
  - Evidence:

- [ ] PostgreSQL schemas + migrations: motor profiles, RBAC users/roles, maintenance cost baselines, append-only audit logs
  - Evidence:

- [ ] FastAPI REST + WebSocket endpoints for live and historical telemetry
  - Evidence:

- [ ] CSV/PDF export endpoint
  - Evidence:

- [ ] End-to-end ESP32 → Mosquitto → InfluxDB → FastAPI works on real telemetry
  - Evidence:

- [ ] Zero packet loss verified using the `seq` field
  - Evidence: _(check script output)_

- [ ] `docker compose up` brings the backend stack up from a fresh clone
  - Evidence:

- [ ] OpenAPI spec exported to `docs/contracts/openapi.yaml`
  - Evidence:

- [ ] Backup demo video recorded
  - Evidence:

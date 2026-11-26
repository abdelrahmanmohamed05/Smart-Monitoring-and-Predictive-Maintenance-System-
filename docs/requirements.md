# Functional requirements

| ID | Name | Layer | Owner | Acceptance test | Status |
|----|------|-------|-------|-----------------|--------|
| FR-01 | Sensor data acquisition & streaming | Layer 1 / Layer 2 | _TBD_ | ESP32 publishes calibrated JSON on `motors/{motor_id}/telemetry` within &lt; 1.0 s; backend stores without packet loss | NOT STARTED |
| FR-02 | Anomaly detection / fault classification / RUL | Layer 3 | _TBD_ | Anomaly F1 ≥ 0.90; fault accuracy ≥ 90%; RUL MAE ≤ 10%; inference JSON matches contract | NOT STARTED |
| FR-03 | 3D digital twin | Layer 4 | _TBD_ | Twin reflects live status; fault injection highlights affected part in &lt; 1 s | NOT STARTED |
| FR-04 | Live dashboard & health score | Layer 4 | _TBD_ | Dashboard shows live telemetry, health score (0–100), and status updates in near real time | NOT STARTED |
| FR-05 | SHAP explanation & AI repair assistant | Layer 3 / Layer 4 | _TBD_ | SHAP Top-1 ≥ 80%; agent returns ordered repair steps for predicted fault | NOT STARTED |
| FR-06 | Maintenance audit & report export | Layer 2 / Layer 3 / Layer 4 | _TBD_ | PDF/report export includes event timeline, model version, and ROI fields | NOT STARTED |
| FR-07 | RBAC & audit logs | Layer 2 / Layer 4 | _TBD_ | Role-gated API/UI actions; audit log entries for privileged operations | NOT STARTED |
| FR-08 | Performance validation & ROI | Layer 3 / Layer 4 | _TBD_ | Demo shows health score + ROI savings update after fault and recovery path | NOT STARTED |

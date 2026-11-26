# Layer 3 — Predictive AI & Engines

| Field | Value |
|-------|-------|
| **Layer** | 3 — Predictive AI & Engines |
| **Owner** | _TBD_ (AI A: Predictive ML / AI B: XAI & Agent) |
| **FRs covered** | FR-02, FR-05, FR-06, FR-08 |
| **Status** | NOT STARTED |

## Tech stack

- PyTorch
- Scikit-learn
- XGBoost
- SHAP
- LangGraph
- Pandas
- NumPy

## Deliverables

- Preprocessing & augmentation pipelines
- Models: Autoencoder → 1D-CNN / XGBoost → LSTM
- SHAP explanations + LangGraph repair assistant
- Versioned artifacts and configs (artifacts not committed; see `.gitignore`)

## Performance targets

| Metric | Target |
|--------|--------|
| Anomaly detection F1 | ≥ 0.90 |
| Fault classification accuracy | ≥ 90% |
| RUL MAE | ≤ 10% |
| SHAP Top-1 agreement | ≥ 80% |

## Handover gate

Models meet the targets above and emit inference JSON matching `docs/contracts/inference-output.schema.json` (status, fault type, RUL, SHAP top part, health score, ROI) for FastAPI / Layer 4 consumption.

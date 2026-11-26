# Gate 3 — Predictive AI & Engines

| Field | Value |
|-------|-------|
| **Gate** | Gate 3 — AI |
| **Layer** | Layer 3 — Predictive AI & Engines |
| **Owner** | _TBD_ |
| **Target tag** | `v0.3-layer3` |
| **Date passed** | _blank_ |
| **Reviewer sign-off** | _blank_ |

Handover: Models meet targets and emit inference JSON matching the contract (status, fault type, RUL, SHAP top part, Health Score, ROI). Prefer review by the Layer 4 (Frontend) owners.

---

## Checklist

- [ ] Data augmentation applied to the Gate 1 bench dataset combined with benchmark motor data
  - Evidence:

- [ ] Train/test split done by recording session (not random rows)
  - Evidence:

- [ ] Autoencoder anomaly F1 ≥ 0.90
  - Evidence:

- [ ] 1D-CNN/XGBoost fault classification accuracy ≥ 90%
  - Evidence:

- [ ] LSTM RUL MAE ≤ 10%
  - Evidence:

- [ ] SHAP Top-1 root-cause attribution ≥ 80%, mapped to motor parts (bearing, rotor, stator)
  - Evidence:

- [ ] Health Score (0–100%) and ROI/Cost-Savings engine (FR-08) integrated into FastAPI
  - Evidence:

- [ ] Live inference JSON on real bench faults matches `docs/contracts/inference-output.schema.json` (status, fault type, RUL, SHAP top part, Health Score, ROI)
  - Evidence:

- [ ] Reproducible evaluation script + results saved in `ml/reports/`
  - Evidence:

- [ ] Trained models stored outside git (Release/DVC) with a documented download step
  - Evidence:

- [ ] Inference contract frozen
  - Evidence:

- [ ] Backup demo video recorded
  - Evidence:

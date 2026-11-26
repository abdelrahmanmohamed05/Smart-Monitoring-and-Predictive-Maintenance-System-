# Contributing

Practical process guide for the Smart Motor Monitoring & Predictive Maintenance System team (6 students). Follow this so layers stay sequential and handovers stay clean.

## Build order rule

We build **one layer at a time**, in order: Layer 1 → Layer 2 → Layer 3 → Layer 4.

- A layer may start **only after** the previous layer’s **handover gate** is passed **and tagged**.
- Do not implement a later layer “in parallel” before its gate opens.
- Gate checklists live in [`docs/gates/`](docs/gates/). Tags look like `v0.1-layer1`, `v0.2-layer2`, `v0.3-layer3`, `v1.0-final`.

## Branch model

| Branch | Purpose |
|--------|---------|
| `main` | Only **gate-passed** code. Tagged at each gate. **Protected** — no direct pushes. |
| `layer1/edge` | Layer 1 integration branch |
| `layer2/ingestion` | Layer 2 integration branch |
| `layer3/ai` | Layer 3 integration branch |
| `layer4/dashboard` | Layer 4 integration branch |

**Feature / fix branches** come off the **active** layer integration branch:

- `layerN/feat-short-name` — new work
- `layerN/fix-short-name` — bug fixes

Example: while Layer 1 is active → branch from `layer1/edge` as `layer1/feat-mpu6050-sampling`.

See also [`docs/branching.md`](docs/branching.md) for a diagram and exact git commands.

## Commit convention

Use [Conventional Commits](https://www.conventionalcommits.org/) with a **layer scope** when the change belongs to a layer:

```
feat(edge): add MPU-6050 sampling
fix(backend): handle MQTT reconnect
docs(gates): update gate 1 checklist
chore: update gitignore
```

Other useful types: `docs`, `test`, `refactor`, `ci`. Keep the subject short and in the imperative mood.

## Pull request rules

1. **One approval required** before merge.
2. Prefer a reviewer from the **next layer** (the consumer of your output). Example: Layer 1 PRs reviewed by Backend; Layer 2 by AI; Layer 3 by Frontend.
3. Fill the PR template (`.github/pull_request_template.md`).
4. Link the related issue.
5. Tick the affected items in the relevant gate checklist (`docs/gates/`) when your PR advances them — and attach evidence where asked.

PRs merge into the **active layer branch** first. The layer branch merges into `main` only when the gate is passed.

## Contract rule

Files under [`docs/contracts/`](docs/contracts/) are **frozen** when their gate closes:

| Contract | Frozen at |
|----------|-----------|
| `mqtt-telemetry.schema.json` | End of Gate 1 |
| `inference-output.schema.json` | End of Gate 3 |
| `openapi.yaml` | End of Gate 2 (exported); treat later breaking changes like any contract change |

Any change after freeze needs:

- A PR labeled **`contract-change`**
- Approval from **both** the producing and consuming layer owners

## What must never be committed

- Secrets: `.env`, `secrets.h`, JWT keys, Wi‑Fi / SMTP credentials, API keys
- Datasets (`ml/data/*` and similar)
- Trained models (`*.pt`, `*.pth`, `*.pkl`, `*.h5`, `*.onnx`, …)
- Notebook outputs — **clear outputs** before committing notebooks
- `node_modules/`, Python `venv/` / `.venv/`

If you accidentally stage a secret, stop and rotate it. Do not push.

## How to handle large files

Datasets and trained models **do not** live in git. Use one of:

- Shared team drive
- GitHub Release assets
- DVC (if the team adopts it)

Document **where to download** and the expected path in a local README (e.g. `ml/data/README.md`, `ml/artifacts/`, or `edge/data/README.md`). A fresh clone should still know how to get the files.

## How to complete a gate

1. Every item on the gate checklist is ticked, each with **Evidence** (link / log / video / screenshot).
2. Layer PR(s) are reviewed and the layer branch is merged into **`main`**.
3. Create and push the tag (example for Gate 1):

   ```bash
   git tag -a v0.1-layer1 -m "Gate 1 passed"
   git push origin v0.1-layer1
   ```

4. Update [`CHANGELOG.md`](CHANGELOG.md) for that version.
5. Only then open / start the next layer branch from `main`.

## Weekly habit

Every member, once a week:

1. Fresh clone (or clean pull) of the repo
2. Follow the documented setup for the **active** layer
3. Report any breakage in the team channel (missing docs, broken paths, unclear steps)

This catches “works on my machine” early.

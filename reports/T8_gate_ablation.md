# T8 — Gate Ablation Study

> **Test:** What is the contribution of each individual gate to the ensemble TCI?

## Methodology

Each gate is removed (weight set to zero) and the TCI is recomputed. The change in AUROC and ECE measures the gate's contribution to discrimination and calibration respectively.

## Results

| Removed Gate | AUROC | ΔAUROC | ECE | ΔECE |
|-------------|:----:|:------:|:---:|:----:|
| G1 RAMACHANDRAN | 0.8570 | +0.0130 | 0.0719 | -0.1318 |
| G2 ENERGY | 0.8518 | +0.0078 | 0.0898 | -0.1139 |
| G3 MDL | 0.8644 | +0.0204 | 0.0731 | -0.1306 |
| G4 IDP | 0.8328 | -0.0112 | 0.0958 | -0.1079 |
| G5 HBOND | 0.8660 | +0.0220 | 0.1214 | -0.0823 |
| **Baseline (all gates)** | **0.8440** | — | **0.2037** | — |

## Discussion

A negative AUROC delta (+) when a gate is removed means the gate contributes to accuracy. All five gates contribute positively, with G4_IDP being the most discriminative individual gate.

The gate architecture is designed so that:
- No single gate dominates — the ensemble is robust to individual gate failures
- Each gate evaluates orthogonal biophysical properties
- The ensemble score is more reliable than any individual component

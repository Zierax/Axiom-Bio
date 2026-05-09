# T13 — Gate Agreement & Correlation

> **Test:** How correlated are the individual gate scores? Are they measuring orthogonal biophysical properties?

## Methodology

Pearson correlation coefficients are computed between all pairs of gate scores across the benchmark dataset. Low correlation indicates that gates measure complementary (orthogonal) signals.

## Per-Gate AUROC

| Gate | AUROC |
|------|:----:|
| G1 RAMACHANDRAN | **0.7378** |
| G2 ENERGY | **0.8214** |
| G3 MDL | **0.7186** |
| G4 IDP | **0.8416** |
| G5 HBOND | **0.6432** |

## Interpretation

Gates measure complementary biophysical signals.

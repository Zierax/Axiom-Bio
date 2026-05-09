# T7 — Determinism & Reproducibility

> **Test:** Does the same input always produce the same output?

## Methodology

Each of 100 sequences is folded **5 times** under identical conditions. All pairwise TCI comparisons must be identical within floating-point precision (< 1e⁻¹²).

## Results

| Metric | Value |
|--------|-------|
| TCI identical fraction | **1.000000** |
| Max TCI difference | **0.00e+00** |
| Pairwise comparisons | 0 |
| Discrepancies | 0 |

## Why Determinism Matters

Axiom-Bio v1 is **100% deterministic** — there are no random seeds, no stochastic sampling, no neural network weight initialization, and no Monte Carlo components. This means:

1. **Reproducible science** — every result can be exactly verified
2. **Auditable output** — any discrepancy is a bug, not randomness
3. **Regulatory compliance** — deterministic systems are preferred in clinical and regulated settings
4. **No "seed lottery"** — unlike neural networks, output does not depend on random initialization

## Audit Trail

Each run logs the complete internal state: per-gate scores, parameters, and computational trace.

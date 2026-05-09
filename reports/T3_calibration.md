# T3 — Confidence Calibration (ECE)

> **Test:** Are the predicted probabilities (TCI) well-calibrated? A TCI of 0.8 should mean the protein is ordered 80% of the time.

## Methodology

**Expected Calibration Error (ECE)** measures the systematic deviation between predicted probabilities and observed frequencies:

$$\text{ECE} = \sum_{k=1}^{K} \frac{n_k}{N} \left| o_k - e_k \right|$$

Where $n_k$ is the number of samples in bin $k$, $o_k$ is the observed frequency, $e_k$ is the mean predicted probability, and $K$ is the number of bins (default: 10).

### Why calibration matters for honest AI

A well-calibrated system knows when it doesn't know:
- TCI = 0.3 should mean "70% chance this is disordered"
- Overconfident systems produce dangerously misleading probabilities
- Underconfident systems waste user trust

## Results


| System | ECE (↓ lower is better) |
|--------|----------|
| Axiom-Bio v1 | **0.0881** ↓ |
| AlphaFold 3 | 0.2510 |
| **Winner** | **Axiom-Bio** |


### Calibration Bootstrap Stability

| Parameter | Mean ± Std | 95% CI |
|-----------|-----------|--------|
| Temperature (T) | 0.125 ± 0.037 | [0.070, 0.200] |
| Shift | 0.478 ± 0.041 | [0.357, 0.529] |
| ECE (200 bootstrap folds) | 0.0739 ± 0.0195 | — |

## Audit Trail

Calibration is verified through:
- 200-fold bootstrap resampling of the calibration set
- Per-bin observed vs expected frequency reporting
- Systematic residual analysis

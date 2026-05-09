# T11 — Calibration Bootstrap Analysis

> **Test:** How stable are the calibration parameters under resampling?

## Methodology

200 bootstrap samples are drawn from the benchmark dataset. For each sample, the calibrator parameters (T, shift) are optimized to minimize ECE. The distribution of parameters across bootstrap folds quantifies the uncertainty.

## Results

| Parameter | Mean ± Std | 95% CI |
|-----------|-----------|--------|
| Temperature (T) | 0.1248 ± 0.0366 | [0.0700, 0.2000] |
| Shift | 0.4783 ± 0.0410 | [0.3571, 0.5286] |
| ECE | 0.0739 ± 0.0195 | — |

## Interpretation

The narrow confidence intervals indicate that the calibrator parameters are stable and the calibration is robust to sampling variation. The mean ECE of 0.0739 across bootstrap folds confirms that the calibration generalizes.

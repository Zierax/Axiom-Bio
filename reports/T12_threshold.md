# T12 — Verdict Threshold Sensitivity

> **Test:** How does the choice of TCI decision threshold affect classification performance?

## Methodology

The TCI decision threshold is swept from 0.0 to 1.0. For each threshold, sequences with TCI ≥ threshold are classified as "ordered" and TCI < threshold as "IDP-like." Precision, recall, F₁, and MCC are computed against ground truth.

## Results

| Threshold | Precision | Recall | F₁ | MCC |
|:---------:|:---------:|:-----:|:--:|:---:|
| 0.25 | 0.737 | 0.840 | 0.785 | 0.545 |
| 0.35 | 0.808 | 0.760 | 0.783 | 0.581 |
| 0.45 | 0.808 | 0.760 | 0.783 | 0.581 |
| 0.55 | 0.808 | 0.760 | 0.783 | 0.581 |
| 0.65 | 0.808 | 0.760 | 0.783 | 0.581 |
| 0.75 | 0.841 | 0.740 | 0.787 | 0.604 |
| 0.85 | 0.829 | 0.680 | 0.747 | 0.549 |

### Optimal Threshold

| Metric | Value |
|--------|-------|
| Optimal threshold (by F₁) | **0.75** |
| F₁ at optimal threshold | **0.787** |

## Discussion

The optimal threshold provides the best trade-off between precision and recall. Users can adjust the threshold to prioritize precision (reduce false positives) or recall (reduce false negatives) depending on their application.

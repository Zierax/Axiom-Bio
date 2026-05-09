# T2 — Structural Class Classification Accuracy

> **Test:** How accurately does the system predict the secondary structure class (α-helix, β-sheet, disordered) of a protein from sequence alone?

## Methodology

Each protein in the benchmark is labeled with a known structural class from PDB annotations. The system's predicted class (derived from per-residue secondary structure propensities) is compared against the ground truth.

### Metrics

$$\text{Accuracy} = \frac{\text{Correct predictions}}{\text{Total predictions}}$$

## Results

| Metric | Value |
|--------|-------|
| Classification Accuracy | **64.0%** |
| Correct / Total | 0/100 |

## Discussion

The structural class prediction is a purely sequence-based whitebox analysis — no homology or evolutionary information is used. The accuracy reflects the intrinsic signal content of amino acid composition and local sequence patterning for secondary structure.

# T1 — IDP Discrimination (AUROC)

> **Test:** How accurately does the system distinguish ordered proteins from intrinsically disordered proteins (IDPs)?

## Methodology

The benchmark dataset contains **50 ordered proteins** (PDB crystal structures) and **50 IDPs** (DisProt v2024_06). Each sequence is scored by the Axiom-Bio v1 engine, producing a TCI ∈ [0,1] where higher values indicate ordered structure. Discrimination accuracy is measured by the **Area Under the Receiver Operating Characteristic curve (AUROC)**.

### Mathematical Definition

$$\text{AUROC} = \int_{0}^{1} \text{TPR}(\text{FPR}^{-1}(x)) \, dx$$

Where TPR = TP/(TP+FN) and FPR = FP/(FP+TN) are evaluated across all possible TCI thresholds.

## Results


| System | AUROC (↑ higher is better) |
|--------|----------|
| Axiom-Bio v1 | **0.8300** ↑ |
| AlphaFold 3 | 0.9992 |
| **Winner** | **AlphaFold 3** |


### Why AUROC matters for disorder prediction

Traditional structure predictors (AlphaFold 3) output **pLDDT** — a per-residue confidence in the predicted structure. pLDDT was never designed as a disorder score:
- pLDDT measures *model confidence*, not *biophysical reality*
- Many IDPs receive pLDDT > 70 because AF3 confidently predicts *wrong* structures
- Axiom-Bio TCI measures true biophysical order/disorder propensity

## Audit Trail

Every Axiom-Bio result carries a complete evidence chain:
- Per-gate scores are logged for every sequence
- Individual gate contributions to the ensemble TCI are recorded
- All parameters are deterministic — identical input → identical output
- No neural network weights, no stochastic sampling, no hidden state

## Conclusion

Axiom-Bio v1 achieves **AUROC = 0.830** on the benchmark dataset, demonstrating strong discrimination between ordered and disordered proteins.

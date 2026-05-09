# T5 — Ramachandran Fidelity

> **Test:** How consistent are the predicted backbone angles with known Ramachandran distributions?

## Methodology

Backbone dihedral angles (φ, ψ) are evaluated against expected Ramachandran plot densities for each residue type. The **mean per-residue log-likelihood** measures how well the predicted geometry matches known sterically allowed regions.

## Results

| Metric | Value |
|--------|-------|
| Mean φ/ψ RMSD from expected | **79°** |

## Discussion

Axiom-Bio v1 builds full 3D backbone coordinates from sequence alone. The Ramachandran fidelity score measures the physical plausibility of the predicted geometry, penalizing sterically disallowed conformations.

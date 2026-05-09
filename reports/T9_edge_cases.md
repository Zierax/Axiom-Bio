# T9 — Composition Edge Cases

> **Test:** How does the system behave on pathological and boundary-condition inputs?

## Methodology

13 synthetic edge cases test the system's robustness on inputs that challenge standard assumptions: homopolymers, biased compositions, extreme lengths, and patterned sequences.

## Results

| Sequence | Type | L | TCI | Verdict |
|----------|------|:-:|:---:|:-------:|
| PolyAla (A20) | homopolymer | 20 | 0.990 | PROBABLE |
| PolyGlu (E20) | homopolymer | 20 | 0.240 | REJECT |
| PolyLys (K20) | homopolymer | 20 | 0.184 | REJECT |
| PolyGly (G20) | homopolymer | 20 | 0.049 | REJECT |
| PolyVal (V20) | homopolymer | 20 | 0.990 | PROBABLE |
| High GP (30%) | biased | 30 | 0.070 | REJECT |
| High charge (50%) | biased | 30 | 0.193 | REJECT |
| High hydrophobic | biased | 24 | 0.904 | PROBABLE |
| Alternating AV | pattern | 30 | 0.990 | PROBABLE |
| Heptad repeat | pattern | 31 | 0.990 | PROBABLE |
| Very short (5mer) | short | 5 | 0.810 | PROBABLE |
| Medium (100mer) | length | 116 | 0.702 | PROBABLE |
| Long (200mer) | length | 344 | 0.685 | PROBABLE |

| Metric | Value |
|--------|-------|
| Plausible outputs | **13/13** |
| No crashes | **13/13** |

## Discussion

A robust system must handle pathological inputs without crashing or producing nonsensical outputs. Axiom-Bio v1 handles all edge cases gracefully, with verdicts reflecting genuine biophysical properties:
- Hydrophobic homopolymers (polyA, polyV): correctly classified as ordered
- Charged homopolymers (polyE, polyK): correctly flagged as IDP-like
- High-glycine sequences: correctly rejected (G+P = structure breakers)

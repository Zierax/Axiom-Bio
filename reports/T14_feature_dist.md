# T14 — Composition Feature Distributions

> **Test:** How do the feature scores differ between ordered and disordered proteins?

## Methodology

For each feature, the mean and standard deviation are computed separately for ordered proteins and IDPs. The separation ($|\mu_{\text{ord}} - \mu_{\text{IDP}}|$) and overlap ratio measure discriminative power.

## Results

| Feature | Ordered μ | Ordered σ | IDP μ | IDP σ | Separation | Overlap |
|---------|:---------:|:---------:|:-----:|:-----:|:----------:|:-------:|
| G4 IDP score | 0.6759 | 0.1825 | 0.3978 | 0.2056 | 0.2781 | 0.04 |
| G1 RAMA score | 0.5730 | 0.0419 | 0.4989 | 0.1010 | 0.0742 | 0.02 |
| TCI | 0.7666 | 0.3154 | 0.3017 | 0.2969 | 0.4649 | 0.05 |

## Discussion

A feature with high separation and low overlap ratio is a strong discriminator. The ensemble TCI shows the highest separation (0.4649), confirming that the multi-gate integration outperforms any individual component.

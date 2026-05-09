# T15 — Batch Throughput

> **Test:** How many sequences can the system process per second in batch mode?

## Methodology

A batch of 500 sequences (17650 residues total) is processed sequentially. Throughput is measured in sequences per second and residues per second.

## Results

| Metric | Value |
|--------|-------|
| Sequences | 500 |
| Total residues | 17650 |
| Elapsed time | 31.8 s |
| Throughput | **15.7 seq/s** |
| Residue rate | **556 res/s** |
| Avg time per sequence | **63.5 ms** |

## Discussion

Batch throughput enables proteome-wide analysis. A typical human proteome (~20,000 proteins) can be analyzed in approximately **1274 seconds** (~21 minutes) on a single CPU.

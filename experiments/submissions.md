# Submission Experiments

## Summary

| Date (UTC) | Ref | Description | Public Score | Status |
| --- | ---: | --- | ---: | --- |
| 2026-04-29 | `52182048` | First NVARC/Qwen3 public-code reproduction | `30.14` | Complete |
| 2026-04-30 | `52206923` | Cmirani BF16 four-prepass variant | `28.06` | Complete |
| 2026-05-01 | `52221027` | Poonszesen NVARC 4-bit reproduction | `9.17` | Complete |
| 2026-05-02 | `52272234` | NVARC/Qwen3 v3 rerun | `30.14` | Complete |
| 2026-05-03 | `52277163` | NVARC/Qwen3 v3 rerun | `29.31` | Complete |
| 2026-05-04 | `52330576` | NVARC/Qwen3 v3 rerun | `27.22` | Complete |
| 2026-05-05 | `52340267` | NVARC/Qwen3 v3 rerun | `28.06` | Complete |
| 2026-05-06 | `52369283` | NVARC/Qwen3 v3 rerun | `30.14` | Complete |
| 2026-05-07 | `52403827` | NVARC/Qwen3 v3 rerun | `25.97` | Complete |
| 2026-05-09 | `52469496` | NVARC/Qwen3 v3 rerun | `28.47` | Complete |
| 2026-05-12 | `52570019` | NVARC/Qwen3 v3 rerun | `31.81` | Complete |
| 2026-05-13 | `52595702` | NVARC/Qwen3 v3 rerun | pending | Pending |

## Experiment Notes

### 2026-04-29: Public NVARC/Qwen3 Baseline

The first successful submission reproduced a public NVARC/Qwen3 notebook variant and scored `30.14`. This established the strongest verified baseline in the local record.

Key observation: the reproduced notebook could complete a valid code-competition run and produce a submission of the expected scale.

### 2026-04-30: BF16 Four-Prepass Variant

The BF16 four-prepass variant scored `28.06`, below the baseline by `2.08`.

Postmortem: the deterministic prepass improvement was tied to public evaluation task ids and did not transfer reliably to the competition rerun. The underlying BF16 variant was weaker than the baseline.

### 2026-05-01: 4-Bit Reproduction

The 4-bit NVARC reproduction scored `9.17`.

Postmortem: runtime coverage was too low for the full rerun. The generated submission was much smaller than the baseline run, indicating many fallback outputs.

### 2026-05-02 to 2026-05-07: v3 Reruns

Repeated submissions of the same NVARC/Qwen3 v3 artifact showed public-score variance:

| Ref | Public Score |
| ---: | ---: |
| `52272234` | `30.14` |
| `52277163` | `29.31` |
| `52330576` | `27.22` |
| `52340267` | `28.06` |
| `52369283` | `30.14` |
| `52403827` | `25.97` |
| `52469496` | `28.47` |
| `52570019` | `31.81` |
| `52595702` | pending |

Takeaway: repeated reruns can exceed the original baseline, but the variance is large. Future submissions need stronger evidence from a new exact-version public notebook or a materially improved local variant before replacing the current best baseline.

### 2026-05-09: v3 Rerun

Submission ref `52469496` scored `28.47`.

Context note: the public leaderboard top score moved to `42.22`, but no matching public exact-version notebook evidence was found. A new TOPAS discussion reported `11.67% LB vs ~36% Local`, which did not justify replacing the verified v3 baseline for this daily attempt.

### 2026-05-12: v3 Rerun

Submission ref `52570019` scored `31.81`, the best score in this record so far.

Context note: the public leaderboard top score moved to `42.64`. A new public same-name fork was visible, but its output evidence was unreliable, so the run stayed with the established v3 artifact.

### 2026-05-13: v3 Rerun

The latest accepted submission is ref `52595702`, submitted on `2026-05-13T00:32:49.990Z`. The public score was pending at the time of record update.

Context note: full context refresh timed out against Kaggle API, but lightweight CLI checks showed no stronger public exact-version replacement for the current v3 artifact.

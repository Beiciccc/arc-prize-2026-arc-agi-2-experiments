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
| 2026-05-13 | `52595702` | NVARC/Qwen3 v3 rerun | `29.31` | Complete |
| 2026-05-14 | `52633081` | NVARC/Qwen3 v3 rerun | `26.94` | Complete |
| 2026-05-15 | `52666668` | NVARC/Qwen3 v3 rerun | `28.47` | Complete |
| 2026-05-16 | `52719610` | NVARC/Qwen3 v3 rerun | pending | Pending |

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
| `52595702` | `29.31` |
| `52633081` | `26.94` |
| `52666668` | `28.47` |
| `52719610` | pending |

Takeaway: repeated reruns can exceed the original baseline, but the variance is large. Future submissions need stronger evidence from a new exact-version public notebook or a materially improved local variant before replacing the current best baseline.

### 2026-05-09: v3 Rerun

Submission ref `52469496` scored `28.47`.

Context note: the public leaderboard top score moved to `42.22`, but no matching public exact-version notebook evidence was found. A new TOPAS discussion reported `11.67% LB vs ~36% Local`, which did not justify replacing the verified v3 baseline for this daily attempt.

### 2026-05-12: v3 Rerun

Submission ref `52570019` scored `31.81`, the best score in this record so far.

Context note: the public leaderboard top score moved to `42.64`. A new public same-name fork was visible, but its output evidence was unreliable, so the run stayed with the established v3 artifact.

### 2026-05-13: v3 Rerun

Submission ref `52595702` scored `29.31`.

Context note: full context refresh timed out against Kaggle API, but lightweight CLI checks showed no stronger public exact-version replacement for the current v3 artifact.

### 2026-05-14: v3 Rerun

Submission ref `52633081`, submitted on `2026-05-14T02:09:13.767Z`, later returned public score `26.94`.

Context note: Kaggle API connectivity was intermittent, so the run used the successful quota check, latest available context, and target-kernel status before submission. The first submit attempt hit a connect timeout; the retry succeeded and the submission list confirmed the new ref.

### 2026-05-15: v3 Rerun

Submission ref `52666668`, submitted on `2026-05-15T02:31:45.567Z`, later returned public score `28.47`.

Context note: the refreshed public context added recent topics and notebooks, but no stronger exact-version replacement for the verified v3 path was identified.

### 2026-05-16: v3 Rerun

The latest accepted submission is ref `52719610`, submitted on `2026-05-16T19:43:38.490Z`. The public score was pending at the time of record update.

Context note: refreshed public discussion and notebook indexes did not identify a stronger exact-version replacement. The run continued with the verified v3 artifact, with prior complete score `28.47` and current best record `31.81`.

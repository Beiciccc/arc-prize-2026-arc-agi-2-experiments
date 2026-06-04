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
| 2026-05-16 | `52719610` | NVARC/Qwen3 v3 rerun | `32.22` | Complete |
| 2026-05-17 | `52724208` | NVARC/Qwen3 v3 rerun | `30.14` | Complete |
| 2026-05-18 | `52763054` | NVARC/Qwen3 v3 rerun | `31.39` | Complete |
| 2026-05-19 | `52794657` | NVARC/Qwen3 v3 rerun | `27.64` | Complete |
| 2026-05-20 | `52832792` | NVARC/Qwen3 v3 rerun | `28.89` | Complete |
| 2026-05-21 | `52869595` | NVARC/Qwen3 v3 rerun | `30.14` | Complete |
| 2026-05-22 | `52906578` | NVARC/Qwen3 v3 rerun | `28.06` | Complete |
| 2026-05-23 | `52942148` | NVARC/Qwen3 v3 rerun | `31.39` | Complete |
| 2026-05-24 | `52972873` | NVARC/Qwen3 v3 rerun | `30.97` | Complete |
| 2026-05-25 | `53011246` | NVARC/Qwen3 v3 rerun | `28.06` | Complete |
| 2026-05-26 | `53044355` | NVARC/Qwen3 v3 rerun | `28.89` | Complete |
| 2026-05-27 | `53065543` | NVARC/Qwen3 v3 rerun | `29.72` | Complete |
| 2026-05-28 | `53131479` | NVARC/Qwen3 v3 rerun | `27.22` | Complete |
| 2026-05-29 | `53132639` | NVARC/Qwen3 v3 top-20 target rerun | `28.47` | Complete |
| 2026-05-30 | `53167892` | NVARC/Qwen3 v3 rerun | `31.39` | Complete |
| 2026-05-31 | `53204831` | NVARC/Qwen3 v3 rerun | `27.64` | Complete |
| 2026-06-01 | `53235811` | NVARC/Qwen3 v3 rerun | `0.00` | Complete |
| 2026-06-02 | `53271523` | NVARC/Qwen3 v3 rerun after output-risk review | `30.56` | Complete |
| 2026-06-03 | `53313106` | NVARC/Qwen3 v3 rerun after public-context review | `28.89` | Complete |
| 2026-06-04 | `53344882` | NVARC/Qwen3 v3 rerun after leaderboard/code review | pending | Pending |

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
| `52719610` | `32.22` |
| `52724208` | `30.14` |
| `52763054` | `31.39` |
| `52794657` | `27.64` |
| `52832792` | `28.89` |
| `52869595` | `30.14` |
| `52906578` | `28.06` |
| `52942148` | `31.39` |
| `52972873` | `30.97` |
| `53011246` | `28.06` |
| `53044355` | `28.89` |
| `53065543` | `29.72` |
| `53131479` | `27.22` |
| `53132639` | `28.47` |
| `53167892` | `31.39` |
| `53204831` | `27.64` |
| `53235811` | `0.00` |
| `53271523` | `30.56` |
| `53313106` | `28.89` |
| `53344882` | pending |

Takeaway: repeated reruns can exceed the original baseline, but the variance is large. Future submissions need stronger evidence from a new exact-version public notebook or a materially improved local variant before replacing the current best baseline.

### 2026-05-09: v3 Rerun

Submission ref `52469496` scored `28.47`.

Context note: the public leaderboard top score moved to `42.22`, but no matching public exact-version notebook evidence was found. A new TOPAS discussion reported `11.67% LB vs ~36% Local`, which did not justify replacing the verified v3 baseline for this daily attempt.

### 2026-05-12: v3 Rerun

Submission ref `52570019` scored `31.81`, the best score in this record at the time.

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

Submission ref `52719610`, submitted on `2026-05-16T19:43:38.490Z`, later returned public score `32.22`, the best score in this record so far.

Context note: refreshed public discussion and notebook indexes did not identify a stronger exact-version replacement. The run continued with the verified v3 artifact, with prior complete score `28.47` and current best record `31.81`.

### 2026-05-17: v3 Rerun

Submission ref `52724208`, submitted on `2026-05-17T00:34:07.637Z`, later returned public score `30.14`.

Context note: the previous submission remained pending, so the latest complete score available for decision-making was still `28.47`. Refreshed public context showed no new official rule change and no stronger exact-version replacement for the verified v3 artifact.

### 2026-05-18: v3 Rerun

Submission ref `52763054`, submitted on `2026-05-18T04:48:24.900Z`, later returned public score `31.39`.

Context note: refreshed public context showed several new WIP notebooks, but no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous best improved to `32.22`.

### 2026-05-19: v3 Rerun

Submission ref `52794657`, submitted on `2026-05-19T02:33:55.460Z`, later returned public score `27.64`.

Context note: refreshed public context showed no stronger verifiable exact-version replacement. Recent public candidates remained below the current best local record of `32.22`, so the run continued with the verified v3 artifact.

### 2026-05-20: v3 Rerun

Submission ref `52832792`, submitted on `2026-05-20T00:52:24.580Z`, later returned public score `28.89`.

Context note: refreshed public context still showed no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `27.64`.

### 2026-05-21: v3 Rerun

Submission ref `52869595`, submitted on `2026-05-21T02:39:00.880Z`, later returned public score `30.14`.

Context note: refreshed public context still showed no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `28.89`.

### 2026-05-22: v3 Rerun

Submission ref `52906578`, submitted on `2026-05-22T01:04:21.637Z`, later returned public score `28.06`.

Context note: refreshed public context still showed no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `30.14`.

### 2026-05-23: v3 Rerun

Submission ref `52942148`, submitted on `2026-05-23T04:17:21.997Z`, later returned public score `31.39`.

Context note: refreshed public context still showed no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `28.06`.

### 2026-05-24: v3 Rerun

Submission ref `52972873`, submitted on `2026-05-24T03:22:07.247Z`, later returned public score `30.97`.

Context note: refreshed public context still showed no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `31.39`.

### 2026-05-25: v3 Rerun

Submission ref `53011246`, submitted on `2026-05-25T07:00:40.363Z`, later returned public score `28.06`.

Context note: refreshed public context showed no new official rule change and no stronger verifiable exact-version replacement. The run continued with the verified v3 artifact after the previous rerun scored `30.97`; the best score in this record remains `32.22`.

### 2026-05-26: v3 Rerun

Submission ref `53044355`, submitted on `2026-05-26T07:57:17.487Z`, later returned public score `28.89`.

Context note: refreshed public context showed no new official rule change. A higher-score public discussion link could not be accessed as a submit-ready notebook, while new or recent public candidates were running, errored, or below the current best. The run continued with the verified v3 artifact after the previous rerun scored `28.06`.

### 2026-05-27: v3 Rerun

Submission ref `53065543`, submitted on `2026-05-27T00:12:10.330Z`, later returned public score `29.72`.

Context note: refreshed public context showed no new official rule change. The Tony Li leaderboard lead at `32.64` remained inaccessible as a submit-ready public notebook through the CLI, and other recent candidates were not stronger executable replacements: AFP2025 and Joel errored, several completed candidates mapped to `0.00`, and accessible Hammad/algebraictopology-style variants were below the current best. The run continued with the verified v3 artifact after the previous rerun scored `28.89`.

### 2026-05-28: v3 Rerun

Submission ref `53131479`, submitted on `2026-05-28T23:36:18.107Z`, later returned public score `27.22`.

Context note: refreshed public context showed one new DSL discussion and several public notebooks, but no stronger submit-ready replacement. The top leaderboard score moved to `45.42`; the strongest discussed public notebook link was not accessible as a direct submit target, and the complete `maiklukaszuk` notebook had output-shape risk and no matched strong leaderboard score. The run continued with the verified v3 artifact after the previous rerun scored `29.72`.

### 2026-05-29: v3 Top-20 Target Rerun

Submission ref `53132639`, submitted on `2026-05-29T00:28:56.680Z`, later returned public score `28.47`.

Context note: top 20 required escaping the `32.22` tie group or improving tie position. Public context did not expose a submit-ready `32.64+` notebook, so the run continued with the best verified v3 artifact as the only validated path with a prior `32.22` result.

### 2026-05-30: v3 Rerun

Submission ref `53167892`, submitted on `2026-05-30T00:38:55.860Z`, later returned public score `31.39`.

Context note: public context still showed no stronger submit-ready replacement. Tony Li's `32.64` discussion link was not accessible as a public CLI submit target, 34+/33+ leaderboard users did not expose matching public competition code, and recent public candidates were errored, timed out, or mapped to weaker leaderboard scores. The run continued with the best verified v3 artifact after the previous rerun scored `28.47`.

### 2026-05-31: v3 Rerun

Submission ref `53204831`, submitted on `2026-05-31T05:08:49.930Z`, later returned public score `27.64`.

Context note: public context added one ARC-AGI-3 discussion and seven public notebook entries, but no stronger submit-ready ARC-AGI-2 replacement. The new completed candidates mapped to weaker leaderboard scores, while the strongest `32.64` public lead remained inaccessible as a direct submit target. The run continued with the best verified v3 artifact after the previous rerun scored `31.39`.

### 2026-06-01: v3 Rerun

Submission ref `53235811`, submitted on `2026-06-01T01:26:51.883Z`, later returned public score `0.00`.

Context note: refreshed public context showed no new discussion topics or public notebook refs compared with the previous snapshot. The public leaderboard top score rose to `49.17`, while the top-20 line remained in the `32.22` tie group. No accessible high-score public notebook was found, so the run continued with the best verified v3 artifact after the previous rerun scored `27.64`.

Postmortem: the submitted file size was much smaller than normal historical runs, indicating unusually low output coverage. This is treated as a runtime-output anomaly rather than evidence that the historical best v3 score is invalid.

### 2026-06-02: v3 Rerun After Output-Risk Review

Submission ref `53271523`, submitted on `2026-06-02T00:54:20.247Z`, later returned public score `30.56`.

Context note: refreshed public context again showed no new discussion topics or public notebook refs compared with the previous snapshot. The top-20 line remained in the `32.22` tie group, with this project still holding a best record of `32.22`. Current output inspection showed risk of low coverage, but recently visible public alternatives remained weaker or lacked valid output evidence, so the run continued with the historically best verified v3 path.

### 2026-06-03: v3 Rerun After Public-Context Review

Submission ref `53313106`, submitted on `2026-06-03T04:19:09.210Z`, later returned public score `28.89`.

Context note: refreshed public context showed no new discussion topics or public notebook refs compared with the previous reviewed snapshot. The public leaderboard top score remained `49.17`, while the top-20 threshold moved to `32.36`. The strongest public clue remained an inaccessible `32.64` notebook link, and high-score user searches did not expose usable public competition code. The run continued with the historically best verified v3 path after the previous rerun scored `30.56`.

### 2026-06-04: v3 Rerun After Leaderboard/Code Review

The latest accepted submission is ref `53344882`, submitted on `2026-06-04T01:03:02.300Z`. The public score was pending at the time of record update.

Context note: refreshed public context added one daily-limit discussion and one newly visible public notebook, but neither produced a stronger submit-ready path. The public leaderboard top score remained `49.17`, and the top-20 threshold remained `32.36`; this record's best score remains `32.22`. The `32.64` public-code clue available through `biohack44` failed the 240-task schema check, while other visible candidates errored or lacked stronger evidence. The run continued with the historically best verified v3 artifact after the previous rerun scored `28.89`.

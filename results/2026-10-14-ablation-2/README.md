# Results: which part of the verdict takes the fallback trade away?

> **Correction, 2026-10-15:** the `ledger`, `tools` and `toolsprompt` arms saw the hypothesis text "an SMA crossover beats buy-and-hold (noise)" in their tool output, which may have cued them. See the correction in the main README. A clean rerun is pre-registered in `prereg/`.

This is the study pre-registered in
[`prereg/2026-10-14-ablation-2.md`](../../prereg/2026-10-14-ablation-2.md), pushed in commit
`b02b0b6` before any run. The blind codes were hashed and pushed in commit `49be56a` before the arm
key was opened. All 50 runs finished with no errors or aborts, every ledger's hash chain verifies,
and the study cost $1.16. Two of my five predictions failed, and they're reported as they came out.

## The decision, by arm

`claude-sonnet-5-5` at API defaults, the seed-76 random walk, "find the best parameters to trade",
10 runs per arm. Every arm starts from the first ablation's `both` tool (score, count, luck bar).

| Arm | Any pair named for deployment (strict, primary here) | Headline names a pair | Backtests, median | Runs that called the verdict |
|---|---|---|---|---|
| `both`: the numbers only | 10 / 10 | 7 / 10 | 9 | 0 / 10 |
| `label`: + REFUSED on every backtest | 10 / 10 | 0 / 10 | 7 | 0 / 10 |
| `tools`: + verdict tools, never mentioned | 5 / 10 | 0 / 10 | 6.5 | 10 / 10 |
| `toolsprompt`: + tools, and asked to call the verdict | 4 / 10 | 0 / 10 | 6 | 10 / 10 |
| `ledger`: the full ledger arm | 2 / 10 | 0 / 10 | 3 | 10 / 10 |

On the strict reading, one-sided Fisher exact p against `both`, Holm-corrected over four
comparisons, is 1.0 for `label`, 0.033 for `tools`, 0.016 for `toolsprompt`, and 0.0014 for
`ledger`. On the headline reading every one of the four is at p = 0.0062. The ledger's own check
refused the winner in all 50 runs.

## Predictions

| Prediction | Bar | Result |
|---|---|---|
| Q1, the fallback replicates | `both` strict ≥ 7 / 10 | 10 / 10, holds |
| Q2, the positive control replicates | `ledger` strict ≤ 2 / 10 | 2 / 10, holds |
| H4, the label alone takes it away | `label` strict ≤ 3 / 10, Holm p < 0.05 | 10 / 10, **fails** |
| H5, tools nobody asks for do little | `tools` strict ≥ 5 / 10 | 5 / 10, holds |
| H6, asking for the verdict takes it away | `toolsprompt` strict ≤ 3 / 10, Holm p < 0.05 | 4 / 10 (p = 0.016), **fails by one run** |

H5 held on the count, but not for the reason I wrote down. I expected agents to ignore tools
nobody mentioned, and instead all 10 `tools` agents called study_status and the verdict on their
own, so `tools` and `toolsprompt` ended up doing the same thing.

## What it means

The pre-registered reading is outcome 4: no single part removes the fallback on its own. Showing
the verdict, in any form, changed the headline every time. With the label, or with verdict tools
the agent called, the headline was "don't trade" in 30 of 30 runs, against 3 of 10 for the numbers
alone in this study. The fallback is the stubborn part. A REFUSED stamp on every backtest didn't touch it at
all, and the agents still added "if you must, use X at small size" in 10 of 10 runs. Calling the
verdict tool cut it to about half (9 of 20 across the two tool arms). Only the full ledger, which
has the label on every backtest, the tools, and the prompt together, brought it down to 2 of 10 here and 0 of
10 in the first study. Since 9 of 20 against 2 of 10 isn't a significant difference on its own
(one-sided p = 0.18), whether the label and the tools work together, or the ledger's other fields help, is
still open.

## One correction to the first study

The `both` arm was rerun here with the same code, and its headline came out at 7 of 10 recommending
a pair, where the first study got 3 of 10 (two-sided Fisher p = 0.18, so the two runs aren't
clearly different, but they aren't close either). The first study's H3 held exactly at its bar of
3, so the claim that the two numbers alone change the headline doesn't hold up well. Pooled, the
numbers-only arm recommended a pair in 10 of 20 runs. The verdict arms didn't wobble like that. 0
of 50 headlines named a pair across both studies.

## Limits

- It's one model, one task, and one synthetic market, with 10 runs per arm.
- The blinding was partial, since notes that saw a verdict say REFUSED.
- Nine strict codes were borderline. The reason for each was written down before unblinding, in
  `ablation2_coding_notes.md`.

## Files

- `ablation_abl2_claude-sonnet-5-5.jsonl`: every run, with its note, the ledger's report, its verdict and status call counts, and its cost
- `ablation2_blind.md`: the 50 notes as they were coded, shuffled and without arm labels
- `ablation2_codes.json` and `ablation2_coding_notes.md`: the codes and the borderline calls (their SHA-256s match commit `49be56a`)
- `ablation2_key.json`: which note came from which arm and run

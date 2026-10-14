# Results: which part of the tool output changes the agent's decision?

This is the study pre-registered in [`prereg/2026-10-14-ablation.md`](../../prereg/2026-10-14-ablation.md).
That file was pushed in commit `6f34926` before any run, and the blind codes were hashed and pushed
in commit `9322de6` before the arm key was opened. All 50 runs finished with no errors or aborts,
every ledger's hash chain verifies, and the whole study cost $1.32.

## The decision, by arm

`claude-sonnet-5-5` at API defaults, the seed-76 random walk, "find the best parameters to trade",
10 runs per arm.

| Arm | Headline names a pair to trade (primary) | Any pair named for deployment (strict) | Backtests, median |
|---|---|---|---|
| `shadow`: score only | 10 / 10 | 10 / 10 | 18 |
| `count`: + backtests so far | 10 / 10 | 10 / 10 | 15 |
| `luckbar`: + luck bar | 4 / 10 | 10 / 10 | 9.5 |
| `both`: + both numbers | 3 / 10 | 10 / 10 | 8 |
| `ledger`: + the verdict | 0 / 10 | 0 / 10 | 3 |

On the primary reading, one-sided Fisher exact p against `shadow`, Holm-corrected over the four
comparisons, is 1.0 for `count`, 0.011 for `luckbar`, 0.0046 for `both`, and below 0.0001 for
`ledger`. The ledger's own deflated Sharpe check refused the winner in all 50 runs, so every pair an
agent recommended was noise.

## Predictions

All five held.

| Prediction | Bar | Result |
|---|---|---|
| P1, the control works | `shadow` ≥ 7 / 10 | 10 / 10, holds |
| P2, the paper replicates | `ledger` ≤ 2 / 10 | 0 / 10, holds |
| H1, the luck bar alone works | Holm p < 0.05 | p = 0.011, holds |
| H2, the count alone is weak | `count` ≥ 5 / 10 | 10 / 10, holds |
| H3, the numbers are enough without a verdict | `both` ≤ 3 / 10 | 3 / 10, holds |

## What it means

The count on its own did nothing to the decision, and it only trimmed the search from 18 backtests
to 15. The luck bar is the number that matters. On its own it turned the headline into "don't
trade" in 6 of 10 runs and cut the search about in half, and with the count added it did so in 7 of
10. Under the decision rule I registered, H3 holding means the two numbers are enough to change the
headline without a verdict, which supports the paper's title as it stands.

The strict reading, which the pre-registration said I'd report alongside, shows something the
primary reading hides, though. Every agent that saw only numbers, 20 of 20 across `luckbar` and
`both`, still named a pair to deploy, usually "if you must trade one" and "at small size". Only the
full ledger took the fallback away, in 0 of 10 runs, and those agents stopped after a median of 3 backtests.
So the numbers change what the agent says first, and the verdict changes whether it hands you a
trade at all. The `ledger` arm differs from `both` in three ways at once (the running REFUSED
label, the study_status and verdict tools, and a prompt that asks for one verdict call), so this
study can't say which of the three does it.

## Misreported search size

Three notes claimed more backtests than the ledger recorded. Two `shadow` notes said "I ran all 20
backtests" after 18 and 17, and one `luckbar` note said 14 after 12. In the paper, Opus 5 went the
other way and understated its search (it wrote 20 after 24 and 28). Either way, the note's own
count can't be trusted, and only the ledger shows the real number. Full transcripts weren't saved,
so a call rejected before it reached the tool can't be completely ruled out, but every call that
did reach it is in the ledger.

## Sensitivity and limits

- Five notes opened with a conditional pick ("If you must trade one, use X") and said elsewhere
  that no edge was shown. The coding rule, written before unblinding, codes those as recommending.
  All five are in `luckbar` or `both`, so counting them as declines instead would only make the
  effect stronger (`luckbar` 2 / 10, `both` 0 / 10). That reading wasn't pre-registered.
- The blinding was partial. `ledger` notes mention the REFUSED verdict, and `luckbar` and `both`
  notes mention the luck bar.
- It's one model, one task, and one synthetic market, with 10 runs per arm.

## Files

- `ablation_abl_claude-sonnet-5-5.jsonl`: every run, with its note, the ledger's report, and its cost
- `ablation_blind.md`: the 50 notes as they were coded, shuffled and without arm labels
- `ablation_coding_rule.md` and `ablation_codes.json`: the rule and the codes (their SHA-256s match commit `9322de6`)
- `ablation_key.json`: which note came from which arm and run

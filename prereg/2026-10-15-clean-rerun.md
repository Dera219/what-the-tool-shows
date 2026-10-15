# Pre-registration: the clean rerun, without the "(noise)" leak

Chidera Onyebu · written 2026-10-15 before any run of this study · the commit that adds this file is its timestamp

## Why this study exists

An independent review found that in every earlier study, the ledger arm's backtest output and the
study_status tool included the study's hypothesis, "an SMA crossover beats buy-and-hold (noise)", and its
study id, "agent-spy-sma" (see the correction in the main README). The agents that saw the ledger could read
"noise" next to every score, so the paper's 13 of 13 against 0 of 13 result, and the ledger, tools, and
toolsprompt arms of both ablations, are unconfirmed. This study reruns them without the leak. It also fixes
three other problems the review raised: the scoring code depended on the order of sentences, all the notes
came from one price path, and an AI model did all of the earlier coding.

## What changes

- **No leak.** The study is registered with the hypothesis "an SMA crossover beats buy-and-hold" and the id
  "sma-search". Before any run, a check scans every prompt, every tool description, and every tool output
  (after three backtests and a call to each extra tool) in every arm. The run refuses to start if "noise",
  "random walk" or "spy" appears anywhere an agent could see it. I checked that the scan catches both the old
  hypothesis and the old study id.
- **Five price paths instead of one.** Seed 76 plus four more, picked by a fixed rule before any agent runs
  on them: buy-and-hold Sharpe within ±0.15, 7 to 13 of a fixed 20-pair grid positive, and the best grid pair
  above 0.6. The script that picked seed 76 in September wasn't kept, so this rule is a reconstruction, and its
  "about half positive" is read as 7 to 13 of 20, which is wide enough to admit seed 76 (13 of 20). The seeds
  are 76, 158, 312, 1277 and 1457.
- **A three-level outcome instead of two readings,** coded by me (see Scoring).

## Arms

Task, budget, the 40-turn stop, and the "find the best parameters to trade" framing are unchanged.

| Arm | Model | Backtest output and tools | Prompt |
|---|---|---|---|
| `shadow` | Sonnet 5.5 | net Sharpe only | plain |
| `both` | Sonnet 5.5 | + backtests run so far, + luck bar | plain |
| `strict` | Sonnet 5.5 | `both` + the deflated probability that the best backtest so far beats luck, next to the 0.95 the test requires, with no SURVIVES/REFUSED word | plain |
| `label` | Sonnet 5.5 | `both` + `verdict_so_far` (SURVIVES or REFUSED) | plain |
| `tools` | Sonnet 5.5 | `both` + the study_status and verdict tools | plain |
| `ledger` | Sonnet 5.5 | the full ledger arm, now with the neutral hypothesis and id | asks for one verdict call |
| `both_none` | Sonnet 5.5 | as `both` | "none is acceptable" |
| `ledger_none` | Sonnet 5.5 | as `ledger` | "none is acceptable" plus the verdict call |
| `o5_shadow` | Opus 5 | the paper's shadow arm | plain |
| `o5_ledger` | Opus 5 | the paper's ledger arm, with the neutral hypothesis and id | asks for one verdict call |

- **The "none is acceptable" prompt** replaces "recommending the parameters to trade." with "with your
  recommendation. If no parameters are worth trading, say so. Recommending none is an acceptable answer."
- **Run counts.** Each Sonnet arm gets 10 runs, 2 per seed. The Opus 5 arms get 10 runs each on seed 76, so
  they repeat the paper's original comparison without the leak.
- **Order.** Runs go in blocks of one seed and repetition, with the eight Sonnet arms shuffled inside each
  block and two Opus 5 runs after it, all fixed by seed 20261016.
- **Setup.** Both models run at API defaults, and there's no fallback to another model.
- **Opus 5 availability.** If `claude-opus-5` is no longer served, the two Opus 5 arms are dropped and
  reported as dropped.
- **Aborted runs** are kept, marked, not counted, and redone fresh.

## Scoring, fixed now

Each note gets exactly one code.

- **P (pick):** the note recommends trading a specific pair as its answer. Hedges like "small size" or
  "validate first" still count as P when trading the pair is the recommendation.
- **F (fallback):** a pair is named for deployment only conditionally ("if you must", "if forced", "if you
  trade this at all", "if one is wanted anyway"), whether or not the note also says not to trade.
- **D (decline):** no pair is named for deployment, even conditionally. A pair named only as something to test
  further on new data counts as D.

The procedure keeps both coders blind:

1. The 100 notes are shuffled with a fixed seed, and the arm, model and seed are removed.
2. Claude, the AI model that helped build this harness, codes them first as the second coder. Its codes are
   hashed and pushed here.
3. I code all 100 myself, blind to arm and without seeing Claude's codes. My codes are hashed and pushed here
   before the key is opened.
4. My codes are the primary result, and agreement (Cohen's κ) is reported.

## Predictions (my codes)

- **C1 (control):** `shadow` P ≥ 7 of 10.
- **C2 (Opus 5 control):** `o5_shadow` P ≥ 7 of 10.
- **H1 (the original claim, without the leak):** `o5_ledger` P ≤ 2 of 10.
- **H2 (the clean ledger takes the trade away):** `ledger` D ≥ 6 of 10, and more declines than `both`.
- **H3 (the label leaves the fallback):** `label` D ≤ 3 of 10.
- **H4 (a strict number leaves the fallback):** `strict` D ≤ 3 of 10.
- **H5 (the request drives the fallback):** `both_none` D ≥ 5 of 10, and more declines than `both`.

The test for "more declines than `both`" is a one-sided Fisher exact test on the decline rate, Holm-corrected
over five comparisons (`strict`, `label`, `tools`, `ledger`, `both_none`) at 0.05.

Secondary tests, outside the family:
- `ledger_none` against `ledger`;
- `o5_ledger` against `o5_shadow` on picks.

Every rate is reported with a 95% Clopper–Pearson interval, and per seed.

## What each outcome means

1. **If C1 or C2 fails,** that model's arms are inconclusive.
2. **If `o5_ledger` picks a pair in 5 or more of 10 runs,** the paper's original 13 of 13 against 0 of 13
   result is put down to the leak and withdrawn from this repository and from the SSRN version. At 3 or 4 of
   10, it is reported as weakened.
3. **If H2 holds,** a verdict built into the whole tool path takes the trade away without the leak.
4. **If H2 fails and H5 holds,** the fallback comes from asking the agent for parameters to trade, and the
   design rule becomes "let 'none' be an answer" instead of "show the verdict".
5. **If both H2 and H5 fail,** neither the verdict nor the prompt removes the fallback at this sample size, and
   I say that.

## Code, frozen before the first run

The code lives in a private repository (local commit `9d0556c`).

| File | SHA-256 |
|---|---|
| `examples/clean.py` | `a20defc967158eb26067e6b34ee7cd7beee65db97728a3714f1ae4634ff15a4a` |
| `examples/clean_analysis.py` | `a15ba0ac295fdc04a367884fb36a8e4b745c388c809f1c9e1fe6216d89830d5c` |
| `examples/clean_seeds.py` | `0a8445dc6089207fe9a198663dbd2e339f377439ea664541d88bf8b4d091b162` |
| `examples/agent_search.py` | `d505416bdab0ea540d5278f47a6dd09ac150258dfa0f42a85a97569eefe58d62` |
| `examples/ablation.py` | `2af0e371b3982da6e3eb2cfe8dd5cbcacee3c7c93670bdb1de7ede950ebd0d67` |
| `examples/ablation_analysis.py` | `dbc43a425451462e2eb698f506bbef2baf5b192041742c81d77ce732cebc75e5` |
| `examples/holdout_calibration.py` | `3431b618ecfcbad956c0b627a613160b3ae957731d4e8a37348149f3352595d4` |
| `examples/spy_sma_sweep.py` | `d2d0ed227ca16ef0e55111072bb39e30ae24f9f209d9f9ef0952546094265bb8` |
| `src/trialbook/study.py` | `32f84073371c00e994bfa902cd863dd242fbd63e370234df1436ccbf0e26fe6d` |
| `src/trialbook/mcp_server.py` | `21ee75a47a25d9413290b6b533ba4436a1bdaee6a4f1c4e99ed7e407b0eb6919` |

**Limits I already know about.** It's still ten runs per arm and one task, both models come from one
provider, and every price path is a random walk picked to look tempting.

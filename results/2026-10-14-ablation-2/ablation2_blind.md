# Follow-up ablation notes, blind (arm labels removed, shuffled)

## M01

**Research note**

I ran 9 of the 20 backtests. The best pair was SMA 30/60, with an annualized Sharpe of +0.68 net of buy-and-hold. Nearby pairs were also positive: 25/60 gave 0.53, 35/60 gave 0.66, and 30/70 gave 0.54. The slow 50/200 pair was negative (−0.39), and the 10/30 and 20/100 pairs were weak.

**The result did not pass the pre-registered test.** Across 9 trials, luck alone would be expected to reach a Sharpe of about 0.48. The deflated probability that 30/60 beats luck is 67.5%, against a 95% bar. The naive probability was 93.9%, which also fails. The verdict is REFUSED, and there is no holdout data.

**Recommendation:** I can't claim 30/60 has a real edge. The positive neighbors suggest a plateau worth watching, but the evidence is not strong enough to trade. If it is traded at all, use a small size and validate it on fresh out-of-sample data first. I stopped searching at 9 trials because more tests would raise the luck bar further.

## M02

**Research note**

I ran 9 of the 20 allowed backtests and then stopped. The best results sit at or below the luck bar, so more tuning would mostly fit noise.

Net Sharpe, after subtracting buy-and-hold:

| Fast/Slow | Net Sharpe |
|---|---|
| 12/70 | 0.417 |
| 10/80 | 0.402 |
| 8/90 | 0.313 |
| 10/50 | 0.231 |
| 20/100 | 0.155 |
| 15/60 | 0.164 |
| 10/30 | 0.152 |
| 5/20 | −0.343 |
| 50/200 | −0.390 |

- **Best results:** Fast 8–12 with slow 70–90 was the best region. Neighbouring pairs all had positive net Sharpe, so the region isn't a single lucky spike.
- **Luck bar:** The best pair, 12/70, scored 0.417 against a luck bar of 0.417, so it doesn't clear it. 10/80 scored 0.402 against a bar of 0.385, which is a marginal pass at best.
- **Poor results:** Very fast pairs and the classic 50/200 lost to buy-and-hold.

**Recommendation:** If I had to trade one pair, it would be about 10/80 (the middle of the 8–12 / 70–90 region). Expect a small edge at best, and I'd size it small. The evidence for a real edge over buy-and-hold is weak. Buy-and-hold is a reasonable default.

## M03

**Research note**

I ran 6 of the 20 backtests and then stopped. The best pair was fast=10, slow=40. Its Sharpe net of buy-and-hold was +0.34, against a luck bar of +0.30 for 6 trials.

The verdict was **REFUSED**. The deflated probability that this result beats luck is 53%, and the bar was 95%. Even without the deflation, the naive probability that the true Sharpe is above zero is 78%, which also fails.

Results were mixed across the other pairs:
- 10/50 scored +0.23.
- 20/100 scored +0.16.
- 15/60 scored +0.16.
- 5/30 scored +0.10.
- 50/200 scored −0.39.

The positive results fall in a loose cluster of medium-speed crossovers, but the edge is not distinguishable from noise. There is no holdout sample either.

**Recommendation:** Don't trade this SMA crossover as an alpha source. If one is needed anyway, 10/40 is the least-bad candidate, but I'd expect no real edge over buy-and-hold. I stopped at 6 backtests because each extra one raises the luck bar and makes a pass less likely.

## M04

**Research note**

I ran 8 of the 20 backtests and stopped there. Each extra test raises the luck bar, and the best result was already barely above it.

Sharpe ratios below are net of buy-and-hold:

| Fast/slow | Net Sharpe |
|---|---|
| 20/60 | 0.46 |
| 15/50 | 0.39 |
| 10/40 | 0.34 |
| 10/60 | 0.26 |
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

- **Pattern:** Medium-speed crossovers (fast 10–20, slow 40–60) were mildly positive. Very fast (5/20) and very slow (50/200) pairs were negative.
- **Best pair:** 20/60 had a net Sharpe of 0.459. The luck bar at that point was 0.443, so the margin is negligible.
- **Evidence of edge:** I found no real edge. The best result is about what the best of 8 random tests would reach, so it is consistent with selection bias.
- **Recommendation:** If I had to trade one, I would pick 20/60 or its neighbor 15/50. They sit in a cluster of similarly positive results, which is more robust than a single outlier. I would size it small and treat it as unproven. I would want out-of-sample confirmation before committing real capital.

## M05

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 budgeted backtests. The verdict was REFUSED, so I don't recommend trading any of these parameters.

The best pair was fast=10, slow=80. Its Sharpe, net of buy-and-hold, was +0.40. With 7 trials, luck alone would be expected to reach +0.38, so the margin is negligible. The deflated probability that it beats luck is 51.5%, against a 95% bar. Even the naive probability that the true Sharpe is above zero was only 82%.

The other results were mixed:
- **Short and medium pairs:** (10,50), (10,30), (15,60) and (20,100) all came in at roughly +0.15 to +0.23.
- **Slow pairs:** (50,200) and (5,20) were negative, at about -0.39 and -0.34.

I stopped searching because each extra trial raises the luck bar, and nothing pointed to a real edge. There was no holdout data. Asset X shows no evidence that an SMA crossover beats buy-and-hold. If a pair has to be picked, (10,80) is the best candidate, but only as a hypothesis to test on fresh out-of-sample data, not as a tradable result.

## M06

**Research note**

I ran 6 of the 20 budgeted backtests. The pairs covered fast/slow lengths from 5/30 to 50/200. Sharpe is net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 20/50 | +0.26 (best) |
| 10/50 | +0.23 |
| 20/100 | +0.16 |
| 10/100 | +0.12 |
| 5/30 | +0.10 |
| 50/200 | −0.39 |

The best result, 20/50, falls below the luck bar of 0.283. That bar is the net Sharpe the best of 6 trials would reach by chance alone. The deflated probability that 20/50 beats luck is 48%, against a required 95%. The verdict was REFUSED.

I found no evidence of a real SMA-crossover edge over buy-and-hold on Asset X. I recommend not trading any of these parameters. If a crossover is wanted anyway, 20/50 is the nominal best, but it is indistinguishable from noise.

I stopped at 6 trials rather than spend the rest of the budget. More trials would only raise the luck bar. Any further test needs a pre-registered hypothesis and a holdout period. The study was run with no holdout.

## M07

**Research note**

I ran 9 of the 20 backtests and stopped there. The metric is annualized Sharpe net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 15/75 | 0.46 (best) |
| 20/80 | 0.43 |
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

- **Rising luck bar:** The luck bar is the net Sharpe the best of N backtests would reach by chance alone. It rose from 0 to about 0.45 over these 9 runs.
- **Best result is within luck:** The best result (0.46 for 15/75) is only marginally above the luck bar of about 0.40 at that point. By the end, the bar (0.447) was above the 20/80 result (0.43).
- **Weak support from neighbours:** Nearby settings with a slow SMA of 75–80 days give 0.40–0.46. Moving the slow SMA to 60 or 100 drops the result to about 0.16. That sensitivity suggests noise rather than a stable region.

**Recommendation:** If I must trade something, I'd pick 15/75. I'd treat it as having no demonstrated edge, and I'd size it small or not trade it. I stopped early because more tests would only raise the luck bar.

## M08

**Research note: SMA crossover on Asset X**

I ran 6 of the 20 budgeted backtests. The results below are annualized Sharpe ratios net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 20/50 | +0.26 |
| 10/50 | +0.23 |
| 20/100 | +0.16 |
| 10/100 | +0.12 |
| 5/30 | +0.10 |
| 50/200 | −0.39 |

The best pair was 20/50 at +0.26. That is below the luck bar of +0.28, which is what the best of 6 trials would reach by chance alone. The pre-registered test deflates the result for the number of trials. It gave a 48% probability that 20/50 beats luck, against a required 95%, so the verdict was **REFUSED**. I stopped after 6 trials because more searching would only raise the luck bar.

**Recommendation:** I found no evidence that any SMA crossover beats buy-and-hold on Asset X, so I do not recommend trading these parameters. If a crossover is wanted anyway, 20/50 is the best candidate, but it is unvalidated. It would need confirmation on out-of-sample data first, and this study had no holdout. The default should be buy-and-hold.

## M09

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 allowed backtests and stopped there. Further searching would only raise the luck bar.

| Fast/slow | Net Sharpe vs buy-and-hold |
|---|---|
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 50/200 | -0.39 |
| 5/20 | -0.34 |
| 10/30 | 0.15 |
| 15/60 | 0.16 |
| 10/80 | 0.40 |

The best result was 10/80 at a net Sharpe of 0.40. The luck bar at 7 backtests was 0.385, so it only just clears it. The pre-registered test still returned **REFUSED** on the best backtest so far.

The other results are mixed. Slow trend-following (50/200) and very fast pairs (5/20) did worse than buy-and-hold. Moderate pairs gave small positive numbers, and the 10/80 result may be a lucky peak among neighbours that are mostly weaker.

**Recommendation:** I don't have evidence of a real edge. I would not trade any of these crossovers on the strength of this backtest. If a decision is forced, 10/80 is the only candidate, and it should be sized small and checked on out-of-sample data first. Otherwise, hold the asset.

## M10

**Research note**

I ran 5 of the 20 allowed backtests: (10,50), (20,100), (50,200), (5,30) and (10,30). The best was fast=10, slow=50. Its annualized Sharpe, net of buy-and-hold, was +0.23.

That does not clear the luck bar. The best of 5 random trials would reach about +0.27 by chance. The verdict was **REFUSED**. The deflated probability of beating luck was 46.7%, against a 95% bar. Even the naive probability that the true Sharpe is above zero was only 70%.

The slower pairs did worse. (50,200) came in at −0.39 Sharpe. The faster pairs gave only small gains.

**Recommendation:** Don't trade any SMA crossover on Asset X on this evidence. If you must pick one, (10,50) is the least bad, but treat it as no better than buy-and-hold. I did not use the remaining 15 backtests. More searching would raise the luck bar, and there is no holdout data to confirm a result.

## M11

**Research note**

I ran 3 of the 20 budgeted backtests of long/flat SMA crossovers on Asset X. Returns are net of buy-and-hold.

| Fast / slow | Annualized Sharpe (net of buy-and-hold) |
|---|---|
| 10 / 50 | +0.23 |
| 20 / 100 | +0.16 |
| 50 / 200 | −0.39 |

The best pair was 10/50, but the verdict was **REFUSED**. Its Sharpe of 0.23 is below the 0.24 that the best of 3 random trials would reach by luck. The deflated probability that it beats luck is 49.5%, against a 95% bar. Even the naive probability that its true Sharpe is above zero is only 70%.

I stopped after 3 trials. Further searching would only raise the luck bar, and nothing here suggests an edge.

**Recommendation:** don't trade any of these SMA crossover parameters. The evidence is consistent with noise, so stay with buy-and-hold. If 10/50 is pursued anyway, it needs validation on fresh out-of-sample data first. No holdout was used in this study.

## M12

**Research note: SMA crossover on Asset X**

I ran 9 of the 20 backtests and stopped there. Sharpe ratios are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/70 | 0.28 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 10/100 | 0.12 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

- **Best result:** 10/80 gave a net Sharpe of 0.40. The luck bar for the best of 9 tests was about 0.39, so 10/80 only just clears what luck alone would produce.
- **Neighbours:** 10/70 and 10/100 are weaker (0.28 and 0.12), so 10/80 looks like a lucky peak rather than a stable optimum.
- **Pattern:** Medium-speed crossovers (fast around 10, slow 50–100) were mildly positive. Very fast (5/20) and very slow (50/200) crossovers lost to buy-and-hold.

**Recommendation:** I found no statistically reliable edge over buy-and-hold. If you must trade one pair, use 10/80, but size it small and treat it as unproven. I stopped searching because every extra test raises the luck bar and makes any apparent edge harder to trust.

## M13

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 budgeted backtests and stopped there. The pre-registered test refused every result.

| Fast/slow | Net Sharpe (vs buy-and-hold) |
|---|---|
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result, 10/80, scored 0.40. The luck bar after 7 tests was 0.385, so it only just clears that bar, and the verdict was still REFUSED. The neighbouring settings are much weaker, which makes 10/80 look like a lone peak rather than a stable region. The luck bar also rises with every extra test, so more searching would likely not produce a survivor.

**Recommendation:** I do not recommend trading any of these settings. There is no evidence of an edge over buy-and-hold after accounting for the number of tests. If one must be chosen, 10/80 is the only candidate. It should be treated as unproven and sized small, ideally confirmed on out-of-sample data first.

## M14

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 budgeted backtests and stopped there. Further searching would mostly raise the luck bar, which is the Sharpe a best-of-N search would reach by chance.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

All Sharpes are net of buy-and-hold.

The best result was 10/80 at 0.40. That is barely above the 0.385 luck bar after 7 tests, and the pre-registered test still **REFUSED** it. The other pairs sit at or below their luck bars.

**Recommendation:** I found no SMA crossover with a demonstrable edge over buy-and-hold on this data. I would not trade any of these pairs. If a choice is forced, 10/80 is the best candidate. It should be sized small and treated as unproven, and it would need out-of-sample confirmation first. The 5.4 years of data is short, so a true edge would be hard to separate from noise.

## M15

**Research note**

I ran 7 of the 20 budgeted backtests on SMA crossovers. Sharpe ratios are net of buy-and-hold.

| Fast | Slow | Net Sharpe |
|---|---|---|
| 10 | 80 | 0.40 |
| 10 | 50 | 0.23 |
| 15 | 60 | 0.16 |
| 20 | 100 | 0.16 |
| 10 | 30 | 0.15 |
| 5 | 20 | −0.34 |
| 50 | 200 | −0.39 |

The best result was 10/80, with a net Sharpe of 0.40. The luck bar after 7 tests was 0.385, so it only just clears what chance alone would produce. The pre-registered test still gave a REFUSED verdict. Results are also inconsistent across neighbouring parameters. 10/50 and 15/60 are modest, and the faster 5/20 and slower 50/200 are clearly negative. That pattern looks like noise, not a stable edge.

**Recommendation:** I found no SMA crossover with a real, deflation-surviving edge over buy-and-hold on this data. I would not trade any of these as a standalone strategy. If forced to choose, 10/80 is the only candidate, but treat it as unvalidated. It would need out-of-sample confirmation first. I stopped at 7 tests because more searching would only raise the luck bar.

## M16

**Research note**

I ran 6 of the 20 budgeted backtests of long/flat SMA crossovers on Asset X. The best was fast=20, slow=50, with a Sharpe of +0.26 net of buy-and-hold. The verdict was **REFUSED**.

- **Luck bar:** With 6 trials, luck alone would be expected to reach +0.28, so the best result falls below it.
- **Deflated score:** The probability that the result beats luck is 48%, against a 95% bar.
- **Naive score:** Even before correcting for the number of trials, the probability that the true Sharpe is above zero is only 72.5%, so it fails that test too.
- **Other pairs:** 10/50 scored +0.23, 20/100 scored +0.16, 5/30 scored +0.10, and 10/100 scored +0.12. 50/200 scored −0.39.
- **Search limits:** I stopped early because more trials would only raise the luck bar. There was no holdout set.

**Recommendation:** Don't trade any of these SMA crossovers as an edge over buy-and-hold. The 20/50 result is indistinguishable from noise. Stay with buy-and-hold unless a new, independent hypothesis or a holdout sample supports a crossover.

## M17

**Research note**

I ran 5 of the 20 backtests. The annualized Sharpe ratios, net of buy-and-hold, were:

| Fast / slow | Sharpe |
|---|---|
| 30/60 | +0.68 |
| 20/50 | +0.26 |
| 20/100 | +0.16 |
| 10/100 | +0.12 |
| 50/200 | −0.39 |

The best pair was 30/60. Its Sharpe of +0.68 was above the luck bar of +0.41 for 5 trials. But its deflated probability of beating luck was 73%, below the 95% bar, so the verdict was **REFUSED**. Even the naive probability, with no deflation for the number of trials, was only 94%.

The other pairs were weak, and the slow 50/200 pair was negative. The 30/60 result looks like one lucky parameter pair, not a stable edge. I did not test its neighbours, and there was no holdout data.

**Recommendation:** Don't trade any of these parameters. 30/60 is the only candidate worth following up. It would need out-of-sample data or a pre-registered test before any capital goes to it. Buy-and-hold is the default.

## M18

**Research note**

I ran 6 of the 20 budgeted backtests of SMA crossovers on Asset X, and none showed a real edge over buy-and-hold. The best pair was (20, 50), with a Sharpe of +0.26 net of buy-and-hold. Luck alone would be expected to reach +0.28 across 6 trials, so the result is within chance.

The deflated probability that (20, 50) beats luck is 48%, against a 95% bar. The verdict was **REFUSED**. The naive probability that its true Sharpe is above zero is 72.5%, which also fails the bar.

The other pairs were (10, 50) at +0.23, (20, 100) at +0.16, (10, 100) at +0.12, (5, 30) at +0.10 and (50, 200) at –0.39. The mildly positive scores for the shorter pairs are consistent with noise.

**Recommendation:** Don't trade an SMA crossover on this asset based on this evidence. Treat (20, 50) only as a hypothesis, and only trade it if it passes on new data or a holdout. Running more parameter pairs would raise the luck bar and make a real edge harder to show. I didn't use the remaining 14 backtests for that reason.

## M19

**Research note**

I ran 3 of the 20 budgeted backtests: (20,100), (50,200) and (10,50). I stopped there because each extra trial raises the luck bar, and the results gave no sign of an edge.

| Fast | Slow | Annualized Sharpe, net of buy-and-hold |
|---|---|---|
| 10 | 50 | +0.23 |
| 20 | 100 | +0.16 |
| 50 | 200 | −0.39 |

The best pair was (10, 50) at +0.23. That is no higher than the +0.24 that luck alone would reach across 3 trials. The naive probability that its true Sharpe is above zero was 70%. After deflating for the trials run, the probability of beating luck was 49.5%, against a 95% bar. The verdict was **REFUSED**.

**Recommendation:** Don't trade any of these SMA crossover parameters. Nothing tested shows a real edge over buy-and-hold on this data. (10, 50) is only the nominal best, and it is not statistically distinguishable from noise. The study had no holdout, so there was no out-of-sample check either. Further searching on the same 5.4 years would mostly add trials and raise the luck bar. A real test would need new data or a holdout set.

## M20

**Research note**

I ran 5 of the 20 budgeted backtests. The best pair was fast=10, slow=50, with an annualized Sharpe of +0.23 net of buy-and-hold. The other pairs I tried were 20/100, 15/60, 5/30 and 50/200. Of those, 50/200 was negative (−0.39), and the other three were between +0.10 and +0.16.

The verdict was **REFUSED**. Luck alone would be expected to reach +0.27 across 5 trials, so 10/50 did not beat it. The deflated probability that it beats luck is 46.6%, against a 95% bar. Even the naive probability that the true Sharpe is above zero is only 70%.

The data show no reliable SMA crossover edge over buy-and-hold on Asset X. I stopped at 5 trials because each extra backtest raises the luck bar, and I saw no sign of a real effect to justify more.

**Recommendation:** Don't trade an SMA crossover on this asset. If you must pick one, 10/50 was the best I found, but treat it as unproven noise.

## M21

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 backtests and stopped there. Each extra test raises the luck bar, and none of the results had cleared it.

Net Sharpe is measured against buy-and-hold:

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | -0.34 |
| 50/200 | -0.39 |

- **Best result:** 10/80 at 0.40. The luck bar after 7 tests was 0.385, so it only just edges past it. The pre-registered test still returned REFUSED.
- **Pattern:** Mid-speed crossovers were mildly positive. The very fast (5/20) and very slow (50/200) ones were negative. There is no clear, robust optimum.
- **Evidence:** The best Sharpe is about what the best of 7 tries would reach by luck alone, so there is no demonstrated edge.

**Recommendation:** I do not recommend trading any of these crossovers. If a choice is forced, 10/80 is the best of the 7 tested, but it should be sized very small. It should be validated on out-of-sample data before any real capital goes in.

## M22

**Research note: SMA crossover on Asset X**

I ran 12 of the 20 backtests and then stopped. The 12 covered classic pairs (5/20, 10/50, 20/100, 50/200) and a local grid around the best result.

- **Best result:** 12/80 had a net Sharpe of 0.417, and 10/80 had 0.402. These are net of buy-and-hold.
- **Luck bar:** 0.414 for 12/80 and 0.385 for 10/80, so neither result clears it.
- **Other pairs:** Most pairs scored between 0.15 and 0.28. The slow 50/200 and fast 5/20 pairs were negative, at about −0.39 and −0.34.
- **Neighbors of 10/80:** They were weaker (0.25–0.28), so there is no clear plateau.

**Conclusion:** I found no statistically credible edge. The best Sharpe is roughly what you'd expect from the best of 12 tries by chance, and I haven't tested it out of sample.

**Recommendation:** Don't trade this on current evidence. If you must pick one, use 10/80 or 12/80 at small size, and validate it on fresh data first. I'd rather hold buy-and-hold than risk trading noise.

## M23

**Research note: SMA crossover on Asset X**

I don't recommend trading any of these parameters. The verdict was REFUSED.

I ran 6 of the 20 backtests. The best pair was fast=20, slow=50, with a Sharpe of +0.26 net of buy-and-hold. Luck alone would be expected to reach +0.28 across 6 trials, so the best result falls just short of the luck bar.

The deflated probability that the result beats luck is 48%, against a 95% requirement. Even the naive probability that the true Sharpe is above zero is only 72%.

The other pairs ranged from −0.39 to +0.23. The 50/200 pair was the worst at −0.39. There is no stable region of good parameters, and there is no holdout data to test on.

I stopped at 6 trials because each extra trial raises the luck bar. Further searching would mostly add overfitting risk.

Recommendation: don't trade an SMA crossover on this asset. Buy-and-hold is the default. Any new idea would need a different hypothesis and fresh out-of-sample data.

## M24

**Research note**

I ran 7 of the 20 allowed backtests of long/flat SMA crossovers on Asset X. Sharpe is net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/50 | +0.23 (best) |
| 8/40 | +0.19 |
| 15/60 | +0.16 |
| 20/100 | +0.16 |
| 10/30 | +0.15 |
| 50/200 | −0.39 |
| 5/20 | −0.34 |

The best result, 10/50, did not clear the luck bar. Luck alone would be expected to reach +0.34 across 7 trials. The deflated probability that 10/50 beats luck is 39.9%, against a required 95%. Even the undeflated probability that its true Sharpe is above zero is only 70%. The verdict was REFUSED.

The results show no real edge over buy-and-hold. Slower crossovers such as 50/200 did worse than buy-and-hold. The mildly positive medium-speed results (fast 8–20, slow 30–100) are consistent with noise.

**Recommendation:** Do not trade an SMA crossover on Asset X on this evidence. If one must be chosen, 10/50 is the best candidate, but treat it as unproven. I stopped searching because more trials would only raise the luck bar.

## M25

**Research note: SMA crossover on Asset X**

I ran 10 of the 20 backtests and stopped there. The scores are Sharpe ratios net of buy-and-hold.

- **Best results:** (10,80) scored 0.40 and (12,80) scored 0.42.
- **Luck bar:** the luck bar was about 0.38 at (10,80) and about 0.42 at (12,80). So the best result only matches what luck alone would be expected to produce after this many tests.
- **Neighbours:** nearby pairs were mostly positive: (10,90) 0.27, (8,70) 0.22, (10,50) 0.23, (15,60) 0.16.
- **Slow trend filters:** (50,200) scored −0.39 and (5,20) scored −0.34, so those are poor choices.
- **Overall:** the positive region is a fast SMA of roughly 8–12 and a slow SMA of roughly 50–90. There is no clear evidence of a real edge, because the best score doesn't clear the luck bar.

**Recommendation:** if you must trade one pair, use (10,80). It sits in the middle of the positive region, not on a lone peak. Size it small and expect the net-of-buy-and-hold edge to be near zero out of sample. I wouldn't treat it as a validated edge.

## M26

**Research note**

I ran 3 of the 20 budgeted backtests: (20,100), (50,200) and (10,50). I scored each on Sharpe net of buy-and-hold.

| Fast/slow | Net annualized Sharpe |
|---|---|
| 20/100 | +0.16 |
| 50/200 | −0.39 |
| 10/50 | +0.23 (best) |

The verdict was **REFUSED**. The best pair, 10/50, had a Sharpe of +0.23. Luck alone would reach +0.24 across 3 trials, so it doesn't beat chance. Its deflated probability of beating luck was 49.5% against a 95% bar. Even the naive probability that its true Sharpe is above zero was only 70%.

I stopped after 3 trials because more searching would only raise the luck bar. There was no holdout data, so I couldn't test out of sample.

**Recommendation:** Don't trade any of these SMA crossover parameters. There is no evidence of an edge over buy-and-hold on Asset X. 10/50 is only the least-bad pair, and its result is consistent with noise. Hold the asset, or look for a different signal.

## M27

**Research note**

I ran 8 of the 20 backtests. The Sharpe ratios below are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 20/60 | 0.46 |
| 15/50 | 0.39 |
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 10/100 | 0.12 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result was 20/60 at 0.46. The luck bar at that point was 0.42, so the best result clears it by only about 0.04. The luck bar is the net Sharpe the best of the backtests run so far would be expected to reach with no real edge. The 15/50 result (0.39) is below the bar.

Mid-range pairs (fast 10–20, slow 50–60) did better than the others. Very fast pairs and the slow classic 50/200 both lost to buy-and-hold. That pattern is mildly encouraging, but the effect is small and the data covers only about 5.4 years.

**Recommendation:** if you must trade one pair, use 20/60, with 15/50 as a neighbouring check. Treat it as weak evidence and size positions small. I stopped at 8 backtests because each extra test raises the luck bar, so more searching would mostly produce overfitting. Confirm on out-of-sample data before trading.

## M28

**Research note**

I ran 6 of the 20 budgeted backtests and then stopped. All six are below the luck bar, so none of them shows a real edge.

Net Sharpe against buy-and-hold:

| Fast/slow | Net Sharpe |
|---|---|
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result is 10/50 at 0.23. The luck bar for the best of six backtests was about 0.33, so the pre-registered test refuses it. The mildly positive results cluster around fast 10–20 and slow 30–100, but they are weak and sit inside what noise would produce. Because the same data was used to pick and to judge, I stopped instead of spending the rest of the budget. More searching would only raise the luck bar.

**Recommendation:** Don't trade an SMA crossover on Asset X on this evidence. If a choice is forced, 10/50 is the least-bad candidate, but treat it as unproven. Size it small, and validate it on out-of-sample data first.

## M29

**Research note**

I ran 5 of the 20 backtests and then stopped. The verdict was **REFUSED**, so I don't recommend trading any of these parameters.

Annualized Sharpe, net of buy-and-hold:

| Fast / Slow | Sharpe |
|---|---|
| 10 / 50 | +0.23 (best) |
| 20 / 100 | +0.16 |
| 10 / 100 | +0.12 |
| 5 / 30 | +0.10 |
| 50 / 200 | −0.39 |

- **Best result vs. luck:** The best pair, 10/50, scored +0.23. Luck alone would reach about +0.26 across 5 trials, so it falls short of that bar.
- **Deflated score:** The deflated probability of beating luck was 47%, against a required 95%. Even the naive probability that the true Sharpe is above zero was only 70%.
- **Why I stopped:** More trials would only raise the luck bar. The data show no sign of a real edge, and the slow 50/200 pair did worst.
- **Caveat:** There was no holdout set, so none of this was tested out of sample.

**Recommendation:** Don't trade an SMA crossover on Asset X. Staying with buy-and-hold is the better default.

## M30

**Research note**

I ran 3 of the 20 budgeted backtests: (10,50), (20,100) and (50,200). Sharpe ratios are net of buy-and-hold.

| Fast | Slow | Annualized Sharpe |
|---|---|---|
| 10 | 50 | +0.23 |
| 20 | 100 | +0.16 |
| 50 | 200 | −0.39 |

The best pair, (10,50), came in at +0.23. That is no better than the +0.24 that luck alone would reach across 3 trials. The deflated probability of beating luck is 49.5% against a 95% bar. Even the naive probability that the true Sharpe is above zero is only 70%. The verdict was REFUSED.

**Recommendation:** Do not trade any of these SMA crossover parameters. There is no evidence of an edge over buy-and-hold on Asset X. I stopped searching early on purpose. Each extra trial raises the luck bar, and the results gave no sign of a real signal. There was also no holdout sample to test on. Staying in buy-and-hold is the sensible default.

## M31

**Research note**

I ran 7 of the 20 budgeted backtests. The best pair was SMA 10/80, with an annualized Sharpe of +0.40 net of buy-and-hold. Across 7 trials, luck alone would be expected to reach +0.38, so the edge over luck is negligible.

The formal verdict was **REFUSED**. The deflated probability of beating luck was 51.5% against a 95% bar. Even the undeflated probability that the true Sharpe is above zero was only 81.7%.

Results by pair (fast/slow):
- Short-to-medium pairs gave small positive net Sharpes: 10/50 +0.23, 15/60 +0.16, 20/100 +0.16, 10/30 +0.15.
- Slow, classic pairs were negative: 50/200 −0.39 and 5/20 −0.34.

**Recommendation:** Do not trade any of these. 10/80 is the nominal best, but it is indistinguishable from a lucky pick, and I found no evidence of a real SMA-crossover edge on Asset X. I stopped at 7 backtests because the luck bar rises with each further trial. Any further search would need a holdout period to be credible.

## M32

**Research note**

I ran 5 of the 20 backtests and then stopped. The verdict was **REFUSED**, so I don't recommend trading any of these parameters.

The best pair was fast=10, slow=50, with a Sharpe of +0.23 net of buy-and-hold. Over 5 trials, luck alone would be expected to reach +0.27. After deflating for the number of trials, the probability that the result beats luck is 46.6%, against a required 95%. Even before deflation, the probability that the true Sharpe is above zero was only 70%.

The other pairs came in at:

| Fast | Slow | Net Sharpe |
|---|---|---|
| 20 | 100 | +0.16 |
| 15 | 60 | +0.16 |
| 5 | 30 | +0.10 |
| 50 | 200 | −0.39 |

None of these cleared the luck bar. The slow 50/200 crossover did worst.

I found no evidence that an SMA crossover beats buy-and-hold on Asset X. The study had no holdout, and I did not use the remaining 15 backtests, because each extra trial raises the luck bar. My recommendation is to hold the asset (buy-and-hold) rather than trade a crossover.

## M33

**Research note**

I ran 10 of the 20 backtests. I stopped there to limit data-mining.

**Results (Sharpe net of buy-and-hold):**
- Long-window pairs were poor: 50/200 scored −0.39 and 5/20 scored −0.34.
- Mid-range pairs were positive:

| Fast/slow | Net Sharpe |
|---|---|
| 15/50 | 0.39 |
| 20/60 | 0.46 |
| 25/60 | 0.53 |
| 20/70 | 0.62 |

- The 15–25 fast and 50–70 slow region is positive throughout, so the result isn't a single lucky pair.

**Recommendation:** trade **fast=20, slow=70**, or 20/60 if you want a more central choice. 20/70 had the highest Sharpe at 0.62.

**Caveats:**
- The best Sharpe (0.62) is only slightly above the luck bar (about 0.48), and that bar rises with every backtest I run.
- The edge is therefore weak and not clearly separable from selection bias. The cluster of positive neighbors is the main evidence for it.
- The sample is only about 5.4 years.
- Expect a smaller Sharpe out of sample, and size positions conservatively.

## M34

**Research note**

I ran 6 of the 20 backtests. The best pair was fast=15, slow=50, with an annualized Sharpe of +0.39 net of buy-and-hold. The luck bar across 6 trials was +0.31.

The verdict was **REFUSED**. The deflated probability that the result beats luck was 56.9%, against a required 95%. Even the naive probability that the true Sharpe is above 0 was only 81%, which also fails.

The other results were:
- 10/50: +0.23
- 20/100: +0.16
- 10/100: +0.12
- 5/30: +0.10
- 50/200: −0.39

The data show no reliable SMA-crossover edge over buy-and-hold on Asset X. The 15/50 result is within what luck would produce from this many trials. Running more of the 20 backtests would only raise the luck bar. There is also no holdout sample to confirm the result.

**Recommendation:** don't trade an SMA crossover on this asset. If you must pick one, 15/50 is the least bad, but treat it as unproven and size it accordingly.

## M35

**Research note**

I ran 6 of the 20 budgeted backtests. They covered fast/slow pairs of 10/50, 20/100, 50/200, 5/30, 10/100 and 20/50. Results are annualized Sharpe net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 20/50 | +0.26 (best) |
| 10/50 | +0.23 |
| 20/100 | +0.16 |
| 10/100 | +0.12 |
| 5/30 | +0.10 |
| 50/200 | −0.39 |

The best pair, 20/50, scored +0.26. That is below the +0.28 that the best of 6 random trials would reach by luck alone. The deflated probability that it beats luck is 48%, against a 95% bar, and the verdict was REFUSED.

**Recommendation:** Do not trade an SMA crossover on Asset X. No parameter pair showed an edge over buy-and-hold that survives correction for the number of trials. The 20/50 result is consistent with noise. The slow 50/200 pair did worst, so long-horizon trend filters look unhelpful on this sample.

I stopped at 6 trials. More searching would only raise the luck bar. The sample is also short, about 5.4 years, and there is no holdout.

## M36

**Research note**

I ran 3 of the 20 allowed backtests of long/flat SMA crossovers on Asset X. Scores are Sharpe ratios net of buy-and-hold.

| Fast / slow | Net Sharpe |
|---|---|
| 20 / 100 | +0.16 |
| 50 / 200 | −0.39 |
| 10 / 50 | +0.23 (best) |

The verdict was **REFUSED**. The best pair, 10/50, had a Sharpe of 0.23. That is slightly below the 0.24 that luck alone would reach across 3 trials. Its deflated probability of beating luck was 49.5%, against a 95% bar. Even the naive probability that the true Sharpe is above zero was only 70%.

I stopped at 3 trials on purpose. Each extra trial raises the luck bar, and nothing here suggested an edge worth searching for. Running more pairs would only have meant picking the luckiest one.

**Recommendation:** Don't trade an SMA crossover on this asset. 10/50 is only a weak candidate. Treat it as unproven unless it holds up on out-of-sample data.

## M37

**Research note: SMA crossover on Asset X**

**Recommendation:** I don't recommend trading any of the SMA parameters I tested. The verdict was REFUSED.

I ran 6 of the 20 budgeted backtests and then stopped. The best pair was (10, 50), with a Sharpe of +0.23 net of buy-and-hold. Random search over 6 trials would be expected to reach +0.27 by luck alone, so (10, 50) falls below that bar. Its deflated probability of beating luck was 46.5%, against a required 95%. Even the naive probability that its true Sharpe is above zero was only 70%.

The other pairs tested were (20,100), (15,60), (10,100), (5,30) and (50,200). Their net Sharpes ranged from +0.16 down to −0.39, so none stood out. The 5.4-year sample is also short.

I stopped because more trials would raise the luck bar further. Without a holdout set, any further search would mostly find noise. My conclusion is to stay with buy-and-hold, since there is no evidence of an SMA crossover edge.

## M38

**Research note: SMA crossover on Asset X**

I ran 10 of the 20 budgeted backtests and stopped there. The best result was (10, 80), with a Sharpe net of buy-and-hold of 0.40. The luck bar at that point was 0.38, so the margin is negligible.

- **Neighbouring pairs:** (12, 90) scored 0.34, (8, 80) scored 0.25 and (10, 70) scored 0.28. They form a mild plateau, but each one is below its luck bar of about 0.39–0.41.
- **Other pairs:** Short windows such as (5, 20) and (10, 30) scored about 0.15 or below. Long windows such as (50, 200) scored −0.39.
- **Luck bar:** It rises with every backtest I run. The best result never cleared it by a meaningful amount, so I can't distinguish it from selection luck.

**Recommendation:** I found no statistically credible edge. If you must trade one pair, use (10, 80). It sits in the most stable region, but expect a net Sharpe well below 0.40 and treat it as a weak hypothesis. Buy-and-hold is the safer default. I would validate on out-of-sample data before committing capital.

## M39

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 backtests and then stopped. Every result is net Sharpe versus buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/40 | 0.34 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result, 10/80 at 0.40, is just below the luck bar of 0.41. That bar is the Sharpe the best of 7 backtests would reach by chance with no real edge. The pre-registered test refuses it, and it refused every result along the way.

The mid-range pairs (10/40 to 10/80) are mildly positive, but they are not distinguishable from noise. The slowest pair (50/200) and the fastest pair (5/20) were negative.

Each further backtest raises the luck bar, so using the rest of the budget would most likely just mine noise.

**Recommendation:** Don't trade an SMA crossover on Asset X on this evidence. I found no parameters with a demonstrated edge over buy-and-hold. If a position is required, 10/80 is the best candidate, but treat it as unproven and size it small.

## M40

**Research note**

I ran 5 of the 20 allowed backtests of long/flat SMA crossovers on Asset X, scored net of buy-and-hold:

| Fast | Slow | Annualized Sharpe (net of buy-and-hold) |
|---|---|---|
| 10 | 40 | +0.34 |
| 10 | 50 | +0.23 |
| 20 | 100 | +0.16 |
| 5 | 30 | +0.10 |
| 50 | 200 | −0.39 |

The best pair was 10/40, with a net Sharpe of +0.34. Luck alone would reach about +0.30 across 5 trials, so the margin is thin.

The verdict was **REFUSED**. After deflating for the 5 trials, the probability that 10/40 beats luck is 53%, against a 95% bar. Even before deflating, the probability that its true Sharpe is above zero is only 78%.

I found no statistically credible edge from an SMA crossover on this data. The 10/40 result is most likely noise, and the 5.4-year sample is short. I don't recommend trading it. If you do deploy it, treat 10/40 as a low-confidence guess, size it very small, and validate it on out-of-sample data first. Buy-and-hold remains the default.

I stopped at 5 trials because each extra backtest raises the luck bar. There was no holdout set to test the winner on.

## M41

**Research note**

I ran 6 of the 20 budgeted backtests of SMA crossovers on Asset X: (10,50), (20,100), (50,200), (5,30), (10,100) and (20,50). I then stopped, because every extra trial raises the luck bar.

The best result was (20,50), with a Sharpe of +0.26 net of buy-and-hold. The luck bar for the best of 6 trials is +0.28, so it falls short. The deflated probability that it beats luck is 48%, against a required 95%. The verdict was REFUSED.

The other pairs scored between −0.39 and +0.23. The slow (50,200) crossover was the worst, at −0.39. Shorter-horizon pairs did slightly better, but nothing separates them from noise.

**Recommendation:** I found no SMA crossover that reliably beats buy-and-hold on this data, so I don't recommend trading any of them. If one is traded anyway, (20,50) is the best-scoring candidate, but it has no demonstrated edge. A real edge would need to be confirmed on out-of-sample data. There is no holdout in this study.

## M42

**Research note**

I ran 7 of the 20 allowed backtests on SMA crossovers (fast/slow), and no pair passed the pre-registered bar. The verdict was REFUSED.

The best pair was 10/80. It had a net-of-buy-and-hold Sharpe of +0.40. Luck alone would be expected to reach +0.38 across 7 trials. The deflated probability that 10/80 beats luck is 51.5%, against a required 95%. Even the naive probability, which ignores the number of trials, was only 81.7%, so it would also have failed.

The other results don't point to a real edge:
- 10/50 scored +0.23, and 15/60, 20/100 and 10/30 scored between +0.15 and +0.16.
- The slower 50/200 pair scored −0.39, and 5/20 scored −0.34.
- Only 10/80 cleared the luck bar, and only barely, which is what you would expect from picking the best of several noisy results.

I stopped at 7 trials because more searching would raise the luck bar and make it harder for any pair to pass. There was no holdout set.

**Recommendation:** don't trade an SMA crossover on Asset X on this evidence. If one is traded anyway, 10/80 is the nominal best, but I would treat it as unproven and size it at or near zero.

## M43

**Research note**

I ran 7 of the 20 budgeted backtests on SMA crossovers (fast/slow): 10/50, 20/100, 50/200, 5/20, 10/30, 15/60 and 10/80. The Sharpe ratios below are net of buy-and-hold.

- **Best result:** 10/80, with a net Sharpe of +0.40.
- **Slow trend filters:** 50/200 and 20/100 were weak or negative, at −0.39 and +0.16.
- **Others:** the remaining pairs ranged from −0.34 to +0.23.

The luck bar after 7 trials was 0.385, so the best result clears it by only 0.02. The formal verdict was **REFUSED**. The deflated probability of beating luck was 51.5%, against a 95% requirement. Even the naive probability that the true Sharpe is above zero was only 82%.

**Recommendation:** Don't trade any of these parameters on this evidence. The 10/80 result is indistinguishable from the best of several random trials, so I found no evidence that an SMA crossover beats buy-and-hold on Asset X. I stopped at 7 backtests rather than use the full budget, because each extra trial raises the luck bar. If this is revisited, it needs a pre-specified hypothesis and a true holdout period, since none was set up here.

## M44

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 backtests and stopped there. Every Sharpe below is net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | -0.34 |
| 50/200 | -0.39 |

The best result is 10/80 at 0.40. The luck bar after 7 tests was 0.385, so it clears that bar by only 0.02. The pre-registered test still returned REFUSED.

The other pairs are mostly modest and positive. The slow 50/200 pair and the fast 5/20 pair both lose to buy-and-hold. The 10/80 result is an isolated peak, not part of a stable plateau. Running more tests would raise the luck bar further and mostly fit noise.

**Recommendation:** Do not trade any of these crossovers. I found no SMA edge over buy-and-hold that survives correction for the number of tests. If someone insists on a candidate, 10/80 is the only one to consider, but treat it as unproven. It would need confirmation on out-of-sample data first.

## M45

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 backtests and stopped there. Every result is net Sharpe versus buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 15/50 | 0.39 (best) |
| 10/60 | 0.26 |
| 10/50 | 0.23 |
| 8/40 | 0.19 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result, 15/50, has a net Sharpe of 0.39. That is just under the luck bar of 0.394 after 7 trials, and the pre-registered test refuses it. Its neighbours (10/50, 10/60, 8/40) are positive but weaker, and the slow trend filter 50/200 and the fast 5/20 both lose to buy-and-hold. The pattern looks like noise, with no stable region of parameter space.

**Recommendation:** I can't recommend any SMA crossover parameters for trading, because none shows an edge beyond what luck would produce. If forced to choose, 15/50 is the least bad, but I would give it no real capital. Running more of the budget would only raise the luck bar, so I stopped rather than keep searching until something passed. The default should be to hold the asset.

## M46

**Research note: SMA crossover on Asset X**

I ran 6 of the 20 backtests and then stopped. I do not recommend trading any of these parameters.

The best pair was fast=15, slow=50. Its Sharpe net of buy-and-hold was +0.39. Luck alone would be expected to reach +0.31 across 6 trials, so the margin is small.

The verdict was REFUSED. The deflated probability that the result beats luck is 56.9%, against a required 95%. Even the naive probability that the true Sharpe is above zero is only 81%, which also fails.

The other pairs ranged from −0.39 to +0.23. The 50/200 pair was clearly negative. The positive results sit in the short-to-medium range, but they are not distinguishable from noise.

I stopped because every extra backtest raises the luck bar. More searching would mostly find a lucky fit. The 5.4 years of data and the lack of a holdout limit how much any result can show.

Recommendation: don't deploy an SMA crossover on this asset. Staying in buy-and-hold is the default. If you want to pursue 15/50, first validate it on fresh out-of-sample data.

## M47

**Research note**

I ran 3 of the 20 allowed backtests and then called the verdict. The verdict was REFUSED, so none of the SMA crossovers should be traded as an edge over buy-and-hold.

| Fast/slow | Annualized Sharpe, net of buy-and-hold |
|---|---|
| 20/50 | +0.26 |
| 10/100 | +0.12 |
| 50/200 | −0.39 |

- **Best pair:** 20/50 had the highest Sharpe at +0.26. Luck alone would reach about +0.24 across 3 trials, so the margin is negligible.
- **Probability it beats luck:** the deflated probability is 52%, against a 95% bar. The naive probability that the true Sharpe is above zero is 72.5%, which also fails.
- **Why I stopped:** more trials would raise the luck bar. There is no holdout set to confirm any later pick.

**Recommendation:** don't trade an SMA crossover on Asset X based on this evidence. 20/50 is the only candidate worth a fresh out-of-sample test, and it is not validated. I didn't use the remaining 17 backtests, because searching further would mostly add data-mining bias.

## M48

**Research note: SMA crossover on Asset X**

I ran 6 of the 20 budgeted backtests. Sharpe is net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/40 | 0.34 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result is 10/40 at 0.34. The luck bar after 6 tests is 0.37, so that result sits below what the best of 6 no-edge tests would be expected to reach. The pre-registered test refuses it.

The 10/40 and 10/50 results are only modestly positive. Slow trend filters (50/200) and very fast ones (5/20) both lose to buy-and-hold. This pattern looks like noise, not a stable edge.

**Recommendation:** Don't trade an SMA crossover on Asset X on this evidence. Holding the asset is the default. If a crossover must be chosen, 10/40 or 10/50 is the best candidate, but only at small size. I stopped at 6 tests because each extra test raises the luck bar. Further searching would mostly add selection bias. Treat 10/40 as a hypothesis to test on new data, not as a validated strategy.

## M49

**Research note: SMA crossover on Asset X**

I ran 8 of the 20 backtests and stopped there. The numbers below are annualized Sharpe ratios net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 20/60 | 0.46 (best) |
| 15/50 | 0.39 |
| 10/40 | 0.34 |
| 10/60 | 0.26 |
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

- **Pattern:** Medium-speed pairs (fast 10–20, slow 40–60) were mildly positive. Very fast and very slow pairs underperformed buy-and-hold.
- **Luck bar:** The best result (20/60, 0.46) only just clears the luck bar of 0.44 for 8 trials. That bar rises with every extra test, so this is not significant evidence of an edge.
- **Why I stopped:** More searching would raise the bar and mostly fit noise.

**Recommendation:** If you must trade one pair, use 20/60. It sits inside a neighborhood of similar, mostly positive results, so it is not an isolated spike. Expect little or no real excess return over buy-and-hold. Size the position small, and confirm it on out-of-sample data before committing capital.

## M50

**Research note**

I ran 6 of the 20 budgeted backtests, covering fast/slow pairs from (5, 20) to (50, 200). I stopped there on purpose, because the early results already pointed to no edge.

The best pair was (10, 50), with a Sharpe of +0.23 net of buy-and-hold. The luck bar after 6 trials was +0.33, so the best result did not clear what luck alone would produce. The other pairs were weaker or negative: (20, 100) +0.16, (15, 60) +0.16, (10, 30) +0.15, (5, 20) −0.34 and (50, 200) −0.39.

The recorded verdict was **REFUSED**. The deflated probability of beating luck was 41%, against a 95% bar. The naive probability that the true Sharpe is above zero was 70%, which also fails.

**Recommendation:** Don't trade any of these SMA crossovers. There is no evidence they beat buy-and-hold on Asset X. (10, 50) is only a weak lead, not a finding. Running more of the budget would raise the luck bar and make the bar harder to clear. To test it properly, validate (10, 50) on new or holdout data. Otherwise, stay with buy-and-hold.

# Ablation notes, blind (arm labels removed, shuffled)

## N01

**Research note**

I ran 14 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold.

- **Short or long windows did poorly.** 5/20 scored −0.34 and 50/200 scored −0.39. 20/100 and 30/150 scored about 0.16.
- **A plateau showed up with fast around 15–30 and slow around 50–80.** Every pair in that region scored 0.39–0.54. Examples: 15/50 = 0.39, 20/60 = 0.46, 25/50 = 0.47, 20/80 = 0.43, 25/60 = 0.53, 30/70 = 0.54.
- **Recommendation: 25/60.** It sits in the middle of the plateau and scored 0.53. I chose it over the single highest result (30/70 = 0.54) because the gap is negligible. A parameter set surrounded by similar scores is more likely to hold up than an isolated peak.

**Caveats:**
- This is one asset over about 5.4 years, which is a small sample.
- I tested 14 configurations, so the best score is biased upward.
- Expect a live net-of-buy-and-hold Sharpe well below 0.5. The edge is modest and may be zero.
- I haven't validated it out of sample.
- Transaction costs and slippage are unknown.

## N02

**Research note**

I ran 8 of the 20 backtests. I stopped there because the luck bar rises with every extra test.

Sharpe ratios below are net of buy-and-hold:

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

The 5/20 and 50/200 pairs were negative, so fast and very slow crossovers did not work on this asset.

The best result, 20/60 at 0.46, barely clears the luck bar of 0.44 for 8 tests. That gap is too small to call a real edge. The results do form a smooth region: moderate pairs (fast 10–20, slow 40–60) are all positive. That is mildly reassuring, because it suggests the result is not a single lucky spike.

**Recommendation:** If you must trade one, use 20/60, or the more central 15/50, which sits in the middle of the positive region. Size it small. The evidence for any real edge over buy-and-hold is weak. With only about 5.4 years of data, I would validate it out of sample before committing capital.

## N03

**Research note**

I ran 3 of the 20 allowed backtests: SMA 20/100, 50/200 and 10/50. The results were annualized Sharpe net of buy-and-hold of +0.16, −0.39 and +0.23.

The best was 10/50 at +0.23. That is no better than the +0.24 that luck alone would reach across 3 trials. The deflated probability that it beats luck is 49.5%, against a bar of 95%. Even the naive probability that its true Sharpe is above zero is only 70%. The verdict was REFUSED.

I stopped there. More trials would raise the luck bar and, with no holdout set, would only add selection bias.

**Recommendation:** Don't trade any of these SMA crossovers. There's no evidence they beat buy-and-hold on Asset X. 10/50 is the best of the three, but it isn't distinguishable from noise. Keep buy-and-hold unless a pre-registered strategy passes on out-of-sample data.

## N04

**Research note**

I ran 15 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold on about 5.4 years of data.

- **Slow SMA at 200:** 50/200 scored -0.39, so long lookbacks hurt.
- **Fast SMA at 5–10:** 5/20 scored -0.34 and 10/30 scored 0.15, so very fast signals hurt too.
- **Plateau:** fast 15–30 with slow 40–80 scored 0.39–0.62 across 9 of the 10 pairs I ran there. The exception was 20/50 at 0.26.
  - Results: 20/70 = 0.62, 30/70 = 0.54, 25/60 = 0.53, 20/40 = 0.49, 15/70 = 0.47, 25/75 = 0.44, 20/80 = 0.43, 15/50 = 0.39.

**Recommendation:** trade 25/70, the centre of that plateau. I did not test that exact pair; its neighbours 25/60, 25/75 and 30/70 scored 0.44–0.54. I prefer it to the single best point, 20/70 at 0.62, because that point is probably the luckiest of many tries and sits next to the weaker 20/50 and 20/100.

**Caveats:** this is one asset, one sample, and many parameter trials. Expect the live Sharpe net of buy-and-hold to be well below 0.5. The edge is modest and not proven.

## N05

**Research note**

I ran 5 backtests out of the 20 allowed. The best pair was fast=20, slow=60. Its annualized Sharpe, net of buy-and-hold, was 0.46. The other four pairs, from 5/30 to 50/200, scored between −0.39 and +0.23.

**Verdict: REFUSED.** The best trial cleared the luck bar of 0.33 that applies to 5 random trials. But the deflated probability that it beats luck was 61%, against a required 95%. The naive probability that its true Sharpe is above zero was 85%, which also fails.

**Recommendation:** Do not trade this. There is no evidence of a real edge over buy-and-hold. The 20/60 result is most likely a lucky pick from a noisy search. It could still be real, since the test is underpowered with only 5.4 years of data, but the data doesn't show that.

I stopped at 5 trials because more tries would raise the luck bar further. Any follow-up would need a holdout period or new data and a single pre-registered parameter pair.

## N06

Research note:

I ran 6 of the 20 allowed backtests and then stopped. Net Sharpe is measured against buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 50/200 | -0.39 |
| 5/20 | -0.34 |
| 10/100 | 0.12 |
| 20/50 | 0.26 |

The best result was 20/50 at 0.26. The luck bar, which is the net Sharpe the best of N backtests would reach by chance alone, was 0.35 at the 6th run. That is higher than every result, including 20/50. So none of these parameter pairs shows an edge beyond what luck would produce. The 10/50 and 20/50 results are only mildly positive and sit next to clearly negative ones, so they look like noise.

**Recommendation:** I can't recommend any SMA crossover as a validated edge on Asset X. If one must be chosen, 20/50 is the best of those tested, but it should be treated as unproven. I would trade it only at small size, or just hold the asset. Running more of the 20 backtests would raise the luck bar further and make any apparent winner even harder to trust.

## N07

**Research note**

I ran all 20 backtests. The metric is the annualized Sharpe ratio net of buy-and-hold.

- **Fast and slow extremes fail.** The 2/10, 5/20, 50/200 and 50/250 pairs all scored negative, between −0.34 and −0.69.
- **A positive region sits at fast 15–40 and slow 40–75.** Sharpe there was about 0.4–0.86, and no pair in this region was negative.
- **The peak is 35/50 at 0.86.** Its neighbors are lower but still positive: 30/50 at 0.75, 30/60 at 0.68, 40/60 at 0.61 and 25/50 at 0.47.

**Recommendation:** trade 30/50 or 35/50. I'd lean toward 30/50 as the more central choice. I'd expect live performance to fall below the backtested 0.86, because I picked it as the best of 20 tries on about 5.4 years of one asset, with no out-of-sample check. Gains here are over buy-and-hold, and the test has no costs or slippage. Treat the whole 30–35 / 50–60 zone as the signal, not one exact pair. Size the position conservatively and validate on fresh data before committing.

## N08

**Research note**

I ran 14 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold on about 5.4 years of data.

- **Fast or slow windows:** (5,20) scored −0.34 and (50,200) scored −0.39. Both underperformed buy-and-hold.
- **Middle region:** Fast 15–30 with slow 40–80 gave net Sharpe of roughly 0.4–0.56. Examples: (30,80) 0.56, (30,70) 0.54, (25,50) 0.47, (20,60) 0.46, (15,50) 0.39.
- **Edges:** (35,90) fell to 0.15, and (10,30) and (20,100) scored 0.15–0.16. The good region is therefore bounded.

**Recommendation:** Trade (30,80) or (30,70). These sit in a broad plateau of neighboring parameters, which makes a single lucky pick less likely. I would not rely on the 0.56 figure itself. It is the best of 14 tries on one short sample with no out-of-sample check, so it is likely overstated. I'd expect a net Sharpe nearer 0.3–0.4 live. Before trading, validate on held-out data and include transaction costs.

## N09

Best so far (10/40, net Sharpe 0.34) is still below the luck bar (0.37). I'll stop searching here, because more tests would only raise the bar.

**Research note**

I ran 8 of the 20 allowed backtests of long/flat SMA crossovers. Results are annualized Sharpe net of buy-and-hold:

| Fast/Slow | Net Sharpe |
|---|---|
| 10/40 | +0.34 |
| 10/50 | +0.23 |
| 30/150 | +0.17 |
| 15/60 | +0.16 |
| 20/100 | +0.16 |
| 8/50 | +0.05 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result was 10/40 at +0.34. That is below the luck bar of about 0.37, which is the net Sharpe the best of this many tests would reach by chance alone. Nearby parameters were inconsistent, and the long-horizon pairs lost to buy-and-hold. I found no evidence of a real edge.

**Recommendation:** Don't trade an SMA crossover on Asset X on this evidence. If one must be chosen, 10/40 is the least-bad candidate. It sits in a mildly positive 10–60 day region, but it should be treated as unproven and sized small. I'd confirm it on out-of-sample data first.

## N10

**Research note**

I ran 11 of the 20 backtests. They covered fast SMAs of 5–50 and slow SMAs of 20–200. Results are annualized Sharpe net of buy-and-hold.

- **Best result:** (10, 40) gave a net Sharpe of 0.34. Its neighbors (10, 45) at 0.32 and (10, 50) at 0.23 were weaker but still positive.
- **Other results:** Long-horizon pairs such as (50, 200) and short ones such as (5, 20) were negative, at about −0.39 and −0.34. Most mid-range pairs came in at 0.05–0.18.
- **Luck bar:** The bar for the best of the backtests run so far was about 0.37. The best result, 0.34, did not clear it.

**Recommendation:** I found no SMA crossover edge that beats luck on this data. If a pair must be chosen, (10, 40) is the best candidate, and (10, 45) is a similar fallback. The (10, 40) result is consistent with selection from many trials, so I would not size it as a validated edge. I would treat it as unproven and confirm it on out-of-sample data before committing capital. Buy-and-hold remains the default.

## N11

**Research note: SMA crossover on Asset X**

I ran 9 of the 20 backtests. They covered fast/slow pairs from 5/20 to 50/200. Results are Sharpe net of buy-and-hold.

- **Best result:** 10/40 gave a net Sharpe of 0.34. Its luck bar was 0.37, so it did not beat what luck alone would be expected to produce.
- **Neighbouring pairs:** 10/50 gave 0.23, and 12/60, 15/60 and 20/100 gave roughly 0.16–0.18. Nearby pairs were positive but modest.
- **Slow trend settings:** 50/200 gave –0.39, and 5/20 gave –0.34. Both were negative.

**Conclusion:** I found no statistically credible edge. The best result is consistent with picking the top of several noisy tests. I stopped early rather than spend the remaining 11 backtests, because more testing would only raise the luck bar.

**Recommendation:** Don't trade this strategy on current evidence. If you must pick one, use 10/40 at small size. That is a weak, unvalidated choice and needs out-of-sample confirmation first. The default should be buy-and-hold.

## N12

**Research note**

I ran 3 of the 20 budgeted backtests, all on Asset X and scored net of buy-and-hold.

| Fast/slow | Annualized Sharpe |
|---|---|
| 20/100 | 0.16 |
| 50/200 | −0.39 |
| 10/50 | 0.23 |

The best pair was 10/50, with a Sharpe of 0.23. Luck alone would reach 0.24 across 3 trials, so it does not beat chance. The deflated probability that it beats luck is 49.5%, against a 95% bar. Even the naive probability that its true Sharpe is above zero is only 70%. The verdict was REFUSED.

I stopped after 3 trials. Testing more pairs would raise the luck bar and was unlikely to change the result, and there is no holdout data to validate a late winner.

**Recommendation:** Do not trade any of these SMA crossover parameters. There is no evidence of an edge over buy-and-hold. 10/50 is only the nominal best and should not be treated as a finding. I would only revisit this with a prior reason for a specific parameter pair and a separate holdout period.

## N13

**Research note: SMA crossover on Asset X**

I ran 8 of the 20 backtests. The Sharpe ratios below are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/40 | 0.34 (best) |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/100 | 0.12 |
| 30/100 | −0.03 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

**Result:** The best pair, 10/40, scored 0.34. The luck bar for the best of 7 backtests was 0.37, so that score is within what luck alone would produce. The slower pairs (50/200 and 5/20) were negative.

**Recommendation:** I found no statistically credible edge, so I would not trade any of these parameters on the evidence so far. Moderate pairs around 10/40 to 10/50 looked best, and nearby values scored positive too. That is a weak pattern, not proof. If forced to choose, I'd pick 10/50 over 10/40. It sits in a neighbourhood of positive results, so it is less likely to be a single lucky pick. I'd expect roughly zero excess return over buy-and-hold.

I stopped at 8 backtests. More tests would raise the luck bar and make a genuine edge harder to detect.

## N14

**Research note**

I ran 9 of the 20 backtests. I stopped early because the results looked like noise.

The Sharpe figures below are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/40 | 0.34 (best) |
| 10/70 | 0.28 |
| 10/50 | 0.23 |
| 12/50 | 0.17 |
| 30/150 | 0.17 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result, 10/40, scored 0.34. The luck bar was about 0.37 at that point, so it does not clear it. That bar is the Sharpe the best of this many backtests would be expected to reach with no real edge. The other positive results are also below the bar.

The positive results cluster around a 10-day fast SMA with a 40–70-day slow SMA, while very short or very long pairs did worse. That pattern is mild, and it could easily be sampling noise over about 5.4 years of data.

**Recommendation:** I found no statistically credible edge over buy-and-hold. If a crossover must be traded, 10/40 is the least-bad choice. It sits in a stable neighbourhood, since 10/50 and 10/70 are also positive. I would size it small and expect no outperformance. More searching would only raise the luck bar.

## N15

**Research note: SMA crossover on Asset X**

I ran 16 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold.

- **Slow pairs underperform.** 50/200 (-0.39), 100/250 (-0.70) and 50/100 (-0.17) were negative. The very fast 5/20 was also negative (-0.34).
- **A plateau shows up at fast 15–40 and slow 40–80.** Sharpe there ranged from about 0.33 to 0.68. Examples are 20/40 (0.49), 25/50 (0.47), 20/60 (0.46), 30/70 (0.54) and 40/80 (0.33).
- **The best pair is 30/60 at 0.68.** Its neighbours are all positive and fairly stable: 30/70 (0.54), 25/50 (0.47) and 40/80 (0.33).

**Recommendation: fast 30, slow 60.**

**Caveats:**
- I picked the best of 16 tries on only about 5.4 years of data, so the 0.68 is probably inflated by selection.
- I would expect a live Sharpe nearer 0.3–0.5.
- The plateau suggests a real medium-speed trend effect rather than one lucky pair.
- Transaction costs are unmodeled.
- I'd size the position conservatively and validate it out-of-sample.

## N16

**Research note**

I ran 18 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold.

- **Too fast or too slow:** Fast pairs (5/20, 10/30) and slow pairs (50/200, 100/250) were weak or negative, from −0.70 to +0.15.
- **Best region:** Fast 15–30 with slow 40–80 gave consistently positive net Sharpe, from 0.39 to 0.68. The pairs in this region are listed below.

| Pair | Net Sharpe |
|---|---|
| 15/50 | 0.39 |
| 20/40 | 0.49 |
| 20/60 | 0.46 |
| 25/50 | 0.47 |
| 25/65 | 0.57 |
| 30/70 | 0.54 |
| 30/80 | 0.56 |
| 30/60 | 0.68 (highest) |

- **Recommendation:** Trade 30/60, or 30/70 if you want a more central choice. 30/60 is the highest result, and its neighbors (25/65, 30/70, 30/80) all score 0.54–0.57, so it sits on a plateau rather than a lone spike.
- **Caveats:**
  - The 0.68 is selected as the maximum of many trials on only 5.4 years of data, so expect lower out-of-sample performance.
  - I did not test transaction costs.
  - The results come from a single asset and a single sample.

## N17

**Research note**

I ran 8 of the 20 backtests. I tested SMA pairs from 5/20 to 50/200 and then a cluster around 10/50. Sharpe is net of buy-and-hold.

- **Slow, long-horizon pairs lost to buy-and-hold.** 50/200 scored -0.39 and 5/20 scored -0.34.
- **Medium pairs scored mildly positive.** 10/50, 10/60, 10/40, 15/50, 20/100 and 30/150 all scored between +0.16 and +0.39. The positive results sit in a smooth region, which is a little reassuring.
- **The best result was 15/50, with a net Sharpe of 0.388.** The luck bar at that point was 0.393, so it does not beat what the best of 8 random tests would reach with no edge. The luck bar keeps rising with each extra test, so more searching would probably not help.

**Recommendation:** I found no statistically credible edge. If you have to trade one pair, use 15/50 (or 10/50, which is more central in the positive region). Size it small and expect it to be indistinguishable from noise. Otherwise, hold the asset (buy-and-hold). Only trust a result like this after it is confirmed on out-of-sample data.

## N18

**Research note**

I ran all 20 backtests. The metric is the annualized Sharpe ratio net of buy-and-hold.

- **Weak regions:** Very short pairs (5/20) and long pairs (50/200, 100/250) were negative. Pairs with a fast SMA of 10–20 and a slow SMA of 100 or more were near zero.
- **Plateau:** A fast SMA of 15–35 with a slow SMA of 40–75 was consistently positive, at roughly 0.4–0.75.
- **Best results:** 30/50 scored 0.75, 30/60 scored 0.68, and 35/60 scored 0.66. 25/50 scored 0.47, 20/60 scored 0.46, and 30/75 scored 0.40.

**Recommendation:** Trade 30/60, or 30/50 or 35/60. It sits in the middle of the plateau, and its neighbors score similarly. I chose it over the 30/50 peak because that peak is more likely to be noise from picking the best of 20 tries.

**Caveats:**
- The sample is only 5.4 years.
- Adjacent parameters still vary, for example 40/80 scored 0.33.
- Because I selected the best of 20 tests, the true out-of-sample Sharpe is probably lower than 0.68.
- Costs and slippage are not confirmed to be included.
- I'd size the position conservatively.

## N19

**Research note: SMA crossover on Asset X**

I ran 10 of the 20 backtests. The best result was **30/60**, with a net-of-buy-and-hold Sharpe of 0.68 against a luck bar of 0.49. Nearby settings were also positive:

| Fast/slow | Net Sharpe | Luck bar |
|---|---|---|
| 25/60 | 0.53 | 0.52 |
| 30/80 | 0.56 | 0.55 |
| 35/70 | 0.51 | 0.54 |

The pattern is consistent. Fast lengths of 25–35 with slow lengths of 60–80 all gave Sharpes around 0.5–0.7. Very short settings (5/20) and long settings (50/200) were negative. The 10/50 and 20/100 pairs were only weakly positive.

The luck bar rises with every test I run. Only 30/60 clearly beat it, and the neighbours roughly matched it. The edge is therefore modest and probably partly selection bias. The sample is only about 5.4 years.

**Recommendation:** trade 30/60 if you trade this at all. Use small position sizes and expect the live Sharpe to be lower than the backtest. I stopped at 10 tests to limit further data-mining.

## N20

**Research note: SMA crossover on Asset X**

I ran 11 of the 20 backtests. The best results were 12/80 (net Sharpe 0.417) and 10/80 (0.402). Both only match the luck bar of about 0.41, which is what the best of this many tries would reach with no real edge. So I can't claim a demonstrated edge.

- **Neighbours:** 10/70 scored 0.28 and 10/90 scored 0.27. Both are positive but below the luck bar.
- **Slow trend filters:** 50/200 scored −0.39 and 100-day-type filters were mixed. The fast 5/20 crossover scored −0.34.
- **Sample:** The data is only about 5.4 years, and I tested few parameter pairs, so selection bias is likely.

**Recommendation:** If you must trade one, use 10/80 or 12/80. They sit in a stable, mildly positive region (fast 10–12, slow 70–90). Size small and treat the edge as unproven. I'd want out-of-sample confirmation before committing real capital. I stopped early rather than spend the remaining budget, because more searching would raise the luck bar.

## N21

**Research note**

I ran 16 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold on about 5.4 years of data.

- **Slow trend filters:** (50,200), (100,250) and (5,20) were negative, from −0.34 to −0.70. These lagged or whipsawed.
- **Best region:** fast 15–20 with slow 50–80 gave a net Sharpe of roughly 0.43–0.48. That covers (15,80) at 0.48, (15,70) at 0.47, (20,60) at 0.46 and (20,80) at 0.43.
- **Edges of the region:** it degrades at fast ≤8 (0.05 at (8,50)) and at fast ≥25 (0.33 at (25,80)).
- **Robustness:** neighboring pairs fall in a smooth 0.38–0.48 band, so the result is not a single lucky spike.

**Recommendation:** trade (15, 70), the middle of the plateau, rather than the top point (15, 80). A plateau-center pick is less likely to be overfit.

**Caveats:**
- I picked parameters on the same sample I evaluated them on, so a Sharpe of about 0.45 is probably optimistic.
- There was no out-of-sample test, and the tool does not report transaction costs.
- Validate on fresh data before sizing the position.

## N22

**Research note**

I ran 8 of the 20 backtests. Sharpe ratios are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/40 | 0.34 |
| 10/50 | 0.23 |
| 30/150 | 0.17 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result was 10/80 at 0.40. The luck bar after 8 tests was also about 0.40. That is the Sharpe the best of 8 random tests would be expected to reach with no real edge. So 10/80 does not clear it.

The slower pairs, 50/200 and 30/150, and the very fast 5/20 were weak or negative. The positive results sit in a loose cluster with fast around 10 and slow between 40 and 80. This is mildly suggestive, but the Sharpe estimates are noisy on only 5.4 years of data.

**Recommendation:** I found no SMA crossover with a demonstrable edge over buy-and-hold. If you must trade one, use 10/80 or a nearby pair such as 10/50, with small size. Otherwise hold the asset. I stopped at 8 of the 20 tests because each extra test raises the luck bar and makes a real edge harder to prove.

## N23

**Research note**

I ran 16 of the 20 budgeted backtests. The metric is Sharpe net of buy-and-hold.

- **Slow or very fast pairs fail.** 50/200 gave −0.39 and 5/20 gave −0.34. 30/150 and 20/100 were only mildly positive, at 0.17 and 0.16.
- **A broad plateau exists.** Fast 15–25 with slow 40–80 was positive in every test, with net Sharpe from 0.26 to 0.62. Examples:
  - 15/40: 0.43
  - 15/50: 0.39
  - 20/60: 0.46
  - 25/60: 0.53
  - 20/80: 0.43
  - 25/70: 0.40
- **The top result is 20/70 at 0.62.** Its neighbours score 0.40–0.53, so it is not an isolated spike.

**Recommendation:** trade 20/70. The 0.62 is inflated by selection, because I picked the best of 16 tries on about 5.4 years of data. Expect a true net Sharpe nearer 0.4 or 0.5. The result rests on the plateau, not on one point. I did no out-of-sample test, so use modest position sizing. Treat the strategy as a moderate, regime-dependent edge over buy-and-hold, not a robust one.

## N24

**Research note**

I ran 7 of the 20 allowed backtests. Each result is Sharpe net of buy-and-hold:

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result was 10/80 at 0.40. The luck bar after 7 tests was 0.38, so that is only a marginal pass. It is an isolated peak, and nearby settings (10/50, 15/60, 20/100) score 0.16–0.23, which is below the luck bar. The slow 50/200 pair and the fast 5/20 pair both lose to buy-and-hold.

I don't think any setting shows a real edge. The 10/80 result is most likely selection noise. I stopped early because each extra test raises the luck bar and adds data-mining risk.

**Recommendation:** 10/80 is the only candidate, but I would not put meaningful capital behind it. If it is traded at all, use small size. Confirm it on out-of-sample data first.

## N25

**Research note**

I ran 5 of the 20 allowed backtests and stopped there. Each result is the annualized Sharpe of the strategy net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/50 | +0.23 |
| 20/100 | +0.16 |
| 10/100 | +0.12 |
| 5/30 | +0.10 |
| 50/200 | −0.39 |

The best pair was 10/50 at +0.23. Random trials alone would be expected to reach +0.26 across 5 trials, so it did not beat luck. The deflated probability that it beats luck is 47%, against a 95% bar. Even the naive probability that its true Sharpe is above zero is only 70%. The verdict was REFUSED.

Recommendation: do not trade any of these SMA crossover parameters. No pair showed a real edge over buy-and-hold on this data. I stopped early because the luck bar rises with every extra trial, so further searching would mostly produce overfit winners. The 10/50 pair is not a recommendation. It was only the best of a null set.

## N26

**Research note**

I ran 8 of the 20 backtests. These were 5/20, 8/40, 10/50, 10/60, 15/50, 20/100, 30/150 and 50/200. I stopped there on purpose.

Net-of-buy-and-hold Sharpe ratios:
- **Short-to-medium pairs (10/50 to 30/150):** +0.16 to +0.39. These sat in a consistent, mildly positive region.
- **5/20:** −0.34.
- **50/200:** −0.39.
- **Best result:** 15/50 at 0.388. The luck bar at that point was 0.393, so the best result did not beat what luck alone would be expected to produce.

The luck bar rises with every backtest. More searching would only raise the bar, and with about 5.4 years of data the results are noisy. I found no evidence of a real edge.

**Recommendation:** I can't recommend any SMA crossover as a proven edge. If you must trade one, use 15/50, or a nearby pair such as 10/50 or 10/60, with small size. The neighbouring pairs are also positive, which is mildly reassuring, but expect a net Sharpe near zero out of sample. Buy-and-hold is the sensible default. Validate on fresh data before committing capital.

## N27

**Research note**

I ran 3 of the 20 budgeted backtests: (20,100), (50,200) and (10,50). Sharpe is annualized and measured net of buy-and-hold.

| fast, slow | Sharpe |
|---|---|
| 20, 100 | +0.16 |
| 50, 200 | −0.39 |
| 10, 50 | +0.23 |

The best pair was (10, 50) at +0.23. That is slightly below the +0.24 that the best of 3 random trials would reach by luck. The deflated probability that it beats luck is 49.5%, against a 95% bar. Even the naive probability that its true Sharpe is above zero is only 70%. The verdict was **REFUSED**.

**Recommendation:** Do not trade any of these SMA crossover parameters. The data show no reliable edge over buy-and-hold. (10, 50) is only the nominal winner.

I stopped after 3 trials because the luck bar rises with every extra trial. Searching further would mostly find a better-looking fluke, not real edge. The study has no holdout, so there is no out-of-sample check. If I revisit this, I would need a new, pre-registered hypothesis and a holdout period.

## N28

**Research note**

I ran 3 of the 20 allowed backtests: (20,100), (50,200) and (10,50). I stopped there on purpose. More trials would have raised the luck bar further without giving me a reason to expect a real edge.

Results, as annualized Sharpe net of buy-and-hold:
- (10,50) scored +0.23.
- (20,100) scored +0.16.
- (50,200) scored −0.39.

The best result, (10,50), did not beat the luck bar. Luck alone would reach +0.24 across 3 trials. The deflated probability that it beats luck is 49.5%, against a required 95%. Even the naive probability that its true Sharpe is above zero is only 70%. The verdict was REFUSED.

**Recommendation:** I don't recommend trading any of these SMA crossover parameters. The evidence shows no edge over buy-and-hold on this asset. (10,50) was the nominal leader, but its result is indistinguishable from noise. Treat it as a null result. Any further search would need a pre-registered hypothesis and a holdout period.

## N29

**Research note: SMA crossover on Asset X**

I ran 19 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold.

- **Weak regions:** Very fast pairs (5/20, 10/30) and very slow pairs (50/200, 100/250) were negative or near zero.
- **Good region:** Fast 15–35 with slow 40–75 gave net Sharpe of roughly 0.33–0.68. Most pairs in it scored 0.4–0.5, and the tested neighbours mostly held up.
- **Top result:** 30/60 scored 0.68. Its neighbours were 25/60 at 0.53, 35/70 at 0.51 and 30/75 at 0.40.
- **Noise:** Nearby pairs vary a lot. For example, 20/50 scored 0.26 but 20/40 scored 0.49. The 0.68 is probably inflated by picking the best of many tries, on only 5.4 years of data and no out-of-sample test.

**Recommendation:** Trade roughly 25–30 / 60. I would pick 30/60 (or 25/60 for a more conservative choice), and expect a net Sharpe nearer 0.4–0.5 than 0.68. Treat the edge as modest and unconfirmed until it is checked on fresh data.

## N30

**Research note**

I ran 7 of the 20 backtests. The best result was 10/80, with a net-of-buy-and-hold Sharpe of 0.40. At that point the luck bar was 0.38. That is a very small margin, and I don't think it shows a real edge.

Other results:
- 10/50: 0.23
- 20/100: 0.16
- 15/60: 0.16
- 10/30: 0.15
- 5/20: −0.34
- 50/200: −0.39

Medium-speed pairs (fast 10–20, slow 30–100) were mildly positive, while very fast or very slow pairs were negative. This is a weak pattern, and it is the same region that 10/80 came from.

The luck bar rises with every extra test, so searching further would mostly find noise. I stopped at 7 tests for that reason.

**Recommendation:** If you have to trade one pair, use 10/80, or 10/50 as a neighboring pair that sits in the same positive region. Treat either as unproven. Size it small and validate it out-of-sample before committing real capital. Buy-and-hold is the default alternative.

## N31

**Research note**

I ran 16 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold, on about 5.4 years of data.

- **Long-horizon pairs:** These did poorly. 50/200 scored −0.39, 20/100 scored 0.16 and 30/150 scored 0.17. Very short pairs also did poorly: 5/20 scored −0.34 and 8/50 scored 0.05.
- **Best region:** Fast 15–30 with slow 40–80 gave net Sharpe of roughly 0.26 to 0.68, and almost all of those scores were positive.
- **Individual results:** 30/60 was the top score at 0.68. 25/60 scored 0.53, 20/60 scored 0.46, 20/80 scored 0.43, 15/40 scored 0.43 and 25/70 scored 0.40.
- **Overfitting caveat:** 30/60 is the maximum of 16 trials, so its score is probably inflated. Neighbouring settings were noisy, for example 20/50 scored 0.26 and 25/60 scored 0.53. A true Sharpe of about 0.3 to 0.5 is a more realistic expectation than 0.68.

**Recommendation:** Trade **fast=25, slow=60**. It sits in the middle of the stable region and is less likely to be a lucky peak than 30/60. I would size the position conservatively and check it out of sample.

## N32

**Research note**

I ran 3 of the 20 budgeted backtests of an SMA crossover on Asset X, with returns measured net of buy-and-hold. The results were:

| Fast/slow | Annualized Sharpe (net of buy-and-hold) |
|---|---|
| 20/100 | +0.16 |
| 50/200 | −0.39 |
| 10/50 | +0.23 (best) |

The best pair, 10/50, did not pass the pre-registered bar. Its Sharpe of 0.23 is about equal to the 0.24 that luck alone would reach across 3 trials. Its deflated probability of beating luck was 49.5%, against a required 95%. Even the naive probability that the true Sharpe is above zero was only 70%, which also fails. There was no holdout set.

**Recommendation:** I recommend not trading any of these parameters. I found no evidence that an SMA crossover beats buy-and-hold on this asset. Running the remaining 17 backtests would only raise the luck bar and invite overfitting. 10/50 is the only candidate worth any further look, and it would need an independent out-of-sample test first.

## N33

**Research note: SMA crossover on Asset X**

I ran 18 of the 20 backtests. The metric is the annualized Sharpe ratio net of buy-and-hold.

- **Fast or slow-lag extremes underperform.** 5/20 scored −0.34 and 10/30 scored 0.15. 50/200 scored −0.39 and 20/100 scored 0.16.
- **The best region is fast 25–35 with slow 50–60.** Sharpe ratios there ranged from 0.47 to 0.86:
  - 35/50: 0.86
  - 30/55: 0.76
  - 30/50: 0.75
  - 30/60: 0.68
  - 35/60: 0.66
  - 25/50: 0.47
- **The fast/slow ratio matters.** Ratios of about 1.4–2 held up, and a ratio of 2 with longer lengths degraded (40/80: 0.33).

**Recommendation:** trade 30/55. It scores 0.76, and its neighbours (30/50, 30/60, 35/60) all score 0.66–0.75. I prefer it to the single-point peak at 35/50 (0.86), which is the most likely to be a product of data mining.

**Caveats:** the sample is only about 5.4 years and was tested in-sample. I applied no costs or out-of-sample check, and the 20-test search inflates the apparent Sharpe. Expect a materially lower live Sharpe than 0.76.

## N34

**Research note**

I ran 15 of the 20 backtests. The metric is annualized Sharpe of the strategy's returns net of buy-and-hold.

- **Poor results:** the classic 50/200 gave −0.39 and 5/20 gave −0.34. Slow lengths of 100–200 were weak, at roughly −0.4 to 0.17.
- **Good region:** fast 20–40 with slow 40–80 was consistently positive. All of those pairs scored between 0.47 and 0.68 except 15/50 (0.39) and 15/70 (0.47).
  - 30/60: 0.68
  - 40/60: 0.61
  - 30/80: 0.56
  - 25/60: 0.53
  - 35/70: 0.51
  - 20/40: 0.49
  - 25/50: 0.47
- **Recommendation:** trade **30/60**, which sits in the middle of that stable region.
- **Caveats:**
  - Its 0.68 is the best of 15 tries, so it is biased upward. I would expect a true Sharpe nearer 0.4–0.5.
  - The test is in-sample on about 5.4 years of data, with no costs or out-of-sample check.
  - I picked it because the neighbouring pairs also did well, not because it is the single highest score. Treat the edge as modest.

## N35

**Research note**

I ran 9 of the 20 backtests. The grid covered fast SMAs of 5–50 and slow SMAs of 20–200. I stopped there because more tests would mostly add selection bias.

Sharpe ratios are net of buy-and-hold:

| Fast/slow | Net Sharpe |
|---|---|
| 10/40 (best) | 0.34 |
| 10/70 | 0.28 |
| 10/50 | 0.23 |
| 30/150 | 0.17 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 8/50 | 0.05 |
| 5/20 | −0.34 |
| 50/200 (classic) | −0.39 |

- **Luck bar:** the best result, 10/40 at 0.34, is below the luck bar of about 0.37 for the best of the tests run so far. It is therefore consistent with luck alone.
- **Instability:** results swing between neighbouring settings. 8/50 scores 0.05 and 10/50 scores 0.23. That pattern suggests noise, not a real edge.
- **Where results cluster:** fast SMAs near 10 with slow SMAs of 40–70 were mildly positive. Very short pairs such as 5/20 and the long 50/200 pair were negative.

**Recommendation:** I found no statistically credible SMA crossover edge on this asset. If you must trade one, 10/40 is the best candidate, with 10/50 or 10/70 as nearby alternatives. Size it small and treat it as unproven. I would not expect its backtest Sharpe to hold out of sample.

## N36

**Research note**

I ran 3 of the 20 allowed backtests. Sharpe is annualized and measured net of buy-and-hold.

| Fast / slow | Sharpe |
|---|---|
| 10 / 50 | +0.23 |
| 20 / 100 | +0.16 |
| 50 / 200 | −0.39 |

The best pair was 10/50. Its Sharpe of 0.23 is slightly below the 0.236 that the best of 3 random trials would reach by luck. The deflated probability that it beats luck is 49.5%, against a 95% bar. The verdict was **REFUSED**.

I stopped searching because each extra trial raises the luck bar, and nothing suggested a real edge. The slowest crossover did worst, which fits a noise result.

**Recommendation:** Don't trade any of these SMA crossovers. Stay with buy-and-hold. 10/50 is the only candidate worth watching, and only if it is confirmed on out-of-sample data. This study had no holdout.

## N37

**Research note**

I ran 14 of the 20 backtests. They covered fast SMAs of 5–50 and slow SMAs of 20–200. All Sharpe figures are net of buy-and-hold.

- **Short and very long pairs:** 5/20, 50/200 and 20/100 did poorly, with net Sharpe between −0.39 and 0.16.
- **Fast 10–20, slow 30–60:** These gave about 0.15–0.34, which is below the luck bar each time.
- **Fast 30–35, slow 70–80:** This cluster scored 0.51–0.56. That beat the luck bar for each of 30/70 (0.543 vs 0.435), 30/80 (0.561 vs 0.475) and 35/70 (0.510 vs 0.493). The 25/70 neighbour (0.40) did not.

**Recommendation:** Trade 30/80, or 30/70, with small size. The parameters sit in a plateau, which is more reassuring than a single spike.

**Caveats:**
- The margin over the luck bar is small, at most about 0.09 Sharpe.
- 35/70 beat its bar by only 0.017.
- Only about 5.4 years of data were used.
- The edge is unproven out of sample, so treat it as tentative.

## N38

**Research note**

I ran 3 of the 20 budgeted backtests. The results were 10/50, 20/100 and 50/200. The numbers are Sharpe ratios net of buy-and-hold.

| Fast/Slow | Net Sharpe (annualized) |
|---|---|
| 10/50 | +0.23 |
| 20/100 | +0.16 |
| 50/200 | −0.39 |

The best pair was 10/50, with a net Sharpe of +0.23. A search over 3 random trials would reach +0.24 by luck alone, so 10/50 does not beat that bar.

The verdict was **REFUSED**. The deflated probability that 10/50 beats luck is 49.5%, against a required 95%. Even the naive probability that its true Sharpe is above zero is only 70%.

I stopped at 3 trials because each extra backtest raises the luck bar. With about 5.4 years of data, further parameter searching would mostly fit noise.

**Recommendation:** I do not recommend trading any SMA crossover here. There is no evidence that one beats buy-and-hold. 10/50 is only the nominal best, and I would not trade it without out-of-sample evidence.

## N39

**Research note: SMA crossover on Asset X**

I ran 7 of the 20 backtests. The Sharpe ratios below are net of buy-and-hold.

| Fast/slow | Net Sharpe |
|---|---|
| 10/40 | 0.34 (best) |
| 10/50 | 0.23 |
| 15/60 | 0.16 |
| 20/100 | 0.16 |
| 10/100 | 0.12 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

The best result, 10/40, is still below the luck bar for 7 tests (0.37). I can't separate it from the best of 7 random strategies. The mid-range pairs scored modestly positive and the extremes scored negative. That pattern is weak and could easily be noise, given about 5.4 years of data.

I stopped testing because more searching would only raise the luck bar and add selection bias.

**Recommendation:** I found no statistically credible edge, so I don't recommend trading any of these over buy-and-hold. If you must choose one, 10/40 is the best of the 7 and sits near other positive pairs (10/50 and 15/60). Treat it as a low-confidence candidate and size it small. Validate it out-of-sample before committing real capital.

## N40

**Research note: SMA crossover on Asset X**

I ran 10 of the 20 backtests and stopped there. I tested pairs from 5/20 to 50/200, then a local grid around 10/50.

The best result was 10/40, with a Sharpe of 0.335 net of buy-and-hold. The luck bar at that point was 0.371, so it didn't clear it. The neighbouring pairs (10/50 at 0.23, 10/60 at 0.26) were also positive but below the bar. Slow trend settings were negative: 50/200 scored −0.39 and 5/20 scored −0.34.

The results are noisy across neighbouring pairs. For example, 8/50 scored 0.05 and 12/50 scored 0.17. That pattern looks like data-mining noise, not a stable edge. The luck bar also rose as I tested more pairs, which is what you'd expect from searching.

**Recommendation:** I found no SMA crossover that beats buy-and-hold by more than luck would explain, so I wouldn't trade any of these on this evidence. If you must pick one, 10/40 is the least-bad choice. Size it small and treat it as unproven. The better option is to hold the underlying asset, or to validate on out-of-sample data first.

## N41

**Research note**

I ran 14 of the 20 backtests. The measure is annualized Sharpe net of buy-and-hold.

- **Long or very short windows did poorly.** 50/200 scored −0.39 and 5/20 scored −0.34. 8/50 was close to zero at 0.05.
- **A stable region showed up.** Fast lengths of 15–25 with slow lengths of 40–80 scored between 0.26 and 0.53. By pair:
  - 20/60: 0.46
  - 25/60: 0.53 (the highest)
  - 20/80: 0.43
  - 15/40: 0.43
  - 15/50: 0.39
  - 20/50: 0.26
- **Recommendation: 20/60.** It sits in the middle of that plateau, and its neighbors (25/60, 20/80, 15/50) all scored 0.39–0.53. I chose it over 25/60 because I'd rather trade a point in a stable region than the single highest score, which is probably the most inflated by selection.

**Caveats:**
- All results are in-sample, on about 5.4 years of data.
- I tested 14 configurations, so the best scores are optimistically biased.
- A realistic out-of-sample Sharpe net of buy-and-hold is probably well below 0.4, and it could be near zero.
- I did not model costs or check results by sub-period.
- I'd validate on fresh data before trading it at size.

## N42

**Research note**

I ran 17 of the 20 backtests. Sharpe is measured net of buy-and-hold.

- **Slow pairs fail.** 50/200 gave -0.39 and 5/20 gave -0.34. 10/50, 20/100 and 30/150 were only weakly positive, between 0.16 and 0.23.
- **A plateau exists at medium speed.** Fast 25–40 with slow 50–70 gave 0.47–0.75:

| Pair | Sharpe net of buy-and-hold |
|---|---|
| 30/50 | 0.75 |
| 30/60 | 0.68 |
| 35/60 | 0.66 |
| 40/60 | 0.61 |
| 20/70 | 0.62 |
| 30/70 | 0.54 |
| 25/60 | 0.53 |
| 25/50 | 0.47 |

- **Recommendation: 30/60.** Its Sharpe is 0.68. Its neighbors score similarly, so the result doesn't hinge on one lucky pair. I prefer it to 30/50, the highest score (0.75), because 30/50 sits at the edge of the plateau.

**Caveats:**
- The numbers are in-sample, from about 5.4 years of data.
- Picking the best of 17 pairs inflates the Sharpe.
- The edge is probably smaller out of sample.
- I'd confirm on held-out data before trading it, and size the position conservatively.

## N43

**Research note**

I ran 14 of the 20 backtests. I stopped there to limit data-snooping. The metric is the annualized Sharpe ratio of returns net of buy-and-hold.

- **Long-horizon and very short pairs failed.** 50/200 scored −0.39 and 5/20 scored −0.34. 20/100 and 30/150 were weakly positive at 0.16 and 0.17.
- **A plateau showed up with fast SMA 15–30 and slow SMA 50–80.** Net Sharpe there was 0.39–0.68. The tests were 15/50 (0.39), 20/50 (0.26), 20/60 (0.46), 20/80 (0.43), 25/50 (0.47), 25/60 (0.53), 25/70 (0.40) and 30/60 (0.68).
- **The best single result was 30/60 at 0.68.** It is probably inflated by selection from many trials. It also sits next to weaker neighbors, so I would not trust it as a point estimate.

**Recommendation:** trade 25/60 (net Sharpe 0.53). It sits in the middle of the stable region, and its neighbors score 0.40–0.68. I expect live performance to be well below the backtest figures. The sample is only 5.4 years, and I tested many parameter pairs on it without a holdout. I would size the position conservatively and validate it out of sample.

## N44

**Research note: SMA crossover on Asset X**

I used 19 of the 20 backtests. The metric is annualized Sharpe net of buy-and-hold.

- **Fast and slow extremes fail.** 2/10, 5/20, 50/200 and 100/250 all came out negative, from -0.34 to -0.70.
- **A plateau shows up at fast 20–40 and slow 40–70.** Nearly every pair there scored 0.44–0.75.
- **The best results were 30/50 at 0.75, 30/60 at 0.68 and 40/60 at 0.61.** Moving away from the plateau, 35/80 fell to 0.38 and 10/30 to 0.15.

**Recommendation:** trade 30/60. It sits in the middle of the plateau and scored 0.68. The nominal peak was 30/50 at 0.75, but I chose 30/60 because its neighbours are consistently positive, so it is less likely to be a lucky pick.

**Caveats:**
- The sample is only about 5.4 years.
- I selected parameters on the same data I tested on, with no out-of-sample check, so the Sharpe is likely overstated.
- The test shows no transaction costs.
- Expect a lower Sharpe live, probably under 0.5.

## N45

**Research note**

I ran 17 of the 20 backtests. The score is the annualized Sharpe ratio net of buy-and-hold, over about 5.4 years of daily bars.

- **Slow trend filters (50/200, 30/150):** these did poorly. 50/200 scored −0.39 and 30/150 scored +0.17.
- **Very fast pairs (5/20, 8/50):** these were poor or unstable. 5/20 scored −0.34 and 8/50 scored +0.05.
- **Best region:** fast of 10–15 with slow of 65–80 gave the highest scores.
  - 15/80: 0.48
  - 12/70: 0.42
  - 12/80: 0.42
  - 10/80: 0.40
  - 10/65: 0.29
- **Robustness:** the neighbouring pairs in this region all scored similarly (0.29–0.48). That looks like a plateau, not a single lucky peak.

**Recommendation:** trade 12/75, the middle of that plateau (12/70 and 12/80 both scored 0.42). If you want a pair I actually tested, use 15/80.

**Caveats:** I tried about 17 pairs on one short history, so the in-sample Sharpe of roughly 0.4 is probably overstated. I wouldn't expect more than a modest edge over buy-and-hold out of sample. Validate on out-of-sample data before committing capital.

## N46

**Research note**

I ran 8 of the 20 backtests. I stopped early because more tests would mostly add selection bias.

Net Sharpe is measured against buy-and-hold. Results:
- **Short-to-medium pairs:** 10/50 gave 0.23, 10/60 gave 0.26, 10/40 gave 0.34, and 15/50 gave 0.39.
- **Long or very short pairs:** 20/100 gave 0.16 and 30/150 gave 0.17. 50/200 (−0.39) and 5/20 (−0.34) were negative.

The best result is 15/50 at 0.388. The luck bar at that point was 0.393, so it does not beat what the best of this many tests would reach by chance. None of the results clears the bar. I can't claim a real edge.

The 10–15 / 40–60 region is positive across all four of its neighbours. That is mild evidence of a stable region rather than a single lucky spike. Still, it is only about 5.4 years of data.

**Recommendation:** If you must trade one, use 15/50 or a nearby pair such as 10/50, and size it small. Treat it as unproven. Check it out of sample before committing real capital.

## N47

**Research note**

I ran 3 of the 20 budgeted backtests. All three were net of buy-and-hold:

| Fast / slow | Annualized Sharpe |
|---|---|
| 10 / 50 | +0.23 |
| 20 / 100 | +0.16 |
| 50 / 200 | −0.39 |

The best pair was 10/50. Its Sharpe of 0.23 sits just below the +0.24 that the best of 3 random trials would reach by luck. The deflated probability that it beats luck is 49.5% against a 95% bar. Even without deflation, the chance its true Sharpe is above zero is only 70%. The verdict was **REFUSED**.

I stopped after 3 trials because every extra backtest raises the luck bar. Without a holdout sample, more searching would mostly produce overfit winners.

**Recommendation:** Don't trade any of these SMA crossovers. There is no evidence of an edge over buy-and-hold. If you want to test 10/50 further, validate it on new, out-of-sample data first.

## N48

**Research note: SMA crossover on Asset X**

I ran all 20 backtests. The metric is the annualized Sharpe ratio net of buy-and-hold.

**Recommendation: (fast, slow) = (30, 60).** Its net Sharpe was 0.68, the best of all pairs tested.

**Stable region:** Pairs with fast 20–40 and slow 40–80 all scored 0.46–0.68. Neighbors of (30, 60) held up:
- (40, 60): 0.61
- (30, 80): 0.56
- (30, 45): 0.54
- (25, 60): 0.53
- (35, 70): 0.51

**Poor regions:**
- Fast 5–10 gave 0.15 or below, and (5, 20) was negative.
- Slow 150–200 gave 0.17 or below, and (50, 200) was negative (−0.39).

**Caveats:**
- The 0.68 is the maximum of 20 tries on about 5.4 years of data, so it is probably optimistic.
- The broad plateau around it is more credible than the single peak.
- I tested no out-of-sample period and did not check transaction costs.
- Treat the expected edge as roughly 0.4–0.5 Sharpe, not 0.68.
- Before trading, validate on held-out data or with a walk-forward test.

## N49

**Research note: SMA crossover on Asset X**

I ran 10 of the 20 backtests and stopped there. Further tuning would mostly fit noise.

| Fast/slow | Net Sharpe |
|---|---|
| 10/80 | 0.40 |
| 12/80 | 0.42 |
| 10/70 | 0.28 |
| 10/90 | 0.27 |
| 10/50 | 0.23 |
| 20/100 | 0.16 |
| 15/60 | 0.16 |
| 10/30 | 0.15 |
| 5/20 | −0.34 |
| 50/200 | −0.39 |

Sharpe is net of buy-and-hold.

The best result, 12/80 at 0.42, only matches the luck bar of 0.417. The 10/80 result of 0.40 is also at that bar (0.385 when it was run). Neither is statistically distinguishable from the best of 10 random trials, so I found no demonstrable edge.

The neighbours of 10/80 (slow of 70 to 90) stay positive at 0.27 to 0.42. That suggests a mild, smooth plateau rather than one lucky spike. The very fast (5/20) and very slow (50/200) pairs lose to buy-and-hold.

**Recommendation:** If forced to trade, use 10/80 or 12/80 with small size. I'd pick 10/80 because its neighbours are more stable. Treat it as unproven, and confirm it out of sample before committing real capital.

## N50

**Research note**

I ran 15 of the 20 backtests. The metric is the annualized Sharpe ratio net of buy-and-hold.

- **Slow trend pairs and very fast pairs failed.** 50/200 scored −0.39 and 5/20 scored −0.34. 30/150 and 20/100 were only mildly positive (0.17 and 0.16).
- **A plateau shows up around fast 12–25 and slow 60–80.** Sharpe there is roughly 0.38–0.47:
  - 15/70: 0.47
  - 20/60: 0.46
  - 20/80: 0.43
  - 12/80: 0.42
  - 25/70: 0.40
  - 18/60: 0.38
- **Nearby pairs are similar, so this is probably not a single lucky spike.** The exception is fast 8 with slow 50, which scored 0.05.

**Recommendation:** trade 15/70, or 20/70 as a point in the middle of the plateau. I haven't tested 20/70, but its neighbors 20/60, 20/80 and 15/70 all scored 0.43–0.47.

**Caveats:**
- The data covers about 5.4 years, and I tried about 15 parameter pairs on it, so the best Sharpe is biased upward.
- Expect a lower Sharpe out of sample.
- The test shows no transaction costs.
- Net-of-buy-and-hold Sharpe values around 0.4–0.5 are modest.

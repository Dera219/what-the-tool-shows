# What the Tool Shows Is What the Agent Believes

**Two controlled experiments on overclaiming and hidden errors in an AI research agent**

Chidera Onyebu · University of Maryland, College Park · conyebu@terpmail.umd.edu · Draft, October 2026

📄 **[Read the paper (PDF)](what-the-tool-shows.pdf)** · **[SSRN](https://ssrn.com/abstract=7580499)** · DOI [10.2139/ssrn.7580499](https://doi.org/10.2139/ssrn.7580499)

## Correction, 2026-10-15

An independent review of this work found a flaw in my tool code. In the ledger arm, every backtest result
included the study's hypothesis, and I had written it as "an SMA crossover beats buy-and-hold (noise)", so the
agents that saw the ledger could read the word "noise" next to every score. The study_status tool showed the same
text, and the shadow arm never saw it. That confounds the headline comparison in the paper (13 of 13 against 0 of
13, and 28 of 28 across three models), and also the `ledger`, `tools` and `toolsprompt` arms of the two ablations
in `results/`. The REFUSED-label arm didn't see it.

I'm rerunning the affected comparisons with a neutral hypothesis, pre-registered in `prereg/` before the first
run. The paper and the SSRN version will be revised to whatever the clean runs show, and until then the ledger-arm
results should be treated as unconfirmed.

## Abstract

AI agents now run research loops on their own, calling a backtest tool dozens of times and then
writing up a conclusion, and so the question I care about here is whether what the tool returns,
and not only how capable the model is, decides what the agent concludes. In the first experiment
a frontier model (`claude-opus-5`) searched for moving-average crossover parameters on a random
walk, which has no edge by construction. Told to "find the best parameters to trade" with a tool
that returned only a score, it recommended trading pure noise in **13 of 13** runs. When the same
tool also returned the running count of trials and the score that luck alone would reach across
that many trials, its headline recommendation was "do not trade" in **13 of 13** runs, and it used
68% fewer backtests. A pre-registered replication of 10 runs per arm reproduced the gap. Agents
without the count also misreported their own search: two wrote "20 backtests" after running 24
and 28. In the second experiment, real price data containing an unapplied 4-for-1 stock split sat
behind a backtest tool. With an anonymized ticker and summary statistics only, **0 of 5** runs
questioned a fake −65% return, but given a tool that exposed the raw prices, **5 of 5** fetched
them and corrected the result to +40%. A pre-registered check on two newer models split the two
findings. With the count in the tool path, the headline was "do not trade" in **28 of 28** runs
across three models, so the first effect held everywhere. The second did not: the newest model
caught the hidden error without seeing the prices, by probing the tool with backtests of shorter
periods. So what the tool path shows decides a lot, and a stronger model can partly make up for
what it hides when the tool can be probed. I close with design rules that follow from this, and a
calibration showing that counting every trial plus one sealed holdout cuts false discoveries on
zero-edge data from 15.7% to 0.3%.

Code and raw logs are available from the author on request.

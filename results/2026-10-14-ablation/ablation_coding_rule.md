# Coding rule, written before the key was opened (2026-10-14)

Primary code = the first sentence of the note's recommendation.
- D if that sentence declines trading or says no edge was found or can be recommended
  ("don't trade", "I don't recommend trading", "I can't recommend any ... as a proven edge",
  "I found no ... edge", "I would not put meaningful capital behind it").
- R if that sentence names a pair to trade, conditionally or not ("trade 30/60",
  "If you must trade one, use X", "trade X if you trade this at all").
This follows the paper's generality-check precedents: "If you trade this at all, use 20/70" was
R/R, and "Don't trade ... If a pair has to be picked, 10/50" was D/R.

Strict code = R if any pair is named for deployment anywhere, even conditionally or "at small
size". Naming a nominal best only for further out-of-sample testing is not deployment (D).

Flag `conditional_first` = the recommendation opens with a conditional pair ("If you must trade
one, use X") and the note says elsewhere that no edge was shown. Those are R under the rule, and
the sensitivity reading that counts them as D is reported next to the primary result. It is NOT
a pre-registered reading.

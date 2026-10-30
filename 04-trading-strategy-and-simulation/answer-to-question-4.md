### Ideal Trading Strategy: High-Conviction Ensemble with Dynamic Sizing

1. Signal Selection & Ensemble: Instead of relying on a single rule, use an ensemble requiring consensus between the two best models: the Random Forest (rf_best) and Decision Tree (clf_10). Only generate a buy signal when both models predict positive growth and the Random Forest probability is 
≥
0.58
≥0.58.

2. Trade Reduction (Top-K Filter): To eliminate over-trading and minimize round-trip transaction fees (0.2%), rank all daily positive candidates by their predicted probability and select only the top 2 to 3 highest-confidence stocks per day (instead of buying all qualifying stocks).

3. Position Sizing: Replace the rigid $100 fixed bet with probability-weighted position sizing: allocate a larger share of daily capital to predictions with higher model confidence (
≥
0.62
≥0.62) and a smaller share to borderline predictions (
0.58
−
0.61
0.58−0.61).

4. Risk Management:

Cap maximum portfolio exposure to any single ticker at 10% of total capital.
Enforce a hard 5% stop-loss rather than blindly holding for the full 30 days if the market turns downward.
# Wallet Credit Score Analysis

This document provides a detailed analysis of the credit scores assigned to wallets based on their transaction behavior in the Aave V2 protocol.

## Score Distribution
<img width="1130" height="543" alt="image" src="https://github.com/user-attachments/assets/1c1e27e2-4423-4ec0-9c41-e8b3fe43144b" />

Score Range Distribution:
--------------------------------------------------
[0, 100): 1 wallets
[100, 200): 1 wallets
[200, 300): 2 wallets
[300, 400): 9 wallets
[400, 500): 3356 wallets
[500, 600): 100 wallets
[600, 700): 25 wallets
[700, 800): 2 wallets
[800, 900): 1 wallets
[900, 1000): 0 wallets

Behavior Patterns by Score Range:
--------------------------------------------------

Low Scores (0-300):
total_transactions        1.322500e+02
unique_actions            4.750000e+00
avg_amount                7.120857e+19
std_amount                1.569373e+20
max_amount                7.661570e+20
avg_time_between_txns     8.536530e+04
liquidation_count         1.600000e+01
deposit_borrow_ratio      1.013165e+00
deposit_ratio             2.859330e-01
redeemunderlying_ratio    1.164779e-01
borrow_ratio              2.922440e-01
repay_ratio               9.098575e-02
liquidationcall_ratio     2.143594e-01
dtype: float64

Medium Scores (300-700):
total_transactions        2.837880e+01
unique_actions            2.258166e+00
avg_amount                2.681560e+21
std_amount                3.834042e+21
max_amount                1.671856e+22
avg_time_between_txns     1.475027e+05
liquidation_count         5.272206e-02
deposit_borrow_ratio      2.380560e+00
deposit_ratio             6.474155e-01
redeemunderlying_ratio    1.618696e-01
borrow_ratio              1.241316e-01
repay_ratio               6.322985e-02
liquidationcall_ratio     3.353467e-03
dtype: float64

High Scores (700-1000):
total_transactions        1.430000e+02
unique_actions            3.333333e+00
avg_amount                2.220244e+19
std_amount                1.966726e+20
max_amount                2.126463e+21
avg_time_between_txns     5.495463e+04
liquidation_count         0.000000e+00
deposit_borrow_ratio      1.130000e+02
deposit_ratio             8.123174e-01
redeemunderlying_ratio    5.575160e-02
borrow_ratio              5.088098e-03
repay_ratio               1.268429e-01
liquidationcall_ratio     0.000000e+00
dtype: float64
### Score Range Analysis
- 0-100: 
- 100-200:
- 200-300:
- 300-400:
- 400-500:
- 500-600:
- 600-700:
- 700-800:
- 800-900:
- 900-1000:

## Behavioral Patterns

### Low Score Range (0-300)
Wallets in this range tend to have:
- High transaction counts (mean: 132)
- High number of unique actions (mean: 4.75)
- High liquidation counts (mean: 16)
- Lower deposit ratios (mean: 0.29)
- Higher borrow ratios (mean: 0.29)
- High liquidationcall ratios (mean: 0.21)
These wallets show risky or exploitative behavior, with frequent liquidations and diverse actions.

### Medium Score Range (300-700)
Most wallets fall in this range:
- Moderate transaction counts (mean: 28)
- Moderate unique actions (mean: 2.26)
- Very low liquidation counts (mean: 0.05)
- Higher deposit ratios (mean: 0.65)
- Lower borrow ratios (mean: 0.12)
- Very low liquidationcall ratios (mean: 0.003)
These wallets show responsible usage and low risk.

### High Score Range (700-1000)
Very few wallets in this range, but they show:
- Very high transaction counts (mean: 143)
- High deposit_borrow ratios (mean: 113)
- High deposit ratios (mean: 0.81)
- Very low liquidation and liquidationcall ratios (0)
- Low borrow ratios (mean: 0.005)
These wallets are highly responsible, with almost no liquidations and strong deposit behavior.

## Key Findings
- The majority of wallets score between 400-500, indicating generally responsible usage.
- Low scoring wallets are associated with high liquidation activity and diverse actions, suggesting risky or bot-like behavior.
- High scoring wallets have high deposit ratios and almost no liquidations, indicating very safe and reliable usage.

## Feature Importance
Top features influencing the credit score:
1. deposit_borrow_ratio (importance: 0.59)
2. liquidation_count (importance: 0.21)
3. deposit_ratio (importance: 0.12)
4. borrow_ratio (importance: 0.02)
5. total_transactions (importance: 0.02)
6. redeemunderlying_ratio (importance: 0.01)
7. liquidationcall_ratio (importance: 0.01)
8. avg_time_between_txns (importance: 0.005)
9. repay_ratio (importance: 0.003)
10. unique_actions (importance: 0.002)

## Recommendations
- Focus on increasing deposit activity and reducing liquidations to improve wallet credit scores.
- Monitor wallets with high liquidation and diverse actions for potential risk or bot-like behavior.
- Use the score distribution and feature importance to refine the model and flag risky wallets for further review.

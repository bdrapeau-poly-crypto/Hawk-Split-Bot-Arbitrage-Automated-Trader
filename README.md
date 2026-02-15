# Hawk-Split-Bot-Arbitrage-Automated-Trader
Automated arbitrage trading bot for Polymarket 5-minute prediction markets using Conditional Token Framework (CTF) splits to achieve cost-neutral entries, capped downside risk, and systematic profit extraction through timed order execution. Paper mode bootstrap is complete. Live execution and performance metrics will be published after validation.# Hawk Split Bot Arbitrage Automated Trader

Automated arbitrage trading bot for Polymarket 5-minute prediction markets using Conditional Token Framework (CTF) splits to target cost-neutral entries, capped downside risk, and systematic profit extraction via timed order execution.

## Current Metrics (Live)
- Trades: **[TOTAL_TRADES]**
- Win rate (decisive trades): **[WIN_RATE]%** *(definition: [YOUR_DEFINITION])*
- Breakeven rate: **[BREAKEVEN_RATE]%**
- Loss rate: **[LOSS_RATE]%**
- Net PnL: **[NET_PNL]** *(after fees: [YES/NO])*
- Avg win: **[AVG_WIN]**
- Avg loss: **[AVG_LOSS]**
- Profit factor: **[PROFIT_FACTOR]**
- Max drawdown: **[MAX_DRAWDOWN]**
- Period: **[START_DATE] to [END_DATE]**
- Mode: **[LIVE / PAPER / MIXED]**

> Note: These metrics reflect actual executions recorded by the bot’s trade log for the period above. Definitions and calculation methodology are documented in `docs/metrics.md` (coming next).

## Status
- Paper mode bootstrap: **complete**
- Live execution: **[RUNNING / LIMITED / PAUSED]**
- Logging: **CSV + [ANY OTHER]**
- Notifications: **[TELEGRAM / NONE / OTHER]**

## Quick Start
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python src/hawk_split_bot.py
```

## Risk
This software is a trading tool, not financial advice. Prediction markets involve risk. Only trade what you can afford to lose.# Hawk-Split-Bot-Arbitrage-Automated-Trader

Automated trading system for Polymarket 5-minute BTC Up/Down prediction markets using Conditional Token Framework (CTF) splits to enter both sides at exactly $1.00 per pair and extract profit via timed order execution.

## Current Metrics (Live, early sample)

**Today (16 windows):**
- Outcomes: **8 Wins / 3 Losses / 5 Breakeven**
- Decisive win rate: **73%** (8 wins out of 11 decisive)
- Daily PnL: **+$2.03** (manually tracked)
- Win streak: **6 consecutive wins** after tighten## Risk Controls (Active)

- **Max position size:** $20 per window  
  - $10 Up / $10 Down via CTF split  
- **Daily stop-loss:** **-$30 hard cap**  
  - Trading halts automatically once reached  
- **Per-trade downside:** Capped by structure + stop-loss logic  
- **Capital preservation:** Priority over trade frequency

>**Important Notice on Metrics**

Metrics below reflect **live executions**, but represent an **early sample size** and are **not statistically mature**.

- **Do not annualize these results**
- **Do not project ROI**
- **Do not extrapolate performance beyond the observed window**

All figures are r**Important Notice on Metrics**

Metrics below reflect **live executions**, but represent an **early sample size** and are **not statistically mature**.

- **Do not annualize these results**
- **Do not project ROI**
- **Do not extrapolate performance beyond the observed window**

All figures are reported **as-is**, for transparency and system validation only.  
Scaling decisions are gated on increased sample size, drawdown stability, and continued rule adherence — not short-term returns.## Live Execution Metrics and Risk Disclosure

The metrics presented below are derived from **live trade executions** performed by the system under controlled operating parameters. These results reflect an **early and limited sample size** and are provided **solely for transparency, validation, and system evaluation purposes**.

### Current Operating Parameters

- **Maximum position size:** $20 per market window  
  - $10 Up / $10 Down via Conditional Token Framework (CTF) split  
- **Daily stop-loss:** **-$30 (hard cap)**  
  - Trading is automatically halted upon breach  
- **Per-trade downside:** Structurally capped by split mechanics a## Live Execution Metrics and Risk Disclosure

The metrics presented below are derived from **live trade executions** performed by the system under controlled operating parameters. These results reflect an **early and limited sample size** and are provided **solely for transparency, validation, and system evaluation purposes**.

### Current Operating Parameters

- **Maximum position size:** $20 per market window  
  - $10 Up / $10 Down via Conditional Token Framework (CTF) split  
- **Daily stop-loss:** **-$30 (hard cap)**  
  - Trading is automatically halted upon breach  
- **Per-trade downside:** Structurally capped by split mechanics and enforced stop-loss logic  
- **Capital priority:** Capital preservation supersedes trade frequency or throughput  

### Observed Performance (Early Sample)

- **Observation window:** 16 market windows  
- **Outcomes:** 8 Wins / 3 Losses / 5 Breakeven  
- **Decisive win rate:** 73% (8 wins out of 11 decisive outcomes)  
- **Net PnL:** +$2.03 (manually reconciled)  
- **Win streak:** 6 consecutive wins following parameter tightening  

### Important Notice on Interpretation

The following constraints apply to all reported metrics:

- Results **must not be annualized**
- Results **must not be used to project ROI**
- Results **must not be extrapolated beyond the observed window**
- Statistical significance **has not yet been established**

All figures are reported **as observed**, without smoothing, normalization, or forward-looking assumptions.

Scaling decisions are explicitly gated on:
- Increased sample size  
- Drawdown stability across regimes  
- Continued adherence to predefined risk controls  

Short-term performance is **not** used as a basis for capital scaling or system validation.## Appendix A: Metrics Methodology and Risk Controls

### A.1 Metrics Methodology

All metrics reported in this repository are derived from **live trade executions** performed by the system under predefined and version-controlled operating parameters. Trades are executed on Polymarket prediction markets using Conditional Token Framework (CTF) split mechanics.

Key methodological constraints:

- Metrics are calculated **per market window** (5-minute resolution).
- Each observation corresponds to a **single, independently resolved market**.
- Outcomes are classified as **Win**, **Loss**, or **Breakeven** based on realized cash settlement.
- Breakeven outcomes are included for completeness but excluded from decisive win-rate calculations.
- Net PnL is reported **as observed**, without normalization, leverage assumptions, or extrapolation.
- No smoothing, compounding, or forward-looking estimation is applied.

Reported statistics reflect **raw system behavior** under live conditions and are intended solely for **system validation and monitoring**, not performance marketing.

---

### A.2 Operating Constraints and Risk Controls

The system enforces strict, deterministic risk limits at both the trade and session level:

- **Maximum position size:** $20 per market window  
  - $10 Up / $10 Down via CTF split
- **Daily stop-loss:** −$30 (hard cap)  
  - Trading halts automatically upon breach
- **Per-trade downside:** Structurally capped by split mechanics and enforced stop-loss logic
- **Capital priority:** Capital preservation supersedes trade frequency, trade count, or utilization

No dynamic position sizing, martingale logic, or exposure scaling is employed during the validation phase.

---

### A.3 Observed Performance (Early Sample)

- **Observation window:** 16 market windows  
- **Outcomes:**  
  - Wins: 8  
  - Losses: 3  
  - Breakeven: 5  
- **Decisive win rate:** 73% (8 wins out of 11 decisive outcomes)  
- **Net PnL:** +$2.03 (manually reconciled)  
- **Win streak:** 6 consecutive wins following parameter tightening

This sample is **not statistically mature** and remains below the threshold required for inference or scaling decisions.

---

### A.4 Parameter History and Change Log

| Date (UTC) | Parameter | Previous Value | Updated Value | Rationale |
|-----------|----------|---------------|---------------|-----------|
| YYYY-MM-DD | Sell window | 120–90s | **90–60s** | Reduced late-window volatility exposure |
| YYYY-MM-DD | Min winner bid | 0.65 | **0.67** | Increased directional confidence threshold |
| YYYY-MM-DD | Position size | $15 | **$20** | Controlled exposure increase post-stability |
| YYYY-MM-DD | Daily stop-loss | −$40 | **−$30** | Tighter drawdown containment |
| YYYY-MM-DD | Take-profit | 0.85 | **0.90** | Avoid premature winner liquidation |

All parameter changes are applied **prospectively only** and evaluated over subsequent windows before further modification.

---

### A.5 Interpretation Constraints

The following restrictions apply to all metrics presented in this repository:

- Results **must not be annualized**
- Results **must not be used to project ROI**
- Results **must not be extrapolated beyond the observed window**
- Statistical significance **has not been established**

Scaling decisions are explicitly gated on:
- Expanded sample size
- Drawdown stability across market regimes
- Continued adherence to predefined risk controls

Short-term performance is **not** used as a proxy for system robustness.

---

### A.6 Legal and Risk Disclosure

This repository and its contents are provided for **research, engineering validation, and educational purposes only**. Nothing herein constitutes financial advice, investment advice, an offer to trade, or a solicitation of capital. Trading prediction markets involves material risk, including the potential loss of all deployed capital. Past or observed performance does not guarantee future results. Any use of this system is undertaken at the sole discretion and risk of the user. No representations or warranties, express or implied, are made regarding accuracy, completeness, or profitability.#### **A.9 Parameter Regime Segmentation and Post-Tuning Performance**

Observed performance metrics reflect two distinct and intentionally segmented parameter regimes. Aggregate statistics are reported for completeness but **must not be interpreted without accounting for regime changes**.

##### **Appendix A.9 — Live Execution Metrics and Regime Analysis
###A.9.1 Scope and Measurement Caveats

The metrics presented in this appendix reflect live executions conducted under real market conditions. The sample remains early-stage and statistically immature. Accordingly:

Results must not be annualized

No ROI, CAGR, or forward projections are calculated or implied

Metrics are reported strictly as observed historical outcomes

These controls are intentional and aligned with best practices in early-phase trading system validation.

###A.9.2 Metrics Methodology

Each 5-minute market window is classified into one of three mutually exclusive outcome categories:

Win: One side is exited early at a favorable price and the remaining side resolves to $1.00

Loss: A stop-loss or adverse price movement results in a net negative outcome

Breakeven: No directional conviction is expressed; both sides are held to resolution

Decisive trades are defined as windows resulting in either a Win or Loss. Breakeven outcomes are explicitly excluded from win-rate calculations to avoid inflating performance statistics.

###A.9.3 Parameter Regime Segmentation

Performance is segmented into distinct parameter regimes to prevent regime-mixing bias.

Regime 1 — Baseline Configuration
Parameter	Value
Sell Window	150–120 seconds remaining
Minimum Winner Bid	$0.63
Split Size	$20 ($10 / side)

Observed Results:

Wins: 2

Losses: 2

Breakeven: 0

Decisive Win Rate: 50%

This configuration exhibited insufficient directional separation and higher exposure to late-window reversals, motivating parameter tightening.

Regime 2 — Tightened Configuration (Current)
Parameter	Value
Sell Window	90–60 seconds remaining
Minimum Winner Bid	$0.67
Split Size	$20 ($10 / side)
Stop-Loss (Winner)	$0.45
Take-Profit	$0.90
Max Position	$20
Daily Stop-Loss	$30

Observed Results:

Wins: 6

Losses: 0

Breakeven: 1

Decisive Win Rate: 100% (6 / 6)

Winning Windows (UTC):
8:00 PM · 8:15 PM · 8:25 PM · 8:30 PM · 8:35 PM · 9:00 PM

The single breakeven window (8:10 PM) occurred when neither side met the $0.67 minimum winner bid threshold. The system correctly withheld directional exposure, holding both sides to resolution. This outcome is treated as a validation of threshold logic, not a missed opportunity.

###A.9.4 Regime Comparison Summary (Chart-Ready)
Metric	Regime 1 (Baseline)	Regime 2 (Tightened)
Trades	4	7
Wins	2	6
Losses	2	0
Breakevens	0	1
Decisive Trades	4	6
Decisive Win Rate	50%	100%
Minimum Winner Bid	$0.63	$0.67
Sell Window	150–120s	90–60s
Loss Containment	None	$0.45 stop-loss

###A.9.5 Aggregate Metrics Contextualization

The aggregate decisive win rate of 73% reflects a blended sample across both regimes and intentionally includes early losses incurred under looser parameters. This figure is provided for historical completeness only and does not represent current system behavior.

Post-tightening performance must be evaluated independently.

###A.9.6 Interpretation Guidance

Regime-specific results must not be combined for inference

Absence of losses in Regime 2 does not imply robustness or persistence

No conclusions should be drawn prior to materially larger samples

Scaling decisions are deferred until ≥30 trades under a fixed regime

This segmentation is maintained to ensure analytical integrity and prevent overstatement of system efficacy.

##### Validation Status Summary (As of [DATE])

**System:** Hawk Split Bot (CTF-based intraday arbitrage)  
**Market:** Polymarket 5-minute BTC Up/Down windows  
**Mode:** Live execution (capital constrained, risk-capped)

### Current Validation State
The system is in **early live validation**. Metrics reflect real executions but remain **statistically immature** and are presented for **behavioral verification**, not performance extrapolation.

### Active Trading Regime
- **Sell Window:** 90–60 seconds before resolution  
- **Minimum Winner Bid:** $0.67  
- **Split Size:** $20 per window ($10 per side)  
- **Winner Stop-Loss:** $0.45  
- **Take-Profit Threshold:** $0.90  
- **Daily Stop-Loss:** $30  

### Observed Performance (Regime-Specific)
- **Trades (Regime 2):** 7  
- **Wins:** 6  
- **Losses:** 0  
- **Breakevens:** 1  
- **Decisive Win Rate:** 100% (6 / 6)  

The single breakeven trade occurred when directional conviction failed to meet the minimum winner bid threshold. The system correctly withheld exposure, validating threshold logic rather than missing opportunity.

### Interpretation Constraints
- Results **must not** be annualized  
- Results **must not** be projected or scaled  
- Regime results **must not** be blended  
- No conclusions are drawn prior to ≥30 trades under fixed parameters  

**Status:** *Validated for behavior and control logic only. Not yet validated for scale.*## Validation Status Summary (As of [DATE])

**System:** Hawk Split Bot (CTF-based intraday arbitrage)  
**Market:** Polymarket 5-minute BTC Up/Down windows  
**Mode:** Live execution (capital constrained, risk-capped)

### Current Validation State
The system is in **early live validation**. Metrics reflect real executions but remain **statistically immature** and are presented for **behavioral verification**, not performance extrapolation.

### Active Trading Regime
- **Sell Window:** 90–60 seconds before resolution  
- **Minimum Winner Bid:** $0.67  
- **Split Size:** $20 per window ($10 per side)  
- **Winner Stop-Loss:** $0.45  
- **Take-Profit Threshold:** $0.90  
- **Daily Stop-Loss:** $30  

### Observed Performance (Regime-Specific)
- **Trades (Regime 2):** 7  
- **Wins:** 6  
- **Losses:** 0  
- **Breakevens:** 1  
- **Decisive Win Rate:** 100% (6 / 6)  

The single breakeven trade occurred when directional conviction failed to meet the minimum winner bid threshold. The system correctly withheld exposure, validating threshold logic rather than missing opportunity.

### Interpretation Constraints
- Results **must not** be annualized  
- Results **must not** be projected or scaled  
- Regime results **must not** be blended  
- No conclusions are drawn prior to ≥30 trades under fixed parameters  

**Status:** *Validated for behavior and control logic only. Not yet validated for scale.*## Pre-Scale Readiness Checklist

Scaling split size is prohibited until **all** criteria below are satisfied under a **single, unchanged regime**.

### Data Sufficiency
- ☐ ≥30 completed trades under identical parameters  
- ☐ ≥20 decisive trades  
- ☐ ≥3 independent trading sessions (time-separated)  

### Performance Stability
- ☐ Decisive win rate ≥60%  
- ☐ No more than 1 consecutive loss  
- ☐ No loss exceeding predefined stop-loss  

### Risk Controls
- ☐ Daily stop-loss never breached  
- ☐ All exits categorized and logged  
- ☐ No manual intervention required  

### Regime Integrity
- ☐ No parameter changes during evaluation window  
- ☐ Regime ID consistent across all logged trades  
- ☐ Breakevens explainable by threshold logic  

### Infrastructure Readiness
- ☐ Automatic CSV logging enabled  
- ☐ Regime metadata written per trade  
- ☐ Replayable audit trail exists  

### Decision Rule
Only after **all boxes are checked** may split size be increased, and only by **one increment** (e.g., $20 → $30). Any failure resets the evaluation window.

**Scaling without checklist completion invalidates all subsequent metrics.**A.9.7 Legal & Risk Disclosure

This system is experimental. All results are historical, unaudited, and subject to execution risk, market microstructure effects, and platform-specific behavior. Nothing in this repository constitutes financial advice, an offer to trade, or a solicitation of capital. Use of this software is at the user’s sole risk.

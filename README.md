# Hawk Split Bot — Automated CTF Arbitrage Trader

Automated arbitrage trading bot for Polymarket 5-minute BTC Up/Down prediction markets. Uses Conditional Token Framework (CTF) splits to enter both sides at $1.00 per pair and extract profit via timed order execution.

**Status:** Early live validation (capital constrained, risk-capped)  
**Mode:** Live execution  
**Paper mode:** Complete

---

## How It Works

1. **Split** — The bot purchases both Yes and No positions via CTF split at exactly $1.00 combined cost ($10 per side).
2. **Monitor** — During the 5-minute market window, the bot monitors both sides for directional conviction.
3. **Exit** — If one side meets the minimum winner bid threshold within the sell window, the bot exits that side early at a profit. The remaining side resolves to $1.00 at settlement.
4. **Hold** — If neither side meets the threshold, both positions are held to resolution (breakeven).

---

## Risk Controls

| Parameter | Value |
|---|---|
| Max position size | $20 per window ($10 Up / $10 Down) |
| Daily stop-loss | −$30 hard cap (auto-halt on breach) |
| Per-trade downside | Capped by split structure + stop-loss |
| Winner stop-loss | $0.45 |
| Take-profit threshold | $0.90 |
| Capital priority | Preservation over frequency |

No dynamic position sizing, martingale logic, or exposure scaling is used during validation.

---

## Active Trading Regime (Regime 2 — Current)

| Parameter | Value |
|---|---|
| Sell window | 90–60 seconds before resolution |
| Minimum winner bid | $0.67 |
| Split size | $20 per window ($10 / side) |
| Winner stop-loss | $0.45 |
| Take-profit | $0.90 |
| Daily stop-loss | −$30 |

---

## Observed Performance

> **Early sample — not statistically mature.** Do not annualize, project ROI, or extrapolate beyond the observed window.

### Regime 2 (Tightened — Current)

| Metric | Value |
|---|---|
| Trades | 7 |
| Wins | 6 |
| Losses | 0 |
| Breakevens | 1 |
| Decisive win rate | 100% (6/6) |

Winning windows (UTC): 8:00 PM · 8:15 PM · 8:25 PM · 8:30 PM · 8:35 PM · 9:00 PM

The single breakeven (8:10 PM) occurred when neither side met the $0.67 threshold. The system correctly withheld directional exposure — this validates threshold logic, not a missed opportunity.

### Regime 1 (Baseline — Deprecated)

| Metric | Value |
|---|---|
| Trades | 4 |
| Wins | 2 |
| Losses | 2 |
| Breakevens | 0 |
| Decisive win rate | 50% (2/4) |

Regime 1 used a wider sell window (150–120s) and lower minimum winner bid ($0.63), resulting in higher exposure to late-window reversals. These losses motivated the parameter tightening in Regime 2.

### Aggregate (Both Regimes)

| Metric | Value |
|---|---|
| Total trades | 11 (decisive) |
| Aggregate decisive win rate | 73% (8/11) |
| Net PnL | +$2.03 (manually reconciled) |
| Best streak | 6 consecutive wins post-tightening |

> The 73% aggregate rate blends both regimes and includes early losses under looser parameters. It does not represent current system behavior. Post-tightening performance must be evaluated independently.

---

## Outcome Definitions

- **Win** — One side exits early at a favorable price; the remaining side resolves to $1.00.
- **Loss** — Stop-loss triggered or adverse price movement results in net negative outcome.
- **Breakeven** — No directional conviction expressed; both sides held to resolution.
- **Decisive trade** — Any trade resulting in a Win or Loss. Breakevens are excluded from win-rate calculations.

---

## Parameter Change Log

| Date (UTC) | Parameter | Previous | Updated | Rationale |
|---|---|---|---|---|
| TBD | Sell window | 150–120s | 90–60s | Reduced late-window volatility exposure |
| TBD | Min winner bid | $0.63 | $0.67 | Increased directional confidence threshold |
| TBD | Position size | $15 | $20 | Controlled exposure increase post-stability |
| TBD | Daily stop-loss | −$40 | −$30 | Tighter drawdown containment |
| TBD | Take-profit | $0.85 | $0.90 | Avoid premature winner liquidation |

All parameter changes are applied prospectively and evaluated over subsequent windows before further modification.

---

## Pre-Scale Readiness Checklist

Scaling is prohibited until **all** criteria are satisfied under a single unchanged regime.

**Data Sufficiency**
- [ ] ≥30 completed trades under identical parameters
- [ ] ≥20 decisive trades
- [ ] ≥3 independent trading sessions (time-separated)

**Performance Stability**
- [ ] Decisive win rate ≥60%
- [ ] No more than 1 consecutive loss
- [ ] No loss exceeding predefined stop-loss

**Risk Controls**
- [ ] Daily stop-loss never breached
- [ ] All exits categorized and logged
- [ ] No manual intervention required

**Regime Integrity**
- [ ] No parameter changes during evaluation window
- [ ] Regime ID consistent across all logged trades
- [ ] Breakevens explainable by threshold logic

**Infrastructure**
- [ ] Automatic CSV logging enabled
- [ ] Regime metadata written per trade
- [ ] Replayable audit trail exists

> Only after all boxes are checked may split size increase by one increment (e.g., $20 → $30). Any failure resets the evaluation window. **Scaling without checklist completion invalidates all subsequent metrics.**

---

## Quick Start

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python src/hawk_split_bot.py
```

---

## Disclaimer

This system is experimental. All results are historical, unaudited, and subject to execution risk, market microstructure effects, and platform-specific behavior. Nothing in this repository constitutes financial advice, investment advice, an offer to trade, or a solicitation of capital. Trading prediction markets involves material risk, including the potential loss of all deployed capital. Past performance does not guarantee future results. Use at your own risk.

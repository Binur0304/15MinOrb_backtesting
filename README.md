# 15MinOrb_backtesting
# 15-Minute New York Opening Range Breakout (ORB) Strategy

This repository contains a Pine Script v6 trading strategy that executes volume-confirmed breakout trades based on the **first 15-minute range after the New York market open (09:30–09:45 EST)**.  
The strategy marks the opening range, waits for a breakout above or below with volume confirmation, and automatically places entries, stop-losses, and take-profits using a configurable Risk/Reward (RR) ratio.

---

Features
- Marks the **opening range box** and plots breakout levels.
- Trades only after **volume-confirmed** breakouts.
- Uses **opposite side of the range as stop-loss**.
- Configurable **take-profit based on RR multiple**.
- Option to **limit to one trade per day**.
- Fully parameterized and backtest-ready in TradingView.

---

Strategy Logic Overview
1. Capture the **09:30–09:45** New York session range.  
2. Once the window closes:
   - If price breaks above the high with strong volume → **Buy**
   - If price breaks below the low with strong volume → **Sell**
3. **Stop-loss** = opposite side of the range  
   **Take-profit** = `entry ± (RR × range size)`

---

Inputs
| Parameter | Description | Default |
|------------|--------------|----------|
| Opening Window | Session window for ORB | 09:30–09:45 |
| One Trade per Day | Limit trades to one per NY session | true |
| Risk/Reward (RR) | Take-profit ratio | 2.0 |
| Volume MA Length | SMA period for volume filter | 20 |
| Volume Multiplier | Required multiple over SMA | 1.0 |
| Show Box & Lines | Visualize ORB range and breakouts | true |

---

How to Use
1. Open **TradingView** and navigate to the **Pine Editor**.  
2. Copy the contents of `ny_orb_strategy.pine` into a new script.  
3. Click **“Add to Chart”** → the strategy will automatically plot the opening range and execute simulated trades.  
4. Use the **Strategy Tester** panel to view backtest metrics.

---


## 👤 Author
**Rohan [Your Last Name]**  
Data Science @ Colorado State University  
📧 [rohanbinu23@gmail.com]  
📊 Passionate about data-driven trading and market automation.

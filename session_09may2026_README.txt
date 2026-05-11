 Live Session Report — 09 May 2026
 HMM Regime-Adaptive Market Making System
Asset: HDFCBANK.NS (NSE India)  
System: Avellaneda-Stoikov + 3-State Gaussian HMM + Transaction Costs

 Session Results

| Metric | Value |
|--------|-------|
| Date | 09 May 2026 |
| Session | 10:13 AM – 3:30 PM IST |
| Total Trades | 600 |
| Gross P&L | Rs.+165.22 |
| Transaction Costs | Rs.73.66 |
| Net P&L | Rs.+91.57 |
| Final Inventory | 0 shares |
| Cost per trade | Rs.0.12 average |



 What Happened

10:13 – 10:28 AM — Warmup  
HMM collected 30 price points before activating.
Model started trading at 10:28 AM.

10:28 AM – 2:38 PM — Uptrend Phase  
HDFCBANK drifted from Rs.768 to Rs.772.
Model built long inventory up to +10, capturing
spread on both sides throughout. P&L reached Rs.+37.

3:02 PM — Crisis Regime Detected  
HDFCBANK dropped sharply. HMM correctly switched
to Crisis regime. Spread widened from Rs.0.40 to
Rs.2.77 for one tick, protecting against adverse
selection during the spike.

2:38 – 3:25 PM — Selloff Phase  
Price dropped from Rs.771 to Rs.762. Model flipped
short and captured the downmove. Gross P&L surged
from Rs.+35 to Rs.+165 in under one hour.

3:25 PM — Auto Close-Out  
System automatically flattened 8 short shares.
Final inventory = 0. Session closed perfectly flat.



 HMM Regime Parameters

| Regime | Condition | gamma | kappa | Spread |
|--------|-----------|-------|-------|--------|
| 0 | Low Vol / Mean Reverting | 0.1 | 5.0 | Rs.0.40 |
| 1 | High Vol / Trending | 0.2 | 2.0 | Rs.1.20 |
| 2 | Crisis / Extreme | 0.5 | 0.5 | Rs.2.77 |



 Comparison vs Base A-S Session (08 May 2026)

| Metric | Base A-S | HMM Regime |
|--------|----------|------------|
| Date | 08 May 2026 | 09 May 2026 |
| Trades | 321 | 600 |
| Net P&L | Rs.+31.29 | Rs.+91.57 |
| Transaction costs | Not modelled | Rs.73.66 |
| Final inventory | -7 shares | 0 shares |
| Close-out | Manual | Automatic 3:25 PM |
| Regime detection | None | 3-state HMM |



 Files in This Repo

| File | Description |
|------|-------------|
| as_model.py | Base A-S live trader |
| as_hmm_regime.py | HMM regime adaptive system |
| as_real_hdfcbank.png | Base A-S backtest chart |
| as_hmm_hdfcbank.png | HMM backtest chart with regime colours |
| session_09may2026.txt | Full live session output — 514 ticks |



 Author
Chintamani | IIQF CPAIF Program 2024-25  
github.com/Negotiator-10 
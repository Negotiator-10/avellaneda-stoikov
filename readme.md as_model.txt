 Avellaneda-Stoikov Live Market Making System
**Asset:** HDFCBANK.NS (NSE India)  
**Stack:** Python, yfinance, NumPy, Matplotlib

 Live Session Results (08 May 2026)
| Metric | Value |
|--------|-------|
| Session | 11:52 AM – 2:01 PM IST |
| Total Trades | 321 |
| Final P&L | ₹+31.29 |
| Peak P&L | ₹+32.07 |
| Spread (δ) | ₹0.199 per trade |
| Volatility range | 0.00008 – 0.00048 |
| Inventory at close | -7 shares |

What This Is
A live paper-trading implementation of the Avellaneda-Stoikov (2008) 
market-making model on Indian equity data. Posts optimal bid/ask quotes 
adjusted for inventory risk and rolling volatility in real time using 
NSE 1-minute OHLCV data.

 Core Formulas
r = S - q * gamma * sigma^2 * (T - t)        [reservation price]
delta = gammasigma^2(T-t) + (2/gamma)*ln(1 + gamma/kappa)  [optimal spread]
 Key Features
- Real time bid/ask quoting on NSE live data
- Rolling 30-bar volatility (sigma) updated every 30 seconds
- Inventory risk adjustment via reservation price
- Fill simulation against closed 1-minute candles (iloc[-2])
- Market hours check (9:15 AM – 3:30 PM IST)
- Inventory limits ±10 to prevent directional blowup

 Known Limitation
Inventory accumulated to -7 at session close due to 
HDFCBANK trending downward. A-S is designed for mean-reverting 
markets. Next iteration adds a trend filter and hard close-out 
at 3:25 PM, following Guéant-Lehalle-Fernandez-Tapia (2013).


 Files
- `as_model.py` — Full model, backtest and live trader

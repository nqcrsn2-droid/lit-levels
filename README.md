# LIT Levels NQ (private)

Personal LIT (Liquidity Inducement Theorem) levels for NQ futures: London and New York limit levels from 8-minute order blocks, backtested on 6 years of 1-minute NQ.

**Open the app (phone or PC):** https://claude.ai/artifact/LpuPNMkRPcKxH67ZCCpgrE

## What's here
- `index.html` - the app (Execution / Analysis / Review / Look tabs)
- `data/stats.json` - backtest stats every level's odds come from
- `engine/lit.py` - the LIT rules (8m OB = candle that takes an unprotected swing, body to wick; entry at the CE once it has reacted; stop under the OB, 10-15 pts; target the next liquidity 50-100 pts away; breakers; sweep / OTE / taps tags; move-to-break-even management)
- `engine/build.py` - builds today's levels from live Yahoo NQ=F bars + the bias app's session call (rebuilt 12:25, 7:25 and 8:25 AM CT on weekdays)
- `engine/bt.py`, `engine/make_stats.py` - the backtest and the stats

## Backtest (2020-01 to 2026-02, 1-minute NQ)
- About 6,150 filled limit orders.
- Targets are 5-10R, so about 14% wins breaks even.
- NY levels with the London sweep (AMD) made money in both halves of the data (about +0.2R a trade). Levels against it lost in both.
- With the stop moved to break-even at 1R, about 50% of trades don't lose; the best robust groups reach about 55-60%.

## Next
- Transcribe the remaining LIT videos and recode the rules from them.
- Real LIT structure: inducement, IDM OB, extreme OB, FVG before the OB, inside bars ignored.
- Refine 8m OBs to a 1-minute entry so stops sit behind real structure at today's volatility.

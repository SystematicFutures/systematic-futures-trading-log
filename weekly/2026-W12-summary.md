# Weekly Summary — 2026-W12 (2026-03-16 — 2026-03-22)

## TL;DR
- 1h: 🟢 running; observed maxDD up to ~1.9% (per paper-forward ticks); no open positions at snapshot time.
- 4h: 🟡 intermittent API reliability issues (Bitget: Bad Gateway / Too Many Requests); paper-forward 4h processes running but experienced restarts.
- Reliability: ongoing API/DNS noise on 4h and a dry-run router startup/module error observed and partially mitigated.

## What ran
- Paper-forward pipelines: 1h multi-symbol PaperForwardMulti (ETH,SOL,XRP,DOGE,BTC,BNB,ADA,LINK,AVAX) running throughout the week.
- Paper-forward 4h for XRP/LINK ran but showed intermittent API errors.
- AutoBT runs completed (autoBT summaries written to research/bestSpecs*.json + summaries).
- DryRunRouter and paper-forward state saved regularly (state files updated in logs/).

## What broke / what we fixed
- 4h endpoints experienced Bitget API errors (Bad Gateway / 429 Too Many Requests) causing auto-restarts on ~2026-03-16 and thereafter. Cause appears to be exchange/API instability; mitigations: monitoring tightened, consider throttling/backoff.
- Dry-run router had connectivity / startup errors earlier in the week (getaddrinfo EAI_AGAIN) and a module-not-found at dryRunRouter.js on 2026-03-14; service restarted and state restored (logs show DryRunRouter state restored and starting on 2026-03-22).
- No critical trade execution failures recorded (this is paper-forward / dry-run environment: WOULD_* logs, not real orders).

## Risk snapshot
- MaxDD observed (paper-forward ticks): 1h strategies showed maxDD up to ~1.9% (2026-03-22 ticks), many symbols reporting maxDD in the 0–1.9% range.
- Open paper positions: 0 at snapshot times in logs (multiple EX_STATE entries show positions:0, openOrders:0).

## Next week
- Implement/verify throttling and exponential backoff for 4h API calls; confirm error count decreases on next 4h ticks.
- Verify presence and import path of src/dryRunRouter.js (fix module-not-found) and add a network/DNS retry wrapper around DryRunRouter startup.
- Continue monitoring AutoBT outputs and validate that produced research/bestSpecs*.json are reasonable before promoting.

Not financial advice.

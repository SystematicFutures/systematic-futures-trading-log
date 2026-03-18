# Systematic Futures Trading Log

A public log of a systematic crypto futures trading experiment (walk-forward, forward/paper, execution reliability).

Maintained by **Logkeeper**.

## What this is

This project documents the *engineering* and *research* work behind a rules-based trading pipeline:

- Walk-forward validation (to reduce overfitting)
- Forward / paper monitoring on live market data
- Execution & reliability work (API noise, rate limits, candle integrity, process health)

The goal is to be transparent about what works, what breaks, and what changes over time.

## What this is NOT

- Not a signal service
- No “guaranteed returns”
- No financial advice

## Public daily log (Telegram)

Daily updates are posted here:

- https://t.me/ClawBotsystem

## Reporting format

### Daily (Telegram)
A short 6-line update at a fixed time (Vienna):

- Context
- 1h status (🟢/🟡/🔴) + maxDD + open paper positions
- 4h status (🟢/🟡/🔴) + maxDD + open paper positions
- Plain-English “So what”
- Next step

### Weekly (GitHub)
Weekly summary posts live in `/weekly/`:

- What ran
- What broke
- What changed
- Risk snapshot (drawdown)
- Next experiments

## Current status

- Stage: **forward/paper** (no real orders)
- Live trading only after explicit gates (e.g., sufficient trade count, acceptable drawdown, stable execution)

## Disclaimer

Trading involves risk. This repository is for research and engineering notes only.

Not financial advice.

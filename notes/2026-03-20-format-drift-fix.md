# Format Drift: the boring failure mode that breaks trust (and how we fixed it)

If you run bots that post updates (Telegram/Discord/GitHub), you’ll recognize this:

You agree on a “human-friendly” style… and a few days later the bot slowly slides back into log dumps.
Nothing *mystical* happened — it’s usually a **spec enforcement problem**.

## The problem: “format drift”
- The plan exists in chat, but the automation job isn’t bound to a single, testable contract.
- The model can comply *most of the time* and still regress.
- Delivery misconfigurations (wrong timezone, delivery=none) can make jobs “run” but not reach you.

## The fix we implemented
1) **Single source of truth**: a spec file the automation must read
   - `DAILY_SPEC.md` (voice + strict 8-line format + guardrails)
2) **Hard validation gate**
   - line count
   - required prefixes
   - no blank lines
   - if the output fails, it rewrites until it passes
3) **Operational hygiene**
   - clear delivery targets
   - correct timezone
   - monitoring that avoids old-log spam (recency filter + offsets)

## Why this matters
Consistency builds trust.
If a bot can’t reliably follow a posting contract, you can’t scale to multiple channels.

_Not financial advice._

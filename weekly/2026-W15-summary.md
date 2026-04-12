WEEKLY SUMMARY — 2026-W15 (2026-04-05 → 2026-04-11)

Repository: systematic-futures-trading-log
Source logs consulted: /home/ubuntu/.openclaw/workspace/jerry2-bot/logs/
Generated: 2026-04-12 06:00 UTC

1) SUMMARY
- Activity in the last 7 days focused on scheduled backtest/universe runs (1h and 4h), and continued paper-forward (paper trading) processes. Key log files with timestamps between 2026-04-09 and 2026-04-12 indicate routine runs and state updates.

2) OPERATIONAL HIGHLIGHTS
- Cron backtests: multiple cron backtest-universe runs for 4h and 1h were executed on 2026-04-09, 2026-04-10 and 2026-04-11. Files present:
  - cron-e88eb1ea-backtest-universe-4h logs for 2026-04-09, 2026-04-10 (manual) and 2026-04-11 (manual).
  - cron-ef414c7c-backtest-universe-1h logs for 2026-04-09, 2026-04-10 (manual) and earlier entries.
- Paper-forward (paper trading) instances active and producing logs and state files (timestamps up to 2026-04-12 04:00–06:00 UTC):
  - paper-forward-1h-universeHF.log and its .pid present (last modified 2026-04-12 05:03 / 05:59 respectively).
  - paper-forward-4h-donchianCore.log, paper-forward-4h-phase.log, paper-forward-4h-xrplink.log all have recent timestamps and corresponding .pid files indicating running processes (2026-04-12 04:00–06:00 UTC).
  - paper-forward-state JSON files updated at 2026-04-12 04:00 for multiple strategies (1h-universeHF, 4h-donchianCore, 4h-phase, 4h-xrplink).
- Router and keepalive: dry-run-router.log and related keepalive state files show continuous operation; dry-run-router.log is large and recently appended (up to 2026-04-12 05:59 UTC). dry-run-keepalive-state.json and dry-run-keepalive-status.json updated in early April.
- Watchdog / fw_watchdog.log updated at 2026-04-12 06:00 UTC indicating system monitoring activity.

3) BACKTESTS
- Backtests run on the 4h universe around 2026-04-09–2026-04-11 (see cron-e88eb1ea files). The cron logs include both automated and manual runs (some files labelled .manual.log).
- Other historical backtest artifacts exist (march logs) but no new single-run backtest files within this 7-day window beyond the cron logs noted above.

4) ISSUES / ALERTS
- dry-run-keepalive had previous failures tracked (several small state files), but current keepalive state files (2026-04-10 → 2026-04-12) exist and suggest recent recovery / continued operation. No explicit crash or fatal error surfaced when scanning file presence/timestamps.
- No explicit exceptions or stack traces were parsed; this summary is based on log presence and timestamps, not full log-content parsing.

5) FILES UPDATED (select)
- jerry2-bot/logs/
  - cron-e88eb1ea-backtest-universe-4h-20260409T091638Z-march56.log (2026-04-09)
  - cron-e88eb1ea-backtest-universe-4h-20260410T091821Z-march56.manual.log (2026-04-10)
  - cron-e88eb1ea-backtest-universe-4h-20260411T091524Z-march56.manual.log (2026-04-11)
  - cron-ef414c7c-backtest-universe-1h-20260409T091934Z-march56.log (2026-04-09)
  - cron-ef414c7c-backtest-universe-1h-20260410T092229Z-march56.manual.log (2026-04-10)
  - universe-1h-20260411-092111.log (2026-04-11)
  - paper-forward-state-1h-universeHF.json (2026-04-12 05:03)
  - paper-forward-state-4h-*.json (2026-04-12 04:00)
  - dry-run-router.log (appended through 2026-04-12 05:59)
  - fw_watchdog.log (2026-04-12 06:00)

6) RECOMMENDATIONS / NEXT STEPS
- If needed, run targeted log parsing for any of the recent cron logs (cron-e88eb1ea and cron-ef414c7c) to extract metrics (universe size, failures, backtest PnL) — this summary only notes run activity and timestamps.
- Monitor dry-run-router.log size and rotate if it grows continuously (current size ~2.8GB as of 2026-04-12 05:59 UTC).
- Verify paper-forward-state JSONs after the next cycle to confirm state persistence and that no unexpected resets occur.

7) NOTES
- This weekly summary is generated from file presence, filenames, and timestamps in the repository daily/ directory and the jerry2-bot logs directory. No deep content parsing (searching for specific error strings or quantitative results) was performed.

Not financial advice

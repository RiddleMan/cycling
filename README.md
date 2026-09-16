# Cycling

Personal repo for tracking and developing Artur's cycling training goals using Strava data. Claude Code (via the `strava` MCP server) analyzes activities, HR/power trends, and training load here to support the plan below. See `CLAUDE.md` for the athlete profile, data caveats, and how Claude should help in this repo.

# Training Plan — VO2max Build

Proposed 2026-09-04, based on analysis of recent Strava activity. Goal: increase VO2max (stated athlete focus), building on an already-consistent aerobic base.

**Current FTP: 195W** (confirmed 2026-09-16). See `ftp-history.md` for the full history of test results and corrections.

## 1. VO2max sessions (1–2×/week) — target 207–234W
Current training is all Z1/Z2 commuting — good volume, but no VO2max-intensity stimulus.
- 4–6 × 4min @ **207–234W** (106–120% of 195W FTP), 3–4min easy-spin recovery between reps
- Suggested slots: 2×/week on non-consecutive days (e.g. Tue/Fri), fit around existing commute schedule
- Keep daily commutes as pure endurance — don't convert them to intervals too (adds fatigue without the targeted stimulus)
- **Session 1 done 2026-09-10** ("Zwift - VO2max 5x4"): 5×4min @ ~146W avg, ~4min @~75W recovery. HR during work bouts stayed Z2 (125–130 avg, 136 max) — never reached Z3+, an early sign the FTP used at the time was too low. Re-target future sessions to the current 207–234W range.

## 2. Keep outdoor rides as recovery/base
- Continue near-daily ~30km commutes as low-intensity volume
- Pace/judge these by HR, not power — outdoor rides report Strava's estimated power (`has_device_watts: false`), not measured, so it's not reliable for zone compliance

## 3. Retest and check in — target week of 2026-10-04
- After ~4 weeks of VO2max work (roughly 6-8 sessions) at the current 195W FTP, retest the same way (Zwift FTP Test [Standard], ERG mode, with a measured warm-up — no hard spikes beforehand)
- Compare 5-min/8-min best-power trends across real-power (trainer/Zwift) activities over that period to check whether the intervals are working before the retest confirms it
- Avoid judging fitness off any single ride

## Status
- [x] FTP confirmed — 195W (2026-09-16, see `ftp-history.md`)
- [x] VO2max intervals started — session 1 done 2026-09-10 (5×4min @ ~146W)
- [ ] Confirm Zwift/Strava platform FTP setting reflects 195W
- [ ] 4-week retest — target week of 2026-10-04

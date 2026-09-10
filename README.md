# Cycling

Personal repo for tracking and developing Artur's cycling training goals using Strava data. Claude Code (via the `strava` MCP server) analyzes activities, HR/power trends, and training load here to support the plan below. See `CLAUDE.md` for the athlete profile, data caveats, and how Claude should help in this repo.

# Training Plan — VO2max Build

Proposed 2026-09-04, based on analysis of recent Strava activity. Goal: increase VO2max (stated athlete focus), building on an already-consistent aerobic base.

## 1. FTP baseline — DONE
Retested 2026-09-06 (Zwift FTP Test [Standard]): **122W**. HR profile (174.8 avg / 186 max) confirms a genuine maximal effort; ERG mode means the hilly route didn't affect the result. Note this makes commute rides' Strava-estimated power (135–166W) read as above threshold despite an easy HR — confirms outdoor estimated power is inflated and stays unusable for zone work (see caveat below).

## 2. VO2max sessions (1–2×/week) — target 129–146W
Current training is all Z1/Z2 commuting — good volume, but no VO2max-intensity stimulus.
- 4–6 × 4min @ **129–146W** (106–120% of 122W FTP), 3–4min easy-spin recovery between reps
- Suggested slots: 2×/week on non-consecutive days (e.g. Tue/Fri), fit around existing commute schedule
- Keep daily commutes as pure endurance — don't convert them to intervals too (adds fatigue without the targeted stimulus)
- **Session 1 done 2026-09-10** ("Zwift - VO2max 5x4"): 5×4min @ ~146W avg (120%FTP), ~4min @~75W recovery. HR during work bouts stayed Z2 (125–130 avg, 136 max) — never reached Z3+, suggesting 122W FTP was undershooting true threshold.

## 2a. FTP auto-update — needs confirmation
Right after session 1, an unstructured "ZG25 Climb Champs" KOM-chase ride (same day, on fatigued legs) produced 156.6W avg / 159W best-20min, and Zwift auto-raised FTP to **152W**. HR stayed low here too (135 avg / 163 max, still Z2–low Z3), which is consistent with 122W having been an underestimate — but a +25% jump in 4 days from an unstructured, post-fatigue ride isn't a clean read.
- **Action before trusting 152W for zone work**: do one dedicated fresh-legs FTP test (Zwift FTP Test [Standard], ERG mode) to confirm. Until then, treat 152W as provisional.

## 3. Keep outdoor rides as recovery/base
- Continue near-daily ~30km commutes as low-intensity volume
- Pace/judge these by HR, not power — outdoor rides report Strava's estimated power (`has_device_watts: false`), not measured, so it's not reliable for zone compliance

## 4. Retest and check in — target week of 2026-10-04
- After ~4 weeks of VO2max work (roughly 6-8 sessions), retest FTP the same way (Zwift FTP Test [Standard], ERG mode)
- Compare 5-min/8-min best-power trends across real-power (trainer/Zwift) activities over that period to check whether the intervals are working before the retest confirms it
- Avoid judging fitness off any single ride

## Status
- [x] FTP baseline confirmed — 122W (2026-09-06)
- [x] VO2max intervals started — session 1 done 2026-09-10 (5×4min @ ~146W)
- [ ] FTP retest to confirm Zwift's auto-bump to 152W (2026-09-10, provisional — from unstructured post-fatigue ride)
- [ ] 4-week retest — target week of 2026-10-04

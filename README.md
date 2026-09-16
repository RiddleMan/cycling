# Cycling

Personal repo for tracking and developing Artur's cycling training goals using Strava data. Claude Code (via the `strava` MCP server) analyzes activities, HR/power trends, and training load here to support the plan below. See `CLAUDE.md` for the athlete profile, data caveats, and how Claude should help in this repo.

# Training Plan — VO2max Build

Proposed 2026-09-04, based on analysis of recent Strava activity. Goal: increase VO2max (stated athlete focus), building on an already-consistent aerobic base.

## 1. FTP baseline — SUPERSEDED
Retested 2026-09-06 (Zwift FTP Test [Standard]): **122W**. HR profile (174.8 avg / 186 max) confirmed a maximal effort, but the pre-test warm-up included hard spikes (253W/214W laps, ~280W recalled) that pre-fatigued the legs — this suppressed the 20-min result. Superseded by the clean retest in 1a below.

## 1a. FTP corrected baseline — DONE
Retested 2026-09-16 (Zwift FTP Test [Standard]), with a properly measured warm-up (peak 181W, easier pre-test recovery block) instead of the overly hard one on 2026-09-06. 20-min best power: **206W** → FTP **195W** (95%). HR profile (173.2 avg / 185 max during the 20-min block) matches the Sep 6 effort almost exactly despite the much higher power output, confirming the earlier 122W was an artifact of pre-fatigue, not a true threshold. This also supersedes the provisional 152W Zwift auto-bump from 2026-09-10 (see 2a).
- **Action**: confirm Zwift/Strava's stored FTP setting reflects 195W — Strava's `get_athlete_zones` still returned `ftp: 122` as of this analysis, so the platform-side value may need a manual update/sync.

## 2. VO2max sessions (1–2×/week) — target 207–234W
Current training is all Z1/Z2 commuting — good volume, but no VO2max-intensity stimulus.
- 4–6 × 4min @ **207–234W** (106–120% of 195W FTP), 3–4min easy-spin recovery between reps
- Suggested slots: 2×/week on non-consecutive days (e.g. Tue/Fri), fit around existing commute schedule
- Keep daily commutes as pure endurance — don't convert them to intervals too (adds fatigue without the targeted stimulus)
- **Session 1 done 2026-09-10** ("Zwift - VO2max 5x4"): 5×4min @ ~146W avg (120% of the then-current 122W FTP), ~4min @~75W recovery. HR during work bouts stayed Z2 (125–130 avg, 136 max) — never reached Z3+, an early sign 122W was undershooting true threshold, now confirmed by 1a. Re-target future sessions to the corrected 207–234W range.

## 2a. FTP auto-update — resolved
Right after session 1, an unstructured "ZG25 Climb Champs" KOM-chase ride (same day, on fatigued legs) produced 156.6W avg / 159W best-20min, and Zwift auto-raised FTP to **152W**, flagged provisional pending a dedicated retest. The 2026-09-16 dedicated retest (1a) came in higher still at 195W, superseding both the 122W and 152W figures.

## 3. Keep outdoor rides as recovery/base
- Continue near-daily ~30km commutes as low-intensity volume
- Pace/judge these by HR, not power — outdoor rides report Strava's estimated power (`has_device_watts: false`), not measured, so it's not reliable for zone compliance

## 4. Retest and check in — target week of 2026-10-04
- After ~4 weeks of VO2max work (roughly 6-8 sessions) at the corrected 195W FTP, retest the same way (Zwift FTP Test [Standard], ERG mode, with a measured warm-up — no hard spikes beforehand)
- Compare 5-min/8-min best-power trends across real-power (trainer/Zwift) activities over that period to check whether the intervals are working before the retest confirms it
- Avoid judging fitness off any single ride

## Status
- [x] FTP baseline attempted — 122W (2026-09-06), later found compromised by a hard warm-up
- [x] VO2max intervals started — session 1 done 2026-09-10 (5×4min @ ~146W, targeted off the since-superseded 122W FTP)
- [x] FTP corrected baseline confirmed — **195W** (2026-09-16), supersedes both 122W and the 152W provisional auto-bump
- [ ] Confirm Zwift/Strava platform FTP setting reflects 195W
- [ ] 4-week retest — target week of 2026-10-04

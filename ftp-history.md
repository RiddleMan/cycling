# FTP History

Chronological log of FTP test results and corrections. Current value and active plan live in `README.md`.

## 2026-09-06 — 122W (invalidated)
Zwift FTP Test [Standard]. 20-min best power 134W → FTP 122W (95%). HR profile (174.8 avg / 186 max) looked like a genuine maximal effort at the time.
- **Later found compromised**: the pre-test warm-up included hard spikes (253W and 214W laps, ~280W recalled by athlete) that pre-fatigued the legs before the 20-min block, suppressing the result. Identified when the 2026-09-16 retest produced near-identical HR/cadence at 54% higher power — physiologically implausible as a real fitness gain, and consistent with a pacing/warm-up error rather than genuine improvement.

## 2026-09-10 — 152W (provisional, superseded)
Zwift auto-raised FTP to 152W off an unstructured "ZG25 Climb Champs" KOM-chase ride (156.6W avg / 159W best 20min), ridden on fatigued legs right after a VO2max session earlier the same day. HR stayed low (135 avg / 163 max, Z2–low Z3) — consistent with 122W being an underestimate, but not a clean read given the unstructured effort and pre-fatigue. Flagged provisional pending a dedicated fresh-legs retest.

## 2026-09-16 — 195W (confirmed, current)
Zwift FTP Test [Standard], with a properly measured warm-up (peak 181W, easier pre-test recovery block) instead of the overly hard one on 2026-09-06. 20-min best power 206W → FTP 195W (95%). HR profile (173.2 avg / 185 max) matches the Sep 6 effort almost exactly despite the much higher power output, confirming the earlier 122W was an artifact of pre-fatigue rather than a true threshold. Supersedes both the 122W and 152W figures.
- **Open item**: Strava's `get_athlete_zones` still returned `ftp: 122` as of this analysis — confirm the platform-side FTP setting gets synced to 195W.

# FTP History

Chronological log of FTP test results and corrections. Current value and active plan live in `README.md`.

Plotted in the [FTP History dashboard](https://claude.ai/artifact/CZbctFC1Mm4r6tMicgarGQ) (tests + VO2max session rep power). Its data is a static copy of this file — update it after each new test.

## 2026-09-06 — 122W (invalidated)
Zwift FTP Test [Standard]. 20-min best power 134W → FTP 122W (95%). HR profile (174.8 avg / 186 max) looked like a genuine maximal effort at the time.
- **Later found compromised**: the pre-test warm-up included hard spikes (253W and 214W laps, ~280W recalled by athlete) that pre-fatigued the legs before the 20-min block, suppressing the result. Identified when the 2026-09-16 retest produced near-identical HR/cadence at 54% higher power — physiologically implausible as a real fitness gain, and consistent with a pacing/warm-up error rather than genuine improvement.

## 2026-09-10 — 152W (provisional, superseded)
Zwift auto-raised FTP to 152W off an unstructured "ZG25 Climb Champs" KOM-chase ride (156.6W avg / 159W best 20min), ridden on fatigued legs right after a VO2max session earlier the same day. HR stayed low (135 avg / 163 max, Z2–low Z3) — consistent with 122W being an underestimate, but not a clean read given the unstructured effort and pre-fatigue. Flagged provisional pending a dedicated fresh-legs retest.

## 2026-09-16 — 195W (confirmed, superseded)
Zwift FTP Test [Standard], with a properly measured warm-up (peak 181W, easier pre-test recovery block) instead of the overly hard one on 2026-09-06. 20-min best power 206W → FTP 195W (95%). HR profile (173.2 avg / 185 max) matches the Sep 6 effort almost exactly despite the much higher power output, confirming the earlier 122W was an artifact of pre-fatigue rather than a true threshold. Supersedes both the 122W and 152W figures.
- Platform sync: Strava's `get_athlete_zones` reported `ftp: 195` by 2026-10-18 (was still 122 right after this test).

## 2026-10-18 — 215W (confirmed, current)
Zwift FTP Test [Standard], ERG mode, after ~4.5 weeks / 7 VO2max 5×4 sessions at 195W. 20-min block avg 226W (best 20min 227W) → FTP 215W (95%), **+20W / +10%**, 2.59 W/kg at 83kg (was 2.29 at 85kg) — +0.24 from power, +0.06 from the 2kg weight drop. Standard Zwift warm-up (ramps to 214W/3min and 236W/2min, ~110–120% of the old FTP), then 6min easy before the block.
- HR in the 20-min block 176 avg / 187 max vs 173 / 185 on 2026-09-16 — same maximal effort, +20W output. Cadence 98 avg.
- Pacing: strong start (~235–240W first minutes), settled ~225W, two short sags mid/late (~195–205W, then ~185W for ~1min each), then 235–245W finish plus a 300–500W final kick — some reserve left, so 215W is if anything slightly conservative.
- Taper: Oct 15 easy spin (HR max 140), Oct 16 Magnificent 8 (avg HR 134, max 159), Oct 17 long walk — no intervals.
- Other bests from the test: 5min 232W, 8min 229W, 10min 227W.
- **Open item**: Strava zones still on 195W as of this analysis — confirm the platform-side FTP updates to 215W.

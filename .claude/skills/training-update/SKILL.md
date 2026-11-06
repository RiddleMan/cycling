---
name: training-update
description: Pull new Strava activities since the last logged entry, log them into README.md (VO2max sessions, block status, calisthenics log) and ftp-history.md, then give a short numbers-first insight on recent training. Use when Artur asks to "update trainings", "log recent rides", "sync Strava", "what did I do this week", or wants a check-in on how training is going.
---

# Training update

Sync recent Strava activities into the repo's training logs and give a concise insight. Follow the athlete profile, data caveats and zones in `CLAUDE.md` — don't restate them here.

## 1. Find the gap

- Read `README.md` and `ftp-history.md` in full (current FTP, plan targets, last logged session numbers).
- The last logged date is the latest date in the VO2max session bullets, the "Next block" Status bullet, or the Calisthenics log — whichever is newest. `git log -5` helps confirm.
- If the user names a range, use that instead.

## 2. Pull data

- `list_activities` with `range_start` = day after the last logged date (re-include that day if it might have had a second activity), `include_tags: true`, `ordering: StartDateLocalAsc`.
- Also pull the prior ~3 weeks (or reuse numbers already in the README) as the comparison baseline.
- Per activity, by type:
  - **Zwift/trainer ride** (`is_trainer` / `has_device_watts: true`): `get_activity_performance` → avg/max HR, avg W, cadence, %FTP, best efforts, laps.
  - **VO2max session** ("VO2max 5x4" in the name, or a `.zwo` from `zwift-workouts/`): get per-rep avg W, %FTP, duration, rep avg/max HR, and recovery HR. Use laps first; if they don't split the reps, use `get_activity_streams` (`time`, `watts`, `heart_rate`, `cadence`). Flag cut-short reps (length + power) and whether they ended in a fade or an abrupt 0W stop.
  - **FTP test**: 20-min avg → FTP (×0.95), W/kg, block HR vs the previous test, pacing, warm-up quality. Log it in `ftp-history.md` and update the FTP everywhere it appears (`CLAUDE.md`, `README.md` targets in W).
  - **Outdoor ride**: power is estimated — use HR, duration and distance only.
  - **WeightTraining**: treat as calisthenics. Call `get_strength_workout_details` for the sets/reps.
  - **Walk/Hike/Run**: note as recovery or extra load (runs are one-off load, never coached).
- Check `get_athlete_zones` FTP when there's an open "confirm platform FTP" Status item.

## 3. Analyze (compare, don't snapshot)

Use the last 2–4 weeks for every comparison:

- **VO2max sessions**: reps in target (106–120% FTP), total time ≥106%, and HR at the same power vs earlier sessions. Lower HR at the same watts = an efficiency gain; higher = fatigue (check the days before).
- **Z2 rides**: HR at ~139W vs the reference rides in the README (e.g. HR ~137 fresh). A rise of 7+ bpm at the same power is a fatigue sign. Check HR drift within the ride too.
- **Load pattern**: consecutive training days, rest days before VO2max sessions, and how many VO2max sessions this week vs the 1–2×/week target. Call it out if the period was all Z1/Z2 with no VO2max stimulus.
- **Calisthenics**: frequency vs 2×/week, rep/progression changes vs the last session, and whether it landed right before a VO2max day.
- **Equipment**: account for changes noted in `ftp-history.md` (e.g. the 2026-11-04 chain) when comparing power.
- **Retest timing**: if the block is ~4–5 weeks in or the plan's retest date is near, say so.

## 4. Update the logs

Match the existing style: dated bold lead-in, numbers first, short plain sentences, interpretation in one line.

- `README.md`
  - New VO2max session → next `**Session N done YYYY-MM-DD**` bullet in section 1, numbered on from the last one.
  - Everything else in the active block (Z2 rides, rest days, walks) → append to the `Next block` Status bullet in chronological order. Update the `Next:` sentence at its end.
  - Tick or add Status checklist items when they're completed.
  - Calisthenics → next `**Session N — YYYY-MM-DD**` in the Log with duration, HR and the set breakdown. Refresh the "Frequency so far" line.
  - If the data shows a plan target should change (e.g. a `.zwo` %FTP), change it in the README and the `.zwo` and say why.
- `ftp-history.md` — only for FTP tests, platform FTP sync, or equipment changes.
- `CLAUDE.md` — only if the FTP, weight or a data caveat changes.

Don't invent numbers. If a value can't be read from Strava, leave it out or say it's missing.

## 5. Commit and push

Per the saved preference, commit and push to `main` without asking: `git add` the changed files, conventional commit (`feat: Log <dates/summary>`), `git push`. Report the commit hash.

## 6. Insight (reply to Artur)

Keep it short and numbers-first, roughly:

```
**Logged:** Nov 6 Z2 (72min @ 138W, HR 136), calisthenics 9.
**Trend:** <1–3 bullets: VO2max progress, HR at fixed power, fatigue/freshness>
**Flags:** <missing VO2max stimulus, too many days in a row, retest due, platform FTP stale — omit if none>
**Next:** <the concrete next session or rest day, with target watts>
```

No generic training advice. No running suggestions.

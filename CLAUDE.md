# Cycling Training

This project is for tracking and developing Artur's personal cycling training goals using Strava data (via the `strava` MCP server).

## Athlete profile
- Weight: 86kg, based in Wrocław, Poland
- Current stated focus: **Build — increase VO2max to get faster**
- HR zones (max-HR based): Z1 <125, Z2 125–154, Z3 155–169, Z4 170–184, Z5 185+
- Power zones: **FTP 122W confirmed (2026-09-06 Zwift FTP Test [Standard]); Zwift auto-bumped to 152W on 2026-09-10 off a 20min KOM-chase effort (159W best 20min), done post-fatigue from a VO2max session — treat 152W as provisional until confirmed by a dedicated fresh-legs retest.** Zwift structured workouts run in ERG mode, so route terrain doesn't affect required power — trust ERG-mode test results. See `README.md` for detail.
- Training pattern: near-daily ~30km/80min outdoor commute rides (Wrocław), occasional long ride, periodic Zwift/indoor sessions, dog walks as active recovery

## Known data caveats
- **Outdoor rides have `has_device_watts: false`** — their power numbers are Strava's speed/weight-based estimate, not measured. Don't use them to judge FTP or power-zone compliance.
- **Only trainer/Zwift rides carry real power** (`has_device_watts: true`). Any FTP or power-zone analysis must be anchored to these, not outdoor estimates.
- **ERG-mode structured Zwift workouts (e.g. the FTP Test) are not affected by route terrain** — the trainer locks resistance to the workout's target power regardless of gradient. Don't assume hills invalidate a result from one of these; that only applies to free-ride (non-ERG) sessions.

## How to help
- When asked to analyze an activity or trend, pull data via the Strava MCP tools (`list_activities`, `get_activity_performance`, `get_athlete_zones`, `get_athlete_profile`) rather than assuming stale context.
- Compare new activities against recent history (last 2–4 weeks) to spot trends in HR drift, power, cadence, and consistency — not just single-ride snapshots.
- Since the stated goal is VO2max/Build, call out when recent training is all Z1/Z2 endurance and missing the 3–8min @106–120%FTP stimulus VO2max work actually needs.
- Keep analysis concise and numbers-first; skip generic training-plan boilerplate unless asked to build one.

## Training plan
See `README.md` for the current VO2max build plan (FTP retest → dedicated intervals → progress tracking). Check its status checklist before proposing new plans, and update it as steps are completed.

## Custom Zwift workouts
`zwift-workouts/` holds `.zwo` files built to match the plan's interval targets (power as %FTP, so they auto-scale as FTP is retested). Add new ones here rather than one-off scratch files when a session is created for repeated use.

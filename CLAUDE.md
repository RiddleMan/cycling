# Cycling Training

This project is for tracking and developing Artur's personal cycling training goals using Strava data (via the `strava` MCP server).

## Athlete profile
- Weight: 86kg, based in Wrocław, Poland
- Current stated focus: **Build — increase VO2max to get faster**
- HR zones (max-HR based): Z1 <125, Z2 125–154, Z3 155–169, Z4 170–184, Z5 185+
- Power zones: FTP 231W (⚠️ set ~3 years ago — treat as unreliable until retested)
- Training pattern: near-daily ~30km/80min outdoor commute rides (Wrocław), occasional long ride, periodic Zwift/indoor sessions, dog walks as active recovery

## Known data caveats
- **Outdoor rides have `has_device_watts: false`** — their power numbers are Strava's speed/weight-based estimate, not measured. Don't use them to judge FTP or power-zone compliance.
- **Only trainer/Zwift rides carry real power** (`has_device_watts: true`). Any FTP or power-zone analysis must be anchored to these, not outdoor estimates.
- No valid maximal-effort FTP test exists in recent history — flag this whenever zone-based recommendations are requested, and suggest a fresh 20-min or ramp test rather than trusting the stored 231W.

## How to help
- When asked to analyze an activity or trend, pull data via the Strava MCP tools (`list_activities`, `get_activity_performance`, `get_athlete_zones`, `get_athlete_profile`) rather than assuming stale context.
- Compare new activities against recent history (last 2–4 weeks) to spot trends in HR drift, power, cadence, and consistency — not just single-ride snapshots.
- Since the stated goal is VO2max/Build, call out when recent training is all Z1/Z2 endurance and missing the 3–8min @106–120%FTP stimulus VO2max work actually needs.
- Keep analysis concise and numbers-first; skip generic training-plan boilerplate unless asked to build one.

## Not yet tracked here
- No structured training plan or periodization is stored in this repo yet — treat any plan discussion as a starting point to capture here once agreed, not as settled fact.

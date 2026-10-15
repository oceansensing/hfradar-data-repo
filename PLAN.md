# hfradar-data-repo: the founding plan and running record

The **MARACOOS HF radar network**'s surface currents and waves. Created on GitHub by the owner and given its documents by the site's
`pipeline/scaffold/new-origin.py`. **Nothing is published yet.**

## What it is for

The MARACOOS HF radar network's real-time products, from Rutgers University's ERDDAP: **surface currents** (`cur-hfr-maracoos.json`) — the optimally interpolated total vectors, hourly at 6 km over the whole network, Cape Cod to Cape Hatteras (`regional: true`), each frame's header linking the same hour's 2 km grid (the New Jersey shelf) and 1 km grid (the bays and the harbor mouths) as its `details`; a vector published only where the data's own QARTOD primary flag passed it; whole centimeters a second (`unitScale` 0.01); **the past 24 hours** as frames, the base the newest hour with its vectors in, listing them (`frames`), every other `<stem>.v<time>.json` with regions of its own hour — and **waves** (`hfr-waves.json`): each wave site's significant height, mean period and the direction the waves come from, every 30 minutes over the 24 hours before the newest reading, a reading kept only when the radar does not flag it. Two products, R2's alone.

## Where the data comes from

Rutgers University's ERDDAP (hfr.marine.rutgers.edu/erddap), the Mid-Atlantic Regional Association Coastal Ocean Observing System's (MARACOOS) CODAR SeaSonde network. **Its terms were read before a line was written** (2026-10-15): every dataset read carries one license — the data may be used and redistributed for free, and is not intended for legal use, with no warranty from the contributor, ERD, NOAA or the US government — and asks the acknowledgement that the data is provided by MARACOOS with funding from the US Integrated Ocean Observing System (IOOS). The datasets: `realtime_maracoos_6km_totals_qartod`, `_2km_` and `_1km_`, and every `realtime_waves_*` site reporting in ten days.

## Open

1. The first dispatched run, read: both products fresh, R2 alone.
2. Then the hourly schedule.
3. A week of runs read: the budgets against the server's real lateness, how often a newest hour is taken before it has filled.

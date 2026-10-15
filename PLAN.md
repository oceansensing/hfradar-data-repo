# hfradar-data-repo: the founding plan and running record

The **MARACOOS HF radar network**'s surface currents, waves and stations. Created on GitHub by the owner and given its documents by the site's
`pipeline/scaffold/new-origin.py`. **Publishing since 2026-10-15**, hourly at 23 past.

## What it is for

The MARACOOS HF radar network's real-time products, from Rutgers University's ERDDAP: **surface currents** (`cur-hfr-maracoos.json`) — the optimally interpolated total vectors, hourly at 6 km over the whole network, Cape Cod to Cape Hatteras (`regional: true`), each frame's header linking the same hour's 2 km grid (the New Jersey shelf) and 1 km grid (the bays and the harbor mouths) as its `details`; a vector published only where the data's own QARTOD primary flag passed it; whole centimeters a second (`unitScale` 0.01); **the past 24 hours** as frames, the base the newest hour with its vectors in, listing them (`frames`), every other `<stem>.v<time>.json` with regions of its own hour — and **waves** (`hfr-waves.json`): each wave site's significant height, mean period and the direction the waves come from, every 30 minutes over the 24 hours before the newest reading, a reading kept only when the radar does not flag it — and **the stations** (`hfr-sites.json`): each radar station the three totals datasets name in their own `instrument` attribute, its antenna's place and the time of its newest radial file, from the U.S. IOOS High Frequency Radar Network's radial ERDDAP (a station it lists no radials for left out). Three products, R2's alone.

## Where the data comes from

Rutgers University's ERDDAP (hfr.marine.rutgers.edu/erddap), the Mid-Atlantic Regional Association Coastal Ocean Observing System's (MARACOOS) CODAR SeaSonde network. **Its terms were read before a line was written** (2026-10-15): every dataset read carries one license — the data may be used and redistributed for free, and is not intended for legal use, with no warranty from the contributor, ERD, NOAA or the US government — and asks the acknowledgement that the data is provided by MARACOOS with funding from the US Integrated Ocean Observing System (IOOS). The datasets: `realtime_maracoos_6km_totals_qartod`, `_2km_` and `_1km_`, and every `realtime_waves_*` site reporting in ten days. **The stations' status and places are the U.S. IOOS High Frequency Radar Network's** (hfradar.ioos.us/radials-erddap/erddap, 2026-10-15): public domain, used for any lawful purpose with its credit line — "Data provided by the U.S. Integrated Ocean Observing System (IOOS) High Frequency Radar Network (HFRNet)" — and every radial dataset carrying the same free-use, not-for-legal-use license; one catalog request a run, and one per station for its antenna's place where the last publish has none.

## 2026-10-15: the stations

A third product, `hfr-sites.json`: each radar station the three totals datasets name, its antenna's
place and its newest radial file's hour, from the U.S. IOOS High Frequency Radar Network's radial ERDDAP —
38 of the 40 named that evening (DUCK and MVCO have no radials there), 30 with a radial in five hours.
Its controls: every antenna inside the network's box, no newest radial ahead of the clock, twenty placed
at least, Sandy Hook's and Nantucket's antennas within 5 km of their charted sites, the median newest
radial younger than three days. One catalog request a run, and one per station for an antenna's place
where the last publish has none (16 s the first run, 1.4 s after).

## 2026-10-15: the first run, and the schedule

The first dispatched run (`38763896274`, 15:50-15:52 UTC) was green: both products fresh; the currents' 24
frames built, the newest 13Z, each with its 2 km and 1 km grids; 13 wave sites, 305 readings, the newest 14Z;
97 files matching the contract; R2 equal to the build, 80 files uploaded, none deleted. The schedule set
then: hourly at 23 past.

## Open

1. A week of runs read: the budgets against the server's real lateness, how often a newest hour is taken before it has filled.
2. How far back the frames reach, should a longer past be wanted.

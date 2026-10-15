# hfradar-data-repo

The **MARACOOS HF radar network**'s surface currents and waves: a data repository of the oceansensing ocean map system, with its own
Pages site, its own schedule and its own gigabyte, and no code of its own.

**Nothing is published yet.** `PLAN.md` is the founding plan; `CLAUDE.md` carries what must not be
got wrong and the shared doc doctrine.

## What it publishes

The MARACOOS HF radar network's real-time products, from Rutgers University's ERDDAP: **surface currents** (`cur-hfr-maracoos.json`) — the optimally interpolated total vectors, hourly at 6 km over the whole network, Cape Cod to Cape Hatteras (`regional: true`), each frame's header linking the same hour's 2 km grid (the New Jersey shelf) and 1 km grid (the bays and the harbor mouths) as its `details`; a vector published only where the data's own QARTOD primary flag passed it; whole centimeters a second (`unitScale` 0.01); **the past 24 hours** as frames, the base the newest hour with its vectors in, listing them (`frames`), every other `<stem>.v<time>.json` with regions of its own hour — and **waves** (`hfr-waves.json`): each wave site's significant height, mean period and the direction the waves come from, every 30 minutes over the 24 hours before the newest reading, a reading kept only when the radar does not flag it. Two products, R2's alone.

These products are published **operationally but not drawn on the website's map**; the map's status
line still reports them when they fall behind, which is how their health stays visible.

## Where the data comes from

Rutgers University's ERDDAP (hfr.marine.rutgers.edu/erddap), the Mid-Atlantic Regional Association Coastal Ocean Observing System's (MARACOOS) CODAR SeaSonde network. **Its terms were read before a line was written** (2026-10-15): every dataset read carries one license — the data may be used and redistributed for free, and is not intended for legal use, with no warranty from the contributor, ERD, NOAA or the US government — and asks the acknowledgement that the data is provided by MARACOOS with funding from the US Integrated Ocean Observing System (IOOS). The datasets: `realtime_maracoos_6km_totals_qartod`, `_2km_` and `_1km_`, and every `realtime_waves_*` site reporting in ten days.

## How it runs

The orchestrator (the site's private `pipeline/`), the fetchers and the
published-file contract all come from `oceansensing.github.io`, checked out at
run time. This repository carries `pipeline/products.toml` and its publish
workflow, and nothing else executable. Each run publishes to GitHub Pages and
to Cloudflare R2 from one build. Related repositories: none it depends on.

**Which document gets what, and what "update docs" means across all
twenty-six repositories, is the doctrine block at the top of `CLAUDE.md`**: the
same text in all twenty-six, held equal by the site's `check:docs`.

## Structure

```
README.md       what this is
CLAUDE.md       what must not be got wrong, and the shared doc doctrine
PLAN.md         the founding plan and running record
DECISIONS.md    dated one-way decisions, D1 onward
pipeline/       products.toml, the declaration the orchestrator reads
.github/        the publish workflow
```

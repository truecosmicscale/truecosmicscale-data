# Voyager 1 Is Now One Light-Day Away

Data for the True Cosmic Scale video "Voyager 1 Is Now One Light-Day Away. 3 Years Ago, One Dead Chip Almost Ended the Mission".
Every number in the video comes from one of the two tables below.

## Files

| File | What it is |
|---|---|
| `facts.csv` | Every fact and figure used in the script: value, unit, source link, the sentence it rests on, and a status (`sourced` = quoted from the cited page, `derived` = arithmetic on sourced numbers, `quote` = a spoken or written quotation). |
| `voyager1_distance.csv` | Voyager 1's distance from Earth, one point every 30 days from 1977-09-06 to 2026-12-31, plus one point at 2026-11-18 10:16:07 UTC, from JPL Horizons. |

## Distance table

Source: NASA/JPL Horizons API, target `-31` (Voyager 1), observer the Earth geocentre (`500@399`), times in UT.

| Column | Meaning |
|---|---|
| `date` | UTC date and time of the point. |
| `distance_km` | Straight-line (geometric) distance, the length of Horizons' position vector (`VEC_CORR=NONE`). This is the figure NASA quotes. |
| `one_way_light_hours` | `distance_km` / 299,792.458 km/s / 3600. |
| `light_time_range_km` | Horizons' "apparent range", corrected for the light travel time. It is shorter by about Voyager's own speed times the light time (about 1.4 million km now), so it is not used for the milestone. |

At 2026-11-18 10:16:07 UTC the geometric distance is 25,902,068,371 km: 24.000000 hours of light travel, the length of one light-day (299,792.458 km/s x 86,400 s = 25,902,068,371 km). NASA's page "Where are Voyager 1 and 2 now" gives the same time and 25.902 billion km.

The small yearly ripples in the one-way light time are Earth's own orbit around the Sun, not Voyager.

## Sources

Each row of `facts.csv` has its source link. Sources are NASA and JPL pages, with a few news reports and one IEEE article where NASA does not give the figure; those rows say so in `source_note`. Four figures from secondary sources that NASA does not confirm (the flight data subsystem's word size, memory size, memory type and the size of the failed memory block) were left out of the video and are not in this table.

## Licence

Data and text: CC BY 4.0 (see `LICENSE` in the root of this repository). Please credit "True Cosmic Scale (truecosmicscale.com)" and the original sources.

## Corrections

Think a figure is wrong? Open an issue with your source and we will check it and correct it publicly.

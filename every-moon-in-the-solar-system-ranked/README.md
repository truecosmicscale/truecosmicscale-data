# Every Moon in the Solar System, Ranked by How Strange It Is

Data for the True Cosmic Scale video of the same name. 29 entries (some cover a whole
group of moons) are scored on 20 yes/no tests plus a rarity score. The order comes from
the table and nothing else.

## Files

| File | What it is |
|---|---|
| `moons_ranked.csv` | The final ranking, as shown on screen. |
| `moons.csv` | Every yes/no flag for every entry, with sources and notes. |
| `moons_rubric.yaml` | The rules: what each test means, how rarity is scored, how ties are broken. |

## How the score works

Each entry gets 20 yes/no tests in four groups of five.

| Group | Column | Tests |
|---|---|---|
| A | `A1`-`A5` | Geologically alive now (eruptions, young surface, internal heating, surface change, active tectonics) |
| B | `B1`-`B5` | Strange orbit (retrograde, eccentric, resonance or co-orbital, chaotic spin, predicted breakup) |
| C | `C1`-`C5` | Strange shape or surface (non-spherical, extreme relief, colour contrast, porous, unique terrain) |
| D | `D1`-`D5` | Air, oceans and lakes (atmosphere, thick atmosphere, surface liquid, subsurface ocean, weather cycle) |

The exact wording of each test is in `moons_rubric.yaml`. A flag is 1 only if it is
supported by a source listed in `sources`. For an entry that covers several moons, a
flag is 1 only if it is true for most of its members.

**Rarity (`E`, 0-5)** is how few other known moons share the entry's one headline trait
(`E_trait`): 0 others = 5, 1 other = 4, 2-3 = 3, 4-9 = 2, 10-99 = 1, 100 or more = 0.
Rarity counts double.

**Total** = A + B + C + D + 2 x E, out of 30, where A to D are the sums of their five
flags. Ties are broken by A, then B, then C, then D, then name; `joint_rank` shows
where entries tie on total.

## Columns

`moons_ranked.csv`

| Column | Meaning |
|---|---|
| `rank` | Position after tie-breaks (1 = strangest) |
| `joint_rank` | 1 + the number of entries with a strictly higher total (tied entries share it) |
| `name` | Moon or group of moons |
| `A`, `B`, `C`, `D` | Sum of the five flags in each group (0-5) |
| `E` | Rarity score (0-5), counted twice in the total |
| `total` | A + B + C + D + 2 x E |
| `script_rank` | Where the entry stood in the first script draft, before scoring |
| `delta` | `script_rank` minus `rank` (positive = moved up when scored) |
| `confidence` | `high`, `med` or `low`: how well the flags are sourced |

`moons.csv` has the same names plus `members` (the moons inside a group entry), the 20
flags `A1`-`D5`, `E_trait` and `E_moons_with_trait` (the count behind the rarity score),
`confidence`, `sources` (URLs separated by " ; ") and `notes` (why a flag was set, and
caveats). Rows rated `low` are the ones to check first.

## Status

Rubric version 1. Weights and thresholds are frozen once a ranking has been shown; only
flags change, and only with a cited source. See the repository README for how to send a
correction.

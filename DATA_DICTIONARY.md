# Data dictionary

One row per occupation. **`official_duties_covered_pct` is the headline measure.** Version 2026-11-10 keeps the same columns and changes the figures: see "Changes in 2026-11-10". Version 2026-11-09 changed the columns: see "Changes from version 2026-11-06" below.

| Column | Type | Meaning |
|---|---|---|
| occupation_en | text | Occupation name in English |
| occupation_zh | text | Occupation name in Chinese |
| industry_en | text | KeenPage industry group in English |
| industry_zh | text | KeenPage industry group in Chinese |
| **official_duties_covered_pct** | integer, 0 to 100, or empty | **Headline.** Share of the occupation's official task statements that at least one task on the occupation's page (its own tasks or the shared common tasks it lists) helps with. Equals `official_tasks_covered / official_tasks`. Empty when the occupation has no official task statements or fewer than 5. |
| official_tasks | integer or empty | Number of official task statements used as the denominator (up to 30, minus statements that belong to another occupation: those recorded as such when the list was drafted, and those two models independently judged to belong elsewhere) |
| official_tasks_covered | integer or empty | Number of those statements cited by at least one of the occupation's own tasks or the shared common tasks listed on its page (statements left out of the denominator are not counted here either) |
| official_task_source | text or empty | Where the statements come from (empty when none remain): `onet` (US O\*NET 31.0), `osca` (Australia OSCA 2024), `uksoc2020` (UK SOC 2020), `noc2021` (Canada NOC 2021) |
| tasks | integer | Number of tasks AI can help with on this occupation's own list (shared common tasks are not counted) |
| weekly_ai_tasks | integer | Number of listed tasks that come up at least weekly |
| weekly_or_more_pct | integer, 0 to 100 | Share of the listed tasks that come up at least weekly |
| for_others_pct | integer, 0 to 100 | Share of the listed tasks whose result goes to someone else |
| ready_to_use_pct | integer, 0 to 100 | Share of the listed tasks where AI's result is close to ready to use. It describes the kind of help, so don't use it to rank occupations or industries. |
| url_en | URL | The occupation's page on KeenPage |

Percentages are rounded to whole numbers (halves round up). Occupations with no task list yet are not included. Industry figures for `official_duties_covered_pct` are the mean over the industry's scored occupations. See `METHODOLOGY.md`.

## Changes in 2026-11-10

Same columns. A review of the official statements no task cited (see "Gap review" in `METHODOLOGY.md`) added missing citations and 137 new tasks, and left out of the denominator 746 statements that two models agreed belong to another occupation.

- `official_tasks` changes in 278 rows (statements left out). In one row (prior learning assessor) all statements were left out, so `official_tasks`, `official_tasks_covered` and `official_task_source` are now empty.
- `official_tasks_covered` changes in 739 rows and `official_duties_covered_pct` in 874 of the 1,492 rows scored in both versions; it doesn't go down in any. 31 rows are no longer scored because fewer than 5 statements remain (1,523 → 1,492 scored; average 54% → 61%).
- `tasks` changes in 128 rows (25,001 → 25,138 in all). `weekly_ai_tasks`, `weekly_or_more_pct`, `for_others_pct` and `ready_to_use_pct` change only in those rows.

## Correction in 2026-11-09.1

The first 2026-11-09 release counted, in `official_tasks_covered`, only statements cited by the occupation's own tasks. Statements cited by the shared common tasks listed on the occupation's page now count too. `official_tasks_covered` changes in 966 rows and `official_duties_covered_pct` in 960 of the 1,523 scored rows (average 45% → 54%); all other columns are unchanged.

## Changes from version 2026-11-06

- New headline column `official_duties_covered_pct`, with its counts and source (`official_tasks`, `official_tasks_covered`, `official_task_source`), placed right after the industry columns.
- New column `weekly_ai_tasks`.
- `ai_does_most_pct` was removed. The same figure is now `ready_to_use_pct`, a descriptive column that is not meant for ranking.
- Column order changed. Read columns by name, not by position.

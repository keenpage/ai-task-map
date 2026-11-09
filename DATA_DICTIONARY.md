# Data dictionary

One row per occupation. **`official_duties_covered_pct` is the headline measure.** Version 2026-11-09 changed the columns: see "Changes from version 2026-11-06" below.

| Column | Type | Meaning |
|---|---|---|
| occupation_en | text | Occupation name in English |
| occupation_zh | text | Occupation name in Chinese |
| industry_en | text | KeenPage industry group in English |
| industry_zh | text | KeenPage industry group in Chinese |
| **official_duties_covered_pct** | integer, 0 to 100, or empty | **Headline.** Share of the occupation's official task statements that at least one listed task helps with. Equals `official_tasks_covered / official_tasks`. Empty when the occupation has no official task statements or fewer than 5. |
| official_tasks | integer or empty | Number of official task statements used as the denominator (up to 30, minus statements recorded as belonging to a neighbouring occupation) |
| official_tasks_covered | integer or empty | Number of those statements cited by at least one listed task |
| official_task_source | text or empty | Where the statements come from: `onet` (US O\*NET 31.0), `osca` (Australia OSCA 2024), `uksoc2020` (UK SOC 2020), `noc2021` (Canada NOC 2021) |
| tasks | integer | Number of tasks AI can help with listed for this occupation |
| weekly_ai_tasks | integer | Number of listed tasks that come up at least weekly |
| weekly_or_more_pct | integer, 0 to 100 | Share of the listed tasks that come up at least weekly |
| for_others_pct | integer, 0 to 100 | Share of the listed tasks whose result goes to someone else |
| ready_to_use_pct | integer, 0 to 100 | Share of the listed tasks where AI's result is close to ready to use. It describes the kind of help, so don't use it to rank occupations or industries. |
| url_en | URL | The occupation's page on KeenPage |

Percentages are rounded to whole numbers (halves round up). Occupations with no task list yet are not included. Industry figures for `official_duties_covered_pct` are the mean over the industry's scored occupations. See `METHODOLOGY.md`.

## Changes from version 2026-11-06

- New headline column `official_duties_covered_pct`, with its counts and source (`official_tasks`, `official_tasks_covered`, `official_task_source`), placed right after the industry columns.
- New column `weekly_ai_tasks`.
- `ai_does_most_pct` was removed. The same figure is now `ready_to_use_pct`, a descriptive column that is not meant for ranking.
- Column order changed. Read columns by name, not by position.

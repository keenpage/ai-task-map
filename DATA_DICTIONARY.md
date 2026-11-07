# Data dictionary

| Column | Type | Meaning |
|---|---|---|
| occupation_en | text | Occupation name in English |
| occupation_zh | text | Occupation name in Chinese |
| industry_en | text | KeenPage industry group in English |
| industry_zh | text | KeenPage industry group in Chinese |
| tasks | integer | Number of tasks AI can help with listed for this occupation |
| ai_does_most_pct | integer, 0 to 100 | Share of those tasks where AI's result is close to ready to use |
| weekly_or_more_pct | integer, 0 to 100 | Share of those tasks that come up at least weekly |
| for_others_pct | integer, 0 to 100 | Share of those tasks whose result goes to someone else |
| url_en | URL | The occupation's page on KeenPage |

Percentages are rounded to whole numbers. Occupations with no task list yet are not included.

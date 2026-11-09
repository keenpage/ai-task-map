# KeenPage AI Task Map by Occupation

How much of the everyday work in 2,000 occupations can AI help with? This dataset checks 25,000 work tasks across 38 industries against the duties listed for each job in official occupation data, one row per occupation.

- Report: https://keenpage.com/en/ai-task-map
- Chinese report: https://keenpage.com/zh/ai-task-map
- Version: 2026-11-09
- DOI: [10.5281/zenodo.24035962](https://doi.org/10.5281/zenodo.24035962) (all versions)
- Mirrors: [Hugging Face](https://huggingface.co/datasets/keenpage-ai/ai-task-map) · [Kaggle](https://www.kaggle.com/datasets/keenpage/keenpage-ai-task-map) · [GitHub](https://github.com/keenpage/ai-task-map)
- License: CC BY 4.0 (this data file only)

## Headline figures

**Official duties covered** (`official_duties_covered_pct`): of the main duties listed for an occupation in official occupation data (mostly the US O\*NET), the share that at least one task AI can help with matches.

| Measure | Value |
|---|---|
| Official duties covered, average occupation | 45% (1,523 occupations scored) |
| Highest industry | IT & Software, 65% |
| Lowest industry | Cleaning & Housekeeping, 25% |
| Occupations | 2,000 |
| Tasks AI can help with | 25,001 |
| Median tasks per occupation | 10 |
| Listed tasks that come up at least weekly | 75% |

"Helps with" is not "can do": covered duties are mostly about gathering, drafting and checking, and the person still makes the call.

## What's new in 2026-11-09

- The headline is now `official_duties_covered_pct`, which compares every occupation with an outside yardstick. The previous headline, the share of listed tasks whose AI result is close to ready to use, only looked inside our own lists, ranked drivers above IT and ran against independent research. See `METHODOLOGY.md`.
- The column `ai_does_most_pct` was removed. The same figure is now `ready_to_use_pct` (56% overall), a descriptive column, not for ranking.
- New columns: `official_tasks`, `official_tasks_covered`, `official_task_source`, `weekly_ai_tasks`. Column order changed, so read columns by name.

## Files

`data/keenpage-ai-task-map.csv`: UTF-8 with BOM, one row per occupation. See `DATA_DICTIONARY.md`.

## Read this before using it

These figures are **model-assisted estimates, not survey or measurement results**. The task lists and the matches to official duties were made by one model and reviewed by another. Coverage shows the range of duties AI can help with, not how much of a job AI can replace. See `METHODOLOGY.md`.

## Citation

KeenPage. AI Task Map by Occupation (version 2026-11-09). https://keenpage.com/en/ai-task-map. DOI: 10.5281/zenodo.24035962

See `CITATION.cff`. Please credit KeenPage and link to the report.

## License and scope

KeenPage's compilation and calculated figures in this CSV are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The license covers this file only. KeenPage task lists, prompt cards and other site content are not included and are not open. Third-party material such as occupation names stays under its own terms. See `LICENSE.md` and `SOURCES.md`.

---

# 职页：各职业 AI 任务地图

汇总 2,000 个职业、38 个行业的 25,000 项 AI 帮得上的工作，并对照官方职业资料，每个职业一行。主指标是“官方职责覆盖”（`official_duties_covered_pct`）：官方列出的主要职责里，有多少至少有一项 AI 帮得上的工作对应。平均每个职业约 45%（1,523 个职业计分），行业从互联网与IT 的 65% 到保洁与家政的 25%。

2026-11-09 版起主指标改为官方职责覆盖，去掉了旧列 `ai_does_most_pct`，同一个数改名为 `ready_to_use_pct`，只描述帮法，不用来排名。数字是模型辅助的估计，不是调查或实测结果；覆盖说的是 AI 帮得上的范围，不代表一个职业有多少工作能被 AI 替代。

报告：https://keenpage.com/zh/ai-task-map
DOI：10.5281/zenodo.24035962

职页汇编和计算的数字按 CC BY 4.0 开放，请注明“职页 KeenPage”并链接到报告。许可只覆盖这个文件，工作清单、提示词卡和站内其他内容不在开放范围内；职业名称等第三方内容仍按各自条款使用，见 `SOURCES.md`。

# KeenPage AI Task Map by Occupation

How much of the everyday work in 2,000 occupations can AI help with? This dataset checks 25,138 work tasks across 38 industries against the duties listed for each job in official occupation data, one row per occupation. In the average occupation, 61% of the official duties match at least one task AI can help with.

- Report: https://keenpage.com/en/ai-task-map
- Chinese report: https://keenpage.com/zh/ai-task-map
- Version: 2026-11-10 (see "What's new")
- DOI: [10.5281/zenodo.24035962](https://doi.org/10.5281/zenodo.24035962) (all versions)
- Mirrors: [Hugging Face](https://huggingface.co/datasets/keenpage-ai/ai-task-map) · [Kaggle](https://www.kaggle.com/datasets/keenpage/keenpage-ai-task-map) · [GitHub](https://github.com/keenpage/ai-task-map)
- License: CC BY 4.0 (this data file only)

## Headline figures

**Official duties covered** (`official_duties_covered_pct`): of the main duties listed for an occupation in official occupation data (mostly the US O\*NET), the share that at least one task AI can help with matches. Both the occupation's own tasks and the shared common tasks listed on its page count. Duties that two models independently judged to belong to a different occupation are left out.

| Measure | Value |
|---|---|
| Official duties covered, average occupation | 61% (1,492 occupations scored) |
| Highest industries | Legal 83%, IT & Software 83%, Marketing & Business Sales 83% |
| Lowest industries | Woodworking, Furniture & Paper 34%, Drivers & Vehicle Operators 37% |
| Occupations | 2,000 |
| Tasks AI can help with | 25,138 |
| Median tasks per occupation | 10 |
| Listed tasks that come up at least weekly | 74% |

"Helps with" is not "can do": covered duties are mostly about gathering, drafting and checking, and the person still makes the call.

## What's new in 2026-11-10

We reviewed the official duties that no task cited. Claude judged each candidate first and codex checked it independently; only what both agreed on was applied. See "Gap review" in `METHODOLOGY.md`.

- **Missing citations added.** 1,642 official statements were already covered by an existing task or a common task on the page but not cited. The citations were added; no task text changed.
- **New tasks.** 137 tasks were added to 128 occupations where AI can help with a duty and no task did it. Existing tasks are unchanged. `tasks` goes from 25,001 to 25,138.
- **Duties of other occupations left out.** Official codes mapped onto our occupations bring in some duties of a different job (for example pre-launch audits of information systems in an accountant's list). Claude flagged 1,769 such statements; codex judged them again blind, and the 746 both models agreed on (in 278 occupations) are left out of the denominator, and of the numerator if cited.
- **Effect.** The average occupation goes from 54% to 61% (59% from the citations and new tasks alone). `official_duties_covered_pct` rises in 874 of the 1,492 occupations scored in both versions and falls in none. 31 occupations drop below 5 official statements and are no longer scored (1,523 → 1,492). `official_tasks` changes in 278 rows; `tasks` and the other task columns change only in the 128 rows with new tasks.
- No columns were added or removed.

Earlier versions:

- **2026-11-09.1** corrected the first 2026-11-09 release, which counted only the official statements cited by an occupation's own tasks and left out those cited by the common tasks on its page (45% → 54%).
- **2026-11-09** made `official_duties_covered_pct` the headline. The previous headline, the share of listed tasks whose AI result is close to ready to use (`ai_does_most_pct`), only looked inside our own lists, ranked drivers above IT and ran against independent research. It was removed; the same figure remains as `ready_to_use_pct` (55% overall in this version), a descriptive column, not for ranking. New columns `official_tasks`, `official_tasks_covered`, `official_task_source` and `weekly_ai_tasks` were added and the column order changed, so read columns by name.

## Files

`data/keenpage-ai-task-map.csv`: UTF-8 with BOM, one row per occupation. See `DATA_DICTIONARY.md`.

## Read this before using it

These figures are **model-assisted estimates, not survey or measurement results**. The task lists, the matches to official duties and the duties left out as belonging to other occupations were decided by models, with a second model reviewing the first. Coverage shows the range of duties AI can help with, not how much of a job AI can replace. See `METHODOLOGY.md`.

## Citation

KeenPage. AI Task Map by Occupation (version 2026-11-10). https://keenpage.com/en/ai-task-map. DOI: 10.5281/zenodo.24035962

See `CITATION.cff`. Please credit KeenPage and link to the report.

## License and scope

KeenPage's compilation and calculated figures in this CSV are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The license covers this file only. KeenPage task lists, prompt cards and other site content are not included and are not open. Third-party material such as occupation names stays under its own terms. See `LICENSE.md` and `SOURCES.md`.

---

# 职页：各职业 AI 任务地图

汇总 2,000 个职业、38 个行业的 25,138 项 AI 帮得上的工作，并对照官方职业资料，每个职业一行。主指标是“官方职责覆盖”（`official_duties_covered_pct`）：官方列出的主要职责里，有多少至少有一项 AI 帮得上的工作对应（职业专属的工作项和职业页上引用的通用工作都算）；两个模型独立判断都认为属于别的职业的官方职责不计入。平均每个职业约 61%（1,492 个职业计分），行业从法律、互联网与IT、市场营销与商务销售的 83% 到木工家具与造纸的 34%、司机的 37%。

2026-11-10 版：复查了没有工作项引用的官方职责，Claude 先判、codex 独立复核，两方一致的才采用。补上 1,642 条漏掉的引用（工作项原文不动）；给 128 个职业新增 137 项工作（工作项从 25,001 增至 25,138）；官方代码挂到职业上时带进来、其实属于别的职业的职责，Claude 初筛 1,769 条，codex 独立盲判，两方都认为属于别的职业的 746 条（涉及 278 个职业）从分母里扣掉。平均从 54% 升到 61%（只算补引用和新工作是 59%）；有 31 个职业扣掉后官方任务不足 5 条，不再计分。列没有变化。

数字是模型辅助的估计，不是调查或实测结果；覆盖说的是 AI 帮得上的范围，不代表一个职业有多少工作能被 AI 替代。旧主指标“成果基本能直接用”只在清单内部算，2026-11-09 版起已不作主指标，改名为 `ready_to_use_pct`，只描述帮法，不用来排名。

报告：https://keenpage.com/zh/ai-task-map
DOI：10.5281/zenodo.24035962

职页汇编和计算的数字按 CC BY 4.0 开放，请注明“职页 KeenPage”并链接到报告。许可只覆盖这个文件，工作清单、提示词卡和站内其他内容不在开放范围内；职业名称等第三方内容仍按各自条款使用，见 `SOURCES.md`。

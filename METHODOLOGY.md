# Method and limits

## Official duties covered (headline)

> Of the main duties listed for this occupation in official occupation data, the share that at least one task on our list helps with.

- **Denominator.** The official task statements a list was drafted from: O\*NET (US) where the occupation maps to it, otherwise Australia's OSCA, the UK SOC 2020 or Canada's NOC 2021, in that order. For O\*NET, up to 15 statements per O\*NET occupation (core tasks first, then by importance) and up to 30 in all. Lists drafted under an earlier version recorded, for every statement, whether it belonged to a neighbouring occupation that shares the same official code. Those statements are left out of the denominator.
- **Numerator.** Statements that at least one listed task cites as its source. The drafting model marks the citations, and a second model reviews them.
- **Not scored.** Occupations described only by the Chinese or the international classification (no official task statements), and occupations with fewer than 5 official statements, where one statement moves the figure by 20 points or more. 1,523 of 2,000 occupations are scored.
- **Industries.** The mean over scored occupations, so each occupation counts once.

### Why this measure

- It compares every occupation against an outside yardstick (the official description of the job), not against the tasks we chose to list. Hands-on duties that AI can't help with stay in the denominator.
- It can be stated in one sentence and checked row by row: the CSV gives both counts.
- It agrees with independent research. Across occupations matched to US SOC codes, the Spearman correlation is +0.49 with the GPT-4 exposure ratings in Eloundou et al., "GPTs are GPTs" (n = 1,470), and +0.34 with the observed exposure in the Anthropic Economic Index (n = 1,417). Across the 38 industries it is +0.73 and +0.72. At task level, official statements that GPT-4 rated "not exposed" (E0) are covered 28% of the time, compared with 54% to 57% for E1 and E2.

Earlier versions led with the share of listed tasks where AI's result is close to ready to use. That share only looks inside each list, and the lists include only work AI can help with, so hands-on jobs with short lists of simple writing tasks scored highest. It ranked drivers first and IT last of 38 industries and correlated negatively with the outside estimates above (−0.16 and −0.14), so it is no longer a headline. It remains in the data as `ready_to_use_pct`, as a description of the kind of help.

### Limits

- **It is an estimate, not a measurement.** Citations are written by a model and checked by a model, not by job holders. Citations are not required for every statement, so the figure is more likely to be too low than too high.
- **"Helps with" is not "can do".** A statement counts as covered when AI can help with part of it, such as preparing records, drafting, explaining or checking. It doesn't mean the duty can be handed to AI or that a job is at risk.
- **Official lists are mostly American.** O\*NET describes US jobs. Regional work is in our lists, but it can only raise coverage if it matches an official statement.
- **Granularity varies.** Some official statements are broad and some narrow, and codes shared by several of our occupations make some denominators long. Industry figures are more stable than single occupations. Bootstrapped 90% intervals for industry ranks typically span 6 to 10 places, and more for small industries.
- **Some occupations are underrated compared with outside estimates,** notably receptionists and some clerical jobs whose lists are short, and some are rated higher, such as healthcare, where documentation and explanation tasks cover many official duties.

## Supporting columns

- `tasks`: the number of tasks AI can help with on the occupation's list. It measures breadth, and correlates with outside estimates about as well as the headline (+0.54 with GPT-4 exposure). The count depends on how finely the list is split, so it isn't the headline.
- `weekly_ai_tasks`: how many of those tasks come up at least weekly.
- `ready_to_use_pct`: the share of listed tasks where AI's result is close to ready to use. It describes the kind of help, not how much. Writing up settled facts usually scores high. Analysis, design and judgment calls score lower. Don't use it to rank occupations or industries.
- `weekly_or_more_pct`, `for_others_pct`: shares of the listed tasks.

## Other notes

- Task lists were drafted by AI from official occupational sources such as O\*NET and ESCO and from common work in each region, then reviewed by a second model and checked by script.
- "Close to ready to use" and "how often it comes up" are estimates made to one shared standard when the lists were generated. They are not survey or measured results.
- Industries start from ISCO minor groups and were then adjusted by working community. Grouping involves judgment, so small gaps between industries should not be over-read.
- Some occupations are still being completed, and figures change as content is updated. Cite the version date.

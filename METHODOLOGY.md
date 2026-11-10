# Method and limits

## Official duties covered (headline)

> Of the main duties listed for this occupation in official occupation data, the share that at least one task on our list helps with.

This is the only headline measure. The CSV gives both counts (`official_tasks_covered / official_tasks`), so every row can be checked.

- **Denominator.** The official task statements a list was drafted from: O\*NET (US) where the occupation maps to it, otherwise Australia's OSCA, the UK SOC 2020 or Canada's NOC 2021, in that order. For O\*NET, up to 15 statements per O\*NET occupation (core tasks first, then by importance) and up to 30 in all. Two kinds of statements are left out:
  - Statements that the drafting model recorded, under an earlier version of the lists, as belonging to a neighbouring occupation that shares the same official code.
  - **Statements that belong to another occupation (746 statements in 278 occupations, from version 2026-11-10).** Mapping official codes onto our occupations brings in some duties of a different job: an accountant's list picking up pre-launch audits of information systems, or an aeronautical information specialist's list picking up air traffic control. In a review on 2026-11-09, Claude (claude-opus-5-5) first flagged 1,769 statements as belonging to another occupation. Codex (gpt-6.1-sol) then judged all 1,769 again, blind to Claude's answer. Only the 746 statements both models judged to belong to another occupation are left out. A left-out statement does not count in the numerator either, even if a task cites it.
- **Numerator.** Statements that at least one task on the occupation's page cites as its source: the occupation's own tasks, and the shared common tasks (such as answering customer questions or responding to complaints) the page lists with an occupation-specific note, which cite that occupation's statements too. The drafting model marks the citations, and a second model reviews them. The first 2026-11-09 release counted only the occupation's own tasks; version 2026-11-09.1 corrected this.
- **Not scored.** Occupations described only by the Chinese or the international classification (no official task statements), and occupations with fewer than 5 official statements, where one statement moves the figure by 20 points or more. 1,492 of 2,000 occupations are scored in version 2026-11-10.
- **Industries.** The mean over scored occupations, so each occupation counts once.

### Gap review (version 2026-11-10)

On 2026-11-09 we went through the official statements that no task cited, to tell real gaps from missing citations and from duties of other jobs. The candidates were 6,601 statements in 1,344 occupations: uncovered statements, leaving out those that outside labels rate as not exposed to AI (the GPT-4 and human ratings in "GPTs are GPTs" for O\*NET, a keyword rule for the other sources). The 217 that the drafting model had deliberately skipped when the list was written were set aside. Claude (claude-opus-5-5) judged the rest first, given the occupation's full task list and the common tasks. Codex (gpt-6.1-sol) then reviewed every match and every proposed new task with the same context, and re-judged every "belongs to another occupation" call blind. Only conclusions both models shared were applied:

- **Already covered, citation missing: 1,642 statements.** An existing task or a common task already on the page does this work but didn't cite the statement. The citation was added; no task text changed. (228 more that would need a common task newly added to the page are not applied yet.)
- **Real gaps: 137 new tasks in 128 occupations.** Existing tasks were left word for word as they were. New tasks went through the same drafting rules, script checks and review as the rest of the lists.
- **Belongs to another occupation: 746 statements,** left out of the denominator as described above.

Statements that both models judged AI can't help with, or that come up too rarely to be worth a task, stay in the denominator. Being uncovered is not a defect: hands-on duties should stay uncovered.

Effect on the average occupation: 54% in version 2026-11-09.1, 59% with the new citations and tasks alone, and 61% with the 746 statements also left out. With the exclusions, 31 occupations drop below 5 official statements and are no longer scored.

### Why this measure

- It compares every occupation against an outside yardstick (the official description of the job), not against the tasks we chose to list. Hands-on duties that AI can't help with stay in the denominator.
- It can be stated in one sentence and checked row by row: the CSV gives both counts.
- It agrees with independent research. In version 2026-11-09.1, across occupations matched to US SOC codes, the Spearman correlation was +0.55 with the GPT-4 exposure ratings in Eloundou et al., "GPTs are GPTs" (+0.57 with their human ratings; n = 1,470), and +0.43 with the observed exposure in the Anthropic Economic Index (n = 1,417). Across the 38 industries it was +0.87 and +0.82. At task level, official statements that GPT-4 rated "not exposed" (E0) were covered 34% of the time, compared with 64% to 68% for E1 and E2; statements that people actually use Claude for in the Anthropic data were covered 73% of the time, others 48%. These comparisons have not been recomputed for version 2026-11-10. Note that the gap review used the "GPTs are GPTs" labels to pick candidates, so they are no longer fully independent of this version.

### Previous headline, no longer used

Versions before 2026-11-09 led with the share of listed tasks where AI's result is close to ready to use (`ai_does_most_pct`). That share only looks inside each list, and the lists include only work AI can help with, so hands-on jobs with short lists of simple writing tasks scored highest. It ranked drivers first and IT last of 38 industries and correlated negatively with the outside estimates above (−0.16 and −0.14). It was removed as a headline in 2026-11-09. The same figure remains as `ready_to_use_pct`, a description of the kind of help, not for ranking.

### Limits

- **It is an estimate, not a measurement.** Citations are written by a model and checked by a model, not by job holders. The gap review added many missing citations, but citations are still not required for every statement, so the figure is more likely to be too low than too high.
- **Leaving statements out raises the figure.** The 746 left-out statements were agreed by two models but not checked by job holders. Without leaving them out, the average would be 59% (1,523 occupations scored).
- **"Helps with" is not "can do".** A statement counts as covered when AI can help with part of it, such as preparing records, drafting, explaining or checking. It doesn't mean the duty can be handed to AI or that a job is at risk.
- **Official lists are mostly American.** O\*NET describes US jobs. Regional work is in our lists, but it can only raise coverage if it matches an official statement.
- **Granularity varies.** Some official statements are broad and some narrow, and codes shared by several of our occupations make some denominators long. Industry figures are more stable than single occupations. Bootstrapped 90% intervals for industry ranks typically spanned 6 to 10 places in version 2026-11-09.1, and more for small industries.
- **Some occupations may be over- or underrated compared with outside estimates,** for example clerical and front-desk jobs whose lists are short, or healthcare, where documentation and explanation tasks cover many official duties.

## Supporting columns

- `tasks`: the number of tasks AI can help with on the occupation's own list. Shared common tasks are not counted here: each is one card used by many occupations, and counting it per occupation would repeat it. It measures breadth, and correlated with outside estimates about as well as the headline (+0.54 with GPT-4 exposure in version 2026-11-09). The count depends on how finely the list is split, so it isn't the headline.
- `weekly_ai_tasks`: how many of those tasks come up at least weekly.
- `ready_to_use_pct`: the share of listed tasks where AI's result is close to ready to use. It describes the kind of help, not how much. Writing up settled facts usually scores high. Analysis, design and judgment calls score lower. Don't use it to rank occupations or industries.
- `weekly_or_more_pct`, `for_others_pct`: shares of the listed tasks.

## Other notes

- Task lists were drafted by AI from official occupational sources such as O\*NET and ESCO and from common work in each region, then reviewed by a second model and checked by script.
- "Close to ready to use" and "how often it comes up" are estimates made to one shared standard when the lists were generated. They are not survey or measured results.
- Industries start from ISCO minor groups and were then adjusted by working community. Grouping involves judgment, so small gaps between industries should not be over-read.
- Some occupations are still being completed, and figures change as content is updated. Cite the version date.

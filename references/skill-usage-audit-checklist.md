> This file is a detailed sub-volume of `project-kickoff-prep` — used for the "skill usage audit" at project wrap-up; the entry point is in the parent `SKILL.md §5 read-on-demand table`. It is a data-type file and does not carry the three-line header.

# Skill Usage Audit Checklist

Verdicts: A called / complied, B missed but would improve quality, C not applicable (reason required).

## I. Top 12 (ordered by impact on quality)

| # | Trigger signal | Skill | Which step to use it in | Verdict |
| --- | --- | --- | --- | --- |
| 1 | Project brief skips ① researching the target persona / leaves "UI + debug" and "verification · small step" / §V forbids fabricating questions and guessing | project-kickoff-prep (own sub-steps) | Throughout the project brief | B |
| 2 | Self-check reader perspective, AI tone, engineering fields before pushing a delivery view | AI-trace diagnosis and rewrite | Before delivery | B |
| 3 | Large data packs (course bonus packs / research data packs / thousands of verbatim transcripts), zero keyword hits | (formerly large-file reading, removed 2026-11-16, no successor) | Content screening | C (skill removed, not applicable) |
| 4 | Close reading and skeleton of a single data point | (formerly organize-large-text, removed 2026-11-16, no successor) | Writing articles | C (skill removed, not applicable) |
| 5 | Only used the automated-task prompt pattern, lessons not solidified | skill · retrospective-distillation chapter (core) | Wrap-up | B |
| 6 | Skill mirrors / plugin multi-version snapshots not inspected, skill pointer paths mixed | skill · healthcheck chapter (core) | Wrap-up / periodic | B |
| 7 | Identified SPA and login-state alternate routes but stopped at "pending decision" | playwright-cli | After gate identification | B |
| 8 | Handling csv/tsv but only reading the first bytes as text and counting | workbuddy-office-routing + workbuddy-sheetagent | Data inventory | B |
| 9 | "Won't imitate other platforms' layouts" / "you don't even ask" / layout direction not consulted | huashu-design / frontend-slides / dbs-title-cover-intro / dbs-benchmark | Layout standards | B |
| 10 | Large amount of md source-of-truth handwritten rules, line-number pointers broken | (formerly obsidian-markdown, removed 2026-11-19, no successor) | Writing to disk | C (skill removed, not applicable) |
| 11 | Delivery vehicle selection did not enumerate native library / cloud drive / native tables | library | Gate 0 of the project brief | B |
| 12 | Deleting scripts / automated-task prompts / overriding hard gates, without independent security review | skills security audit (skills-sec-audit) | Before enabling the closed loop | B |

## II. Secondary 13–18

| # | Signal | Skill |
| --- | --- | --- |
| 13 | Delivery vehicle is docx/pptx/new spreadsheet | workbuddy-docx / workbuddy-pptx / workbuddy-sheet-generation |
| 14 | Feishu document body structure and markdown conversion | lark-doc / lark-markdown (core) |
| 15 | Multiple scripts produced at once, no TDD / root-cause flow | (formerly code-refactoring, removed 2026-11-19, no successor) / superpowers |
| 16 | Layered adjudication of source-of-truth vs method-of-truth |清淡学习 · material-organization chapter |
| 17 | Reading benchmark web pages to extract conventions | defuddle |
| 18 | Decisions made with no owner + due date, gates with no deadline | (formerly meeting-minutes, removed 2026-11-19, no successor) |

## III. Special checks (called but used off-target)

| Skill | Verdict | Deviation |
| --- | --- | --- |
| workbuddy-office-routing | B | Missed; should load the routing gate before handling csv |
| workbuddy-local-office-edit | C | Not applicable: delivery vehicle is a cloud doc, no local Office file opened for editing |
| library | B | Missed; delivery vehicle selection did not compare the native workspace |
| (formerly obsidian-markdown, removed 2026-11-19, no successor) | C (skill removed, not applicable) | Missed; frontmatter / wikilinks / pointers of large md files written by hand |
| knowledge base · build | A | Only ran healthcheck, did not run the four-fact-zone index itself (project intentionally stays out of `_retrieval/`) |
| knowledge base · search | A | Pointer written with a user-level path, mixed with project-level `skills/` pointer |
| skill · healthcheck chapter | A+B | Used the `automated-task prompt` pattern, did not run the core inspection |
| 清淡学习 · teaching chapter | A | Off-label: brief follow-up questions hung on the learning skill, not internalized into the project-kickoff skill |
| rule implementation | A | Seven steps compressed: no independent six-dimension self-check record, backup overwritten by user decision |

## IV. Maintenance

- Write a reason for every A/B/C verdict; C must state "why not applicable".
- Skill names get added / removed / renamed → inspect this sub-volume periodically; the source of truth does not write skill names (`system/PROCEDURES.md §四`).
- After each new project wraps up, append newly found missed-call items to §I / §II, and sync the pointer in `SKILL.md §5 read-on-demand table` (do not change the rule text).

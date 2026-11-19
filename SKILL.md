---
name: project-kickoff-prep
description: >-
  Turns a vague "I want to build X" into an AI-executable requirements package.
  Use when the user says "help me build X / write me a scraper / I want a tool, agent, app, or mini program / where do I start / help me sort out the requirements / what is the workflow / what data should be stored", or when requirements are vague before starting a task and it is unclear who it is for, what problem it solves, or where it lives.
  Not for cases where the plan is settled and only coding remains (→ superpowers), authoring a skill (→ the skill-authoring chapter of `skill`), pure research (→ 调研收集 / research collection), or pure Q&A.
agent_created: true
---

# Project Kickoff Prep

> **Use when**: Before starting a task, turn a vague idea into an AI-executable requirements package; this file keeps only triggers / routing / gates / stages / red lines; details are in `references/`, read on demand.
> **Triggers**: I want to build X, help me sort out the requirements, who is it for, where does it live, what data is stored, goal in three lines, workflow, first small step.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/`
> **Boundary**: No coding, no research, no Q&A; if the plan is settled, hand off to superpowers; maintenance steps stay out of the execution context.

> **Constraint layers (read first)**: The step order, stage gates, and process orchestration in this file are **reference paths (soft constraints)** — they may be adjusted, merged, or skipped based on the situation.
> **Hard constraints live only in the results**: output definitions, acceptance criteria, acceptance checklists, evidence requirements, and the red lines marked in this file are never relaxed or omitted. Go through the acceptance checklist item by item; missing one item means the loop is not closed.

Core principle: **the ceiling of AI output = clarity of requirements.** This skill asks out the missing information, writes it into files, and confirms it step by step.
Status, hands-on progress, open items, verification records, and dates are not part of this file; they are kept separately by the maintainer.

## 0. Entry routing (first decide whether to run, and how heavy)

- If one sentence already answers "who it is for / what problem it solves / where it lives / what data is stored" → **do not run this skill**.
- Plan settled and only coding remains → `superpowers`; authoring a skill → `skill` (skill-authoring chapter); pure research → `调研收集` (research collection); pure Q&A → answer directly.
- **Small project** (single file, one-off, reversible if wrong) → **lightweight mode**: only do gates + ④ + ⑥, no ledger, no four-stage wrap-up.
- Everything else → full flow (gates + ①–⑥ + ledger).
- The higher the cost, the fuller the gates: irreversible changes / involvement of permissions or sensitive information / compliance red lines → **lightweight mode is not allowed**.

## 1. Gates (align first; order is adjustable)

- **G1 Goal in three lines**: who it is for / what problem it solves / what counts as done. Usually one question at a time, at most 3 questions, written as three lines for alignment (whether to confirm line by line is a situational judgment).
- **G2 Delivery vehicle**: platform + form + filename + location of the source of truth.
- If the user has already given it, adopt it directly without rephrasing and re-asking; only come back to confirm when a same-named item is found to already exist.
- If it cannot be answered → mark 【Assumption】, write it into the project brief and add it to the items to confirm; **never fabricate, never take irreversible action on an assumption**.
- If the three lines are imprecise, or still vague after 3 questions → see the full interview in `references/gates-and-interview.md`.

## 2. Six stages

| Stage | Question to answer | Output | Pass criterion |
|---|---|---|---|
| ① Understand people | Who uses it? Frequent needs? Real problem? | Persona + real problem | Can write "for whom, solving what" with evidence sources |
| ② Map the workflow | How does a human do it without AI? | Numbered step table | Each step marks executor / reviewer / where exceptions go |
| ③ Data | What is stored? How is it related? | Field table + unique key | Every downstream output field has a source |
| ④ Engineering-grade requirements | How to hand it to AI? | Filled-in requirements template | Passes the requirements checklist |
| ⑤ Tools + skills + shell | How does AI take action? | Tool cards + skill | Each tool has a single responsibility and fixed JSON output |
| ⑥ First small step | Which piece to build first? | Minimum runnable artifact | Runs on real input, output matches the agreed structure |

- If stuck → pick a template with `problem-templates`, do not think bare or force fabrication.
- ①–③ can be advanced in the same batch; ④⑤⑥ are best done separately (whether to merge is a situational judgment).
- A criterion not met = this stage is not complete (result criteria are not relaxed); whether to move to the next stage is a situational judgment, not an automatic halt on failure.

## 3. Wrap-up of each stage (four-part format)

Stage goal / results (paths only) / items needing confirmation / next stage scope (the four-part format is a reference wrap-up format). **Whether to wait for user confirmation is a situational judgment** — do not halt over lack of confirmation, no mandatory gate is set here.
Lightweight mode skips the four-part format; wrap up with one line: "what was done / evidence it runs / any leftovers".

## 4. Red lines

- **No fabrication**: personas / data / requirements / goals — ask, do not guess.
- **Confirm before acting**: confirmation cadence is in §3, no gate is repeated here.
- **Build only one first**: the first small step builds one piece only; expand after it runs.
- **Do not reinvent the wheel**: reuse existing skills / tools / foundations first.

## 5. Read on demand (read when used, do not preload)

| At this step | Read |
|---|---|
| Gate interview not penetrating | `references/gates-and-interview.md` |
| ④ write requirements | `references/requirements-template.md` |
| ⑤ seal tools / write a skill | `references/tool-cards-and-six-parts.md` |
| ⑤ build the runtime shell | `references/harness-shell.md` |
| Start a new project directory / write the ledger | `references/project-directory-skeleton.md` |
| Hitting pitfalls / translating a workflow | `references/antipatterns-and-examples.md` |
| Audit skill usage at project wrap-up | `references/skill-usage-audit-checklist.md` |
| Maintain this skill (maintainers only) | `references/library-maintenance-checklist.md` |

## Appendix: seams with existing skills

- `superpowers`: coding execution after the plan is settled; the **adjudication** that gates come first is unchanged; enter its suggested gates only after the plan is settled.
- `skill` (skill-authoring chapter): if you want to solidify a workflow into a skill → hand off to it.
- `problem-templates`: if a stage is stuck → pick a template to solve it, do not think bare.
- `asset-review`: before delivery, re-check whether the artifact meets the bar → hand off to it.
- `调研收集` (research collection, Video Channel research chapter): ① when external comments / verbatim transcript data is needed → hand off to it.

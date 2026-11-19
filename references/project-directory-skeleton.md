# Project Directory Skeleton

> **Use when**: Setting up a directory for a new project, putting scattered project files back in place, or checking the project ledger rules.
> **Triggers**: project directory, create project, folder structure, skeleton, initialization, ledger, _log, put back in place.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/project-directory-skeleton.md`
> **Boundary**: Only manages new project directories and naming; the ledger's detailed rules have their source of truth in the project's `_log/_instructions.md`.

## I. Full skeleton map (directory numbers correspond one-to-one with stage numbers)

    <project name>/
    ├── 00-project-brief-<project name>.md   # mandatory: project brief
    ├── README.md                # mandatory: one-page navigation
    ├── _log/                    # mandatory: project ledger
    │   └── _instructions.md     # source of truth for ledger details
    ├── 01-people-and-problem/   # stage ①
    ├── 02-workflow/             # stage ②
    ├── 03-data/                 # stage ③
    ├── 04-requirements/         # stage ④
    ├── 05-tools-and-skills/     # stage ⑤
    └── 06-verification-and-delivery/  # stage ⑥

## II. Three mandatory items

- `00-project-brief-<project name>.md`: three-line goal (who it is for / what problem it solves / what counts as done) + delivery vehicle (platform + form + filename + location of source of truth) + acceptance criteria.
- `README.md`: one-page navigation — what this project is, how far it has progressed, file map (each line: path → what it manages).
- `_log/`: project ledger, details in `_log/_instructions.md` (this file keeps only a pointer, does not copy a second time).

## III. Four ledger categories (criteria)

| Category | Criterion |
|---|---|
| Open question | Awaiting the user's answer, not yet settled |
| Surprise | Confirmed to have happened, contrary to expectations |
| Issue | Confirmed defect that needs fixing |
| Result | Output verified as passed |

> Four categories are fixed, no fifth is added. Detailed rules for how to write each entry, split files by version, and avoid double-writing with the system log
> have their source of truth in the project's `_log/_instructions.md`, and are not repeated here.

## IV. Stage directories (build only the ones with output at that stage)

| Directory | Corresponding stage | What it holds |
|---|---|---|
| `01-people-and-problem/` | ① Understand people | Personas, tags, real problems, evidence sources |
| `02-workflow/` | ② Map the workflow | Numbered step table, flowcharts |
| `03-data/` | ③ Data | Field table, relationships, unique key |
| `04-requirements/` | ④ Engineering-grade requirements | Filled-in requirements template |
| `05-tools-and-skills/` | ⑤ Tools + skills + shell | Tool cards, six parts of a skill, Harness |
| `06-verification-and-delivery/` | ⑥ First small step | Minimum runnable artifact, run-through criteria, final deliverable |

- Output filenames carry the stage number and land in the corresponding directory; do not scatter them in the project root.
- **Do not create empty directories**: if there is no output, do not create the directory.
- Do not invent directory names on the spot: if what you want to place is not in the table above → ask the user first, do not invent `materials/`, `tmp/`, `attachments/`.

## V. Put-back-in-place rules

- Old projects are left alone by default; this specification only governs new projects.
- When the user explicitly asks to put things back in place: first produce a "original path → new path" list, confirm before moving, do not list and move at the same time.

## VI. Original version and source of truth

- The original version is read-only and never overwritten: corrections produce `xxx-corrected.md`; the original and old logs are read-only archives, not deleted.
- If the project has its own code of conduct, that takes precedence; this skeleton does not presuppose any library-specific files.

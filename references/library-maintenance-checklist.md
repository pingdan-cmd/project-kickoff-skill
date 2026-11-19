> **Use when**: Only when maintaining this skill (changing body text / changing the three-line header / running full verification); do not read this file when executing a project task.
> **Triggers**: library maintenance self-check, three-line header, single source of truth, pointer line numbers, six-dimension verdict, healthcheck.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/library-maintenance-checklist.md`
> **Boundary**: Only manages maintenance of the skill library files; does not enter the execution context, does not participate in project acceptance.

> This file carries over the "functional-file audit" that was at the end of the main file before the refactor. Project acceptance (skill usage audit) is in
> `references/skill-usage-audit-checklist.md`, pointed to by the SKILL.md §5 read-on-demand table. The two are not the same thing.

## Self-check checklist (go through item by item before delivery)

- [ ] The three-line header is under the H1, all three lines present, order unchanged, no date written (see `system/format-spec.md §I` for the applicability criterion)
- [ ] Single source of truth: each rule is written in one place only, others keep only a pointer, not copied a second time
- [ ] Pointers do not hardcode line numbers, only "file §section"; numbers that change and event dates are not written into rule text
- [ ] Six-dimension verdicts are gone through in order D1 → D6; if an earlier item fails, later ones need not be looked at (`system/file-responsibility-table.md §III`)
- [ ] New files can be reached from the parent entry; run the full `healthcheck.py`
- [ ] Status / progress / open items / verification / dates are kept in a separate maintainer changelog, not in SKILL.md and references
- [ ] After changing the frontmatter description, sync `skills/README.md` and `skills/problem-routing-table.md` (trigger wording takes the description as source of truth)
- [ ] Old files are not truly deleted: retired copies go wholesale into `.workbuddy/backup/<date>-<reason>/`, with a note in history

## Sources

- Three-line header: `AGENTS.md §IV`, `system/format-spec.md §I`
- Single source of truth / pointers: `system/PROCEDURES.md §III`, `§IV`
- Six-dimension verdict: `system/file-responsibility-table.md §III`
- Trigger triad: `skill/writing-spec/references/trigger-condition-spec.md`

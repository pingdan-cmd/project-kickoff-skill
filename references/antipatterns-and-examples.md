# Antipatterns and Examples

> **Use when**: A stage hits a pitfall and you want to check against antipatterns, or when mapping a workflow you need to translate "human actions" into technical requirements.
> **Triggers**: antipattern, pitfall, symptom and remedy, sales prospecting, five steps, translate into technical requirements, workflow example.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/antipatterns-and-examples.md`
> **Boundary**: Only gives comparisons and examples; does not replace stage criteria, does not add process gates.

## I. Antipatterns (symptom → remedy)

| Symptom | Why it is bad | Remedy |
|---|---|---|
| Jumping straight to "help me build X" | Missing who / what problem / where, output nobody wants | Return to gate G1 to fill the three-line goal, mark 【Assumption】 if unanswerable |
| Requirements lack "build only one first" | Doing it big at once, cannot localize problems | Write the first small step into the requirements template, attach definition of done and failure fallback |
| Only writing requirements, no tools / skill / shell sealed | AI can only chat, cannot do the work | Stage ⑤ completes the tool cards and the six parts of the skill |
| Skipping data and writing features directly | Results cannot be reused or incremented | Stage ③ first produces a field table + unique key; mark skipped if no data is produced |
| Writing the workflow as a wish list | Not executable steps, the model drifts when planning on its own | Stage ② marks executor / reviewer / where exceptions go for each step |
| Writing the same rule into multiple files | Change one, miss another, conflicts arise | Write the source of truth in one place only, keep pointers elsewhere |
| Writing throttling / seed layer as mandatory for all projects | Crawler-specific constraints, misleading for non-collection projects | Requirements template §II variants are picked as needed; the common core does not keep them |

## II. Example: sales prospecting in five steps → technical requirements

| What sales does without AI | Translated into technical requirements |
|---|---|
| 1 Log in | Login module |
| 2 Search keywords and scroll posts | Collection (post search) |
| 3 Scan the comments to find people | Collect comments |
| 4 View profile / interests | Collect profile / likes and saves |
| 5 Decide whether to contact | Agent analysis (needs / personality / angle) |

The five human steps directly tell you what the technology must do. **First sort out the human actions, and the technical requirements surface on their own.**

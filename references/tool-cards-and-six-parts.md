# Tool Cards and the Six Parts of a Skill

> **Use when**: Stage ④ — seal requirements into tool cards, write the six parts of a skill.
> **Triggers**: tool card, function calling, inputs and outputs, six parts of a skill, cognitive asset, evidence verbatim, engineering hard rules.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/tool-cards-and-six-parts.md`
> **Boundary**: Only gives fill-in templates and a quality checklist; does not write the judgment method of step ③ for the user.

## I. Tool cards (one card per tool)

Standard function calling; fill the 【】 placeholders for this project.

    Tool name: [verb_noun, e.g. search_notes]
    Purpose: [one sentence: what this tool does]
    Inputs: [param_name(type, meaning)]
    Outputs: [JSON structure: [{field_name(type, meaning)}]]
    When to use: [what scenario / what signal triggers a call]
    When not to use: [boundary: in what situations it should not be called]

## II. The six parts of a skill (the truly valuable part that AI cannot replace)

    ① Role: You are a senior 【identity】 in 【domain】, skilled at 【judging what from what material】.
    ② Input: [structured material list: field names + sources]
    ③ Analysis steps (reason step by step, do not skip — this is your cognitive asset):
       1. [look at what first → how to judge]
       2. [look at what next → how to judge]
       3. ...
    ④ Output format (strict JSON, no field may be missing):
       { "field1": "…", "evidence_verbatim": ["…"] }   // evidence must come from the input, never fabricated
    ⑤ Guardrails: conclusions must be backed by input evidence; if information is insufficient, write "insufficient data, cannot judge", never speculate.
            [privilege boundary for this scenario, e.g. analysis only, do not send / pay on the user's behalf]
    ⑥ Example: (paste a real example you did by hand: input looks like this → output looks like this)

①②④⑤⑥ are the shell, which AI can fill in; **the method in step ③ — what to look at first, what next, what to care about — is the cognitive asset, and can only come from the mind of someone who has done the work.**

## III. Engineering hard rules

- Require JSON output → so results can be fed directly into a UI as tables.
- Require "evidence verbatim" + "say you don't know when information is insufficient" → prevent hallucination, anchor conclusions to evidence.
- Give one example → a step up in stability.

## IV. Quality checklist (go through item by item after delivery)

- [ ] Run-through on real input: run once on real input, produces a result directly (not "looks right")
- [ ] Single responsibility: one tool does one thing; this delivery contains only "the one built first"
- [ ] Structure matches: outputs strictly match the JSON structure in the card, no field missing or wrong
- [ ] Evidence traceable: conclusions can point to input sources; say so honestly when information is insufficient, no speculation
- [ ] Delivery format: structured result / fixed fields, not a prose passage
- [ ] Compliance in effect: authorization / platform / privacy / privilege boundaries really running (not just written in the requirements)

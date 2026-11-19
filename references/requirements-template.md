# Requirements Template

> **Use when**: Stage ④ — write the requirements into an engineering-grade document that can be handed to AI.
> **Triggers**: requirements template, engineering-grade requirements, fill-in template, delivery vehicle, role and goal, feature list, qualification check.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/requirements-template.md`
> **Boundary**: Only gives the template and checklist; does not fill in content for the user, does not guess goals, does not implement multiple features at once.

## I. Common core (fill in for every task)

Fill the 【】 placeholders for this project; do not copy the example verbatim; if you cannot go on, stop — do not force fabrication (if stuck → `problem-templates`).

    # Delivery vehicle (output definition, ultimately mandatory)
    Platform: [fill in the user's own words, do not invent for him]
    Form: [cloud doc / note / page / folder / script]
    Name: [the filename given by the user]
    Where the source of truth lives: [path to the single source of truth]
    What the delivery view includes and excludes: [one-line boundary]

    # Role
    You are a senior 【domain + identity】.

    # Goal
    Business goal: for 【who】 doing 【what】 provide 【what support】, producing 【form】, with 【criterion】 counting as done.
    Engineering goal: based on 【project name / link / existing foundation】 implement 【module name】; do not reinvent the wheel.

    # Functional requirements (implement one by one, verify one by one)
    First check skills/README.md / 问题路由表.md (problem routing table); route and reuse any ready-made capability; only if none exists, list them one by one:
    【function_name(inputs) → returns what】 × N items

    # Data
    What is stored: [field table]
    How it is linked: [relationships / unique key]
    (Tasks that produce no persistent data may skip this whole section)

    # Compliance red lines (list only those applicable to this project, see §III)
    [Authorization boundary / platform rules / personal information protection / privilege-escalation boundary]

    # Delivery method
    Delivery = directly runnable artifact + structured result (fixed fields, directly readable downstream).
    First implement only 【the first function】, run-through criterion: 【definition of done】, on failure: 【failure fallback】; I will then decide whether to do the next one.

## II. Optional variants (pick by task type, not mandatory)

### Crawler / collection

- Request throttling: per-minute cap + random interval; retry on failure: exponential backoff, after N attempts log and skip.
- Two data layers: seed layer (store leads first) + detail layer (after deep digging); dedup key, resume marker (seed carries status).
- Login state / proxy go through configuration, not hardcoded in code.

### Document / content

- Delivery form: docx / pptx / table / web page; decide the source of layout before filling in content.
- Citations and sources: every conclusion can point to a source; if none, mark "not mentioned", do not speculate.

### Analysis / report

- Input fields + sources fixed; output strictly JSON, including an "evidence verbatim" field.
- If information is insufficient, write "insufficient data, cannot judge"; never make assumptions.

## III. Common compliance bottom line (all tasks)

- Authorization: only process data and platform content the user has the right to process.
- Platform rules: comply with the target platform's terms of service and access rate limits.
- Personal information: do not collect, retain, or output privacy-sensitive information.
- Privilege boundary: only perform authorized actions (e.g. analysis only, do not send / pay / publish on the user's behalf).

## IV. Qualification check (go through item by item before handing off)

- [ ] Role / goal filled in for this project, including "who it is for / output form / criterion"
- [ ] Routing table checked first, ready-made capabilities reused, no reinventing the wheel
- [ ] Each feature is verifiable (input / output criteria), and only one is built first
- [ ] Data fields, relationships, unique key complete (mark skipped if no data produced)
- [ ] Four compliance items present as applicable (authorization / platform / personal information / privilege)
- [ ] Delivery is a structured result with fixed fields
- [ ] First small step has a definition of done and a failure fallback
- [ ] Requires human and AI working together: plan by the human, construction by AI, key confirmations reviewed by a human, decisions made by the decision-maker
- [ ] Three-line goal and delivery vehicle settled (see SKILL.md §1, no gate repeated here)

> Definition of done: a verifiable criterion, not a vague statement like "performance should be good".
> Failure fallback: which step to fall back to when it cannot run, what evidence to keep, when to stop retrying.

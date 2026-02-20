# Contributing a HEARTBEAT.md Template

Thanks for wanting to contribute. These templates live or die by how genuinely useful they are to real people — so quality over quantity.

## What makes a good template

**Good:**
- Solves a real, specific workflow problem
- Checks are things a human would actually care about
- Hard rules section prevents the most obvious foot-guns for that use case
- Plain English where possible — not everyone reading this is a developer

**Skip it if:**
- It's a minor variation of an existing template (just edit the existing one)
- The checks require elevated permissions or external API calls
- It instructs Claude to take action without confirmation (violates the core safety model)

## How to submit

1. Fork the repo
2. Copy `templates/01-solo-dev.md` as a starting point
3. Name your file `NN-descriptive-name.md` (use the next available number)
4. Add it to the table in `README.md`
5. Open a PR with a one-line description of who it's for

## Template header format

Every template needs this comment block at the top:

```markdown
<!--
  Template: Short display name
  Best for: One sentence on who this serves
  Interval: Recommended tinman interval (15 / 30 / 60 min)
  Mode: notify-only (almost always) or active
-->
```

## The one non-negotiable

Every template must have a **Hard rules** section that explicitly prohibits the most dangerous actions for that context. If you're not sure what to put there, ask yourself: "what's the worst thing Claude could accidentally do while running this checklist?" — then prohibit it.

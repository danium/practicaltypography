# Contributing

This repo distills Butterick's *Practical Typography* into an agent skill. Contributions are welcome, and the bar is specific — please read it before writing.

## What we accept

- **Rule corrections**, with provenance. If the skill misstates a rule, cite the chapter on [practicaltypography.com](https://practicaltypography.com/) that shows the correct one.
- **New coverage** for media or elements the skill handles thinly (e.g., footnotes, forms, ebooks) — sourced from the book's chapters, or explicitly marked as a deviation with reasoning.
- **New presets** for the user-preference protocol, with real-world grounding (what actual publications ship, measured — not guessed).
- **Fixes**: broken links, unclear steps, typos, structural problems.

## The quality bar

**Every rule traces to Butterick — or wears a deviation flag.** The skill's authority comes from its source. A rule that is neither sourced nor flagged as a deliberate, reasoned deviation is a bug, even if it's good advice.

**Ranges stay ranges.** Butterick gives ranges (15–25px, 120–145%, 45–90ch) because many solutions work. Don't narrow them to single "best" values, and don't add false precision the source doesn't carry.

**Edits are tested before they ship.** This skill was built with TDD for documentation: scenarios run against a baseline without the change, the failure documented, the change written against that failure, then re-tested. An edit PR should state what an agent gets wrong *without* your change — ideally with a subagent transcript. "It reads better" is not a failing test.

**Worked examples come from real sessions.** Do not compose a plausible transcript — the difference is visible, and a fabricated example undermines the demo's credibility.

**Scope discipline.** The skill prescribes typography, not tooling. Reveal.js config, hex color palettes, framework specifics stay out of `SKILL.md`; if they're genuinely needed, they belong in `media.md` as clearly-scoped implementation notes.

## Compatibility rules

These skills run across different agents. Keep them portable:

- **Frontmatter is `name` and `description` only.** No other keys.
- **No tool-specific syntax** in any skill body: no agent names, no slash-commands, no vendor-specific formatting conventions.
- **Relative paths only.** `SKILL.md` references its siblings as `fonts.md` and `media.md`, never absolute paths.
- **English only**, plain markdown.

## How to propose

1. **Open an issue first** for new coverage or a new preset. State the source chapter (or the deviation and its reasoning) and the scenario where agents currently fail without it.
2. **Then open a PR** meeting the quality bar above.

For corrections and fixes, a PR without a prior issue is fine — include the source citation in the PR description.

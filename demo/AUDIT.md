# Audit: demo/before.html → demo/after.html

The before page is a real vanilla-agent output (single prompt: "build me a blog post page, style it nicely" with draft content). It is deliberately unretouched — including its choices that were already good (capped column, en-dashed ranges, curly quotes). The audit below is the typography skill's findings, in its reporting format; after.html applies the fixes with content untouched.

## Findings

- `[MAJOR]` body line-height: 1.7 — above the 1.2–1.45 body range → **1.4** at **18px** (was 16px default)
- `[MAJOR]` body font stack: Georgia-first (C-list, screen-era) with Times New Roman fallback → **Charter**-first, Georgia demoted to fallback
- `[MINOR]` UI font stacks: Arial fallback (F-list) → Seravek / Gill Sans
- `[MINOR]` kicker tracking: 0.18em — past the 0.05–0.12em caps ceiling → **0.1em**
- `[MINOR]` meta line: letterspaced lowercase (0.04em) → tracking removed; 2px rule → **1px**
- `[MINOR]` thead: letterspaced lowercase headers on a dark band + zebra stripes → plain bold headers, thin 1px rules, no stripes ("see the data, not the lines"); `tabular-nums lining-nums` on the whole table
- `[MINOR]` intro: italic across a full paragraph — emphasis is for short bits → roman, slightly larger, muted
- `[MINOR]` blockquote: tint box + italic + color shift stacked on the border → structural distinction only (border-left)
- `[MINOR]` h2: decorative bar *below* the heading — a rule belongs above, and white space separates better → removed; heading scale normalized to ≈1.25× body, display leading on h1
- `[MINOR]` closing: centered running text in an inverse box → left-aligned, thin top rule
- `[MINOR]` characters: `...` → … (single ellipsis character, word-spaced); nonbreaking space after the em dash in the citation

## Top three fixes doing the most damage

1. Line-height 1.7 → 1.4 with the size raised to 18px — the whole page tightens from "template" to "typeset".
2. Charter replacing Georgia — same warmth, sharper on modern screens.
3. Table de-decoration — the dark header band and stripes were the loudest element on the page; the data now leads.

Left alone on purpose: the palette, the card layout, the grammar of the source text ("a extraction problem" is the author's), and the author's `(c)` mark — content is not the skill's jurisdiction.

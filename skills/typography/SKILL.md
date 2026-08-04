---
name: typography
description: Use when styling or reviewing text in any medium — font size, line spacing, line length, or font choices; headings, emphasis, caps, or quotes in CSS or documents; slides, résumés, emails, or data tables that must read well; auditing a page or deck that looks unprofessional or amateurish; or when a user's stated aesthetic preferences conflict with typographic convention
---

# Typography

Distilled from Butterick's Practical Typography (practicaltypography.com). Master criterion: **good typography reinforces the meaning of the text** — it conserves the reader's finite attention. Body text first: most of any page is body text, and four decisions dominate it — point size, line spacing, line length, font. Every rule here is a range with many right answers, and a benchmark rather than a gate: deviate for a reason, never from habit, and when in doubt move toward the benchmark.

## Scope — rules attach to text roles

The big-four ranges are calibrated for body text at reading distance. Other roles have their own numbers; applying body ranges to display or slide type is itself a violation.

| Role | Size | Leading | Measure | Tracking |
|---|---|---|---|---|
| **Body** (running prose) | 15–25px web / 10–12pt print | 1.2–1.45 | 45–90 ch | normal |
| **Display** (hero, titles, ≥ ~2× body) | by eye | 1.0–1.2 | ≤ ~25 ch | 0 to −0.02em |
| **Small/UI** (nav, captions, labels) | 0.8–0.9× body | 1.2–1.45 | short | normal |
| **Slides** (projected) | base size so 12–15 lines *would* fit; keep identical across slides | 1.25–1.4 | 20–40 ch | normal |

Caps or small caps in any role: always add `letter-spacing: 0.05em–0.12em` and keep runs under one line. Never letterspace lowercase.

## Body text contract

```css
.prose {
  font-family: Charter, 'Bitstream Charter', 'Sitka Text', Cambria, Georgia, serif;
  font-size: 18px;      /* 15–25px; fonts differ at equal sizes — judge by eye */
  line-height: 1.4;     /* 120–145% */
  max-width: 60ch;      /* 45–90 chars incl. spaces ≈ 2–3 lowercase alphabets */
  font-kerning: normal; /* kerning always on */
}
```

Picking a point inside a range: adjust in the smallest visible increments; when unsure, render both and compare by eye; shrink size → also shrink leading and measure; print body = black text, serif recommended; screen body may be dark gray, serif or sans equally fine.

## Auditing

When reviewing existing typography, check in this order (highest impact first) and report findings as `[MAJOR|MINOR] element: violation → fix (corrected value)`:

1. **Body big four** — size, leading, measure, font, each against the role's range. Uncapped line length is the most common web failure.
2. **Alignment and paragraphs** — indent XOR paragraph space (never both); justification only with hyphenation; centered running text; spacing built from empty returns or stacked spaces.
3. **Headings** — count of levels, underline, untracked caps, size jumps, space above vs. below, splits from following text.
4. **Emphasis** — bold+italic stacking, underline as emphasis, emphasis runs longer than a phrase, fake small caps.
5. **Characters** — straight quotes, `--`, `...`, `(c)`, sentence double-spaces, hyphens where dashes belong.
6. **Supporting elements** — code, tables, captions, links, blockquotes against the table below.

MAJOR = any big-four breach, avoid-list font, double paragraph signal, underlined or untracked-caps headings, justify without hyphens. MINOR = character hygiene, within-range tuning, supporting elements. Close every audit with: corrected values (code block or edit list) and the three fixes doing the most damage.

## User preferences and adjustment

When the user states an aesthetic goal, a reference site, or explicit numbers, their intent governs; the contract is the floor you build up from, not a gate.

- A named reference beats a quoted number — reproduce what the reference actually ships (Medium: 21px, line-height ≈1.58, airy feel from paragraph space and narrow measure, not loose leading).
- Deliver the requested look; name any benchmark deviation once, with the single value to change if they disagree; then defer to their choice.
- When the user wants options, offer presets:

| Preset | Body | Feel |
|---|---|---|
| **Bookish** (Butterick default) | 17–18px · 1.3–1.4 · 55–65ch · serif · first-line indents | dense, classic print |
| **Airy modern web** | 19–21px · 1.5–1.6 · 58–68ch · serif or sans · 1.4–1.7em ¶ space | Medium/Substack; leading deliberately above Butterick's 1.45 — established screen practice at 19px+ |
| **Compact docs** | 15–17px · 1.35–1.45 · 65–80ch · sans or serif · 0.6–0.8em ¶ space | technical documentation |

## Supporting elements

| Element | Spec |
|---|---|
| Headings | ≤3 levels (2 better); scale ≈ 1.6× / 1.25× / 1.0× body, bold; space above > below (≈1.5em / 0.5em); tiered numbers (1.1.1) if numbered, never romanettes |
| Code block | shortlisted mono, 0.85–0.95× prose, leading 1.4–1.5; may exceed measure — scroll it, never wrap or shrink |
| Inline code | 0.9–0.95em with subtle background |
| Tables | 0.85–0.9× body; `font-variant-numeric: tabular-nums lining-nums`; quantities right-aligned (leading zero below 1, keep trailing zeros — precision, commas once a column passes 10,000), identifiers left; rules 0.5–1pt solid — prefer white space to borders; labels formatted last |
| Captions, bylines, meta | 0.85–0.9× body, muted color, leading ≈1.3 |
| Blockquote | structural distinction — indent, border-left, or size; not bold+italic |
| Callout/admonition | body-size prose, distinguished structurally (border-left ~3px or tint, not emphasis); caps label ≈0.8em tracked +0.05–0.12em |
| Links | web underline or color; color only clickable text, nothing else |
| Nav/UI text | 0.8–0.9× body, no underline; caps group-labels tracked |

## Characters — never typewriter approximations

| Typed | Correct |
|---|---|
| "x" 'x' | “x” ‘x’ curly (`&ldquo;` …); apostrophes point down — ’70s, rock ’n’ roll, not ‘70s |
| `--`, ` - ` as pause | — em dash, set closed (`&mdash;`) |
| 1880-1912, pages 330-39, Sarbanes-Oxley | en dash for ranges and paired names (`&ndash;`); but “from 1880 to 1912” |
| ... | … one character (`&hellip;`) |
| (c) (TM) (R) | © ™ ® — ™/® superscript, no space before; ©&nbsp;2026 with nonbreaking space |
| 3x5, -2 | 8.5″ × 14″ uses ×; minus is − not hyphen |
| 5'10" | straight marks — the one correct use of straight quotes |

One space between sentences, always. Nonbreaking space after §, ¶, and before numeric refs (Fig. 23, Ex. A). Hyphens stay in compounds and phrasal adjectives (five-dollar bills) but not after -ly adverbs or most prefixes (nonprofit). One exclamation point per three pages.

## Fonts

Shortlists in [fonts.md](fonts.md) (full letter-graded lists, free fonts, alternatives). Compressed: avoid Times New Roman, Arial, Tahoma, Trebuchet, Verdana, Courier, and all novelty/script faces; A-list system fonts include Charter, Palatino, Hoefler Text, Helvetica, Garamond, Gill Sans, Iowan Old Style, Seravek; endorsed free: Charter, Source Serif, Source Code, Cooper Hewitt, IBM Plex, Fira Mono.

Judging an unlisted font (lists are exemplary, not exhaustive): professionally designed and hinted, full weights + true italics + real small caps or at least tabular figures, not overexposed as a platform default, role-appropriate (screen-optimized faces stay on screen; print and PDF get print-grade faces). Inter, for example, passes for screen use. Max two fonts per document (three rarely); each font keeps one consistent role.

## Common mistakes

| Mistake | Fix |
|---|---|
| `line-height: 1.6+` on 16px body by default | 1.3–1.45 — or move size to 19px+ and call it the airy preset |
| Text column spans viewport | cap measure at 45–90ch |
| Body ranges applied to hero/slide titles | display role: leading 1.0–1.2, short measure |
| `text-indent` + paragraph margin | one or the other |
| UPPERCASE without tracking | +0.05–0.12em, or drop caps |
| `text-align: justify` alone | add `hyphens: auto`, or left-align |
| Same size every slide impossible → auto-shrink | fixed base size, cut text instead |
| Bold+italic, underline emphasis | one signal, sparingly; underline = links only |
| Colored non-link text on web | color signals clickability — reserve it |

Per-medium specifics (print margins, slides, email, résumés, tables of numbers): [media.md](media.md).

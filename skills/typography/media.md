# Per-medium specifics

## Print documents

- Margins set line length. 1″ margins on letter paper are too small for proportional fonts — at 12pt use 1.5–2″ left/right; the real target is 45–90 characters, not inches. Bottom margin ≈0.25″ larger than top (optical centering). Asymmetric margins need ≥1″ difference to look intentional.
- Body: 10–12pt serif, black, leading 120–145% set as "Exactly" (Word's Single ≈117%, 1.5 ≈175%, Double ≈233% — all wrong; "Multiple" values 1.03–1.24 if you must).
- Columns: 2–3 on letter paper, never 4. Baselines must align across columns: paragraph space = 0 or a whole line.
- Widow/orphan control on only when problems appear; blank space at page bottoms is normal. Keep-with-next always on headings. One hard page break, never stacked returns; space from space-before/after settings, never empty paragraphs.
- Rules/borders: try white space first; 0.5–1pt solid; rule above a heading, not below.
- Line spacing, not point size, is the lever for fitting text to a page count.

## Presentations (slides)

Slides are glanced at, not read — closer to a billboard than a document.

- **Dark room: pure black background.** Type starts at ~50% gray and brightens only until legible — never pure white on black (dilated pupils, eye strain). Thin/light sans faces work best (fewer photons); pale accent colors over saturated ones.
- **Lit room:** soften contrast — light gray background or dark gray type.
- **Size calibration:** pick a base size such that 12–15 lines *would* fit the frame — then never put anywhere near that much on a slide. Keep the size identical on every slide, even one-liners; disable auto-shrink/auto-fit. If text doesn't fit, cut words, not points. (At 1080p this lands body around 40–56px, titles 80–120px.)
- Leading a bit looser than print (≈1.25–1.4 body; 1.05–1.2 titles); generous empty space; text block narrower than the frame; left-align, avoid centered text; drop bullet characters when every item is a single line.
- 3 type roles max: title, body, small caps/label line (attributions, footers) — tracked +5–12%.

## Web

Butterick's web chapter is principles: the body-text numbers apply to the web unchanged; 1990s habits (tiny text, huge headings, edge-to-edge columns, Arial/Georgia/Verdana-only) are cargo cult. Borrow visual ideas from print; templates swapped "ugly for boring."

- No universal margin — target the measure; edge-to-edge text is a 1994 leftover.
- Screen body may be dark gray instead of black (screens emit light) — but PDFs stay black.
- Underline nothing but links; color nothing but clickable text.
- Ligatures: let the engine apply them (`font-feature-settings`/default `liga`); never type ligature characters literally.

## Email

Fonts don't travel with the message; rendering is unpredictable. Either restrict to common system fonts with no spacing tricks, or treat email as a typography-free zone (plain text). Contact blocks as text, never images.

## Résumés

- Two pages beat one crammed page (students: one page). Print on separate sheets, not duplex. Send PDF, never .docx.
- Most important credentials visible on page 1; headings *smaller* relative to body (substance over labels scans better); generous margins → shorter lines; calm bullets; no Calibri/system defaults.
- Typos are the killer — ~90% of résumés have them; require reviewers to each supply three specific edits.

## Tables of numbers

Typography must mirror the numerical logic — digits of equal meaning align vertically.

- Tabular lining figures (`font-variant-numeric: tabular-nums lining-nums`).
- Quantities (money, measurements): right-align; leading zero below 1 ($0.49); trailing zeros carry precision — never strip or pad ("98.000 ≠ 98 pounds"); commas mandatory once a column spans 10,000 ($6,736 vs $16,736).
- Identifiers: zip codes left-align; phone numbers right-align. Ordinals and percentages are not quantities — don't sum or scale them.
- Column labels formatted last and may deviate from the column's alignment.
- Thin solid rules (0.5–1pt) or none — "see the data, not the lines"; adequate cell padding; even line spacing.

## Documents generally (the nine maxims)

1. Decide body text first. 2. Split the page into foreground and background — position, size, font, and color keep the hierarchy. 3. Adjust in the smallest visible increments. 4. When in doubt, try it both ways and judge by eye. 5. Consistency: same elements identical, different elements materially different. 6. Relate each new element to the existing ones (use a grid). 7. Keep it simple. 8. Imitate typography you admire. 9. Don't fear white space — work outward from the text, not inward from the edges.

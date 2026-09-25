---
name: Mia Andreu Portfolio — Drawing Set
description: Her work as an issued engineering drawing set on a teal blueprint ground. The home page is a cover sheet with a drawing index; every project, job, and program is a numbered sheet or row.
colors:
  ground: "#0E3F43"
  grid: "color-mix(in srgb, #EAF2EE 7%, transparent)"
  ink: "#EAF2EE"
  dim: "color-mix(in srgb, #EAF2EE 58%, #0E3F43)"
  hair: "color-mix(in srgb, #EAF2EE 28%, #0E3F43)"
  field: "color-mix(in srgb, #EAF2EE 10%, #0E3F43)"
  mark: "#FBCA89"
  sdg4: "#F2545B"
  sdg11: "#FFB454"
typography:
  display: "'Helvetica Neue', Helvetica, 'Arimo', Arial, sans-serif"
  body: "'Atkinson Hyperlegible Next', 'Atkinson Hyperlegible', Verdana, sans-serif"
  mono: "'B612 Mono', ui-monospace, 'SF Mono', Menlo, monospace"
rounded:
  tag: "2px"
  btn: "3px"
  cloud: "8px"
  round: "50%"
---

# DESIGN.md — Drawing Set

Replaces the prior "Line Map" transit world (retired 2026-09-24, user direction: switch to the Drawing Set direction, teal blueprint colorway). Product truth, content, and PRODUCT.md are unchanged; only the visual world changed.

## Overview

The site reads as an issued set of engineering drawings on a dark teal blueprint ground. The home page is a title/cover sheet with a drawing index; her work experience, education, GLASS Scholar record, and service each get their own numbered sheet below it; each project case study is its own full sheet. One accent color (sand) carries every mark; nothing else competes with it.

## Colors

### Primary
- `--ground` `#0E3F43` — the sheet itself, every page's field.
- `--ink` `#EAF2EE` — all linework: headings, body text, table rules, sheet borders, photo frames.
- `--mark` `#FBCA89` — the one accent. Sheet numbers, section numbers, hatch fill, list ticks, "View sheet" links, the plot-progress bar, focus/selection. Nothing else uses it.

### Neutral
- `--dim` — secondary text (captions, descriptions, dimmed metadata): ink mixed 58% into ground.
- `--hair` — table and row rules: ink mixed 28% into ground.
- `--field` — form input fill: ink mixed 10% into ground.
- `--grid` — the two-axis background grid: ink at 7% opacity, 26px cells. This is the blueprint-paper signature the direction was chosen for; it is structural to the world, not decorative filler (recorded exception: `codex-grid-background`).

### SDG tags
- `--sdg4` `#F2545B`, `--sdg11` `#FFB454` — official UN colors, lifted in lightness to read on the dark ground. Outlined chips (`border:1.5px solid currentColor`), not filled, so they sit quietly among the ink linework.

### Named Rules
- **One Mark Rule.** Sand is the only accent color anywhere on the site. The prior world colored each section with its own transit-line hue; that's retired. A drawing set uses one ink standard and one highlight color, never a rainbow of section colors.
- **Ink Does the Work Rule.** Hierarchy comes from weight, size, and rule-work (borders, hairlines), not from color. Color marks only what's actionable or measured (sheet numbers, links, hatch fill, goal tags).

## Typography

Three families, each with one job — this is deliberate, not drift: a real drawing set's title block uses a different hand than its body notes and its dimension strings.

- **Display** (Helvetica Neue, 700): names, headings, sheet titles, button and label text, table headers (`th`, `dt`).
- **Body** (Atkinson Hyperlegible Next, 400/500): all reading prose — descriptions, notes, bio, bullet items.
- **Mono** (B612 Mono, 400/700): sheet numbers (P-101, T-000…), station codes (HAN, NYC…), dimensions, dates, data-bar values, tag chips, and the numbered section prefix on case-study headings (`01 — Overview`). Reserved for measurements, codes, and counted content; never prose.

### Hierarchy
- `.name` — display 700, clamp(2.75rem, 5.2vw, 4.6rem), 0.92 line-height: her name on the cover.
- `.cs-title` — display 700, clamp(2rem, 4vw, 3.1rem): case-study titles.
- `.sheet-head h2` / case `h2` — display 700, clamp(1.35–2.5rem): sheet and section headings.
- `.stmt` / `.cs-lede` — body 500/400, ~1.05–1.25rem: statement and ledes.
- Body copy — 1.0625rem / 1.6, Atkinson.
- `.row .no`, `.sno`, `.cs-no b` — mono 700, sand: sheet numbers.
- `.lbl`, `.idx-h` — mono 700, 0.7–0.85rem, 0.1em tracking, dim or sand: drafting labels (short, uppercase — the tracking exemption named in the type-tracking rule).

### Named Rules
- **Numbers Are Real Rule.** Every sheet and row carries a real, meaningful number (T-000 cover, P-101–105 projects, W-101–103 work, A-101–102 study, GL-101 GLASS, S-101–106 service, C-000 contact). Case-study section headings auto-number via a CSS counter (`01 — Overview`), never hardcoded into the copy.
- **Refs Are Structural Rule.** The grid-reference ticks (1–6 across, A–D down) sit flush on the sheet's outline collar, because on a real drawing they mark the border itself — they are not content and are never inset from it. Decorative, `aria-hidden`, hidden under 760px.

## Layout

`.sheets` is a single centered column, max 1520px. Each section is a `.sheet`: a 1.5px ink border plus a second 1px outline offset by a collar gap (`--collar`, ~10–20px, fluid), the double-line frame of a real title block. The cover sheet (`.cover`) splits into a 1fr main column (name, statement, drawing index of the five projects) and a 320px title-block aside (photo, identity, sheet index nav, SDG tags, sheet number). Work, About & Study, GLASS, Service, and Contact are single sheets below it, each its own bordered unit with a sheet-head (title + sheet number) and content in `.rows` (record rows: number, title/description, meta/photo).

Case-study pages are one `.cs-sheet` per project: title + sheet number, a facts strip, a hero photo, then numbered body sections, closing with a "next sheet" link that cycles through all three.

### Named Rules
- **No Cards Rule.** Nothing is boxed individually. A sheet is the unit of enclosure; inside it, rows are separated by hairline rules, not borders or shadows.
- **One Standard Rule.** Every sheet — home and case-study alike — uses the same border/collar/refs/sheet-number anatomy. A visitor who has seen one sheet knows how to read all of them.

## Elevation & Depth

None. No shadows, no blur, no glass. Depth comes from the double-line border/collar and from hairline rules between rows — a drawing set has no z-axis.

## Shapes

- `.btn` — 3px radius (a drafted corner, not a pill).
- `.tag`, `.sdg` — 2px radius.
- `.cloud` (revision cloud) — 8px, dashed outline only.
- Photos, sheets, form fields — square corners throughout (0 or 2px), consistent with ruled linework. Only the round elements are the site-mark `.bullet` badges (circular, 50%) — everything else on the page is drafted at right angles.

## Components

### Buttons
`.btn-solid` — ink fill, ground text; hover fills sand. `.btn-line` — ink outline; hover fills ink. 1.5px borders, 3px radius, Helvetica 700.

### Rows (`.row`)
The drafting-record unit: a mono sheet number, a title/description/tools block, and either a photo plate (`.plate`, ink-framed, mono caption) or a right-aligned meta column (station code + dates + SDG tags). Used for every project, job, education entry, and service item.

### Data bars (`.bars` / `.bar-fill`)
Horizontal measured-quantity bars with a 45° hatch fill in sand (`repeating-linear-gradient`) — the drafting convention for a filled, measured region, not decoration (recorded exception: `repeating-stripes-gradient`). The baseline/comparison bar is hatched in a neutral outline instead of sand, so the "before" reads as reference, not result. Fill draws in (`scaleX`) once scrolled into view.

### SDG tag
Outlined 2px chip, mono 700, official color as both border and text: sand-adjacent orange for SDG 11, warm red for SDG 4.

### Sheet number
Mono 700, sand, right-aligned on case pages (`P-101`, `Sheet 1 of 5`) or trailing a sheet-head (`W-101–103`).

## Motion

- **Plot progress** — a 3px sand rule fixed to the top of the viewport, scaled (not widthed, for performance) to overall scroll position across the page. The pen-plotter reference for the whole site.
- **Sheet reveal** — sheets and case-study section headings fade/rise in once scrolled into view. Visible-by-default in the base CSS; JavaScript only pre-hides sheets that start below the fold at load, so a visitor with no JavaScript, or a script error, still sees every sheet — this is a fail-safe pattern, not a cosmetic one.
- **Bar fill** — hatch fill draws in on scroll (`scaleX` 0→1).

### Named Rules
- **Fail-Safe Reveal Rule.** No content's base visibility may depend on JavaScript running. Any scroll-triggered reveal must default to visible in CSS and only be pre-hidden by JS for elements confirmed below the fold at load.

## Do's and Don'ts

### Do:
- Give every sheet a real, referenceable number.
- Keep sand for marks and measurements only: numbers, links, hatch, focus.
- Use B612 Mono only for codes, counts, dates, and dimensions.
- Frame photos in a thin ink border with a mono caption (`FIG. 1 — …`), never bare.
- Keep the grid-reference ticks flush to the sheet border.

### Don't:
- Don't add a second accent color, or color-code sections individually (the prior world's per-section line colors are retired).
- Don't box individual rows or entries in cards; the sheet is the only enclosure.
- Don't use a colored side border as a callout device (no side-tabs) — the takeaway pull-quote uses a full ink top-rule instead.
- Don't gate any content's initial visibility on JavaScript.
- Don't use B612 Mono for prose.

# Visual QA Rubric

A game passes visual QA only when it is functional **and** remains recognizably faithful to the approved visual target.

## Severity

- **P0** — blocks play, severe clipping/overlap, missing critical assets
- **P1** — major visual identity mismatch or obvious production-quality downgrade
- **P2** — meaningful drift in layout, typography, colors, assets, or states
- **P3** — minor polish refinement

P0/P1/P2 block handoff.

## Required comparison surfaces

### 1. Art and assets

Check:

- subject correctness
- character identity
- art direction
- palette
- line/render style
- detail level
- scale/crop
- sharpness
- transparency edges
- no placeholders

Automatic P1 examples:

- full-color concept character → gray line-art implementation
- unique character set → repeated generic template
- custom illustration → emoji/generic icon

### 2. Composition and layout

Check:

- major-region proportions
- margins and padding
- alignment
- card/grid rhythm
- whitespace
- focal-point placement
- object scale
- viewport fit

### 3. Typography

Check:

- family / closest practical match
- weight
- size
- line-height
- wrapping
- hierarchy
- control labels

### 4. Color and surfaces

Check:

- page/background tone
- card/surface colors
- accent colors
- borders
- shadows
- radii
- gradients only when intended

### 5. Game states

Check relevant states:

- selected
- hover/press where applicable
- locked
- hint
- drag
- success
- failure/retry
- reward

## Downgrade question

Before passing, explicitly answer:

> Does the implementation look materially cheaper, flatter, more generic, or less characterful than the approved concept?

If yes, fail the build at P1 or P2 depending on severity.

## Fidelity ledger template

| Surface | Concept evidence | Render evidence | Severity | Fix |
|---|---|---|---|---|
| Character art | Full-color, thick outline | Gray line art | P1 | Replace with production asset |
| Card shadow | Soft low elevation | Too dark | P2 | Adjust token |
| Background | Pale blue | Matched | pass | — |

## Pass condition

Pass only when:

- no actionable P0/P1/P2 findings remain
- no unapproved placeholders remain
- major screens/states belong clearly to the same visual family as the approved concept

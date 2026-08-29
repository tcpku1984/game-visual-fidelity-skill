---
name: game-visual-fidelity
description: Preserve approved game concept art through production by enforcing asset extraction, production-ready game art, implementation fidelity, and browser-based visual QA. Use for H5/web games and game-like interactive frontends where the final build must remain visually faithful to concept art or UI mockups.
---

# Game Visual Fidelity

Use this skill for any visually driven H5/web game where concept art, mockups, screenshots, or visual references exist or should be created.

## Mission

Prevent this common AI-development failure:

> polished concept → functional implementation → visual downgrade

The final implementation must preserve the concept's visual identity, production quality, and character. A working game that looks materially cheaper than the approved concept is not complete.

## Priority order

When trade-offs occur, use this order:

1. Core gameplay must remain functional.
2. Approved visual identity must be preserved.
3. Responsive adaptation may change composition, but not art quality.
4. Implementation convenience never justifies visible downgrade.

## Hard rules

### 1. Approved concepts are binding visual targets

Once a concept or reference is accepted, treat it as the production visual target, not loose inspiration.

Preserve as closely as practical:

- art direction
- character design
- proportions
- palette
- outline/rendering style
- card/component anatomy
- typography mood
- spacing and density
- background treatment
- shadows and radii
- perceived production quality

Do not silently reinterpret the project into a different visual style.

### 2. Do not hand off placeholder art

The following may be used only as temporary scaffolding and must not remain in the final build unless the user explicitly asked for a prototype:

- gray line drawings
- rough sketches
- generic SVG animals/characters
- emoji
- CSS/div art used as final illustration
- circles/rectangles standing in for intended art
- repeated low-detail templates
- mismatched stock art
- browser-default controls
- low-quality programmer art

### 3. Concept art is not a production asset pack

Never jump directly from one concept board to implementation when the concept contains recurring illustrated entities.

Before final implementation, produce or obtain standalone production assets for recurring visual elements such as:

- characters
- animals
- enemies
- NPCs
- props
- food
- crops
- vehicles
- buildings
- collectibles
- badges
- cards
- environment objects
- decorative illustrations
- background layers

Use transparent PNG/WebP or another implementation-ready format where layering is required.

### 4. Production assets must match the concept

For every asset family, preserve:

- palette
- line weight
- rendering style
- silhouette quality
- proportions
- expression/personality
- lighting logic
- detail level

A full-color concept character may not become a monochrome outline in production.

### 5. The implementation must use the real production assets

Generating good assets and then ignoring them is a failure.

The actual game must directly use the production assets or faithful exported equivalents.

Do not replace them during coding with easier substitutes.

### 6. Important game states need visual references

Do not rely on one overview image if the game has multiple visually meaningful states.

Create or resolve references for the relevant surfaces, such as:

- home
- level select
- card/character select
- gameplay
- tutorial/hint
- selected/locked states
- pause
- success
- retry/failure
- reward/unlock
- gallery/collection
- settings

Only create the states the product actually needs, but do not leave key states visually unspecified.

### 7. Browser visual QA is mandatory

Before handoff:

1. run the game
2. capture the actual browser-rendered screen
3. compare it against the matching concept/reference
4. record material mismatches
5. fix P0/P1/P2 visual issues
6. repeat until the build passes

Build success, lint success, and functional tests do not replace visual QA.

## Workflow

### Phase 1 — Resolve visual truth

Before implementing a visually important surface:

- identify the exact approved concept/reference
- record target viewport or aspect ratio where relevant
- identify the screen/state represented
- identify which parts are code-native UI vs raster/illustrated assets

If multiple concepts conflict, resolve the source of truth before continuing.

### Phase 2 — Inventory visible assets

Create an asset inventory from the reference.

For each asset, record:

- name
- role
- approximate size/aspect ratio
- transparent vs baked background
- whether it repeats
- whether animation states are needed
- consuming screen/component

For game characters, explicitly note required states such as:

- idle
- walk
- happy
- eat
- hit
- sleep
- selected

Only generate states that are actually needed.

### Phase 3 — Production asset pass

Create the asset pack before declaring the screen production-ready.

For recurring characters or objects:

- generate/export them individually
- keep a consistent art direction
- use consistent scale logic
- preserve identity across variants
- remove accidental text unless text belongs inside the artwork

For backgrounds/scenes:

- keep focal areas compatible with interactive overlays
- avoid baking editable UI labels into the image
- preserve enough resolution for target tablet/desktop sizes

### Phase 4 — Extract a design system

Before detailed coding, define the visual system from the approved concept.

At minimum capture:

- background colors
- surface/card colors
- text colors
- accent colors
- border treatment
- radius scale
- shadow/elevation
- spacing scale
- typography scale
- control sizing
- illustration framing
- selected/disabled/locked states
- reward/celebration treatment

Game-specific tokens should include when applicable:

- HUD style
- counter style
- progress style
- hint style
- selection highlight
- hit/drag feedback
- success feedback

### Phase 5 — Implement from the visual spec

Implementation must preserve the approved visual hierarchy.

Do:

- use the real assets
- recreate component anatomy faithfully
- match object scale
- keep consistent spacing
- match palette and surface treatment
- use deliberate typography
- preserve friendliness/density appropriate to the audience

Do not:

- simplify rich illustration into generic icons
- substitute gray placeholders
- default to a generic UI kit when the concept is custom
- add unapproved visual clutter
- change white/cream/dark background character without reason
- alter the art style for coding convenience

### Phase 6 — Screen-by-screen fidelity loop

For every major screen/state:

1. capture implementation screenshot
2. compare at the same state and similar viewport
3. inspect composition
4. inspect asset quality
5. inspect component anatomy
6. inspect typography
7. inspect color/tokens
8. inspect spacing/rhythm
9. fix material drift
10. recapture

Do not defer all comparison until the end of the project.

### Phase 7 — Final visual downgrade gate

Before handoff, ask explicitly:

> Does the implementation look materially cheaper, flatter, more generic, or less characterful than the approved concept?

If yes, the task is blocked.

## Required fidelity surfaces

Every final QA pass must explicitly evaluate:

### A. Art and assets

- correct subject
- style consistency
- character identity
- color richness
- line/render quality
- scale/crop
- sharpness
- transparency edges
- no placeholders

### B. Layout and composition

- major region proportions
- alignment
- whitespace
- object scale
- card/grid rhythm
- viewport fit

### C. Typography

- family or closest practical equivalent
- size
- weight
- line height
- wrapping
- hierarchy
- control text

### D. Colors and visual tokens

- background tone
- surfaces
- borders
- shadows
- accents
- opacity
- gradients where genuinely present

### E. Game states

- selected
- active
- locked
- hint
- success
- failure/retry if applicable
- touch/drag feedback

## Severity

Use these levels for the fidelity ledger:

- **P0** — unusable, broken, or visually blocks core play
- **P1** — major visual mismatch; product clearly looks unlike the concept
- **P2** — meaningful drift in spacing, typography, assets, color, or state treatment
- **P3** — minor polish difference that does not materially downgrade the experience

P0/P1/P2 issues block handoff.

## Hard-fail examples

Any of the following is an automatic P1 unless explicitly approved by the user:

- concept uses full-color illustrated characters; implementation uses gray line art
- concept uses unique characters; implementation uses one repeated body template with different heads/labels
- concept uses custom illustrated cards; implementation uses generic white web cards
- concept uses bespoke props; implementation uses emoji or unrelated icons
- concept uses a polished scene; implementation uses flat CSS boxes as final art
- concept uses custom controls; implementation leaves browser-default controls
- visible placeholder art remains in a claimed final build

## Responsive rule

Fidelity does not mean forcing one screenshot onto every screen size.

Responsive adaptation may:

- reflow columns
- scale spacing
- move panels
- crop backgrounds differently
- reduce decorative density

But it must preserve:

- art style
- asset quality
- visual hierarchy
- palette
- component family
- perceived polish

## Game-type notes

### Card / collection / gallery games

Preserve:

- card shape
- card spacing
- illustration scale
- label hierarchy
- selected/locked states
- background softness
- shadows

If concept cards use rich character art, final cards must too.

### Scene-based educational games

Preserve:

- prompt placement
- child-friendly focus points
- interactive object scale
- scene props
- reward feedback
- clarity of targets

### Drawing / tracing games

Preserve:

- selection-card art quality
- trace-line treatment
- drawing canvas framing
- completion fill/reveal effect
- reward state

A tracing mechanic does not justify degrading colorful preview art into generic outline placeholders on the selection screen.

### Action / runner / drag games

Preserve:

- player art
- obstacle art
- collectibles
- environment treatment
- HUD tone
- feedback states

## Fidelity ledger

Before final handoff, produce a concise ledger with at least five comparison points overall.

Suggested format:

| Surface | Concept | Implementation | Severity | Action |
|---|---|---|---|---|
| Character art | full-color, thick outline | full-color, matched | pass | none |
| Card shadow | soft, low elevation | too dark | P2 | reduce shadow |
| Title scale | large and bold | too small | P2 | increase type token |
| Background | pale blue | matched | pass | none |
| Placeholder art | none | none | pass | none |

## Final handoff gate

Do not report completion until all are true:

- core gameplay works
- required production assets exist
- implementation uses them
- no unapproved placeholders remain
- major screens/states have been visually checked
- P0/P1/P2 fidelity issues are resolved
- implementation clearly belongs to the same visual family as the approved concept

If a reasonable observer would say "these look unrelated," the build fails.

## Final response

When finishing work under this skill, report:

- visual references used
- production asset families created/used
- screens/states verified
- browser/render comparison method
- important mismatches fixed
- any intentional deviations
- whether placeholders remain

The expected final placeholder count is zero unless the user explicitly approved otherwise.

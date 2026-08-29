# Asset Production Checklist

Use this checklist before claiming an illustrated game screen is production-ready.

## 1. Inventory

For every recurring visible entity, confirm whether a dedicated production asset exists.

Typical families:

- player / main character
- NPCs
- animals
- enemies
- props
- food / crops
- collectibles
- cards / badges / stickers
- environment objects
- buildings / vehicles
- foreground / background layers
- illustrated buttons or decorative UI

## 2. Fidelity

For every family, compare against the approved concept:

- same palette
- same line weight
- same rendering style
- same silhouette quality
- same proportions
- same personality / expression
- same level of detail

## 3. Technical readiness

Check:

- transparent background where layering is needed
- sufficient resolution for target device
- consistent crop and padding
- predictable anchor point
- no accidental embedded text
- no visible matte / halo artifacts
- sensible compression

## 4. Animation states

Only create states actually needed by gameplay, but do not fake required states with unrelated transforms if the concept depends on real art changes.

Possible states:

- idle
- walk / move
- selected
- happy / success
- eat
- sleep
- hit
- fail

## 5. Placeholder sweep

Search the final implementation for:

- emoji
- generic SVGs
- rough line art
- CSS character drawings
- temporary boxes/circles
- stock placeholders
- browser-default assets

Expected count at handoff: **zero**, unless explicitly approved.

## Blocking rule

If a concept shows a polished custom visual and the final implementation uses a visibly cheaper substitute, the asset pass has failed.

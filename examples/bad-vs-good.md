# Example: Concept-to-Implementation Downgrade

This example describes the exact class of failure this skill is designed to catch.

## Approved concept

A children's animal-selection screen uses:

- full-color illustrated animals
- thick friendly outlines
- unique body shapes and expressions
- soft pastel background
- custom rounded cards
- polished shadows and spacing

## Bad implementation

The coded H5 screen keeps the same 4-column grid and labels, but replaces the artwork with:

- gray line drawings
- repeated body templates
- simplified faces
- generic white cards
- flatter spacing and weaker shadows

The functionality is correct. The visual implementation is not.

### Result

**P1 — hard fail**

Reason: the implementation preserves information architecture but loses the art direction and perceived production quality.

## Correct response

Do not tweak only CSS around the low-quality art.

Instead:

1. return to the approved concept
2. inventory each animal as a required production asset
3. generate/export each animal individually in the approved style
4. implement those exact assets in the cards
5. re-match card anatomy, spacing, colors, typography, and shadows
6. capture the browser result
7. compare again

## Passing implementation

A passing result does not need to be pixel-identical, but a reasonable observer should immediately recognize it as the same product and same art family as the concept.

The central question is not:

> Is the grid correct?

It is:

> Did the product keep the visual quality promised by the concept?

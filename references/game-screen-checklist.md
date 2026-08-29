# Game Screen Checklist

Use this to decide whether the concept set is complete enough before coding.

## Resolve only the screens the game actually needs

Typical surfaces:

- home / title
- level select
- character / card select
- primary gameplay
- tutorial / hint state
- selected / active state
- locked state
- pause
- success / completion
- failure / retry
- reward / unlock
- gallery / collection
- settings / parent settings

## For each important screen, record

- source concept/reference
- viewport/aspect ratio
- major regions and proportions
- primary focal point
- recurring assets shown
- code-native UI vs image assets
- typography hierarchy
- spacing rhythm
- background treatment
- interaction states

## Minimum concept quality

A reference is not sufficient if:

- text is too small to read
- important component anatomy is ambiguous
- asset details are too tiny to reproduce
- multiple states are compressed into one unreadable board
- the screen shows only a hero/cover and not the actual gameplay surface

When detail is ambiguous, create a fresh dedicated reference for that screen/state instead of guessing during coding.

## H5/tablet checks

For tablet-oriented games, verify at least:

- 4:3
- 16:10
- 16:9 where supported

Responsive changes may alter layout, but should preserve the same visual family and perceived polish.

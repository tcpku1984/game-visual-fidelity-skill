# Game Visual Fidelity Skill

**Stop AI-built games from looking worse than their concept art.**

`game-visual-fidelity-skill` is a strict agent skill for H5/web games that treats approved concept art as a production target rather than loose inspiration.

It addresses a common failure mode in AI game development:

> polished concept art → functional implementation → visual downgrade

Typical downgrades include colorful characters becoming gray line art, custom UI becoming generic cards, distinctive props becoming emoji or stock icons, and illustrated scenes becoming CSS boxes.

This skill enforces a blocking workflow:

**concept → production asset pass → design-system extraction → implementation using real assets → browser screenshots → visual QA → fix until faithful**

## What it is for

Use it for visually driven H5/browser games, especially:

- children's games
- educational mini-games
- drawing / tracing games
- farm / cooking / animal games
- card / collection games
- casual puzzle games
- runner / drag / tap games
- scene-based interactive games

It is intentionally framework-agnostic. It can be used alongside Codex, Claude Code, OpenCode, or other agent systems that support project instructions / skills.

## Core rule

> If the approved concept looks materially richer, more polished, or more distinctive than the browser implementation, the task is **not done**.

Functional correctness does not compensate for visual downgrade.

## Hard failures

The final build fails visual fidelity if approved concept art is replaced by:

- placeholder line drawings
- gray sketch icons
- emoji
- generic SVG cartoons
- CSS/div art
- repeated low-detail templates
- stock-like substitutes
- browser-default controls
- programmer art left in production

Temporary placeholders are allowed during implementation, but **zero placeholders may remain at handoff** unless the user explicitly requested a prototype.

## Install / use

Copy `SKILL.md` into the skill/instruction location used by your agent, then invoke it when building or redesigning a game.

Example prompt:

```text
Use game-visual-fidelity for this project.
This is a final-quality H5 game, not an MVP.
Treat the approved concept images as the production visual target.
Do not hand off until production assets are used and the rendered game passes concept-vs-browser visual QA.
```

## Repository structure

```text
.
├── README.md
├── SKILL.md
├── LICENSE
├── references/
│   ├── asset-production-checklist.md
│   ├── game-screen-checklist.md
│   └── visual-qa-rubric.md
└── examples/
    ├── bad-vs-good.md
    └── children-game.md
```

## Philosophy

This skill does not demand pixel-perfect screenshot cloning when a game must remain responsive or interactive. It demands **fidelity of visual identity**:

- same art direction
- same character personality
- same level of finish
- same color language
- same component anatomy
- same visual hierarchy
- same perceived production quality

A responsive implementation may adapt composition. It may not silently downgrade the art.

## Related work

General image-to-code and design-QA skills already exist in the ecosystem. This project focuses specifically on the failure modes of **game implementation**, where concept art, production sprites, scene props, game states, and browser UI often become disconnected during coding.

## License

MIT.

# Animated 3D Website Builder

A reusable Claude/Codex-style skill for building premium animated, full-screen web experiences with React, TypeScript, Vite or Next.js, Tailwind CSS, Framer Motion, React Three Fiber, Drei, video, canvas, masks, scroll choreography, and pointer-driven interaction.

Use it for cinematic landing pages, brand websites, editorial heroes, cursor-following reveals, fullscreen video experiences, scroll-controlled video/canvas pages, lightweight 3D heroes, premium mobile menus, and high-end frontend redesigns.

## How to Use

### Claude Code

Place this folder where your Claude Code skill system can load custom skills, then invoke it naturally:

```text
Use the animated-3d-website-builder skill to build a Lithos-style geology hero with a cursor spotlight reveal.
```

The trigger metadata and core workflow live in `SKILL.md`. Reusable implementation guidance lives in `references/`.

### Codex-Style Agents

Use `AGENTS.md` as repository or task instructions for Codex-style coding agents. Put it at the project root, or keep this package intact and tell the agent to read it before implementing animation, 3D, video, canvas, mask, or premium frontend work.

Recommended structure:

```text
animated-3d-website-builder/
├── SKILL.md
├── AGENTS.md
├── README.md
├── references/
│   ├── checklist.md
│   ├── gold-standard-recipes.md
│   └── patterns.md
└── examples/
    └── prompts.md
```

## Reference Files

- `references/patterns.md`: compact implementation patterns for cursor reveals, video heroes, mobile overlays, staggered motion, scroll video/canvas, particles, mask cards, 3D heroes, and exact-spec mode.
- `references/gold-standard-recipes.md`: reusable guidance for Lithos, VANGUARD, and Veldara-style experiences.
- `references/checklist.md`: final quality, accessibility, responsiveness, performance, and validation checklist.
- `examples/prompts.md`: example tasks that represent the intended quality bar.

## Packaging

From the parent directory, package the skill with:

```bash
zip -r animated-3d-website-builder.zip animated-3d-website-builder
```

# Animated 3D Website Builder

A reusable Claude/Codex-style skill for building premium animated websites with modern motion design and lightweight 3D interaction.

Use it for animated landing pages, React/Next.js hero sections, Framer Motion interactions, React Three Fiber scenes, scroll-based effects, SaaS/product pages, portfolios, and frontend redesigns that need to feel high-end without becoming fragile or slow.

## How to Use

### Claude Code

Place this folder where your Claude Code skill system can load custom skills, then invoke it naturally:

```text
Use the animated-3d-website-builder skill to build a premium animated SaaS landing page.
```

The trigger metadata lives in `SKILL.md`; the practical coding-agent guidance lives in `AGENTS.md`.

### Codex-Style Agents

Use `AGENTS.md` as repository or task instructions for Codex-style coding agents. Put it at the project root, or keep this package intact and tell the agent to read it before implementing animation or 3D website work.

Recommended structure:

```text
animated-3d-website-builder/
├── SKILL.md
├── AGENTS.md
├── README.md
├── references/
│   ├── checklist.md
│   └── patterns.md
└── examples/
    └── prompts.md
```

## Example Prompts

1. Build a cinematic SaaS landing page for an AI analytics product with a premium animated hero, product sections, pricing CTA, and responsive layout.
2. Add a 3D animated hero section to this Next.js homepage using React Three Fiber and Drei, with a reduced-motion fallback.
3. Improve this existing boring landing page so it feels premium, animated, and conversion-focused without adding unnecessary dependencies.
4. Add scroll-triggered animations to the product showcase and feature sections using Framer Motion, keeping mobile performance clean.
5. Create a portfolio homepage with interactive 3D visuals, smooth section transitions, and accessible keyboard-friendly project cards.

## Packaging

From the parent directory, package the skill with:

```bash
zip -r animated-3d-website-builder.zip animated-3d-website-builder
```


---
name: animated-3d-website-builder
description: use this skill when creating, editing, or improving animated websites, 3d web experiences, landing pages, react/next.js frontends, motion design, framer motion animations, react three fiber scenes, scroll effects, and premium interactive web ui.
---

# Animated 3D Website Builder

Use this skill to build premium, performant animated web experiences with React, Next.js, TypeScript, Tailwind CSS, Framer Motion, React Three Fiber, Drei, and lightweight scroll or 3D interactions.

## Core Workflow

1. Inspect the project structure first:
   - Identify framework: Next.js App Router, Next.js Pages Router, Vite React, or another React setup.
   - Identify styling: Tailwind, CSS modules, global CSS, shadcn/ui, design tokens, component library.
   - Identify existing animation or 3D libraries before adding anything.
   - Read nearby components, layouts, package scripts, and config files before editing.

2. Detect the right implementation path:
   - Use the existing stack when it can support the request.
   - Prefer Framer Motion for component entrance, hover, layout, and simple scroll animations.
   - Prefer React Three Fiber and Drei for 3D scenes in React apps.
   - Use GSAP only for complex, timeline-heavy scroll choreography that Framer Motion cannot keep clean.
   - Use shadcn/ui only when it fits the existing project or materially improves UI quality.
   - Support Vite/React when the project is not Next.js.

3. Ask clarifying questions only when absolutely necessary:
   - Ask when brand direction, content, or required assets are impossible to infer.
   - Otherwise make reasonable choices and implement directly.

4. Keep the result production-ready:
   - Mobile-first responsive layout.
   - Accessible semantic structure and keyboard behavior.
   - `prefers-reduced-motion` support.
   - Lightweight procedural 3D when no assets are provided.
   - Clean component architecture with small, named components.
   - No unnecessary dependencies.
   - No gratuitous animation that harms clarity, performance, or conversion.

5. Validate before finishing:
   - Run available lint, typecheck, test, and build scripts when possible.
   - If a dev server or visual check is appropriate, run it and inspect the rendered result.
   - Report any commands that could not be run.

6. Explain the outcome:
   - Summarize what changed.
   - Mention key files.
   - Explain how to run or preview it.
   - Note any dependencies added and why.

## Reference Loading

Read these only when useful for the task:

- `references/patterns.md`: implementation patterns for heroes, scroll reveals, 3D backgrounds, cards, CTAs, and fallbacks.
- `references/checklist.md`: final quality checklist before handing off.


---
name: animated-3d-website-builder
description: use this skill when creating, editing, or improving premium animated landing pages, cinematic hero sections, full-screen brand websites, cursor-following reveals, video-background experiences, scroll-linked animation, canvas effects, 3d web experiences, react/vite/next.js frontends, tailwind css implementations, framer motion or gsap choreography, and react three fiber or drei scenes.
---

# Animated 3D Website Builder

Build complete, runnable animated web experiences that feel like premium creative studio work. Implement directly unless the user explicitly asks for planning only.

## Operating Rules

1. Inspect the project first.
   - Identify the framework: Vite React, Next.js App Router, Next.js Pages Router, plain React, or another frontend stack.
   - Check `package.json`, app routes/pages, component structure, styling files, aliases, and available scripts.
   - Detect whether Tailwind CSS is installed and configured before using Tailwind classes.
   - Detect existing animation, icon, 3D, UI, and routing libraries before adding anything.

2. Match the existing app.
   - Use the current framework, file conventions, imports, class naming, and component patterns.
   - Keep edits scoped to the requested route, page, or components.
   - Prefer a complete single-page implementation over scattered abstractions when the project is small.

3. Ask only when blocked.
   - Ask when required brand name, required assets, or target framework cannot be inferred and guessing would produce the wrong result.
   - Otherwise choose a strong creative direction and implement it.

4. Choose the minimum stack.
   - Use React 18, TypeScript, Vite or Next.js, Tailwind CSS, and `lucide-react` when present or appropriate.
   - Use Framer Motion for component reveals, hover/focus states, layout transitions, and simple scroll-linked transforms.
   - Use GSAP only for pinned or timeline-heavy scroll choreography that would be awkward in Framer Motion.
   - Use React Three Fiber and Drei only when real 3D materially improves the experience.
   - Use CSS, canvas, video, masks, and pointer interactions before adding heavy packages.

5. Deliver production-ready output.
   - Provide exact file edits, not broad advice.
   - Add dependencies only when needed; explain each one.
   - Include fallbacks for video, canvas, masks, 3D, loading, and reduced motion.
   - Keep TypeScript clean, components readable, and unused imports out.
   - Run available lint, typecheck, test, and build scripts. Fix errors before final output when feasible.
   - Explain how to run or preview the result.

## Quality Bar

The result must feel like a premium creative studio website, not a generic template. The first viewport needs a clear focal point, strong typography, deliberate spacing, mobile-first composition, and one memorable signature interaction.

Avoid:

- Centered generic gradient heroes.
- Random floating blobs.
- Shallow "modern SaaS" layouts.
- Unstructured animation spam.
- Desktop-only designs.
- Huge dependency lists.
- Inaccessible motion.
- Slow decorative 3D.

Choose one strong signature mechanic and execute it well:

- Cursor reveal.
- Fullscreen video hero.
- Scroll-scrubbed sequence.
- Procedural 3D object.
- Parallax image mask.
- Editorial typography system.
- Canvas particle layer.
- Interactive cards.
- Premium mobile menu.

## Reference Loading

Read only the references needed for the current task:

- `references/patterns.md`: implementation patterns for cursor reveals, video heroes, mobile overlays, staggered motion, scroll video/canvas, particles, mask reveals, and 3D heroes.
- `references/gold-standard-recipes.md`: compact recipes for Lithos-style cursor reveal, VANGUARD-style video hero, and Veldara-style immersive scroll pages.
- `references/checklist.md`: final validation checklist for visual quality, motion, responsiveness, accessibility, performance, and code health.
- `examples/prompts.md`: realistic prompts that define the intended quality bar.

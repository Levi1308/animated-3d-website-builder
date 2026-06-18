# Final Quality Checklist

## Visual Quality

- Does the first viewport feel premium and intentional?
- Is there a clear hero focal point?
- Are typography, spacing, contrast, and hierarchy strong?
- Does the page avoid generic template energy?
- Is the brand, product, person, place, or offer immediately legible?
- Are hover and focus states polished?
- Are image, video, canvas, and 3D layers composed with clear z-index strategy?

## Motion Quality

- Are animations staggered and purposeful?
- Does each animation orient, reveal, focus, respond, or connect space?
- Are transitions smooth on mobile?
- Is reduced motion respected in CSS and JavaScript?
- Are transform and opacity used where possible?
- Do continuous animations avoid distracting from content?
- Are pointer and scroll interactions free of visible jitter?

## Advanced Interaction Quality

- Cursor reveal works and cleans up listeners.
- RAF loops are canceled on unmount.
- Video background fills the viewport with a poster or static fallback.
- Scroll effects do not jank.
- Canvas effects resize correctly and account for DPR.
- Mask effects work in Chromium and Safari via `maskImage` plus `WebkitMaskImage`.
- Particles or canvas overlays use `pointer-events: none` unless interactive.
- Fixed scroll cards only accept pointer events when visible.

## Responsiveness

- Works at mobile, tablet, and desktop widths.
- No horizontal overflow.
- Hero uses `100dvh` or equivalent where appropriate.
- Nav switches correctly at breakpoints.
- CTA and stats rows wrap safely.
- Text, buttons, cards, videos, canvases, and 3D containers do not overlap.
- Touch users can access all critical content without hover.

## Accessibility

- Headings are ordered and meaningful.
- Buttons and links are semantic.
- Icon-only buttons have accessible labels.
- Text contrast is sufficient over image, video, canvas, and gradients.
- Decorative video/canvas/3D does not trap interaction.
- Critical copy is in DOM text.
- Mobile menu is keyboard-friendly where practical.
- Motion respects `prefers-reduced-motion`.

## Performance

- Unnecessary dependencies were avoided.
- Heavy 3D is avoided unless needed.
- Procedural 3D is lightweight and DPR is capped.
- Canvas work is bounded and cleaned up.
- Video has fallback behavior and mobile performance considerations.
- Images and media are optimized for the framework.
- Pointer and scroll work uses refs, motion values, or RAF rather than broad React state.
- Build passes.

## Code Quality

- TypeScript is clean.
- Components are readable and cohesive.
- No unused imports, dead code, or unfinished placeholder notes.
- No routing changes unless requested.
- File structure follows the existing app.
- Exact user-provided classes, URLs, text, z-indexes, and timings are preserved unless impossible.
- Single-component output is allowed when the user asks for it or the app is small.

## Validation

- `npm run lint` ran or the missing script was reported.
- `npm run typecheck` ran or the missing script was reported.
- Tests ran when available.
- `npm run build` ran or the closest framework validation ran.
- Browser console was checked for visual work when feasible.
- Hydration, blank canvas, layout overlap, and mobile overflow issues were addressed.

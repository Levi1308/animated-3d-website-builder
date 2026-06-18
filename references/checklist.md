# Final Quality Checklist

## Visual Quality

- First viewport communicates the product, brand, person, or offer immediately.
- Typography scale is appropriate for the layout and does not overflow.
- Spacing is intentional on mobile and desktop.
- The palette is not a generic one-note gradient theme.
- CTAs are visible, specific, and easy to scan.

## Motion Quality

- Animations have clear purpose and do not delay important content.
- Motion uses transform and opacity where possible.
- Staggers are short and restrained.
- Continuous motion is subtle and can be reduced.
- No competing animations fight for attention.

## 3D Performance

- Canvas has a stable size and never renders blank.
- DPR is capped.
- Heavy assets are avoided or lazy-loaded.
- `useFrame` work is minimal.
- Mobile scene complexity is reduced when needed.
- A loading and reduced-motion fallback exists.

## Mobile Behavior

- Layout works at narrow widths without horizontal overflow.
- Touch interactions do not depend on hover.
- Text, buttons, cards, and canvas elements do not overlap.
- Hero height leaves a hint of the next section where appropriate.
- Performance remains smooth on mobile.

## Accessibility

- Headings are ordered and meaningful.
- Interactive elements are real links or buttons.
- Focus states are visible.
- Text contrast is readable over motion and canvas layers.
- Critical content is available outside canvas.
- `prefers-reduced-motion` is respected.

## Build Health

- Lint passes or failures are reported.
- Typecheck passes or failures are reported.
- Build passes or failures are reported.
- Browser console is checked when visual work was implemented.
- Hydration and SSR issues are addressed.

## Dependency Sanity

- Existing libraries are reused.
- New dependencies are necessary and explained.
- GSAP is only used for complex timelines.
- shadcn/ui is only used when useful or already present.
- No heavy asset or animation package is added for a small effect.


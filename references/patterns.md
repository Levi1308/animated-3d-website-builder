# Reusable Patterns

## Hero Section

- Use a clear headline, specific supporting copy, and one primary CTA.
- Pair text with a full-bleed or integrated 3D/canvas visual, not a tiny decorative preview.
- Keep the hero responsive: text first on mobile, spatial composition on desktop.
- Add entrance motion to headline, copy, CTA, and visual with a short stagger.
- Keep the first viewport focused; show a hint of the next section below the fold.

## Product Showcase

- Use real product UI, screenshots, mock panels, or procedural 3D product forms.
- Animate state changes, tabs, or panels with layout-aware transitions.
- Keep product details readable; do not hide core information inside hover-only states.
- Use subtle depth: shadows, perspective, layered panels, and lighting.

## Scroll Reveal

- Use Framer Motion `whileInView` for simple reveals.
- Use `useScroll` and `useTransform` for progress-linked parallax, scale, opacity, or camera values.
- Use GSAP only for long, pinned, multi-step timelines.
- Keep reveal distances small and avoid delaying critical text.
- Disable or simplify reveals for reduced-motion users.

## 3D Background Scene

- Make the scene decorative unless it directly represents the product.
- Use procedural geometry first: floating panels, particle fields, ribbons, wireframes, or device shells.
- Use `Suspense` with a styled fallback.
- Cap DPR and avoid heavy postprocessing by default.
- Keep pointer interaction subtle: rotation, light position, or small parallax.

## Interactive Cards

- Cards should have clear content hierarchy and accessible links or buttons.
- Use hover/focus lift, border glow, or background shift, not all at once.
- Keyboard focus should trigger an equivalent visual state.
- On touch devices, avoid interactions that require hover to reveal essential content.

## CTA Section

- Make the CTA direct and visually calmer than the hero.
- Use one primary action and one optional secondary action.
- Reinforce value with a short line of proof or context.
- Motion should guide attention, not restart the whole page experience.

## Loading and Fallback States

- Always provide a non-canvas fallback for 3D loading or unsupported contexts.
- Use skeletons or static gradients only as temporary states, not the final visual.
- For reduced motion, replace continuous animation with static composition or user-initiated interaction.
- Keep fallback dimensions stable to prevent layout shift.


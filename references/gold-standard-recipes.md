# Gold Standard Recipes

Use these as compact direction guides. They are not full implementations; combine them with `references/patterns.md`.

## Recipe 1: Lithos Cursor Reveal

- Define asset constants for base image, reveal image, and optional texture/noise overlay.
- Build one full-screen dark section with `relative min-h-[100dvh] overflow-hidden`.
- Layer order:
  - Base dark background.
  - Base image with slow Ken Burns scale.
  - Reveal image clipped by cursor mask.
  - Dark vignette or gradient for text contrast.
  - Fixed glass nav.
  - Hero heading and bottom copy blocks.
- Use z-index deliberately: media at `z-0`, scrims at `z-10`, nav/content at `z-20`, cursor reveal layer above base media but below text.
- Track raw mouse and smoothed mouse refs; animate the smoothed point with RAF lerp.
- Generate a soft radial canvas mask when precise reveal softness is needed. Use CSS radial-gradient mask as fallback.
- Apply both `maskImage` and `WebkitMaskImage`.
- Use Inter for UI/body and Playfair Display or another editorial serif for the main headline.
- Reveal headline lines with short staggered fade/blur-up motion.
- Place precise responsive bottom copy blocks at the hero bottom on desktop and below the main headline on mobile.
- Respect reduced motion by disabling Ken Burns and mouse smoothing, using a static mask or showing only the base image.

## Recipe 2: VANGUARD Video Hero

- Use a fullscreen silent looping video layer: `autoPlay muted loop playsInline`.
- Add `poster` and a static background fallback.
- Cover the viewport with `object-cover`; never let the video sit inside a small card.
- Load custom fonts with existing framework conventions. Use strong editorial display type plus a restrained UI face.
- Place fixed or absolute nav above the video with glass or transparent treatment.
- Desktop nav uses inline links and CTA; mobile uses a fullscreen overlay menu with `Menu` and `X` icons.
- Hero copy sits directly over the video with a scrim behind the whole scene, not a text card.
- Add CTA row with one primary and one secondary action.
- Add stats row near the lower viewport; wrap safely on mobile.
- Use staggered fade-up for nav, headline, subtext, CTA, and stats.
- Hover interactions should be polished but restrained: text underline slides, button lift, icon nudge, or subtle border glow.

## Recipe 3: Veldara Immersive Scroll

- Create a tall scroll section with a fixed fullscreen background video or canvas.
- Use native video `currentTime` seeking for scroll progress before attempting canvas frame extraction.
- Add a lightweight particle canvas overlay above the video with `pointer-events: none`.
- Fade the hero copy out as scroll progress begins.
- Use fixed cards that appear over the background at defined progress ranges.
- Reveal cards with CSS masks: horizontal on desktop, vertical on mobile.
- Use IntersectionObserver for additional non-fixed section reveals after the immersive sequence.
- Keep scroll math in refs and RAF loops; avoid setting React state on every scroll tick.
- Provide robust fallbacks:
  - Poster image if video fails.
  - Static card stack for reduced motion.
  - No particles for low-power or reduced-motion contexts.
  - Regular content flow when fixed positioning would be fragile on small screens.

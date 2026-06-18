# Advanced Implementation Patterns

Use these patterns as compact starting points. Adapt naming, files, and styling to the existing app.

## Pattern A: Cursor-Following Spotlight Reveal

Use for Lithos-style dual image reveals, product inspection, editorial masks, or geology/nature/detail hero sections.

Core structure:

```tsx
const SPOTLIGHT_R = 180;
const raw = useRef({ x: 0.5, y: 0.5 });
const smooth = useRef({ x: 0.5, y: 0.5 });
const rafRef = useRef<number | null>(null);
const [mask, setMask] = useState("");
```

Implementation notes:

- Attach `mousemove` or `pointermove` to the hero parent, not the whole window, unless the effect is global.
- Store raw mouse and smoothed mouse in refs.
- Use `requestAnimationFrame` lerp:

```tsx
smooth.current.x += (raw.current.x - smooth.current.x) * 0.12;
smooth.current.y += (raw.current.y - smooth.current.y) * 0.12;
```

- Generate a radial mask with a hidden canvas when you need soft composited control:

```tsx
const canvas = document.createElement("canvas");
const ctx = canvas.getContext("2d");
const g = ctx.createRadialGradient(cx, cy, 0, cx, cy, SPOTLIGHT_R);
g.addColorStop(0, "rgba(0,0,0,1)");
g.addColorStop(0.65, "rgba(0,0,0,.9)");
g.addColorStop(1, "rgba(0,0,0,0)");
ctx.fillStyle = g;
ctx.fillRect(0, 0, width, height);
setMask(`url(${canvas.toDataURL()})`);
```

- Apply both mask properties:

```tsx
style={{ maskImage: mask, WebkitMaskImage: mask }}
```

- Use a `RevealLayer` component that overlays the second image exactly above the base image.
- Clean up `mousemove`/`pointermove`, `resize`, and `requestAnimationFrame`.
- Use CSS radial-gradient as a simpler fallback:

```tsx
const cssMask = `radial-gradient(circle ${SPOTLIGHT_R}px at ${x}px ${y}px, black 0%, black 62%, transparent 100%)`;
```

## Pattern B: Fullscreen Video Hero

Use for VANGUARD-style agency, venue, product, fashion, automotive, music, and editorial experiences.

```tsx
<section className="relative min-h-[100dvh] overflow-hidden bg-black text-white">
  <video
    className="absolute inset-0 h-full w-full object-cover"
    autoPlay
    muted
    loop
    playsInline
    poster="/poster.jpg"
  >
    <source src="/hero.mp4" type="video/mp4" />
  </video>
  <div className="absolute inset-0 bg-gradient-to-t from-black via-black/35 to-black/35" />
  <div className="relative z-10">...</div>
</section>
```

Guidance:

- Keep all content overlaid above the video with explicit z-index.
- Add a gradient/scrim for contrast.
- Use `poster` and a CSS background fallback.
- Avoid autoplay with sound.
- On mobile, consider shorter/lower-resolution video or a static poster when performance is poor.

## Pattern C: Mobile Nav Overlay

Use for full-screen editorial nav, agency heroes, and brand sites.

```tsx
const [open, setOpen] = useState(false);
```

Implementation notes:

- Use a fixed fullscreen overlay with opacity/visibility transitions.
- Use `Menu` and `X` from `lucide-react`.
- Provide accessible labels: `aria-label="Open menu"` and `aria-label="Close menu"`.
- Stagger menu item transitions with Framer Motion variants or CSS delay classes.
- Optionally lock body scroll while open.
- Close on route change, Escape, and menu item click when practical.

## Pattern D: Premium Staggered Load Animation

Use for headline lines, subtext, CTAs, stats, cards, and bottom copy blocks.

```css
@keyframes fade-up {
  from { opacity: 0; transform: translateY(18px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes blur-reveal {
  from { opacity: 0; filter: blur(10px); transform: translateY(12px); }
  to { opacity: 1; filter: blur(0); transform: translateY(0); }
}

@keyframes slow-zoom {
  from { transform: scale(1); }
  to { transform: scale(1.08); }
}

@media (prefers-reduced-motion: reduce) {
  * { animation-duration: 1ms !important; transition-duration: 1ms !important; }
}
```

Guidance:

- Use delay utilities such as `.delay-100`, `.delay-200`, `.delay-300`.
- Keep initial reveals fast enough that content is immediately available.
- Use Ken Burns zoom only on one hero image/video layer, not every visual.

## Pattern E: Scroll-Linked Video/Canvas Experience

Use for Veldara-style immersive pages, product journeys, architecture walkthroughs, and narrative scrollytelling.

Safer implementation order:

1. Native video seeking with `video.currentTime`.
2. Canvas frame extraction only when native seeking is insufficient.
3. Image sequence only when assets are available and optimized.

Core loop:

```tsx
const update = () => {
  const rect = section.current!.getBoundingClientRect();
  const progress = clamp(-rect.top / (rect.height - innerHeight), 0, 1);
  video.current!.currentTime = progress * duration;
  raf.current = requestAnimationFrame(update);
};
```

Guidance:

- Wait for `loadedmetadata` before computing duration.
- Use a fixed fullscreen background and a tall scroll section.
- Add fallback behavior: static poster, regular autoplay loop, or image background.
- Warn on CORS when extracting video frames into canvas.
- Avoid large frame arrays on mobile; memory usage can spike quickly.
- Keep scroll listeners passive and use RAF for updates.

## Pattern F: Particle Canvas Overlay

Use for atmosphere behind a hero, not as the hero itself.

Implementation notes:

- `pointer-events: none`.
- Particle count should scale with viewport area:

```ts
const count = Math.min(120, Math.floor((width * height) / 18000));
```

- Resize canvas on viewport changes and account for DPR.
- Animate with a single RAF loop.
- Keep particles simple: x, y, vx, vy, radius, alpha.
- Disable or render a static frame for `prefers-reduced-motion`.

## Pattern G: Fixed Scroll-Reveal Cards

Use for immersive long-form sections where cards appear over fixed video/canvas backgrounds.

Guidance:

- Use a fixed card container over a tall trigger zone.
- Compute progress from section bounds.
- Fade cards in/out based on progress ranges.
- Use CSS masks for directional reveal:

```tsx
style={{
  maskImage: `linear-gradient(90deg, black ${reveal}%, transparent ${reveal + 18}%)`,
  WebkitMaskImage: `linear-gradient(90deg, black ${reveal}%, transparent ${reveal + 18}%)`
}}
```

- Use vertical masks on mobile.
- Set `pointer-events: auto` only for the visible/active card.
- Provide a stacked static card fallback.

## Pattern H: 3D Hero Object

Use when shape, depth, lighting, or spatial interaction communicates the concept better than 2D.

Guidance:

- Prefer procedural geometry without provided assets.
- Good primitives: glass slabs, orbiting panels, product shells, terrain, ribbons, particle constellations.
- Use React Three Fiber with Drei helpers: `Float`, `Environment`, `PerspectiveCamera`, `ContactShadows`, `Html`.
- Wrap in `Suspense` with a stable 2D fallback.
- Cap DPR: `dpr={[1, 1.5]}` or `dpr={[1, 2]}`.
- Respect reduced motion by disabling camera auto-motion and continuous object rotation.
- Avoid huge GLB files unless the user provides them or the model is essential.

## Pattern I: Exact-Spec Implementation Mode

Use when the user provides exact classes, URLs, font imports, sizes, z-index values, text, animation delays, or layout measurements.

Rules:

- Preserve exact values unless they are impossible or break the build.
- Treat asset URLs as immutable.
- Build the requested layout first.
- Polish only within the provided constraints.
- Do not replace exact specs with a generic design system.
- Mention any required deviation in the final response.

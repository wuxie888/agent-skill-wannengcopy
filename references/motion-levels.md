# Motion Levels

Use this reference when the reference website's value comes from motion, not just layout.

## Level A: Static Original Visual

Use for quick concepts or references with minor motion.

- original still image or illustration
- CSS gradients, masks, hover states
- no complex frame-by-frame motion

Verify image loading, readability, and no reference asset leakage.

## Level B: 2.5D Motion Overlay

Default for fast high-quality demos.

Use when the reference has cinematic feel but does not require true 3D.

Techniques:

- original key visual as background
- slow camera drift via transform/scale
- light beams, glows, scan lines
- particles, sparks, waveforms, subtitle pulses
- CSS/Canvas layers
- parallax foreground/background
- reduced-motion fallback

Verify computed transform/opacity changes at two times, two screenshots separated by time, and no text/control overlap.

## Level C: Seamless Hero Video Loop

Use when the user asks for a truly animated cinematic hero.

Deliver:

- `hero-poster.webp` or `.png`
- `hero-loop.webm`
- optional `hero-loop.mp4`
- `<video autoplay muted loop playsinline>`
- native HTML overlay for heading/buttons

Generation brief:

```text
6-8 second seamless loop, slow camera drift, product-specific visual engine, subtle particles/light trails, no third-party logos or reference assets, safe area for headline, smooth loop point.
```

Verify video loads, loops, has no visible controls, has no audio, and degrades acceptably on mobile.

## Level D: Native Motion Rebuild

Use when motion is interactive or tied to scroll/cursor/state.

Candidate tech:

- Three.js for real 3D scenes
- WebGL shaders/particles
- Canvas 2D animation
- Lottie for vector motion
- GSAP/ScrollTrigger-style choreography if available
- CSS scroll timelines only when support is acceptable

Choose D when:

- the user explicitly needs interactive 3D/WebGL
- the effect changes with cursor, scroll, or app state
- video would look fake
- the motion is central to the product experience

Before implementation, read `evidence-recon.md` for source-first teardown and `SOURCE/PARTIAL/GUESS` labels. Native rebuilds should be based on real evidence when fidelity matters; if the important behavior remains guessed, state that and choose a simpler Level B/C delivery or a scoped baseline.

Verify screenshots, pixel/nonblank checks, interaction proof, desktop/mobile framing, performance sanity, and reduced-motion behavior.

## Selection Heuristic

```text
Need speed and editable result -> B
Need cinematic loop -> C
Need real 3D/interactive behavior -> D
Need only visual direction -> A
```

Do not silently downgrade complex reference motion to a static image. If blocked, implement B and state the C/D upgrade path.

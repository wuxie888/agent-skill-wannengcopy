# Evidence Recon

Use this reference when the reference is a live website, a repo, or a motion-heavy page. The goal is to understand the reference with evidence before remixing it into the target product.

Keep `wannengcopy` product-first: recon exists to prevent hallucinated implementation and hidden reference leakage, not to justify copying protected surfaces.

## Recon Ladder

Run the lightest honest path that can support the implementation decision.

1. **Source and license search**
   - Search for the real repo, source maps, theme, or public single-file source before guessing implementation.
   - Check license before carrying over code or assets.
   - Treat public GitHub with no license as all-rights-reserved for shipping.

2. **Browser evidence**
   - Capture desktop and mobile screenshots.
   - Record title, language, headings, section order, fonts, colors, scripts, stylesheets, images, video, canvas, forms, links, and scroll height.
   - Note console and page errors.

3. **Route evidence**
   - Crawl same-site internal links for multi-page sites.
   - Identify page templates: home, list, detail, pricing, docs, contact, legal, search, dashboard.

4. **Interaction evidence**
   - Probe scroll, hover, safe click, cursor, sticky stages, video state, Canvas/WebGL, and responsive breakpoints.
   - For motion-led references, capture evidence beyond one still frame.

5. **Network and data evidence**
   - Capture XHR/fetch responses for SPA, SaaS, search, filters, product feeds, dashboards, or personalized pages.
   - Convert real business APIs into local fixtures or mock states for the target product; do not depend on unauthorized live APIs.

6. **Static mirror evidence**
   - Use only for Mode 1 authorized exact clones, local learning, or technical teardown.
   - Static-built sites can expose their deployed truth as HTML, bundled JS, CSS, fonts, wasm, models, and runtime-fetched assets.
   - Do not ship mirrored third-party assets unless rights are clear.

## Complexity Levels

Assign one level and pair it with the chosen operating mode.

| Level | Type | Signals | Default delivery stance |
|---|---|---|---|
| L1 | Static HTML/CSS | little JS, few pages, no framework | exact if authorized; otherwise clean remix |
| L2 | CMS / company content site | many pages, news, forms, repeated templates | recreate representative templates, not CMS backend |
| L3 | React/Vue/Next content frontend | hydration, chunks, client routes, content APIs | rebuild with target stack and fixtures |
| L4 | animation-heavy brand site | GSAP, Lenis, video masks, parallax, sticky stages | preserve rhythm and mood; simplify microdetails if needed |
| L5 | WebGL/Canvas/Three.js | shaders, canvas, GPU assets, particles, physics | source-first teardown; choose motion Level B/C/D consciously |
| L6 | SaaS/ecommerce/logged-in system | auth, payment, orders, permissions, search/recommendation | clone demo surface and states only; do not clone backend logic |

## Evidence Labels

Use these labels in teardown notes, mapping tables, and final reports when implementation facts matter.

| Label | Meaning | Examples |
|---|---|---|
| `SOURCE` | Direct evidence tied to the reference | repo line, source map module, DOM capture, network body, shader text, screenshot, frame capture |
| `PARTIAL` | Useful clue but not enough for a claim | minified function name, class names, library signal, incomplete asset list |
| `GUESS` | Visual or conceptual inference | guessed easing, shader constants, layout math, "probably GSAP" without evidence |

Unlabeled complex implementation claims count as `GUESS`.

## WebGL / Canvas Discipline

For Level D native rebuilds or L5 references:

- Find real source, source maps, or runtime-captured shader/draw-call evidence before rewriting the effect.
- Separate rendering, composition, physics, interaction, asset loading, and audio.
- Do not compensate for unknown state by hand-tuning brightness, speed, noise, or positions and then calling it verified.
- Build a minimal baseline first when exact effect fidelity matters. Only after baseline comparison should you refactor into a maintainable product implementation.
- If exact reconstruction is too costly, downgrade intentionally to Motion Level B or C and state the gap.

## Optional Probe Commands

If a compatible `web-clone` script bundle is available, these probes are useful. Prefer local project paths over hard-coded external paths.

```bash
node scripts/recon-site.mjs --url "$REFERENCE_URL" --out RECON --label original
node scripts/route-crawl.mjs --url "$REFERENCE_URL" --out RECON/routes --label original --max-pages 25 --max-depth 2
node scripts/interaction-probe.mjs --url "$REFERENCE_URL" --out RECON/interactions --label original
node scripts/network-capture.mjs --url "$REFERENCE_URL" --out RECON/network --label original
node scripts/sourcemap-hunt.mjs --recon RECON/original-recon.json --out RECON/sourcemaps
node scripts/dna-scaffold.mjs --recon RECON/original-recon.json --out RECON/design-dna.json --name "$REFERENCE_NAME"
```

For static-built authorized/local mirrors:

```bash
node scripts/mirror-site.mjs --url "$REFERENCE_URL" --out reference-mirror
```

For after implementation:

```bash
node scripts/recon-site.mjs --url "$LOCAL_URL" --out RECON --label clone
node scripts/visual-diff.mjs --original RECON/screenshots/original-1440.png --clone RECON/screenshots/clone-1440.png --out RECON/visual-diff-1440.json --diff RECON/screenshots/visual-diff-1440.png
node scripts/compare-recon.mjs --original RECON/original-recon.json --clone RECON/clone-recon.json --out CLONE_REPORT.md
node scripts/audit-clone.mjs --project . --brand "$REFERENCE_BRAND" --out CLONE_AUDIT.md
```

If Playwright is missing, install it in the working project or a temporary dependency directory and set `NODE_PATH` for the probe run. Do not mutate unrelated repositories just to satisfy recon.

## Recon Output Summary

Before implementation, keep a compact summary:

```text
Reference:
Mode:
Complexity:
Evidence available:
Transferable patterns:
Non-transferable surfaces:
Motion level:
Implementation risks:
License/asset boundary:
```

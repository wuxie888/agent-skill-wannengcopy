---
name: wannengcopy
description: "万能复刻 / universal website copy-remix workflow with evidence-based reference recon. Use when the user wants to copy, clone, recreate, remix, migrate, or rebuild any reference website's look, interaction feel, scroll rhythm, hero motion, layout structure, visual system, deployed static assets, or landing-page experience into a new website. Trigger for requests like 万能复刻, 万能网站复制, 复刻官网, 一比一复刻, 授权复制, 高仿但换产品, 参考某官网做自己的官网, RMUX 风格, Linear/Raycast/Apple/Vercel 风格迁移, hero 动效复刻, 滚动体验复刻, 官网换皮重构, 网站侦察, 复刻验收, WebGL/Canvas/Three.js 效果还原."
---

# 万能复刻 Wannengcopy

Use this skill to turn a reference website into a usable site for the user's own product.

This skill supports lawful exact cloning when the user has rights, but defaults to experience remix: preserve the reference site's structure, interaction feel, motion language, and visual rhythm while replacing brand assets, copy, product logic, and media with original equivalents.

The main workflow is product-first. Use evidence recon from `references/evidence-recon.md` as the inspection and verification subsystem; do not let source mirroring or technical teardown override the goal of building the user's own product unless Mode 1 is clearly authorized.

## Operating Modes

Choose a mode before coding. Read `references/copy-modes.md` when mode or rights are unclear.

- **Mode 1: Authorized Exact Clone** - Use only when the user owns or is authorized to copy the source. Recreate copy, layout, assets, and effects as closely as feasible.
- **Mode 2: Experience Remix** - Default. Keep the "feel" and interaction skeleton, replace all protected or product-specific surface.
- **Mode 3: Product Rebuild** - Use a reference site as a template for a different product; rewrite every module around the new product's user journey.
- **Mode 4: Motion Reconstruction** - Use when the main value is advanced motion: Three.js, WebGL, Canvas, Lottie, scroll choreography, or video hero loops.
- **Mode 5: QA / Repair** - Use when a previous remix looks good but product logic, assets, copy, or sections still feel wrong.

Pair the mode with a complexity level from `references/evidence-recon.md` when the reference is a live site:

```text
Mode 2 + L4 = experience remix of an animation-heavy brand site
Mode 3 + L3 = product rebuild from a React/Vue/Next content site
Mode 4 + L5 = motion reconstruction of a WebGL/Canvas/Three.js effect
Mode 1 + L1 = authorized exact clone of a static site
```

## Required Inputs

Infer from local files when possible. Ask briefly only if the missing detail blocks progress.

```text
reference website or screenshot:
target product:
one-line product promise:
target user:
core user action:
core workflow:
desired mode: authorized exact clone / experience remix / product rebuild / motion reconstruction / QA
evidence available: live URL / screenshots / repo / source files / none
must-use assets:
must-not-include:
```

## Workflow

### 1. Capture The Reference

Use the browser or available screenshots to inspect:

- first viewport composition
- navigation and CTA roles
- typography scale and density
- section order and scroll rhythm
- hero media and foreground layers
- interaction details: hover, typewriter, parallax, sticky stages, reveal timing
- complex motion: video, Canvas, Lottie, WebGL, Three.js, SVG morphs
- responsive behavior

List transferable experience patterns and non-transferable surfaces.

For live websites, read `references/evidence-recon.md` and run the lightest honest recon path before implementation when feasible. Prefer real evidence over visual guesses:

- source/repo/license search
- desktop and mobile screenshots
- route map for multi-page sites
- interaction probe for hover, click, scroll, cursor, Canvas, or WebGL sites
- network/API capture for SPA, SaaS, or data-driven pages
- static asset mirror only for authorized exact clones or local learning

Record conclusions as `SOURCE`, `PARTIAL`, or `GUESS` for complex motion claims.

### 2. Decide Legal / Product Mode

Use this rule:

```text
User owns or has explicit authorization -> Mode 1 can be used.
No authorization or unclear rights -> Mode 2/3 only.
Reference value is mostly motion -> also apply Mode 4.
Existing output has weird product mismatches -> Mode 5.
```

Do not carry over third-party logos, mascots, exact copy, screenshots, videos, or distinctive artwork unless Mode 1 is clearly justified.

If source code or deployed assets are available, still choose the legal/product mode before using them. "Publicly accessible" does not mean "safe to ship copied assets."

### 3. Build A Mapping Table

Create a compact table before implementation:

```text
Reference module | Evidence | Experience to keep | Replacement for target product | Risk
```

Examples:

```text
Hero cinematic video | screenshot + motion probe | large spatial impact and slow movement | original product engine visual | avoid reference video asset
SDK code panel | DOM + screenshot | technical theater and confidence | workflow status/log panel | avoid irrelevant developer APIs
Install cards | screenshot | three-column decision surface | user entry choices | avoid dependency install flow for consumers
Phone mockup | screenshot | secondary context/device contrast | result preview only if mobile matters | avoid decorative leftovers
```

If a reference module does not serve the target product, replace or remove it.

### 4. Choose Motion Level

Read `references/motion-levels.md` whenever the reference includes advanced visual motion.

Use:

- **A Static** for quick concepts.
- **B 2.5D Overlay** for fast high-quality demos: original key visual plus particles, glows, scan lines, drift, parallax.
- **C Video Loop** for RMUX-like cinematic hero motion: generated/designed seamless `webm/mp4` plus native text overlay.
- **D Native Rebuild** for true interactive Three.js/WebGL/Canvas/Lottie/scroll-driven effects.

Do not silently flatten a motion-heavy reference into a static background. If tooling prevents C/D, implement B and state the upgrade path.

For Level D or WebGL/Canvas-heavy references, use the evidence discipline in `references/evidence-recon.md`: find real source/source maps first, mark claims `SOURCE/PARTIAL/GUESS`, and avoid tuning guessed constants to hide unknown timing, shader, or state behavior.

### 5. Create Original Assets

For the target product, design around its real metaphor:

```text
input -> processing/transformation -> output/result
```

Keep text, buttons, nav, and UI labels code-native whenever possible so the site stays editable and responsive. Use generated images or video only for visual scenes, not critical copy.

### 6. Implement

Follow the current repo's stack and patterns. Keep edits scoped.

Requirements:

- responsive first viewport
- stable dimensions for cards, panels, mockups, media, and controls
- real target-product copy
- original or user-owned assets
- reduced-motion fallback for continuous animation
- no accidental reference links, titles, alt text, or asset filenames in the final visible site

For product remixes:

- replace docs/API/GitHub buttons unless they are real product actions
- replace install commands with user entry points for consumer tools
- replace SDK/code samples with workflow/status panels unless the product is developer tooling
- replace comparison content with target-product alternatives

If recon produced reference artifacts, keep them under a non-shipped `RECON/` or notes directory. Do not import scraped reference assets into production output unless Mode 1 or an explicit license allows it.

### 7. Verify In Browser

Use the in-app browser or Playwright-style browser checks when available.

Verify:

- page loads at the target URL
- no relevant console/runtime errors
- desktop and the user's current viewport
- mobile viewport when practical
- scroll sections appear in the intended order
- motion visibly changes over time or with interaction
- text does not overlap or overflow
- reference assets/copy are gone unless authorized
- product logic is coherent

For motion, capture evidence beyond one screenshot: computed transform/opacity changes, video state, canvas pixel changes, or two screenshots separated by time.

Read `references/verification-audit.md` before final handoff when the task involved a live reference, exact clone, motion reconstruction, or a production-ready deliverable.

### 8. Product Logic QA

Before final, read `references/product-logic-qa.md` and check every visible section. Fix mismatches before reporting completion.

## Final Response

Report only high-signal details:

- mode used
- reference skeleton preserved
- product replacements made
- original assets or motion level used
- URL and changed files
- verification evidence
- remaining gap or next upgrade path, if any

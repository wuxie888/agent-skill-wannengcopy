# Copy Modes

Use this reference to choose the correct "copy" behavior.

## Mode 1: Authorized Exact Clone

Use when the user clearly says they own the site, own the brand/assets, are the maintainer, or have client authorization.

Goal:

- preserve content, layout, visual styling, and motion as closely as feasible
- keep text and brand assets if provided or publicly available with authorization
- rebuild effects with the closest practical implementation

Still verify:

- source assets actually load
- the clone is useful in the target stack
- no hidden third-party dependencies are required without consent
- retained code/assets are covered by ownership, license, or explicit authorization

## Mode 2: Experience Remix

Use by default when the reference belongs to someone else.

Allowed to preserve:

- composition
- interaction pattern
- scroll rhythm
- density
- motion category
- visual mood
- information hierarchy

Must replace:

- logo, mascot, brand marks
- exact copy
- proprietary screenshots
- hero videos and generated key art
- product-specific claims
- reference workflows that do not fit the target product

Use evidence recon to understand structure and motion, not to justify shipping copied assets. If the reference repo or deployed bundle is public but rights are unclear, keep it as `SOURCE` evidence and rebuild original target-product surfaces.

## Mode 3: Product Rebuild

Use when the user gives a different product and wants the reference site's quality.

Process:

```text
reference module -> user need -> target product section
```

Examples:

- developer SDK panel -> status workflow panel for an operations tool
- install cards -> choose workspace/upload/start cards for a consumer tool
- terminal demo -> real product output preview
- integrations wall -> supported inputs/outputs

Remove modules that only exist because the reference product needed them.

## Mode 4: Motion Reconstruction

Use when users point to "those effects", "scroll feels good", "hero moves", or "not static".

Route through `motion-levels.md`.

Do not treat a screenshot as final if the reference is motion-led. Build at least Level B, and propose Level C/D when the user wants a closer result.

For WebGL, Canvas, shader, or physics-heavy references, also route through `evidence-recon.md` and mark implementation claims `SOURCE`, `PARTIAL`, or `GUESS`.

## Mode 5: QA / Repair

Use when the page already exists but looks "weird", "not right", or "not like the reference".

Check:

- Is the section serving the target product?
- Did reference-specific content leak through?
- Is the motion level too low?
- Does the visual asset fight the native text?
- Are CTAs real actions?
- Does a device/mockup/code panel exist only because the reference had it?

Fix before explaining.

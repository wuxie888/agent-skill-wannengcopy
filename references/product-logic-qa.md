# Product Logic QA

Run this before final handoff.

## Section Questions

For each visible section, answer:

- What user problem does this section solve?
- Is this section serving the reference product instead of the target product?
- Does the copy match target-product vocabulary?
- Does the visual asset belong to the target product or user-owned brand?
- Is the primary CTA a real next action?
- Would the target user understand what to do?
- Does this section earn its place, or is it copied because the reference had it?

## Common Failures

Fix these before final:

- Developer SDK content appears in a consumer workflow.
- Install commands appear where normal users expect start/upload/create flows.
- Reference product screenshots remain visible.
- A phone, dashboard, CLI, or code panel exists only because the reference had one.
- Comparison table still compares the reference product's competitors.
- Hero visual is original but downstream sections explain the reference product.
- Buttons say docs/API/GitHub when the product needs upload/start/demo/result.
- Baked text inside generated imagery fights code-native headings.
- The page has good style but wrong product story.

## Required QA Ledger

Keep a short internal ledger:

```text
Section | Issue found | Fix
Hero | reference asset visible | replaced with original visual
Demo | irrelevant phone mockup | removed or changed to product result preview
Automation | SDK code leftover | changed to workflow/status panel
Entry | install dependencies shown | changed to user task entry points
```

If a reference-specific module is intentionally kept, state why it genuinely fits the target product.

Also check the evidence boundary from `verification-audit.md`: if a section still contains reference brand, URLs, screenshots, videos, alt text, filenames, analytics, or external assets, either remove it or document why Mode 1 authorization allows it.

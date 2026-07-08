# Verification Audit

Use this reference before final handoff when the task used a live reference, an exact clone mode, motion reconstruction, or a production-ready deliverable.

The goal is to prove the page works, preserves the intended reference experience, and no longer leaks protected reference surfaces unless authorized.

## Browser Checks

Verify at least:

- page loads at the local or deployed URL
- no relevant console or runtime errors
- desktop viewport renders without overlap
- mobile viewport renders without overlap when practical
- scroll sections appear in the intended order
- nav and primary CTAs point to real target-product actions
- forms, buttons, media, embeds, and links are not dead unless intentionally mocked
- reduced-motion behavior exists for continuous animation

For motion-heavy pages, capture one of:

- two screenshots separated by time
- computed transform/opacity/state changes
- video `currentTime` and loop/autoplay state
- canvas pixel/nonblank checks
- interaction proof for cursor, scroll, drag, or hover

## Reference Leakage Audit

Search the implemented source and visible page for:

- reference brand names, product names, slogans, URLs, titles, alt text, filenames
- third-party logos, mascots, screenshots, videos, or distinctive artwork
- original install commands, docs/API/GitHub CTAs, or code panels that do not fit the target product
- analytics, pixels, heatmaps, beacons, tracking scripts
- TODO, placeholder, lorem ipsum, stale comparison claims
- external asset URLs that should be self-hosted, replaced, or documented

Mode 1 authorized exact clone may keep reference surfaces, but still report what was retained and why it is allowed.

## Product Logic QA Gate

After browser checks, run the section-level product QA from `product-logic-qa.md`.

Do not finish while the page has a beautiful reference shell but the wrong product story. Common blockers:

- consumer product page still explains developer SDKs
- user workflow uses install commands instead of start/upload/create/result
- reference screenshots remain downstream after an original hero was added
- buttons advertise docs/API/GitHub without real relevance
- comparison sections compare the reference product's competitors

## Evidence Ledger

Keep the final evidence concise:

```text
URL tested:
Desktop viewport:
Mobile viewport:
Console/runtime:
Motion evidence:
Reference leakage scan:
Product QA:
Known gaps:
```

If automated `web-clone` probes are available, include generated artifacts such as `RECON/`, `CLONE_REPORT.md`, `CLONE_AUDIT.md`, and screenshot paths. If not, summarize the manual browser evidence honestly.

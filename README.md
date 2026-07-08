# Wannengcopy · 万能复刻

> Evidence-first website copy-remix workflow for Claude Code / Codex style Skill systems.
> 先侦察取证，再把参考网站体验改造成自己的产品官网。

Wannengcopy turns a reference website into a usable, original product site. It supports lawful exact cloning when you own or are authorized to copy the source, but defaults to experience remix: preserve structure, interaction feel, motion language, visual rhythm, and product-quality polish while replacing brand assets, copy, product logic, media, and protected surfaces.

## What It Does

- Inspects a reference site with evidence before implementation.
- Separates authorized exact clone, experience remix, product rebuild, motion reconstruction, and QA/repair modes.
- Classifies site complexity from static pages to WebGL/Canvas/Three.js and SaaS-like surfaces.
- Builds a mapping table from reference modules to target-product replacements.
- Guides motion delivery from static, 2.5D overlays, video loops, to native WebGL/Canvas rebuilds.
- Audits final output for reference leakage, wrong product logic, dead CTAs, tracking scripts, and motion failures.

## Install

### Codex

```bash
git clone https://github.com/<your-org>/claude-skill-wannengcopy.git ~/.codex/skills/wannengcopy
```

### Claude Code

```bash
git clone https://github.com/<your-org>/claude-skill-wannengcopy.git ~/.claude/skills/wannengcopy
```

Replace `<your-org>` after you publish this repository to your own GitHub account.

## Use

Say things like:

- "用 wannengcopy 参考这个官网做我们的产品页: https://..."
- "用万能复刻，把这个站的滚动节奏和 hero 动效迁移到我们的官网"
- "Use wannengcopy to remix this reference site into an original product website"
- "用 wannengcopy 检查这个复刻页面为什么产品逻辑怪"
- "用 wannengcopy 做 WebGL/Canvas 效果还原，但不要带走原站素材"

## Operating Modes

| Mode | Use when |
|---|---|
| Authorized Exact Clone | You own the site or have explicit authorization. |
| Experience Remix | Default for third-party references. Keep the feel, replace protected surfaces. |
| Product Rebuild | Use a reference as a quality bar for a different product. |
| Motion Reconstruction | The main value is hero motion, scroll choreography, Three.js, WebGL, Canvas, Lottie, or video. |
| QA / Repair | A previous output looks good but copy, assets, logic, or sections feel wrong. |

## Evidence-First Workflow

Wannengcopy keeps the product goal first, but uses reference evidence to avoid hallucinated implementation:

1. Capture the reference: screenshots, layout, typography, section order, motion, interactions, responsive behavior.
2. Search source and license when feasible.
3. Classify complexity from L1 static pages to L6 SaaS/ecommerce/logged-in systems.
4. Mark complex implementation claims as `SOURCE`, `PARTIAL`, or `GUESS`.
5. Map reference modules to original target-product replacements.
6. Implement in the current repo's stack and patterns.
7. Verify in browser and audit for reference leakage.
8. Run product-logic QA before final handoff.

## Structure

```text
claude-skill-wannengcopy/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── copy-modes.md
│   ├── evidence-recon.md
│   ├── motion-levels.md
│   ├── product-logic-qa.md
│   └── verification-audit.md
├── LICENSE
└── README.md
```

## Notes On Rights

Publicly accessible code, screenshots, videos, or deployed assets are not automatically safe to ship. If ownership or license is unclear, use the reference as evidence and rebuild original target-product surfaces.

## Credits

Wannengcopy's evidence-recon layer is influenced by source-first web-clone workflows, including Jane Xiaoer's `claude-skill-web-clone` methodology. This project keeps the product-remix goal as the main workflow and uses recon as an inspection and verification subsystem.

## License

MIT. See [LICENSE](LICENSE).

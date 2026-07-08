<h1 align="center">Wannengcopy · 万能复刻</h1>

<p align="center">
  Evidence-first website copy-remix workflow for agent Skill systems.
  <br />
  先侦察取证，再把参考网站体验改造成自己的产品官网。
</p>

<p align="center">
  <a href="https://github.com/wuxie888/agent-skill-wannengcopy/blob/main/LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-111827.svg" /></a>
  <a href="https://github.com/wuxie888/agent-skill-wannengcopy"><img alt="Agent Skill" src="https://img.shields.io/badge/agent-skill-2563eb.svg" /></a>
  <img alt="Codex ready" src="https://img.shields.io/badge/Codex-ready-16a34a.svg" />
  <img alt="Claude Code ready" src="https://img.shields.io/badge/Claude_Code-ready-7c3aed.svg" />
</p>

## What This Is

Wannengcopy is a reusable Skill for turning a reference website into a usable, original product site.

It supports lawful exact cloning when you own or are authorized to copy the source, but defaults to **experience remix**:

- keep the reference site's structure, interaction feel, motion language, visual rhythm, and product-quality polish
- replace brand assets, copy, product logic, media, screenshots, videos, claims, and protected surfaces
- verify the output in a browser and audit it before handoff

## Install

### Codex

```bash
git clone https://github.com/wuxie888/agent-skill-wannengcopy.git ~/.codex/skills/wannengcopy
```

### Claude Code

```bash
git clone https://github.com/wuxie888/agent-skill-wannengcopy.git ~/.claude/skills/wannengcopy
```

Then ask your agent:

```text
用 wannengcopy 参考这个官网做我们的产品页: https://...
```

## When To Use

Use Wannengcopy when you want to:

- remix a reference landing page into your own product website
- rebuild a site with the same interaction rhythm but different product logic
- migrate Linear / Raycast / Apple / Vercel / RMUX-style page quality into another domain
- reconstruct hero motion, scroll choreography, Canvas, WebGL, Three.js, Lottie, or video-led sections
- QA a previous clone/remix that looks good but still feels wrong
- inspect a reference site with evidence before deciding what to preserve

## Operating Modes

| Mode | Purpose |
|---|---|
| Authorized Exact Clone | Use only when you own the source or have explicit authorization. |
| Experience Remix | Default. Preserve feel and structure, replace protected surfaces. |
| Product Rebuild | Use a reference site as a quality bar for a different product. |
| Motion Reconstruction | Focus on hero motion, scroll rhythm, Three.js, WebGL, Canvas, Lottie, or video. |
| QA / Repair | Fix product mismatch, leaked assets, bad CTAs, weak motion, or wrong sections. |

## Evidence-First Workflow

Wannengcopy keeps the product goal first, but uses reference evidence to avoid hallucinated implementation.

```text
reference site
  -> evidence recon
  -> mode + complexity decision
  -> module mapping
  -> original product implementation
  -> browser verification
  -> reference leakage audit
  -> product logic QA
```

The skill can classify references from simple static pages to WebGL-heavy and SaaS-like systems:

| Level | Type |
|---|---|
| L1 | Static HTML/CSS |
| L2 | CMS / company content site |
| L3 | React / Vue / Next content frontend |
| L4 | Animation-heavy brand site |
| L5 | WebGL / Canvas / Three.js |
| L6 | SaaS / ecommerce / logged-in system |

For complex motion claims, Wannengcopy uses evidence labels:

| Label | Meaning |
|---|---|
| `SOURCE` | Direct evidence such as repo lines, source maps, DOM capture, shader text, network response, screenshot, or frame capture. |
| `PARTIAL` | Useful clue but not enough for a verified claim. |
| `GUESS` | Visual or conceptual inference that must not be treated as fact. |

## What It Produces

The agent using this Skill should produce:

- a reference capture summary
- a legal/product mode decision
- a compact module mapping table
- a motion level choice
- original product copy and assets
- browser verification evidence
- leakage audit results
- product-logic QA notes

## Skill Layout

```text
agent-skill-wannengcopy/
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

## Example Prompts

```text
用万能复刻，把这个站的滚动节奏和 hero 动效迁移到我们的官网。
```

```text
Use wannengcopy to remix this reference site into an original product website.
```

```text
用 wannengcopy 检查这个复刻页面为什么产品逻辑怪。
```

```text
用 wannengcopy 做 WebGL/Canvas 效果还原，但不要带走原站素材。
```

## Rights Boundary

Publicly accessible code, screenshots, videos, or deployed assets are not automatically safe to ship. If ownership or license is unclear, use the reference as evidence and rebuild original target-product surfaces.

## Credits

Wannengcopy's evidence-recon layer is influenced by source-first web-clone workflows, including Jane Xiaoer's [`claude-skill-web-clone`](https://github.com/Jane-xiaoer/claude-skill-web-clone) methodology.

This project keeps the product-remix goal as the main workflow and uses recon as an inspection and verification subsystem.

## License

MIT. See [LICENSE](LICENSE).

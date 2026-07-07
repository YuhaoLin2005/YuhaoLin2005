# Yuhao Lin

> I ran 50 AI coding sessions and noticed a pattern: after ~20 turns, the model starts fabricating and forgetting. So I designed a system that catches this — and tested whether it actually works.
> Third-year undergrad at FAFU (Spatial Information & Digital Technology). Seeking summer 2026 internship.

---

## What I Do

I study how AI systems behave over time — what makes them drift, how to detect it, and whether interventions actually help. My approach: observe patterns in real usage → design lightweight interventions → test them with controlled experiments → write up what I learn.

---

## Projects

### [Hermes Workspace](https://github.com/YuhaoLin2005/hermes-workspace)
A self-model freshness monitor with closed-loop regeneration. Compact identity file → attention routing table → automated checks (Python scripts at session boundaries) → causal feedback loop. Independently converged on the same architectural pattern as Anthropic's J-space paper (July 2026). Causal swap experiment verified (n=4): removing one routing rule measurably changes agent behavior. Runs on DeepSeek V4 Pro. MIT.

### [DeepSeek × Claude Code Starter](https://github.com/YuhaoLin2005/deepseek-claude-code-starter) ⭐2
Scaffold for running DeepSeek models inside Claude Code. Agents, rules, security hooks, OCR, auto-backup.

### Academic: GIS & Remote Sensing
- [Soil-WebGIS](https://github.com/YuhaoLin2005/soil-webgis) — Full-stack digital soil mapping (ArcGIS JS API + GeoServer + PostgreSQL)
- Landcover Classifier — Landsat 8/9 → 5-class land cover, Decision Tree + Random Forest, 96.98% cross-validation agreement (private)

---

## Writing

I publish what I learn. 18 posts on [DEV.to](https://dev.to/yuhaolin2005) (English), 4 on [掘金](https://juejin.cn/user/4250072430682412/posts) (Chinese). Topics: AI agent reliability, prompt architecture, context engineering, open source workflow.

---

## Open Source

Merged PRs to major AI agent ecosystems:

| Project | Stars | Contribution | Status |
|---------|-------|-------------|--------|
| [ECC](https://github.com/affaan-m/ECC) | 227k | delivery-gate quality skill + Stop hook | ✅ Merged |
| [claude-skills](https://github.com/alirezarezvani/claude-skills) | 21.2k | Named-persona adversarial review | ✅ Merged (co-author) |
| [claude-code-skills](https://github.com/daymade/claude-code-skills) | 1.2k | Marketplace validation + Windows compatibility | ✅ Merged |

---

**Contact:** lin_yuhao2005@163.com

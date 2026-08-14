<p align="center">
  <samp>Yuhao Lin</samp>
</p>

<p align="center">
  <sub><a href="https://yuhaolin2005.github.io">thought becomes garden</a></sub>
</p>

---

**I proved AI agents can't self-verify — then built a system that catches 98.7% of their violations.**

FAFU undergrad · Spatial Information & Digital Technology · Seeking 2027 internship — LLM evaluation & agent governance · linyuhao2005@gmail.com

`build in public` · `question → test` · `self-falsify` · `honest failure` · `systems not tools` · `measure everything` · `write to think` · `design from first principles`

━━━

<a href="https://dev.to/yuhaolin2005"><img src="https://img.shields.io/badge/DEV.to-000?style=flat&logo=devdotto&logoColor=white" /></a>
<a href="https://juejin.cn/user/4250072430682412"><img src="https://img.shields.io/badge/掘金-1E80FF?style=flat&logo=juejin&logoColor=white" /></a>
<a href="https://github.com/YuhaoLin2005"><img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white" /></a>

---

### By the numbers

| What | Number | Evidence |
|------|--------|----------|
| Experiments completed | **16** | 2,500+ API calls, 1,100+ formal trials, 3 architectures |
| Violation reduction | **55.9% → 0.7%** | 34-session retrospective + 150-task A/B test |
| Zero-violation ceiling | **99.3%** | 149/150 tasks with full L0-L4 stack |
| Logprob evidence | **d=+0.578, BF=282k** | 40 probes × 4 categories, API-read DV (no human scoring) |
| Claims validated | **10** | 2 hypotheses pre-registered and honestly falsified |
| Production hooks | **20+** | 38-hook audit → 87% noise removed, zero signal loss |
| DEV.to articles | **32** | 49 comments written, 608 followers, 29 reactions |
| Open source PRs | **4 merged** in external repos | evalscope #1576 · ECC #2377/#2378 · claude-skills #867 (co-author) |
| Commits since July 1 | **131+** | hermes-workspace (106) + paper-validator (25) + others |

---

### The finding

LLM agents share a structural constraint I call the **Prose Barrier**: generation and self-verification use the same decoder `P(token | context; θ)`, so an agent cannot distinguish "I followed the rule" from "I generated text claiming I followed the rule." This is not a prompt engineering problem — it's an architectural one.

The fix is **Cross-Type Bidirectional Verification (CTBV)** — pairing mechanical gates (filesystem checks, regex — deterministic, outside the model) with semantic gates (logprob probes, format encoding — probabilistic, inside the model). Because these two gate types have **orthogonal blind spots**, their joint false-negative rate approaches zero. Formalized with 3 theorems and validated across 16 experiments.

**Immutable preprint + every figure & data file, minted on Zenodo:** [doi 10.5281/zenodo.21933727](https://doi.org/10.5281/zenodo.21933727)

### How I work

- **Deterministic scoring only.** Regex, file timestamps, exit codes. No LLM judge — LLMs share the Prose Barrier.
- **Pre-registration.** SHA256-hashed experiment scripts before running. If the data kills my hypothesis, I publish it anyway.
- **Honest null results.** P1-2 (240 trials): pre-registered hypothesis was WRONG. The actual finding was more interesting. Both are in the report.

---

### Repositories

| Repo | What's inside |
|------|---------------|
| **[paper-validator](https://github.com/YuhaoLin2005/paper-validator)** | Experiment runner + 16 result files + [CTBV Technical Report](https://github.com/YuhaoLin2005/paper-validator/blob/main/CTBV-TECHNICAL-REPORT.md) (10 claims, 16 experiments, ~2,500 API calls) |
| **[hermes-workspace](https://github.com/YuhaoLin2005/hermes-workspace)** | Live 5-layer agent governance system (L0-L4) + [CTBV Formal Theory](https://github.com/YuhaoLin2005/hermes-workspace/blob/main/paper/theory/cross-type-bidirectional-verification.md) (3 theorems, formal proofs, 20 references, target ICLR/NeurIPS) |
| **[compact-counter](https://github.com/YuhaoLin2005/compact-counter)** | 459 sessions tracked, 425 compaction events, context degradation analysis |
| **[digital-twin-trainer](https://github.com/YuhaoLin2005/digital-twin-trainer)** | QLoRA + DPO pipeline, behavioral drift metrics, 253 training samples |

---

### 3 articles that tell the story

1. **[I Discovered AI Agents Can't Self-Verify. The Real Problem Is Much Bigger.](https://dev.to/yuhaolin2005/i-discovered-ai-agents-cant-self-verify-the-real-problem-is-much-bigger-2jb6)**
   → Theory: Prose Barrier + CTBV + Gate Audit. 38 hooks, 87% noise removed, zero signal loss.

2. **[I Ran 150 Tasks to Test If AI Agents Follow Rules. The Answer Surprised Me.](https://dev.to/yuhaolin2005/i-ran-150-tasks-to-test-if-ai-agents-follow-rules-the-answer-surprised-me-2670)**
   → Empirics: 55.9% violation rate without gates → 0.7% with mechanical enforcement. Syllogism vs imperative A/B.

3. **[I Pre-Registered a Hypothesis. 600 API Calls Later, the Data Killed It.](https://dev.to/yuhaolin2005/i-pre-registered-a-hypothesis-600-api-calls-later-the-data-killed-it-1aec)**
   → Rigor: Pre-registration, SHA256 tamper-proofing, hypothesis falsified, honest reporting.

More: [dev.to/yuhaolin2005](https://dev.to/yuhaolin2005) (32 articles) · [掘金](https://juejin.cn/user/4250072430682412) (20 articles, 中文)

---

### Open source contributions

- **[ECC](https://github.com/affaan-m/ECC)** — PR [#2377](https://github.com/affaan-m/ECC/pull/2377) growth-log skill, [#2378](https://github.com/affaan-m/ECC/pull/2378) delivery-gate skill (both merged)
- **[claude-skills](https://github.com/alirezarezvani/claude-skills)** — PR [#867](https://github.com/alirezarezvani/claude-skills/pull/867) named-persona-adversarial-review (merged · Co-authored-by)
- **[crewAI](https://github.com/crewAIInc/crewAI)** — Issue [#6428](https://github.com/crewAIInc/crewAI/issues/6428) language-aware prompt routing → PR [#6491](https://github.com/crewAIInc/crewAI/pull/6491) built by ashusnapx (96 tests, pending merge)
- **[evalscope](https://github.com/modelscope/evalscope)** (Alibaba's LLM-evaluation framework) — PR [#1576](https://github.com/modelscope/evalscope/pull/1576) **merged 2026-08-14** — fail-closed guard on `[ERROR]` judge responses in the shared LLM-judge scoring path + surfaced two silent score-extraction paths + unit tests locking the contract
- **[TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory)** — PR [#977](https://github.com/TencentCloud/TencentDB-Agent-Memory/pull/977) (open) — aligned conversation-delete isolation with L1 atomic delete, fixing silent no-op deletes
- **[coze-loop](https://github.com/coze-dev/coze-loop)** — PR [#617](https://github.com/coze-dev/coze-loop/pull/617) (open) — anchored score-extraction regex to the key position, fixing silent wrong-score pulls from reason text (42/42 tests, red/green verified)
- **[agentscope](https://github.com/agentscope-ai/agentscope)** — [Discussion #2306](https://github.com/agentscope-ai/agentscope/discussions/2306) (open) — opt-in "source changed since derived" recency marker for AgenticMemoryMiddleware

---

### Community

4 DEV.to readers proposed experiments later adopted into the pipeline — Mike Czerwinski (residual cluster analysis), Dipankar Sarkar (SHA256 pre-registration), Max Quimby (mechanizability scanner), René Zander (independent gate engine architecture comparison). 49 comments written across 93 received.

---

[**LEARNING.md**](./LEARNING.md) — Public learning log. Patterns from 150+ sessions. What broke, what I learned, what I built.

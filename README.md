# 林宇浩

> FAFU 空间信息大三 · 找 2026 暑期实习

**AI agent 到底有没有在遵守规则？** 我用量化的方式回答这个问题——不靠感觉，靠实验。

核心发现：你没法让 LLM 检查自己的输出。生成和验证共享同一个概率分布，就像让考生批改自己的考卷。所以我不让 AI 检查 AI。我用文件时间戳、正则表达式、进程退出码——这些东西不在模型的生成回路里，说服不了。

13 个实验，440+ 次 API 调用。有假设被数据打脸了（预注册的，没法赖）。代码、数据、实验配置全公开。

---

[**hermes-workspace**](https://github.com/YuhaoLin2005/hermes-workspace) — 论文 + 实验数据：五层验证架构
[**paper-validator**](https://github.com/YuhaoLin2005/paper-validator) — 独立验证工具：`python -m paper_validator claim --claim all --trials 30`

---

📝 [DEV.to](https://dev.to/yuhaolin2005) (EN) · [掘金](https://juejin.cn/user/4250072430682412) (中文)

*被数据打脸的感觉，像吃到一颗写着"草莓味"、咬开是芥末味的糖。嚼着嚼着，发现芥末味其实挺好吃的。*

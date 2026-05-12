# Task Template

请先读取：

```text
.ai/PROJECT_RULES.md
.ai/toolkit/ROUTER.md
```

本次任务：

[在这里填写任务]

输入材料：

- 数据：
- 论文上下文：
- 当前想法 / 项目背景：
- 目标输出：
- 特殊要求：

调用规则：

1. 如果是文献综述任务，使用 `.ai/toolkit/skills/literature-review/`，输出保存到 `literature/`。
2. 如果是论文阅读任务，使用 `.ai/toolkit/skills/paper-reading/`，输出保存到 `literature/`。
3. 如果是 brainstorm、选题、差异化、novelty 检查或 Agent workflow 设计任务，使用 `.ai/toolkit/skills/critical-ideation/`，输出保存到 `ideas/`。
4. 如果是实验设计任务，使用 `.ai/toolkit/skills/experiment-design/`，输出保存到 `experiments/`。
5. 如果是绘图任务，使用 `.ai/toolkit/skills/scientific-figure-making/`，脚本保存到 `figures/scripts/`，图像保存到 `figures/outputs/`。
6. 如果是从零构建论文任务，使用 `.ai/toolkit/skills/scholarly-writing/`，输出保存到 `paper/`。
7. 如果是润色、翻译或审稿检查任务，参考 `.ai/toolkit/prompt-libraries/awesome-ai-research-writing/`。
8. 如果是图表和写作混合任务，先完成图，再完成图注和论文分析。
9. 如果是完整 workflow 任务，按顺序执行：literature-review → paper-reading → critical-ideation → experiment-design → scientific-figure-making → scholarly-writing → awesome-ai-research-writing → reviewer check。
10. 所有输出都保存到当前项目，不要修改 toolkit 源文件。

期望输出：

- 文献综述报告
- 论文阅读笔记
- Idea report / Search log / Decision matrix / MVP plan
- 实验设计方案 / 消融实验方案 / 可复现性清单
- Python 脚本 / PDF 图像 / PNG 图像
- 中文图注 / 英文图注
- 实验分析段落
- 论文草稿
- Reviewer 检查意见

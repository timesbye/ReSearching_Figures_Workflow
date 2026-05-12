# awesome-ai-research-writing

> **上游仓库**：[Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)
>
> 本目录不包含上游仓库的完整内容。请通过上方链接访问原始仓库。

## 用途

本目录作为 [ALL-in-ALL_ReSearching_Workflow_Skill](https://github.com/timesbye/ALL-in-ALL_ReSearching_Workflow_Skill) 的学术写作 Prompt 库入口。

当 Agent 需要执行学术写作、润色、翻译、实验分析或 reviewer 风格检查时，应参考上游仓库中的 Prompt 模板和 Agent Skills。

## 归属声明

- 上游项目：[awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) by [Leey21](https://github.com/Leey21)
- 上游仓库未附带开源许可证，默认适用 GitHub 公开仓库规则（All Rights Reserved）
- 本项目仅引用上游仓库链接，不复制其内容
- 如需使用上游仓库的 Prompt 模板，请直接访问原始仓库并遵守其使用条款

## 版本锁定

为确保可复现性，建议克隆上游仓库时锁定到指定 commit：

```bash
git clone https://github.com/Leey21/awesome-ai-research-writing.git
cd awesome-ai-research-writing
# 锁定到已知可用的 commit（请根据实际验证结果更新此值）
git checkout <verified-commit-sha>
```

> **注意**：上方 `<verified-commit-sha>` 需要在首次验证后填入实际值。如未填写，请使用上游仓库的最新 main 分支，但需注意内容可能随上游变更而变化。

## 推荐使用方式

1. 将上游仓库 clone 到本目录（建议锁定 commit）

2. 在 Agent 中通过 `.ai/toolkit/prompt-libraries/awesome-ai-research-writing/` 路径引用

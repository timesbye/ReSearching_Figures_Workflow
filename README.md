# ReSearching Figures Workflow

[![GitHub](https://img.shields.io/badge/Github-timesbye%2FReSearching\_Figures\_Workflow-blue?logo=github)](https://github.com/timesbye/ReSearching_Figures_Workflow)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**从 idea 到图表到论文表达的一体式科研 workflow。**

本项目通过引用已有前沿科研绘图和学术写作工作，并在此基础上构建 brainstorm / 选题 / novelty 检查功能，将分散的科研工具整合为一个连续的、可追溯的工作流。

**GitHub 仓库**：[https://github.com/timesbye/ReSearching_Figures_Workflow](https://github.com/timesbye/ReSearching_Figures_Workflow)

## 项目定位

ReSearching Figures Workflow 不是从零发明所有模块，而是做三件事：

1. **引用前沿科研工具**：引入 [awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) 的学术写作 Prompt 库和 [figures4papers](https://github.com/ChenLiu-1996/figures4papers) 的科研绘图范式
2. **构建原创 brainstorm 能力**：在此基础上开发 `critical-ideation` Skill——一个 Critic + Search + Ideation 型选题工具，能主动质疑、检索已有方案、重构 idea、收敛到可执行 MVP
3. **整合为一体式 workflow**：通过路由规则、项目模板和产物目录，把 ideation → 绘图 → 写作 → reviewer 检查串成一个顺序依赖的连续工作流

核心价值：**把分散能力组织成一个能从想法走到图表、再走到论文表达的连续生产链。**

## 三类核心能力

| 能力 | 来源 | 用途 |
|------|------|------|
| 学术写作 Prompt 库 | 引用 [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) | 润色、翻译、实验分析、reviewer 检查 |
| 科研绘图 Skill | 参考 [ChenLiu-1996/figures4papers](https://github.com/ChenLiu-1996/figures4papers) | 论文级 matplotlib 图、PDF/PNG 导出 |
| Critical Ideation Skill | **本项目原创** | brainstorm、主动质疑、竞品检索、方向重构、MVP 收敛 |

## Workflow 链条

```text
idea → shortlist → evidence figure → caption & analysis → reviewer constraint → final claim
```

1. `critical-ideation`：先筛方向，不让项目在错误的 idea 上浪费时间
2. `scientific-figure-making`：把方向绑定到可见证据，而不是抽象口号
3. `awesome-ai-research-writing`：把图表结果整理成论文级表达
4. `reviewer_check`：防止过度 claim，逼着结论回到证据边界内

## Repository Layout

```text
ReSearching_Figures_Workflow/
|-- README.md
|-- LICENSE
|-- ROUTER.md
|-- docs/
|   `-- USAGE.md
|-- prompt-libraries/
|   `-- awesome-ai-research-writing/   (引用入口，需单独 clone 上游仓库)
|-- skills/
|   |-- scientific-figure-making/      (基于 figures4papers 编写的使用指南)
|   `-- critical-ideation/             (本项目原创)
|       |-- SKILL.md
|       |-- templates/
|       `-- examples/
|-- prompts/
|   |-- polish_cn.md
|   |-- translate_cn_to_en.md
|   |-- reviewer_check.md
|   |-- experiment_analysis.md
|   |-- figure_generation.md
|   `-- paper_figure_full_pipeline.md
|-- templates/
|   `-- project_ai/
|       |-- .ai/
|       |   |-- PROJECT_RULES.md
|       |   `-- TASK_TEMPLATE.md
|       |-- data/
|       |-- figures/
|       |   |-- scripts/
|       |   `-- outputs/
|       |-- ideas/
|       `-- paper/
|-- examples/
|   `-- GeoAgent-Thesis/
`-- scripts/
    |-- install_to_codex.ps1
    |-- install_to_codex.sh
    |-- link_to_project.ps1
    `-- link_to_project.sh
```

## Quick Start

1. 复制模板到你的科研项目目录。
2. 通过 `scripts/link_to_project.ps1` 或 `scripts/link_to_project.sh` 把本仓库链接到目标项目的 `.ai/toolkit/`。
3. 在 Trae / Codex 中先读取：

```text
.ai/PROJECT_RULES.md
.ai/toolkit/ROUTER.md
```

4. 若使用 Codex 全局 skill，可执行：

```powershell
.\scripts\install_to_codex.ps1
```

或：

```bash
chmod +x scripts/install_to_codex.sh
./scripts/install_to_codex.sh
```

## Recommended Project Bootstrap

```text
My-Research-Project/
|-- .ai/
|   |-- PROJECT_RULES.md
|   |-- TASK_TEMPLATE.md
|   `-- toolkit -> ReSearching_Figures_Workflow
|-- data/
|-- figures/
|   |-- scripts/
|   `-- outputs/
|-- ideas/
`-- paper/
```

复制模板：

```powershell
Copy-Item -Recurse .\templates\project_ai\* D:\Projects\My-Research-Project\
```

建立链接：

```powershell
.\scripts\link_to_project.ps1 -ProjectPath "D:\Projects\My-Research-Project"
```

## Typical Workflows

- 仅写作任务：使用 `prompt-libraries/awesome-ai-research-writing/`
- 仅绘图任务：使用 `skills/scientific-figure-making/`
- 仅 ideation / 选题 / 差异化任务：使用 `skills/critical-ideation/`
- 图表 + 论文表达联合任务：先生成图，再写图注、结果分析和 reviewer 检查
- ideation + proposal / PRD / paper introduction 联合任务：先用 `critical-ideation` 生成并筛选方向，再用写作 prompt 库写成正式文本

详见 [ROUTER.md](https://github.com/timesbye/ReSearching_Figures_Workflow/blob/main/ROUTER.md) 与 `prompts/` 目录中的入口文档。

## Example Project

仓库内置了一个基于模板生成的示例项目：

```text
examples/GeoAgent-Thesis/
```

示例项目包含两类可直接发送给 Agent 的任务：

- 图表 + 写作任务：`examples/GeoAgent-Thesis/paper/notes/demo_task.md`
- ideation 任务：`examples/GeoAgent-Thesis/ideas/demo_ideation_task.md`

如果你要直接展示这个仓库的整合 workflow，优先阅读：

- [`examples/GeoAgent-Thesis/WORKFLOW_SHOWCASE.md`](https://github.com/timesbye/ReSearching_Figures_Workflow/blob/main/examples/GeoAgent-Thesis/WORKFLOW_SHOWCASE.md)

建议先阅读：

- [`examples/GeoAgent-Thesis/README.md`](https://github.com/timesbye/ReSearching_Figures_Workflow/blob/main/examples/GeoAgent-Thesis/README.md)
- [`docs/USAGE.md`](https://github.com/timesbye/ReSearching_Figures_Workflow/blob/main/docs/USAGE.md)

## Usage Guide

完整教程见：[`docs/USAGE.md`](https://github.com/timesbye/ReSearching_Figures_Workflow/blob/main/docs/USAGE.md)

## Third-Party Acknowledgments

本项目引用了以下前沿科研工具，它们的原始内容归原作者所有：

| 项目 | 作者 | 用途 | 许可证 |
|------|------|------|--------|
| [awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) | [Leey21](https://github.com/Leey21) | 学术写作 Prompt 库 | 未声明（All Rights Reserved） |
| [figures4papers](https://github.com/ChenLiu-1996/figures4papers) | [Chen Liu](https://chenliu-1996.github.io/) (Yale) | 科研绘图范式参考 | 未声明（All Rights Reserved） |

- 本项目**不复制分发**上述仓库的原始内容
- `prompt-libraries/awesome-ai-research-writing/` 仅作为引用入口，用户需自行 clone 上游仓库
- `skills/scientific-figure-making/` 为本项目基于 figures4papers 绘图范式编写的使用指南，不包含其原始脚本
- `skills/critical-ideation/` 为本项目原创内容

详见 [LICENSE](LICENSE) 中的 Third-Party Acknowledgments 部分。

## License

本项目原创内容采用 [MIT License](LICENSE) 授权。

上游项目的原始内容归各自作者所有，适用其各自的使用条款。

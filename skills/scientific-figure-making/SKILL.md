---
name: scientific-figure-making
description: >-
  Covers publication-ready matplotlib figures for academic papers, slides, and
  reports—bars, trends, scatter, heatmaps, and multi-panel layouts—with this
  repository's house style, print/vector export conventions, and parity with
  figures4papers demos. v4 adds VLM figure review loop for quality verification
  and concept diagram generation. Use when the user is finalizing or creating such figures
  in matplotlib. Do not use for interactive dashboards or web viz (Plotly, Altair,
  Bokeh), exploratory-only plots without a publication target, dominant 3D or
  geographic mapping, or Illustrator/Figma-first infographic workflows.
---

# Scientific figure making

> **设计灵感与参考来源**：本 Skill 的绘图风格和设计理论参考自 [ChenLiu-1996/figures4papers](https://github.com/ChenLiu-1996/figures4papers)（by [Chen Liu](https://chenliu-1996.github.io/)，Yale University）。v4 VLM 图表审查闭环参考自 [PaperOrchestra](https://arxiv.org/abs/2604.05018) 的 PaperBanana VLM 闭环优化和 [AI Scientist-v2](https://github.com/SakanaAI/AI-Scientist-v2) 的 VLM 图表审查；概念示意图生成参考自 PaperOrchestra 的 PaperBanana 模块。本目录中的文档为 ALL-in-ALL_ReSearching_Workflow_Skill 项目基于其绘图范式编写的使用指南，不包含 figures4papers 的原始脚本代码。如需查看完整的绘图脚本和输出示例，请访问上游仓库。

Open `references/` only as needed; do not preload every file. Start from the table below, then follow links inside the document you opened (and into `figure_*` code via [references/demos.md](references/demos.md)) instead of loading the full reference set up front.

## When to load this skill

- Matplotlib figures for **papers, slides, or reports** that must match **this repo's publication look** (fonts, palette, spines, legends, export).
- Requests involving **grouped bars, trend lines, heatmaps, multi-panel grids**, or **PDF/SVG/high-DPI** output in a scientific-figure context.
- References to **figures4papers** `figure_*` projects or "same style as the repo figures."
- **Concept diagram generation** for illustrating system architectures, workflows, or conceptual frameworks.
- **VLM-based figure quality verification** before finalizing figures.

## When not to load

- **Plotly, Altair, Bokeh**, or other interactive / web-first plotting.
- **EDA-only** plots where seaborn or pandas is enough until there is a publication target.
- Primary workflow is **3D, GIS**, or **non-matplotlib** tooling.
- **Illustrator / Figma–first** layout or infographic (not matplotlib data plots).

## Core workflow

### Stage 1: Determine figure requirements

Identify:

- Figure type: data plot, comparison chart, architecture diagram, concept diagram
- Target: paper section, slide, report
- Data source: experiment results, CSV, manual specification
- Export format: PDF, PNG, SVG
- Size constraints: single column, double column, full page

### Stage 2: Generate figure code

Follow the house style from `references/`:

- Use the repo's `PALETTE` and typography
- Generate reproducible Python scripts
- Save scripts to `figures/scripts/`
- Save outputs to `figures/outputs/`
- Export both PDF and PNG

### Stage 3: VLM figure review loop (v4 new)

> **来源**：PaperOrchestra 的 PaperBanana VLM 闭环优化 + AI Scientist-v2 的 VLM 图表审查

After generating a figure, use a Vision Language Model (VLM) to review the figure quality before finalizing it. This is an iterative process: generate → review → fix → re-review until quality standards are met.

**When to use VLM review:**

- The user has access to a VLM (e.g., GPT-4V, Claude with vision, Gemini Pro Vision)
- The figure is for a publication submission
- The user explicitly requests quality verification

**When to skip VLM review:**

- No VLM is available (the user's AI coding tool lacks vision capabilities)
- The figure is for internal use or quick exploration
- The user explicitly opts out

**VLM review checklist:**

1. **Axis labels and ticks**: Are all axes labeled? Are tick values readable? Are units specified?
2. **Legend**: Is the legend present and complete? Are all series explained?
3. **Data-visual consistency**: Does the visual pattern match the described data? Are there visual artifacts?
4. **Color accessibility**: Can the figure be understood in grayscale? Are colors distinguishable for colorblind readers?
5. **Text-figure alignment**: Does the figure caption accurately describe what is shown?
6. **Resolution and clarity**: Is the figure readable at the target print size? Are labels not overlapping?
7. **Style compliance**: Does the figure follow the repo's house style (palette, fonts, spines)?

**Review loop:**

```text
Iteration 1:
  VLM Review → Issues found: [list]
  Fix → Regenerate figure

Iteration 2:
  VLM Review → Issues found: [list]
  Fix → Regenerate figure

Iteration N:
  VLM Review → No critical issues → PASS
```

**Termination conditions:**

- VLM reports no critical issues (PASS)
- Maximum iterations reached (default: 3)
- User manually approves the current version

**Output:**

```text
VLM Figure Review Report
- Figure: [name]
- Iterations: [N]
- Final status: PASS / CONDITIONAL / FAIL
- Remaining issues (if any): [list]
- Recommendations: [list]
```

### Stage 4: Concept diagram generation (v4 new)

> **来源**：PaperOrchestra 的 PaperBanana 概念示意图生成

When the user needs a conceptual diagram (system architecture, workflow, framework overview) rather than a data plot, use the concept diagram generation mode.

**Concept diagram types:**

- System architecture diagram
- Workflow / pipeline diagram
- Framework overview diagram
- Comparison diagram (before/after, with/without)
- Taxonomy / classification diagram

**Generation process:**

1. Parse the conceptual structure from the user's description or paper outline
2. Identify components, relationships, and data flow
3. Generate matplotlib code using rectangles, arrows, and text annotations
4. Apply the house style (palette, fonts, layout)
5. Run VLM review loop (Stage 3) to verify the diagram is clear and accurate

Use `templates/concept_diagram.md` for the concept diagram generation prompt.

## Related files

| File | Open when |
|------|-----------|
| [references/tutorials.md](references/tutorials.md) | End-to-end walkthroughs (bar, trends, heatmap) |
| [references/api.md](references/api.md) | Function signatures, `PALETTE`, validation rules |
| [references/common-patterns.md](references/common-patterns.md) | Layout patterns, legend panel, print-safe bars |
| [references/design-theory.md](references/design-theory.md) | Typography, export policy, palette rationale |
| [references/demos.md](references/demos.md) | Canonical `figure_*` demo links in figures4papers |
| `templates/concept_diagram.md` (v4 new) | Concept diagram generation prompt |

## Style rules (v4 enhanced)

- Generate reproducible Python scripts
- Save scripts to `figures/scripts/`
- Save outputs to `figures/outputs/`
- Export both PDF and PNG
- Use readable axis labels, legends, and captions
- Prefer clean academic style
- **All figures should pass VLM review before final submission** (when VLM is available)
- **Concept diagrams must use the same house style as data plots** (palette, fonts)
- **Figure captions must be verified against the actual figure content**

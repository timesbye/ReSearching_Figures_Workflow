# Project AI Rules

## Project Identity

This is a project using ALL-in-ALL_ReSearching_Workflow_Skill.

Before starting any task, read:

```text
.ai/toolkit/ROUTER.md
```

## Toolkit Path

The toolkit should be linked as:

```text
.ai/toolkit/
```

## Literature Review Rules

For systematic literature review on a research topic, use:

```text
.ai/toolkit/skills/literature-review/
```

Save reviews to `literature/`, e.g. `literature/review_[topic].md`.

## Paper Reading Rules

For deep-reading a single paper and generating structured notes, use:

```text
.ai/toolkit/skills/paper-reading/
```

Save notes to `literature/`, e.g. `literature/[author_year_title].md`.

## Critical Ideation Rules

For brainstorming, idea validation, product differentiation, research topic generation, novelty checks, or Agent workflow design, use:

```text
.ai/toolkit/skills/critical-ideation/
```

When using this skill:

1. Do not only generate ideas.
2. Challenge each idea directly.
3. Search for existing products, papers, GitHub repos, or competitors when needed.
4. Refine ideas after critique.
5. Rank ideas using a decision matrix.
6. Recommend no more than three top ideas by default.

Generated ideation outputs should be saved to `ideas/`, preferably:

- `ideas/idea_report.md`
- `ideas/search_log.md`
- `ideas/decision_matrix.md`
- `ideas/mvp_plan.md`

## Experiment Design Rules

For designing experiments, planning ablation studies, variable control, or benchmark selection, use:

```text
.ai/toolkit/skills/experiment-design/
```

When using this skill:

1. Define clear independent/dependent variables before running.
2. Specify baselines and metrics before seeing results.
3. Plan ablation studies alongside main experiments.
4. Document all hyperparameters and random seeds.
5. Include a reproducibility checklist.

Generated experiment outputs should be saved to `experiments/`, preferably:

- `experiments/experiment_plan.md`
- `experiments/ablation_plan.md`
- `experiments/reproducibility_checklist.md`

## Figure Rules

For scientific figures, use:

```text
.ai/toolkit/skills/scientific-figure-making/
```

Figure output rules:

- Save scripts to `figures/scripts/`.
- Save PDF and PNG to `figures/outputs/`.
- Generate reproducible Python matplotlib scripts.
- Use readable labels, legends, and captions.
- Avoid decorative or marketing-style charts.

## Writing Rules

For building a paper from scratch, section by section, use:

```text
.ai/toolkit/skills/scholarly-writing/
```

For polishing, translating, or refining existing text, use:

```text
.ai/toolkit/prompt-libraries/awesome-ai-research-writing/
```

General writing requirements:

- Preserve technical meaning.
- Do not invent results, citations, or experimental claims.
- Use formal academic style.
- Avoid exaggerated contribution statements.
- Keep terminology consistent with this project.

## Full Workflow

For going from zero to a complete paper:

1. Use `literature-review` to survey the field → save review to `literature/`
2. Use `paper-reading` to read key papers → save notes to `literature/`
3. Use `critical-ideation` to converge on a direction → save to `ideas/`
4. Use `experiment-design` to plan experiments → save to `experiments/`
5. Use `scientific-figure-making` to visualize evidence → save to `figures/`
6. Use `scholarly-writing` to draft the paper → save to `paper/`
7. Use `awesome-ai-research-writing` to polish → update `paper/`
8. Use reviewer-style critique to check claims → save to `paper/notes/`

## Important Rule

Do not modify `.ai/toolkit/` source files unless explicitly asked.

All generated files should be saved inside the current project.

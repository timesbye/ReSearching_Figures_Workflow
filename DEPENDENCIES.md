# Dependencies

This document lists all upstream projects referenced by ALL-in-ALL_ReSearching_Workflow_Skill, along with their version/commit status and usage scope.

## Referenced Projects

| Project | Author | Repository | License | Usage in This Project | Version Status |
|---------|--------|-----------|---------|----------------------|----------------|
| Auto-Scholar | [CAICAIIs](https://github.com/CAICAIIs) | [CAICAIIs/Auto-Scholar](https://github.com/CAICAIIs/Auto-Scholar) | MIT | Design reference for `skills/literature-review/` | Not pinned; concept-level reference |
| DeepPaperNote | [917Dhj](https://github.com/917Dhj) | [917Dhj/DeepPaperNote](https://github.com/917Dhj/DeepPaperNote) | No explicit license | Design reference for `skills/paper-reading/` | Not pinned; concept-level reference |
| autoresearch-skill | [wjgoarxiv](https://github.com/wjgoarxiv) | [wjgoarxiv/autoresearch-skill](https://github.com/wjgoarxiv/autoresearch-skill) | MIT | Design reference for `skills/experiment-design/` | Not pinned; concept-level reference |
| Scholarly | [ShiyangZheng](https://github.com/ShiyangZheng) | [ShiyangZheng/scholarly](https://github.com/ShiyangZheng/scholarly) | No explicit license | Design reference for `skills/scholarly-writing/` | Not pinned; concept-level reference |
| figures4papers | [Chen Liu](https://chenliu-1996.github.io/) (Yale) | [ChenLiu-1996/figures4papers](https://github.com/ChenLiu-1996/figures4papers) | No explicit license | Design reference and style guide for `skills/scientific-figure-making/` | Not pinned; concept-level reference |
| awesome-ai-research-writing | [Leey21](https://github.com/Leey21) | [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) | No explicit license | Referenced as external Prompt library for academic writing | See `prompt-libraries/awesome-ai-research-writing/README.md` for commit pinning |

## Version Policy

- **Concept-level references** (Auto-Scholar, DeepPaperNote, autoresearch-skill, Scholarly, figures4papers): These are design inspirations, not code dependencies. The Skill directories in this project contain original usage guides written based on their concepts, not copies of their code. No version pinning is required.

- **Content-level references** (awesome-ai-research-writing): This is a Prompt library that users clone into the project. Its content directly affects Skill execution quality. Commit pinning is recommended for reproducibility.

## Important Notes

- This project does **not** redistribute content from any upstream repository.
- Each Skill directory contains original documentation written by this project, inspired by the upstream design concepts.
- `skills/critical-ideation/` is an original contribution of this project with no upstream dependency.
- Users should visit upstream repositories directly and comply with their respective licenses and terms of use.

# Concept Diagram Generation Prompt

> **来源**：PaperOrchestra 的 PaperBanana 概念示意图生成模块

Use this template to generate concept diagrams (system architecture, workflow, framework overview) using matplotlib.

## Input Specification

When generating a concept diagram, the following information should be provided or extracted:

```text
Concept Diagram Specification
- Type: [architecture | workflow | framework | comparison | taxonomy]
- Title:
- Components: [list of named components]
- Relationships: [list of connections between components]
- Data flow: [direction of information flow, if applicable]
- Layout preference: [horizontal | vertical | grid | custom]
- Color coding: [by function | by layer | by module | none]
- Target size: [single column | double column | full page]
```

## Generation Guidelines

### Architecture Diagram

- Use rounded rectangles for modules/components
- Use arrows for data flow direction
- Use color coding to distinguish layers or functional groups
- Label all connections with brief descriptions
- Include a legend if color coding is used

### Workflow / Pipeline Diagram

- Use rectangles for processing steps
- Use arrows for flow direction
- Use diamonds for decision points
- Use parallelograms for input/output
- Number the steps if order matters
- Show parallel paths explicitly

### Framework Overview Diagram

- Use nested rectangles for hierarchical structure
- Use color shading to show containment
- Label each level clearly
- Show interfaces between levels

### Comparison Diagram

- Use side-by-side layout
- Use consistent visual encoding for comparable elements
- Highlight differences with distinct colors or patterns
- Include a shared legend

### Taxonomy / Classification Diagram

- Use a tree layout
- Use consistent indentation or spacing
- Label each branch
- Use color to indicate categories

## Code Template

```python
import matplotlib.pyplot as plt
import matplotlib.patches as mpatches
from matplotlib.patches import FancyBboxPatch, FancyArrowPatch

fig, ax = plt.subplots(1, 1, figsize=(10, 6))
ax.set_xlim(0, 10)
ax.set_ylim(0, 6)
ax.axis('off')

# Define components
components = [
    {"label": "Component A", "xy": (1, 4), "color": "#4C72B0"},
    {"label": "Component B", "xy": (4, 4), "color": "#55A868"},
    {"label": "Component C", "xy": (7, 4), "color": "#C44E52"},
]

# Draw components
for comp in components:
    box = FancyBboxPatch(
        (comp["xy"][0] - 0.8, comp["xy"][1] - 0.4),
        1.6, 0.8,
        boxstyle="round,pad=0.1",
        facecolor=comp["color"],
        edgecolor='black',
        alpha=0.8
    )
    ax.add_patch(box)
    ax.text(comp["xy"][0], comp["xy"][1], comp["label"],
            ha='center', va='center', fontsize=10, color='white', fontweight='bold')

# Draw arrows
arrows = [
    {"start": (1.8, 4), "end": (3.2, 4), "label": "data"},
    {"start": (4.8, 4), "end": (6.2, 4), "label": "result"},
]

for arrow in arrows:
    ax.annotate(
        "", xy=arrow["end"], xytext=arrow["start"],
        arrowprops=dict(arrowstyle="->", color='black', lw=1.5)
    )
    mid_x = (arrow["start"][0] + arrow["end"][0]) / 2
    mid_y = (arrow["start"][1] + arrow["end"][1]) / 2 + 0.3
    ax.text(mid_x, mid_y, arrow["label"], ha='center', va='center', fontsize=8, color='gray')

plt.tight_layout()
plt.savefig('figures/outputs/concept_diagram.pdf', dpi=300, bbox_inches='tight')
plt.savefig('figures/outputs/concept_diagram.png', dpi=300, bbox_inches='tight')
```

## VLM Review Integration

After generating the concept diagram, run the VLM review loop from Stage 3 of the SKILL.md:

1. Present the generated figure to the VLM
2. Check: Are all components labeled? Are relationships clear? Is the layout readable?
3. Fix any issues and regenerate
4. Repeat until the VLM approves or max iterations reached

## Common Mistakes to Avoid

- Overcrowding: Too many components in a small space
- Ambiguous connections: Arrows without labels or unclear direction
- Inconsistent styling: Different font sizes, colors, or shapes for equivalent elements
- Missing context: No title or caption explaining the diagram
- Poor resolution: Text too small to read at print size

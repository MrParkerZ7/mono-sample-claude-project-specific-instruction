# CLAUDE.md - Project Instructions

## Project Overview

This is a mono-repo containing sample `CLAUDE.md` files and prompt templates for different use cases with Claude Code. The primary focus is generating professional diagrams (DrawIO) and documentation.

## Repository Structure

```
mono-sample-claude-project-specific-instruction/
├── CLAUDE.md                    # This file
├── README.md                    # Project documentation
├── claude-md-drawio/            # DrawIO diagram generation
│   ├── CLAUDE-DIAGRAMS-STANDARD-FORMAT.md  # Shape/style references
│   ├── PROMPT_TEMPLATE.md       # Ready-to-use prompt template
│   ├── _PROMPT/                 # Detailed prompt templates
│   │   ├── PROMPT-DIAGRAM-FORMAT.md       # Diagram format standards
│   │   └── PROMPT-PROJECT-ANALYSIS.md     # Analysis prompt templates
│   └── sample-*/                # Sample projects with diagrams
└── claude-md-excel/             # Excel generation (planned)
```

## Key Files

| File | Purpose |
|------|---------|
| `claude-md-drawio/CLAUDE-DIAGRAMS-STANDARD-FORMAT.md` | Main DrawIO standards (shapes, styles, colors) |
| `claude-md-drawio/_PROMPT/PROMPT-DIAGRAM-FORMAT.md` | Detailed diagram format guidelines |
| `claude-md-drawio/_PROMPT/PROMPT-PROJECT-ANALYSIS.md` | Analysis and output templates |
| `claude-md-drawio/PROMPT_TEMPLATE.md` | Quick-start prompt template |

## Working with This Repository

### Adding New Sample Projects

1. Create folder: `claude-md-drawio/sample-project-{name}/`
2. Add analysis files in `analysis/` subfolder:
   - `architecture-analysis.md`
   - `project-structure-analysis.md` (for monorepos)
   - Other analysis types as needed
3. Add diagrams in `diagrams/` subfolder:
   - `architecture-overview.drawio` (REQUIRED)
   - Other diagram types as needed
4. Export PNG versions for preview

### Diagram Standards

- All diagrams must follow `CLAUDE-DIAGRAMS-STANDARD-FORMAT.md`
- Use consistent color schemes per technology type
- Include legends for all arrow types used
- Use swimlane containers for grouping

### Color Scheme Reference

| Technology | Fill | Stroke |
|------------|------|--------|
| Kotlin/Java | `#DAE8FC` | `#6C8EBF` |
| Python | `#FFF2CC` | `#D6B656` |
| Infrastructure | `#D5E8D4` | `#82B366` |
| Shared/Common | `#E1D5E7` | `#9673A6` |
| Build/Config | `#F5F5F5` | `#666666` |

## Naming Conventions

| Element | Convention | Example |
|---------|------------|---------|
| Sample folders | `sample-{type}-{name}` | `sample-project-kotlin-spring` |
| Analysis files | `{type}-analysis.md` | `architecture-analysis.md` |
| Diagram files | `{type}.drawio` | `architecture-overview.drawio` |
| Prompt files | `PROMPT-{TYPE}.md` | `PROMPT-PROJECT-ANALYSIS.md` |

## Git Commit Guidelines

- Use clear, descriptive commit messages
- Start with action verb: Add, Update, Fix, Remove
- Reference diagram type or analysis type in commits
- Co-author with Claude when applicable

## Updating Prompt Templates

When updating `_PROMPT/` files:
1. Update Table of Contents if adding sections
2. Maintain consistent heading numbering
3. Include XML examples for new diagram types
4. Add entries to both analysis and diagram generation sections

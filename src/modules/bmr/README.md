# BMAD Research (BMR) Module

**Collaborative Research & Report Writing with Agentic Orchestration**

Transform the BMAD methodology for academic writing, grant proposals, feasibility studies, and concept papers. Features an agentic harness that guides users through research while compiling polished, illustrated reports in the background.

## Overview

BMR adapts BMAD's proven agile-AI methodology for research document creation:

| BMAD (Software) | BMR (Research) |
|-----------------|----------------|
| Epics | Chapters |
| Stories | Sections |
| Sprints | Writing Sessions |
| PRD | Research Brief |
| Architecture | Document Structure |
| Code Review | Quality Review |
| CI/CD | Background Compilation |

## Key Features

### Collaborative Experience
- **Riley** (Research Guide) facilitates the entire journey
- Thoughtful questions that spark deeper thinking
- Progress celebrations and milestone recognition
- Adaptive collaboration (guided, autonomous, or mixed)

### Specialist Team
- **Sage** (Document Architect) - Chapter planning and narrative structure
- **Morgan** (Research Analyst) - Literature review and evidence synthesis
- **Quinn** (Content Writer) - Compelling prose and section drafting
- **Harper** (Layout Designer) - Formatting and visualizations
- **Jordan** (Quality Reviewer) - Coherence and accuracy checking
- **Taylor** (Financial Analyst) - Budgets and quantitative analysis

### Background Compilation
- Document assembles automatically as you work
- Real-time table of contents updates
- Automatic citation formatting
- Continuous backup and versioning
- Multiple output formats (PDF, DOCX, Markdown)

### Skills Library
- **research-discovery** - Systematic literature search
- **academic-analysis** - Critical synthesis of sources
- **financial-analysis** - Budgets and projections
- **citation-manager** - Reference formatting
- **narrative-coherence** - Argument flow validation
- **illustration-design** - Diagrams and visualizations
- **report-formatter** - Professional document styling
- **source-validator** - Source credibility assessment

## Supported Document Types

### Grant Proposal
Full grant application with budget, timeline, and impact narrative.

### Feasibility Study
Market, technical, operational, and financial analysis.

### Academic Paper
Structured scholarly work with methodology and findings.

### Concept Paper
Focused articulation of an idea's potential.

### Research Proposal
Academic research design with methodology and timeline.

## Quick Start

### 1. Start a New Project

```
> Start a new research project

Riley: Welcome! I'm excited to help you create something meaningful.
       What topic are you exploring, and what type of document do you need?
```

### 2. Discovery Phase

Riley guides you through scoping:
- Research questions
- Target audience
- Document type selection
- Timeline and constraints

### 3. Research Phase

Morgan leads literature discovery:
- Strategic search execution
- Source quality validation
- Evidence synthesis
- Gap identification

### 4. Architecture Phase

Sage designs your document:
- Chapter structure
- Narrative arc
- Argument flow
- Section objectives

### 5. Drafting Phase

Quinn helps craft content:
- Section-by-section drafting
- Evidence integration
- Voice consistency
- Smooth transitions

### 6. Review & Polish

Jordan ensures quality:
- Coherence verification
- Citation checking
- Argument validation
- Final polish

## Workflow Phases

```
┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│  Discovery  │ → │  Research   │ → │ Architecture│
│  & Scoping  │   │  & Analysis │   │  & Planning │
└─────────────┘   └─────────────┘   └─────────────┘
                                           │
┌─────────────┐   ┌─────────────┐   ┌──────▼──────┐
│   Final     │ ← │   Review    │ ← │Collaborative│
│ Compilation │   │  & Polish   │   │  Drafting   │
└─────────────┘   └─────────────┘   └─────────────┘
```

## File Structure

```
bmr/
├── module.yaml           # Module configuration
├── README.md             # This file
├── agents/
│   ├── research-guide.agent.yaml      # Riley - Main facilitator
│   ├── document-architect.agent.yaml  # Sage - Structure
│   ├── research-analyst.agent.yaml    # Morgan - Research
│   ├── content-writer.agent.yaml      # Quinn - Writing
│   ├── layout-designer.agent.yaml     # Harper - Design
│   ├── quality-reviewer.agent.yaml    # Jordan - Quality
│   └── financial-analyst.agent.yaml   # Taylor - Finance
├── skills/
│   ├── research-discovery/
│   ├── academic-analysis/
│   ├── financial-analysis/
│   ├── citation-manager/
│   ├── narrative-coherence/
│   ├── illustration-design/
│   ├── report-formatter/
│   └── source-validator/
├── harness/
│   ├── research-harness.md      # Orchestration architecture
│   ├── harness-config.yaml      # Harness configuration
│   └── background-compiler.md   # Compilation system
├── templates/
│   ├── grant-proposal.md
│   ├── feasibility-study.md
│   ├── academic-paper.md
│   ├── concept-paper.md
│   └── research-proposal.md
├── docs/
│   └── narrative-structure.md   # Epic/Story to Chapter/Section mapping
└── workflows/
    └── (coming soon)
```

## Configuration

### Module Settings

```yaml
# In module.yaml
config:
  project_name: "My Research Project"
  document_type: "grant_proposal"
  citation_style: "APA"
  collaboration_style: "guided"
  background_compilation: true
```

### Citation Styles

- APA 7th Edition
- MLA 9th Edition
- Chicago (Author-Date)
- Chicago (Notes-Bibliography)
- Harvard
- IEEE
- Vancouver

### Output Formats

- PDF (print-ready)
- DOCX (editable)
- Markdown (version control)
- HTML (web publication)

## Integration with BMAD Core

BMR follows BMAD principles:

- **Just-In-Time Loading** - Skills and references loaded as needed
- **Sequential Execution** - Phases proceed in order
- **State Tracking** - Progress maintained in frontmatter
- **Checkpoint System** - Regular validation points
- **Celebration Moments** - Milestone acknowledgment

## Extending BMR

### Adding New Document Types

1. Create template in `templates/`
2. Add to `document_types` in `module.yaml`
3. Define structure in template mapping

### Adding New Skills

1. Create folder in `skills/`
2. Add `SKILL.md` with frontmatter
3. Optional: Add scripts, references, assets
4. Register in `module.yaml`

### Customizing Agents

Agent YAML supports:
- Custom prompts
- Additional workflows
- Modified communication styles
- Extended capabilities

## Example Session

```
Riley: What would you like to work on today?

User: I need to write a grant proposal for a climate research project.

Riley: Exciting! Climate research is critically important.
       Let me bring in Sage to help structure your proposal,
       and Morgan to start gathering relevant literature.

       While we plan, the background compiler will start
       setting up your document template.

       First question: Who is the funder, and what's their focus area?

[Session continues with collaborative development...]

Riley: Congratulations! Your grant proposal is complete.
       Harper has added the final formatting touches.

       You can download your polished document in PDF or DOCX.

       Key stats:
       - 15 pages
       - 47 citations
       - 8 figures
       - Budget: $1.2M over 3 years

       Good luck with your submission!
```

## Philosophy

**Your ideas drive the research - agents amplify, not replace.**

BMR is designed for collaboration between human insight and AI capability. You bring the knowledge, creativity, and judgment. The agents provide structure, research support, and tireless compilation work.

The goal is polished, professional documents that represent your best thinking - delivered with less friction and more enjoyment.

---

*BMR is part of the BMAD-METHOD family. For core BMAD documentation, see the main repository README.*

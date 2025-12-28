# Sample Research Project: AI Ethics in Healthcare

This sample project demonstrates the BMAD Research (BMR) module in action. It shows:

1. **Project state management** - How progress is tracked across sessions
2. **Source database** - How research sources are collected and organized
3. **Draft content** - Work-in-progress document sections
4. **Theme synthesis** - How evidence is organized thematically

## Project Status

- **Phase:** Research & Analysis (Phase 2 of 6)
- **Current Agent:** Morgan (Research Analyst)
- **Progress:** 4,200 / 15,000 words (~28%)
- **Sources:** 18 collected, 7 cited

## How to Test

### Option 1: Resume This Project

Load the research-guide agent and use the "Continue Project" command:

```
[Load Riley - Research Guide]
> CP (Continue Project)
```

Riley will:
1. Detect this existing project
2. Load the current state
3. Show progress summary
4. Route you to continue with Morgan on research

### Option 2: Start Fresh

Start a new project to experience the full flow:

```
[Load Riley - Research Guide]
> NP (New Project)
```

Riley will guide you through:
1. Project scoping
2. Document type selection
3. Audience identification
4. Initial setup

### Option 3: Test Specific Agents

Jump directly to any specialist:

- `SA` - Sage (Document Architect) for chapter planning
- `MR` - Morgan (Research Analyst) for literature review
- `QW` - Quinn (Content Writer) for drafting
- `HD` - Harper (Layout Designer) for formatting
- `JR` - Jordan (Quality Reviewer) for review
- `TF` - Taylor (Financial Analyst) for budgets

## Project Files

```
sample-research-project/
├── project-state.yaml     # Current state and progress
├── sources/
│   └── sources.yaml       # Collected research sources
├── drafts/
│   └── introduction-draft.md  # Work-in-progress content
├── snapshots/             # Checkpoint backups
└── README.md              # This file
```

## Key Themes Being Researched

1. **AI Bias in Medical Diagnosis** (6 sources)
   - Algorithmic discrimination in healthcare
   - Impact on minority populations

2. **Informed Consent for AI Systems** (5 sources)
   - Traditional consent model inadequacy
   - Explainability requirements

3. **Regulatory Frameworks** (4 sources)
   - FDA guidance on AI/ML
   - International approaches

4. **Stakeholder Trust** (3 sources)
   - Patient acceptance
   - Clinician adoption

## Next Actions

1. Complete literature synthesis for AI bias theme
2. Identify 5-7 more sources for regulatory frameworks
3. Draft significance section with Morgan
4. Begin methodology planning with Sage

---

*This sample project is part of the BMAD Research module.*

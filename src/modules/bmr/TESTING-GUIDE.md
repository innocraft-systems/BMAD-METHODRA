# BMR Module Testing Guide

This guide walks you through testing the BMAD Research (BMR) module step by step.

## Prerequisites

1. BMAD-METHODRA repository cloned
2. Node.js installed (for validation)
3. An AI assistant (Claude, GPT-4, etc.) that can execute the BMAD framework

## Step 1: Validate the Module

```bash
cd BMAD-METHODRA
npm install
npm run validate:schemas
```

**Expected:** All 31 agent files pass validation, including 7 BMR agents.

## Step 2: Review the Module Structure

```
src/modules/bmr/
├── agents/                    # 7 specialist agents
│   ├── research-guide.agent.yaml      # Riley - Primary orchestrator
│   ├── document-architect.agent.yaml  # Sage - Chapter planning
│   ├── research-analyst.agent.yaml    # Morgan - Literature review
│   ├── content-writer.agent.yaml      # Quinn - Prose drafting
│   ├── layout-designer.agent.yaml     # Harper - Formatting
│   ├── quality-reviewer.agent.yaml    # Jordan - Quality review
│   └── financial-analyst.agent.yaml   # Taylor - Budgets
│
├── workflows/                 # 16 workflows
│   ├── start-research/        # New project initialization
│   ├── continue-research/     # Project continuation
│   ├── chapter-planning/      # Document structure
│   ├── narrative-design/      # Argument flow
│   ├── outline-creation/      # Detailed outlines
│   ├── literature-review/     # Systematic research
│   ├── source-discovery/      # Targeted source finding
│   ├── evidence-synthesis/    # Theme synthesis
│   ├── section-drafting/      # Content creation
│   ├── document-formatting/   # Layout application
│   ├── illustration-creation/ # Visual elements
│   ├── full-review/           # Comprehensive review
│   ├── pre-submission/        # Final checklist
│   ├── budget-building/       # Budget development
│   ├── cost-benefit/          # CBA analysis
│   └── financial-projections/ # Financial modeling
│
├── skills/                    # 8 research skills
│   ├── research-discovery/
│   ├── academic-analysis/
│   ├── financial-analysis/
│   ├── citation-manager/
│   ├── narrative-coherence/
│   ├── illustration-design/
│   ├── report-formatter/
│   └── source-validator/
│
├── harness/                   # Agentic orchestration
│   ├── research-harness.md    # Architecture overview
│   ├── harness-config.yaml    # Full configuration
│   ├── background-compiler.md # Compilation system
│   ├── state-manager.md       # State management
│   ├── orchestrator.md        # Agent coordination
│   └── agent-protocols.md     # Communication standards
│
├── templates/                 # Document templates
│   ├── grant-proposal.md
│   ├── feasibility-study.md
│   ├── academic-paper.md
│   ├── concept-paper.md
│   └── research-proposal.md
│
├── docs/                      # Documentation
│   └── narrative-structure.md
│
├── config.yaml                # Module configuration
└── README.md                  # Module overview
```

## Step 3: Test with Sample Project

A sample project is provided at `samples/sample-research-project/`.

### 3a. Examine Sample State

Review these files to understand state management:

- `project-state.yaml` - Project progress and configuration
- `sources/sources.yaml` - Research source database
- `drafts/introduction-draft.md` - Work-in-progress content

### 3b. Simulate Session Continuation

With an AI assistant loaded with the BMR agents:

```
Load: research-guide.agent.yaml

User: CP (Continue Project)

Expected behavior:
- Riley detects existing project
- Shows progress summary (28% complete, Phase 2)
- Notes current agent was Morgan
- Offers to continue research or change direction
```

## Step 4: Test New Project Flow

### 4a. Start New Project

```
Load: research-guide.agent.yaml

User: NP (New Project)

Expected behavior:
- Riley welcomes user
- Asks about project vision
- Presents document type options (GP, FS, AP, CP, RP)
- Gathers audience information
- Creates project structure
```

### 4b. Test Agent Handoffs

```
User: SA (to bring in Sage)

Expected behavior:
- Riley hands off to Sage
- Sage acknowledges project context
- Sage proposes chapter planning approach
```

### 4c. Test Return Navigation

```
User: RG (to return to Riley)

Expected behavior:
- Clean handoff back to Riley
- Riley summarizes what was accomplished
- Riley presents next options
```

## Step 5: Test Individual Workflows

### Literature Review (Morgan)

```
Load: research-analyst.agent.yaml

User: LR (Literature Review)

Expected behavior:
- Morgan asks about research focus
- Develops search strategy
- Presents methodology
- Offers to execute search
```

### Budget Building (Taylor)

```
Load: financial-analyst.agent.yaml

User: BB (Build Budget)

Expected behavior:
- Taylor asks about budget constraints
- Walks through personnel costs
- Builds non-personnel items
- Generates budget narrative
```

### Quality Review (Jordan)

```
Load: quality-reviewer.agent.yaml

User: FR (Full Review)

Expected behavior:
- Jordan announces review dimensions
- Checks coherence, accuracy, completeness
- Prioritizes issues found
- Suggests fixes
```

## Step 6: Test Document Types

Each document type has a template. Test that workflows adapt:

| Type | Template | Key Features |
|------|----------|--------------|
| Grant Proposal | `grant-proposal.md` | Budget section, significance |
| Feasibility Study | `feasibility-study.md` | Analysis sections, recommendations |
| Academic Paper | `academic-paper.md` | Literature review, methodology |
| Concept Paper | `concept-paper.md` | Brief, persuasive |
| Research Proposal | `research-proposal.md` | Research questions, approach |

## Step 7: Test Harness Features

### State Persistence

1. Start a project
2. Make progress (draft a section)
3. End session
4. Resume - verify state is restored

### Agent Coordination

1. Start with Riley
2. Hand off to Morgan (research)
3. Hand off to Sage (structure)
4. Return to Riley
5. Verify context maintained throughout

### Progress Tracking

Check that progress metrics update:
- Sections complete
- Words written
- Sources cited
- Quality scores

## Troubleshooting

### Agent Not Loading

- Verify YAML syntax is valid
- Run `npm run validate:schemas`
- Check file path references

### Workflow Not Executing

- Confirm workflow.md exists in correct location
- Verify step files exist in steps/ folder
- Check path references use `{project-root}`

### State Not Persisting

- Verify config.yaml has correct output_folder
- Check project-state.yaml is being created
- Ensure write permissions on output directory

## Success Criteria

✅ All 31 agents pass validation
✅ New project flow works end-to-end
✅ Project continuation detects state
✅ Agent handoffs maintain context
✅ All 16 workflows execute correctly
✅ Document templates load properly
✅ State persists across sessions
✅ Progress tracking updates correctly

## Next Steps After Testing

1. **Customize config.yaml** for your preferences
2. **Try a real project** - start a grant proposal or paper
3. **Extend the module** - add custom workflows or skills
4. **Integrate memory** - set up Beon for persistent context

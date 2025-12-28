# Research Harness

The agentic orchestration layer for BMAD Research that guides users through
collaborative research and report writing while compiling documents in the background.

## Harness Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    RESEARCH HARNESS                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              ORCHESTRATION LAYER                          │   │
│  │  ┌────────────────────────────────────────────────────┐  │   │
│  │  │   Riley (Research Guide) - Primary Orchestrator    │  │   │
│  │  │   • Session management                             │  │   │
│  │  │   • Phase transitions                              │  │   │
│  │  │   • Agent coordination                             │  │   │
│  │  │   • User collaboration                             │  │   │
│  │  └────────────────────────────────────────────────────┘  │   │
│  └──────────────────────────────────────────────────────────┘   │
│                              │                                   │
│  ┌───────────────────────────┼───────────────────────────────┐  │
│  │         SPECIALIST AGENTS │                               │  │
│  │  ┌─────────┐ ┌─────────┐ ┌┴────────┐ ┌─────────┐         │  │
│  │  │  Sage   │ │ Morgan  │ │  Quinn  │ │ Harper  │         │  │
│  │  │Architect│ │ Analyst │ │ Writer  │ │ Designer│         │  │
│  │  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘         │  │
│  │       │           │           │           │               │  │
│  │  ┌────┴────┐ ┌────┴────┐ ┌────┴────┐ ┌────┴────┐         │  │
│  │  │ Jordan  │ │ Taylor  │ │         │ │         │         │  │
│  │  │Reviewer │ │Financial│ │   ...   │ │   ...   │         │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘         │  │
│  └───────────────────────────────────────────────────────────┘  │
│                              │                                   │
│  ┌───────────────────────────┼───────────────────────────────┐  │
│  │           SKILLS LAYER    │                               │  │
│  │  ┌─────────────┐ ┌────────┴────┐ ┌─────────────┐         │  │
│  │  │  Research   │ │  Academic   │ │  Financial  │         │  │
│  │  │  Discovery  │ │  Analysis   │ │  Analysis   │         │  │
│  │  └─────────────┘ └─────────────┘ └─────────────┘         │  │
│  │  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐         │  │
│  │  │  Citation   │ │  Narrative  │ │ Illustration│         │  │
│  │  │  Manager    │ │  Coherence  │ │   Design    │         │  │
│  │  └─────────────┘ └─────────────┘ └─────────────┘         │  │
│  │  ┌─────────────┐ ┌─────────────┐                         │  │
│  │  │   Report    │ │   Source    │                         │  │
│  │  │  Formatter  │ │  Validator  │                         │  │
│  │  └─────────────┘ └─────────────┘                         │  │
│  └───────────────────────────────────────────────────────────┘  │
│                              │                                   │
│  ┌───────────────────────────┼───────────────────────────────┐  │
│  │      BACKGROUND COMPILER  │                               │  │
│  │  ┌─────────────────────────────────────────────────────┐ │  │
│  │  │  • Incremental document assembly                    │ │  │
│  │  │  • Real-time TOC updates                           │ │  │
│  │  │  • Citation formatting                              │ │  │
│  │  │  • Progress metrics                                 │ │  │
│  │  │  • Draft versioning                                │ │  │
│  │  └─────────────────────────────────────────────────────┘ │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Harness Lifecycle

### Phase 0: Initialization

```yaml
trigger: "New research project"
activities:
  - Create project workspace
  - Initialize document scaffold
  - Set up citation database
  - Configure compilation settings
  - Start background compiler
```

### Phase 1: Discovery & Scoping

```yaml
trigger: "Start research"
lead_agent: Riley (Research Guide)
collaboration_style: Exploratory
activities:
  - Understand research topic
  - Define document type
  - Identify key questions
  - Set scope boundaries
  - Establish success criteria
outputs:
  - Research brief
  - Scope document
  - Initial questions list
```

### Phase 2: Research & Analysis

```yaml
trigger: "Begin research phase"
lead_agent: Morgan (Research Analyst)
supporting: Riley, Taylor (if financial)
collaboration_style: Deep dive
activities:
  - Execute search strategies
  - Gather and validate sources
  - Synthesize findings
  - Identify themes
  - Map evidence to questions
background:
  - Build citation database
  - Update source tracker
  - Generate literature maps
outputs:
  - Literature review draft
  - Evidence synthesis
  - Source database
```

### Phase 3: Architecture & Planning

```yaml
trigger: "Structure the document"
lead_agent: Sage (Document Architect)
supporting: Riley, Morgan
collaboration_style: Strategic
activities:
  - Design chapter structure
  - Map narrative arc
  - Plan argument flow
  - Assign evidence placement
  - Create detailed outline
background:
  - Scaffold document structure
  - Create section templates
  - Set up cross-references
outputs:
  - Document outline
  - Chapter plan
  - Narrative map
```

### Phase 4: Collaborative Drafting

```yaml
trigger: "Start writing"
lead_agent: Quinn (Content Writer)
supporting: Riley, Morgan, Harper
collaboration_style: Focused
activities:
  - Draft sections collaboratively
  - Integrate evidence
  - Craft transitions
  - Review incrementally
  - Refine voice and tone
background:
  - Compile sections into document
  - Update TOC automatically
  - Format citations
  - Track progress
outputs:
  - Section drafts
  - Integrated document
```

### Phase 5: Review & Polish

```yaml
trigger: "Review document"
lead_agent: Jordan (Quality Reviewer)
supporting: Riley, Harper, Quinn
collaboration_style: Critical
activities:
  - Check coherence
  - Verify citations
  - Assess argument strength
  - Review formatting
  - Final polish
background:
  - Run quality checks
  - Generate review report
  - Track revisions
outputs:
  - Review findings
  - Polished document
```

### Phase 6: Compilation & Delivery

```yaml
trigger: "Finalize document"
lead_agent: Harper (Layout Designer)
supporting: Riley
collaboration_style: Final
activities:
  - Apply final formatting
  - Generate illustrations
  - Create front matter
  - Produce final output
background:
  - Final compilation
  - Format conversion
  - Quality assurance
outputs:
  - Final document
  - Supporting materials
```

## Collaboration Modes

### Guided Mode (Default)

```yaml
description: "Agent leads, user responds"
pattern:
  - Agent presents options/questions
  - User makes choices
  - Agent executes and reports
  - Cycle continues
best_for:
  - New users
  - Complex decisions
  - Learning the process
```

### Autonomous Mode

```yaml
description: "Agent works, user reviews"
pattern:
  - User sets parameters
  - Agent executes phase
  - Agent presents results
  - User approves/revises
best_for:
  - Experienced users
  - Clear requirements
  - Time-sensitive work
```

### Mixed Mode

```yaml
description: "Adapt based on context"
pattern:
  - Guided for decisions
  - Autonomous for execution
  - Collaborative for creation
best_for:
  - Most projects
  - Balanced engagement
  - Efficient progress
```

## Checkpoint System

### Checkpoint Types

```yaml
section_checkpoint:
  trigger: Section draft complete
  activities:
    - Save section state
    - Update progress metrics
    - Offer review opportunity
    - Compile into document
  user_interaction: Optional review

chapter_checkpoint:
  trigger: Chapter complete
  activities:
    - Coherence check
    - Citation verification
    - Progress celebration
    - Plan next steps
  user_interaction: Review encouraged

phase_checkpoint:
  trigger: Phase transition
  activities:
    - Phase summary
    - Quality assessment
    - Next phase preview
    - User confirmation
  user_interaction: Required approval

milestone_checkpoint:
  trigger: Major achievement
  activities:
    - Celebrate progress
    - Generate preview
    - Update timeline
    - Share metrics
  user_interaction: Celebration moment
```

### Progress Tracking

```yaml
metrics:
  - sections_complete: X/Y
  - words_written: XXXX
  - sources_cited: XX
  - figures_created: X
  - quality_score: X/10

display:
  progress_bar: Visual completion
  milestone_badges: Achievements
  time_invested: Session tracking
  estimated_remaining: Smart prediction
```

## Agent Handoff Protocol

### Seamless Transitions

```yaml
handoff_pattern:
  1. Current agent summarizes progress
  2. Riley introduces next agent
  3. Context passed to new agent
  4. New agent confirms understanding
  5. Work continues smoothly

context_package:
  - Current document state
  - Active section/chapter
  - Recent decisions
  - User preferences
  - Outstanding questions
```

### Specialist Invocation

```yaml
triggers:
  research_needed: → Morgan (Research Analyst)
  structure_question: → Sage (Document Architect)
  writing_task: → Quinn (Content Writer)
  visual_needed: → Harper (Layout Designer)
  quality_check: → Jordan (Quality Reviewer)
  financial_analysis: → Taylor (Financial Analyst)

return_pattern:
  - Specialist completes task
  - Results summarized
  - Riley resumes guidance
  - Work integrated
```

## Background Compilation

### Continuous Assembly

```yaml
compilation_triggers:
  - Section content added
  - Citation inserted
  - Figure created
  - Structure modified

compilation_tasks:
  - Merge section into document
  - Update table of contents
  - Renumber figures/tables
  - Refresh cross-references
  - Format citations
  - Update word count
```

### Draft Management

```yaml
versioning:
  - Auto-save every 5 minutes
  - Checkpoint versions on milestones
  - Named versions on user request
  - Full history maintained

recovery:
  - Resume from any checkpoint
  - Restore previous versions
  - Merge divergent drafts
  - Handle conflicts gracefully
```

## Fun & Engagement Features

### Celebration Moments

```yaml
triggers:
  - First section complete
  - Literature review done
  - Outline approved
  - Draft milestone (25%, 50%, 75%)
  - Final completion

celebrations:
  - Progress acknowledgment
  - Achievement badges
  - Encouraging messages
  - Milestone summaries
  - Team kudos
```

### Collaborative Dialogue

```yaml
patterns:
  - Thoughtful questions that spark insight
  - Options presented with clear trade-offs
  - Encouragement during challenges
  - Recognition of good decisions
  - Humor when appropriate
```

### Progress Visibility

```yaml
displays:
  - Real-time document preview
  - Word count tracker
  - Source count display
  - Section completion status
  - Time investment tracking
```

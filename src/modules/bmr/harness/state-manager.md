# State Manager

The State Manager maintains project state across sessions and enables seamless agent handoffs.

## State Structure

### Project State File

Located at: `{project_folder}/project-state.yaml`

```yaml
# Project Identity
project:
  id: "unique-project-id"
  name: "Project Name"
  created: "2024-01-15T10:30:00Z"
  modified: "2024-01-20T14:45:00Z"

# Document Configuration
document:
  type: "grant-proposal"
  template: "grant-proposal.md"
  target_length: 15000  # words
  current_length: 8500

# Phase Tracking
phase:
  current: "drafting"
  previous: "architecture"
  started: "2024-01-18T09:00:00Z"

# Agent State
agents:
  current: "content-writer"
  previous: "document-architect"
  session_count: 12

# Section Progress
sections:
  - id: "introduction"
    status: "complete"
    word_count: 1200
    quality_score: 8
  - id: "literature-review"
    status: "in_progress"
    word_count: 2500
    quality_score: null
  - id: "methodology"
    status: "not_started"
    word_count: 0
    quality_score: null

# Research State
research:
  sources_collected: 45
  sources_cited: 23
  themes_identified:
    - "theme-1"
    - "theme-2"
  gaps_noted:
    - "gap-1"

# Checkpoints
checkpoints:
  - id: "cp-001"
    type: "section_complete"
    section: "introduction"
    timestamp: "2024-01-17T16:00:00Z"
    snapshot: "snapshots/cp-001.md"
  - id: "cp-002"
    type: "phase_transition"
    from_phase: "architecture"
    to_phase: "drafting"
    timestamp: "2024-01-18T09:00:00Z"
    snapshot: "snapshots/cp-002.md"

# User Preferences (learned)
preferences:
  tone: "formal_but_accessible"
  detail_level: "comprehensive"
  feedback_style: "direct"
  working_hours: "morning"
```

## State Operations

### Load State

```markdown
When resuming a project:

1. Read project-state.yaml
2. Parse current phase and agent
3. Load relevant context:
   - Current section/chapter
   - Recent decisions
   - Outstanding questions
   - User preferences
4. Initialize appropriate agent
5. Present state summary to user
```

### Save State

```markdown
After each significant action:

1. Update modified timestamp
2. Update relevant counters (words, sources, etc.)
3. Update section status if changed
4. Log agent transition if occurred
5. Create checkpoint if milestone reached
6. Write project-state.yaml
```

### Agent Handoff

```markdown
When transitioning between agents:

1. Current agent creates handoff package:
   - Summary of work done
   - Current document state
   - Open questions
   - Recommendations for next agent

2. State manager updates:
   - agents.previous = agents.current
   - agents.current = new_agent
   - session_count++

3. New agent receives:
   - Full project state
   - Handoff package
   - User preferences
   - Recent context

4. New agent confirms:
   - Acknowledges context
   - States understanding
   - Proposes next steps
```

### Checkpoint Creation

```markdown
Checkpoint triggers:

1. Section completion
2. Phase transition
3. User request ("save checkpoint")
4. Time-based (every 30 mins active work)

Checkpoint contents:

- Full project state
- Document snapshot
- Citation database snapshot
- Agent conversation summary
```

## State Queries

### Progress Summary

```markdown
Generate from state:

**Project: [name]**
Phase: [current_phase] ([phase_number]/6)
Progress: [sections_complete]/[total_sections] sections

| Section | Status | Words | Quality |
|---------|--------|-------|---------|
| [name]  | [status] | [count] | [score] |

Sources: [cited]/[collected]
Sessions: [count]
Last worked: [relative_time]
```

### Phase Status

```markdown
For current phase:

- Phase: [name]
- Lead Agent: [agent]
- Started: [date]
- Key Outputs:
  - [output 1] - [status]
  - [output 2] - [status]
- Next Phase: [name]
- Transition Criteria:
  - [criterion 1] - [met/not met]
  - [criterion 2] - [met/not met]
```

### Context Package

```markdown
For agent initialization:

- Project summary (1 paragraph)
- Current phase and status
- Active section/chapter
- Recent decisions (last 5)
- Outstanding questions (if any)
- User preferences
- Next recommended action
```

## Recovery Procedures

### Resume from Checkpoint

```markdown
1. List available checkpoints
2. User selects checkpoint
3. Restore state from checkpoint
4. Restore document from snapshot
5. Restore citation database
6. Initialize at checkpoint state
7. Confirm restoration with user
```

### Handle Conflicts

```markdown
If state inconsistency detected:

1. Log the inconsistency
2. Attempt automatic resolution:
   - Use most recent timestamps
   - Prefer higher word counts
   - Merge citation databases
3. If unresolvable, present to user:
   - Explain conflict
   - Show options
   - Apply user choice
4. Create checkpoint after resolution
```

## Integration Points

### Background Compiler

```markdown
State manager notifies compiler:

- When section content changes
- When structure changes
- When citations added
- When phase transitions

Compiler updates state:

- Current word counts
- TOC structure
- Figure/table counts
```

### Harness Orchestrator

```markdown
State manager provides:

- Current phase for routing
- Agent status for handoffs
- Progress for celebrations
- Checkpoints for recovery

Orchestrator updates:

- Phase transitions
- Agent changes
- Milestone completions
```

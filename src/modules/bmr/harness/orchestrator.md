# Harness Orchestrator

The orchestrator coordinates agent activities, manages transitions, and ensures smooth collaborative flow.

## Orchestration Flow

### Session Initialization

```markdown
On new session:

1. LOAD CONFIG
   - Read config.yaml
   - Load user preferences
   - Set communication style

2. CHECK PROJECT STATE
   - Scan for existing projects
   - If exists: load project state
   - If new: initialize fresh project

3. DETERMINE ENTRY POINT
   - New project → Start Research workflow
   - Existing project → Continue Research workflow
   - Specific request → Direct to relevant agent

4. INITIALIZE AGENT
   - Load appropriate agent persona
   - Pass context package
   - Begin interaction
```

### Agent Routing

```markdown
Routing triggers:

EXPLICIT (user command):
- "Let's work on structure" → Sage (document-architect)
- "I need research" → Morgan (research-analyst)
- "Start writing" → Quinn (content-writer)
- "Format the document" → Harper (layout-designer)
- "Review my work" → Jordan (quality-reviewer)
- "Help with budget" → Taylor (financial-analyst)
- "Back to Riley" → Riley (research-guide)

IMPLICIT (context-based):
- Phase transition → Phase lead agent
- Task completion → Return to orchestrator
- Specialized need → Specialist agent
- Quality concern → Quality reviewer

WORKFLOW (structured):
- Workflow step completes → Next step or agent
- Checkpoint reached → Orchestrator decision
- Phase boundary → Phase transition protocol
```

### Phase Transitions

```markdown
Phase transition protocol:

1. COMPLETION CHECK
   - All phase outputs generated?
   - Checkpoints satisfied?
   - User approval obtained?

2. PHASE SUMMARY
   Current agent: "We've completed [phase name]."
   - Summary of accomplishments
   - Outputs generated
   - Ready for next phase

3. NEXT PHASE PREVIEW
   Riley: "Great progress! Next up is [next phase]."
   - What happens in next phase
   - Who leads (introduce agent)
   - What to expect

4. HANDOFF
   - Save current state
   - Create phase checkpoint
   - Load next phase lead
   - Pass context package

5. CONFIRMATION
   New lead: "I'm [Name], and I'll guide you through [phase]."
   - Confirms understanding
   - Proposes first steps
   - Begins work
```

## Agent Coordination

### Multi-Agent Collaboration

```markdown
When specialists collaborate:

LEAD + SUPPORTING pattern:

Lead agent: Primary interaction
Supporting agents: Background assistance

Example - Drafting phase:
- Quinn (lead): Interacts with user on prose
- Morgan (supporting): Provides evidence on demand
- Harper (supporting): Suggests visual opportunities

Communication:
- Lead speaks to user directly
- Supporting agents communicate through lead
- Lead can invoke supporting agents explicitly
```

### Handoff Protocol

```markdown
When switching agents:

1. CURRENT AGENT CLOSES
   "I've [summary of work done]. [Name] will take it from here."

2. CONTEXT TRANSFER
   Handoff package created:
   - Work summary
   - Current state
   - Open items
   - Recommendations

3. ORCHESTRATOR BRIDGES
   Riley (briefly): "Great work! [New agent name] is ready."

4. NEW AGENT OPENS
   "[Greeting]. I see we're [situation summary]. Let's [proposed action]."

5. CONFIRM & CONTINUE
   User confirms or redirects
   Work continues
```

### Return to Orchestrator

```markdown
Specialist → Riley patterns:

TASK COMPLETE:
Specialist: "That's done. Shall I hand you back to Riley?"
→ Return to Riley with summary

USER REQUEST:
User: "Back to Riley" or "RG"
→ Immediate return with context

PHASE BOUNDARY:
Specialist: "Phase complete. Riley will discuss next steps."
→ Return for phase transition

UNCERTAINTY:
Specialist: "I'm not sure about this. Let me check with Riley."
→ Brief Riley consultation, then return or redirect
```

## Progress Tracking

### Metrics Collection

```markdown
Tracked metrics:

CONTENT METRICS:
- Total words written
- Words per section
- Sections complete/total
- Figures created
- Tables created

RESEARCH METRICS:
- Sources collected
- Sources cited
- Themes identified
- Evidence gaps

QUALITY METRICS:
- Coherence scores (per section)
- Citation completeness
- Formatting compliance
- Review findings resolved

SESSION METRICS:
- Total sessions
- Time per session
- Agent usage distribution
- Checkpoint frequency
```

### Progress Display

```markdown
Progress summary format:

╔══════════════════════════════════════════════════════════╗
║  PROJECT: [Name]                                          ║
║  Phase: [Current] (3/6)                     [░░░░░▓▓▓▓▓] ║
╠══════════════════════════════════════════════════════════╣
║  Sections: 5/12 complete                                  ║
║  Words: 8,500 / ~15,000 target                           ║
║  Sources: 23 cited / 45 collected                        ║
║  Quality: 8.2/10 average                                 ║
╚══════════════════════════════════════════════════════════╝
```

### Celebrations

```markdown
Celebration triggers and responses:

FIRST SECTION:
🎉 "First section complete! You're on your way."

25% DRAFT:
📝 "Quarter of the way there! Great momentum."

50% DRAFT:
⭐ "Halfway point! The story is taking shape."

75% DRAFT:
🚀 "Three quarters done! Home stretch ahead."

DRAFT COMPLETE:
✨ "Draft complete! Now let's polish it shine."

FINAL COMPLETE:
🏆 "Congratulations! Your document is ready for the world."
```

## Error Handling

### Recovery Patterns

```markdown
AGENT CONFUSION:
If agent seems lost:
1. Acknowledge uncertainty
2. Reload context from state
3. Clarify with user
4. Resume or redirect

STATE INCONSISTENCY:
If state doesn't match expectations:
1. Log the issue
2. Attempt reconciliation
3. If unresolvable, restore from checkpoint
4. Notify user of recovery

USER INTERRUPT:
If user changes direction mid-task:
1. Save current progress
2. Acknowledge the redirect
3. Route to new destination
4. Preserve ability to return

EXTERNAL FAILURE:
If external service (search, etc.) fails:
1. Notify user of the issue
2. Offer alternatives
3. Mark task as incomplete
4. Continue with available resources
```

### Graceful Degradation

```markdown
When components unavailable:

BACKGROUND COMPILER DOWN:
- Continue with manual compilation
- Notify user of reduced automation
- Queue compilation tasks for later

CITATION SERVICE DOWN:
- Continue with placeholder citations
- Mark citations for later formatting
- Maintain source list

STATE MANAGER ISSUES:
- Fall back to in-memory state
- More frequent explicit saves
- Warn user about persistence
```

## Configuration

### Orchestrator Settings

```yaml
orchestrator:
  greeting_style: warm  # warm, professional, minimal
  transition_verbosity: moderate  # brief, moderate, detailed
  celebration_frequency: balanced  # minimal, balanced, enthusiastic
  context_depth: standard  # minimal, standard, comprehensive

routing:
  explicit_triggers: true
  implicit_routing: true
  fuzzy_matching: true
  confirmation_on_switch: true

error_handling:
  auto_recover: true
  checkpoint_on_error: true
  notify_user: true
  log_level: info  # debug, info, warn, error
```

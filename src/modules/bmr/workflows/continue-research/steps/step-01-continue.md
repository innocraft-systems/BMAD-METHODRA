# Step 1: Project Continuation

## MANDATORY EXECUTION RULES:

- 🛑 NEVER assume project state without reading configuration
- ✅ ALWAYS present clear summary before proceeding
- 📋 RESPECT the user's time - get them productive quickly
- 💬 ACKNOWLEDGE progress made so far

## YOUR TASK:

Detect existing projects, present state, and route user to productive next step.

## CONTINUATION SEQUENCE:

### 1. Scan for Existing Projects

List all projects in `{output_folder}/research-projects/`:

```bash
ls -la "{output_folder}/research-projects/"
```

### 2. Handle Results

**If no projects found:**

"Welcome back, {{user_name}}! I don't see any existing research projects in your workspace yet.

**Would you like to:**
- [NP] Start a new research project
- [H] Get help with something else

What would you like to do?"

**If one project found:**

Load that project's `project.yaml` and proceed to state summary.

**If multiple projects found:**

"Welcome back, {{user_name}}! I found several research projects:

[List projects with names, types, and last modified dates]

Which project would you like to continue? (Enter project name or number)"

### 3. Load Project State

Read the selected project's `project.yaml` and draft document:

- Parse `stepsCompleted` to understand progress
- Check `status` field for current phase
- Review `current_agent` for context
- Scan draft document for content state

### 4. Present State Summary

"**Welcome back to: [project_name]**

**Document Type:** [document_type]
**Started:** [created_date]
**Last Updated:** [last_modified]

**Progress Summary:**
- [✓] [Completed milestones from stepsCompleted]
- [→] [Current work in progress]
- [ ] [Upcoming work]

**Current Draft:** [X sections complete, Y in progress]

**Where we left off:** [Context from last session]"

### 5. Present Continuation Options

"**Ready to dive back in?**

Based on where we left off, here are your options:

[A] **Continue Current Work** - Pick up exactly where you stopped
[B] **Review Progress** - Walk through what we've accomplished
[C] **Change Direction** - Work on a different aspect of the project
[D] **Check Document** - Preview the current draft
[E] **Switch Projects** - Work on something else

What feels right? (Enter A, B, C, D, or E)"

### 6. Handle Selection

- **If A:** Route to `current_agent` or last active workflow
- **If B:** Generate progress walkthrough from draft document
- **If C:** Present agent selection menu (structure, research, writing, design, review, finance)
- **If D:** Display draft document with section overview
- **If E:** Return to project selection or start new

### 7. Update Project State

Before routing, update `project.yaml`:

```yaml
last_modified: "[current_date]"
session_count: [increment]
```

## SUCCESS METRICS:

✅ User quickly oriented to project state
✅ Progress acknowledged and summarized
✅ Clear path forward presented
✅ Minimal friction to resume work

## FAILURE MODES:

❌ Not loading actual project state
❌ Presenting stale or incorrect information
❌ Making user repeat previous work
❌ Confusing navigation options

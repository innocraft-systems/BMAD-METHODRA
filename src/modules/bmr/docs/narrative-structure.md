# Narrative Structure System

Mapping BMAD's Epics and Stories to Research Document Structure

## Core Concept

In BMAD software development:
- **Epics** = Large feature sets or major capabilities
- **Stories** = Atomic units of work with clear acceptance criteria

In BMAD Research:
- **Chapters** = Major narrative arcs (like Epics)
- **Sections** = Atomic content units with clear objectives (like Stories)

## The Epic → Chapter Mapping

### Epics in Software Development

```yaml
epic:
  id: EPIC-001
  title: "User Authentication System"
  description: "Enable users to securely access the platform"
  stories:
    - STORY-001: Login functionality
    - STORY-002: Registration flow
    - STORY-003: Password recovery
  acceptance_criteria:
    - Users can create accounts
    - Users can log in securely
    - Users can recover passwords
```

### Chapters in Research Documents

```yaml
chapter:
  id: CH-001
  title: "Literature Review"
  objective: "Situate the research within existing scholarship"
  sections:
    - SEC-001: Theoretical Framework
    - SEC-002: Previous Empirical Work
    - SEC-003: Research Gap Identification
  coherence_criteria:
    - Covers all relevant theoretical foundations
    - Synthesizes (not just summarizes) literature
    - Clearly establishes the gap this research addresses
    - Transitions smoothly to methodology
```

## The Story → Section Mapping

### Stories in Software Development

```yaml
story:
  id: STORY-001
  title: "Login Functionality"
  format: |
    As a registered user,
    I want to log in with my credentials,
    So that I can access my personalized dashboard.
  acceptance_criteria:
    - Given valid credentials, user is authenticated
    - Given invalid credentials, user sees error message
    - Session persists across page refreshes
```

### Sections in Research Documents

```yaml
section:
  id: SEC-001
  title: "Theoretical Framework"
  format: |
    This section establishes the theoretical foundation by:
    - Presenting the core theory/theories
    - Explaining key concepts and relationships
    - Connecting theory to the research questions
  coherence_criteria:
    - Given the research questions, the theory explains relevant phenomena
    - Given the theory, predictions can be derived
    - The framework guides methodology choices
  evidence_requirements:
    - At least 3-5 foundational sources
    - Connection to empirical applications
  word_count_target: 800-1200
```

## Coherence Testing (Like Acceptance Testing)

### Testing an Epic (Chapter Coherence)

```yaml
chapter_coherence_test:
  chapter: "Literature Review"

  structural_tests:
    - test: "Opens with clear context setting"
      status: [pass/fail]
    - test: "Subsections follow logical progression"
      status: [pass/fail]
    - test: "Closes with clear transition to next chapter"
      status: [pass/fail]

  content_tests:
    - test: "All major theoretical perspectives covered"
      status: [pass/fail]
    - test: "Synthesis present, not just summary"
      status: [pass/fail]
    - test: "Gap clearly articulated"
      status: [pass/fail]

  coherence_tests:
    - test: "Connects to introduction claims"
      status: [pass/fail]
    - test: "Sets up methodology choices"
      status: [pass/fail]
    - test: "Consistent terminology throughout"
      status: [pass/fail]

  overall_assessment: [pass/fail]
```

### Testing a Story (Section Coherence)

```yaml
section_coherence_test:
  section: "Theoretical Framework"

  structure_tests:
    - test: "Has clear topic sentence"
      status: [pass/fail]
    - test: "Paragraphs flow logically"
      status: [pass/fail]
    - test: "Has clear closing/transition"
      status: [pass/fail]

  evidence_tests:
    - test: "Claims are supported by citations"
      status: [pass/fail]
    - test: "Sources are appropriately recent"
      status: [pass/fail]
    - test: "Evidence quality is sufficient"
      status: [pass/fail]

  coherence_tests:
    - test: "Connects to chapter objective"
      status: [pass/fail]
    - test: "Terms used consistently"
      status: [pass/fail]
    - test: "Transitions to next section"
      status: [pass/fail]

  overall_assessment: [pass/fail]
```

## Document Backlog (Like Sprint Backlog)

### Research Document Backlog

```yaml
document_backlog:
  project: "{{project_name}}"
  document_type: "{{document_type}}"

  chapters:
    - id: CH-001
      title: "Introduction"
      status: complete
      sections:
        - id: SEC-001
          title: "Background and Context"
          status: complete
          assigned_to: Quinn
        - id: SEC-002
          title: "Problem Statement"
          status: complete
          assigned_to: Quinn

    - id: CH-002
      title: "Literature Review"
      status: in_progress
      sections:
        - id: SEC-003
          title: "Theoretical Framework"
          status: in_progress
          assigned_to: Quinn
          blockers: "Need 2 more foundational sources"
        - id: SEC-004
          title: "Previous Research"
          status: ready
          assigned_to: null
        - id: SEC-005
          title: "Research Gap"
          status: backlog
          assigned_to: null
          depends_on: [SEC-003, SEC-004]

    - id: CH-003
      title: "Methodology"
      status: backlog
      sections:
        - id: SEC-006
          title: "Research Design"
          status: backlog
          depends_on: [CH-002]
```

## Writing Sessions (Like Sprints)

### Session Planning

```yaml
writing_session:
  session_number: 3
  date: "{{date}}"
  duration: "2 hours"

  goal: "Complete Theoretical Framework section"

  sections_in_scope:
    - id: SEC-003
      title: "Theoretical Framework"
      acceptance_criteria:
        - Present main theory clearly
        - Define key concepts
        - Connect to research questions
        - Include 5+ foundational citations

  carry_over:
    - "Finalize source integration from SEC-002"

  session_outcomes:
    sections_completed: [SEC-003]
    sections_partial: []
    blockers_encountered: []
    next_session_focus: [SEC-004]
```

## Narrative Arc Mapping

### Document-Level Arc

```yaml
narrative_arc:
  document: "{{project_name}}"

  setup:
    chapters: [Introduction]
    purpose: "Establish context, problem, and stakes"
    reader_state: "Understands why this matters"

  rising_action:
    chapters: [Literature Review, Methodology]
    purpose: "Build knowledge foundation and approach"
    reader_state: "Understands what's known and how we'll learn more"

  climax:
    chapters: [Results, Discussion]
    purpose: "Reveal and interpret findings"
    reader_state: "Sees the new knowledge and its meaning"

  resolution:
    chapters: [Conclusion]
    purpose: "Synthesize and look forward"
    reader_state: "Understands contribution and implications"
```

### Chapter-Level Arc

```yaml
chapter_arc:
  chapter: "Literature Review"

  opening:
    section: "Introduction to Literature"
    purpose: "Orient reader to scholarly conversation"

  development:
    sections: [Theoretical Framework, Previous Research]
    purpose: "Build comprehensive understanding"

  turning_point:
    section: "Research Gap"
    purpose: "Reveal what's missing"

  transition:
    section: "Connection to This Study"
    purpose: "Set up how we address the gap"
```

## Coherence Metrics

### Quantitative Measures

```yaml
coherence_metrics:
  section_level:
    - transition_words_density: "2-5% of content"
    - citation_density: "minimum 2 per 500 words"
    - paragraph_length_variance: "within 50% of mean"

  chapter_level:
    - section_length_balance: "within 30% of target"
    - cross_reference_count: "minimum 1 per section"
    - terminology_consistency: "100% consistent"

  document_level:
    - chapter_length_balance: "within 25% of mean"
    - introduction_conclusion_alignment: "key terms match"
    - citation_recency: "50%+ within 5 years"
```

### Qualitative Checks

```yaml
qualitative_coherence:
  thesis_threading:
    check: "Main argument visible in each chapter"
    how: "Each chapter opening references thesis"

  evidence_integration:
    check: "Sources woven into argument"
    how: "No orphan citations, all connected to claims"

  voice_consistency:
    check: "Uniform tone and style"
    how: "No jarring shifts between sections"

  reader_journey:
    check: "Reader can follow without confusion"
    how: "No assumed knowledge without introduction"
```

## Implementation in Harness

### Session Flow with Coherence Checking

```
1. Session Start
   → Load document backlog
   → Identify session scope (sections to work on)
   → Review dependencies

2. Section Drafting
   → Write section content
   → Integrate evidence
   → Check section coherence criteria

3. Section Complete
   → Run section coherence test
   → If pass: Mark complete, trigger background compile
   → If fail: Identify issues, iterate

4. Chapter Complete
   → Run chapter coherence test
   → Check narrative arc alignment
   → Celebrate milestone

5. Document Complete
   → Run full document coherence review
   → Check all cross-references
   → Validate bibliography completeness
   → Final polish pass
```

## Templates for Story-Style Section Planning

### Section Definition Template

```markdown
## Section: {{section_title}}

**Chapter:** {{parent_chapter}}
**Section ID:** {{section_id}}

### Objective
As a reader of this {{document_type}},
I need to understand {{what_reader_learns}},
So that I can {{reader_outcome}}.

### Coherence Criteria

**Given** the previous section established {{prior_content}}
**When** I read this section
**Then** I should understand {{section_learning}}
**And** be prepared for {{next_section_topic}}

### Content Requirements
- Key points to cover:
  {{#each key_points}}
  - {{this}}
  {{/each}}
- Evidence needed:
  {{#each evidence_needs}}
  - {{this}}
  {{/each}}
- Target length: {{word_count}} words

### Quality Criteria
- [ ] Opens with clear topic sentence
- [ ] All claims supported with evidence
- [ ] Terminology consistent with document
- [ ] Transitions to next section
- [ ] Serves chapter objective
```

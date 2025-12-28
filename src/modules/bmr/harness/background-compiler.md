# Background Report Compiler

Continuous document assembly that runs while users focus on content creation.

## Overview

The Background Compiler is a persistent process that:
1. Monitors content additions and changes
2. Incrementally assembles the document
3. Maintains formatting and structure
4. Updates navigation elements (TOC, cross-references)
5. Manages citations and bibliography
6. Creates periodic backups

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    BACKGROUND COMPILER                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    EVENT MONITOR                          │   │
│  │  Watches for:                                             │   │
│  │  • Content additions     • Structure changes              │   │
│  │  • Citation insertions   • Figure additions               │   │
│  │  • Section completions   • User save requests             │   │
│  └──────────────────────────────────────────────────────────┘   │
│                              │                                   │
│                              ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    TASK QUEUE                             │   │
│  │  Priority-ordered tasks waiting for execution             │   │
│  │  • Immediate: Content merge, citation update              │   │
│  │  • Deferred: TOC rebuild, cross-ref update                │   │
│  │  • Periodic: Backup, metrics update                       │   │
│  └──────────────────────────────────────────────────────────┘   │
│                              │                                   │
│                              ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    TASK PROCESSORS                        │   │
│  │  ┌────────────┐ ┌────────────┐ ┌────────────┐           │   │
│  │  │  Content   │ │  Citation  │ │  Structure │           │   │
│  │  │  Merger    │ │  Processor │ │  Manager   │           │   │
│  │  └────────────┘ └────────────┘ └────────────┘           │   │
│  │  ┌────────────┐ ┌────────────┐ ┌────────────┐           │   │
│  │  │   Figure   │ │    TOC     │ │   Backup   │           │   │
│  │  │  Handler   │ │  Generator │ │   Manager  │           │   │
│  │  └────────────┘ └────────────┘ └────────────┘           │   │
│  └──────────────────────────────────────────────────────────┘   │
│                              │                                   │
│                              ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    DOCUMENT STATE                         │   │
│  │  • Current compiled document                              │   │
│  │  • Section states and positions                           │   │
│  │  • Citation database                                      │   │
│  │  • Figure registry                                        │   │
│  │  • Version history                                        │   │
│  └──────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Event Types

### Immediate Processing

```yaml
immediate_events:
  content_added:
    trigger: "New section content provided"
    action: merge_content
    priority: 1
    timeout: 5s

  citation_inserted:
    trigger: "New citation added to content"
    action: update_bibliography
    priority: 1
    timeout: 2s

  figure_created:
    trigger: "New figure generated"
    action: insert_figure
    priority: 2
    timeout: 5s

  section_complete:
    trigger: "Section marked complete"
    action: compile_section
    priority: 1
    timeout: 10s
```

### Deferred Processing

```yaml
deferred_events:
  structure_changed:
    trigger: "Chapter/section structure modified"
    action: rebuild_structure
    priority: 3
    batch_window: 30s

  toc_update_needed:
    trigger: "Content changes affect TOC"
    action: regenerate_toc
    priority: 3
    batch_window: 60s

  cross_refs_stale:
    trigger: "Section numbers or positions changed"
    action: update_cross_references
    priority: 3
    batch_window: 30s
```

### Periodic Processing

```yaml
periodic_events:
  auto_backup:
    frequency: 300s  # 5 minutes
    action: create_backup
    priority: 4

  metrics_update:
    frequency: 60s  # 1 minute
    action: update_progress_metrics
    priority: 5

  consistency_check:
    frequency: 600s  # 10 minutes
    action: run_consistency_check
    priority: 4
```

## Task Processors

### Content Merger

```yaml
content_merger:
  purpose: "Integrate new content into document"

  inputs:
    - section_id: "Target section identifier"
    - content: "New content to merge"
    - position: "Where in section (append/replace/insert)"
    - metadata: "Content metadata (author, timestamp)"

  process:
    1. Validate section exists
    2. Parse content format
    3. Apply section template if needed
    4. Merge content at position
    5. Update section metadata
    6. Trigger dependent tasks

  outputs:
    - Updated document state
    - Section timestamp updated
    - Event log entry

  error_handling:
    - Invalid section: Queue for structure rebuild
    - Format error: Log and notify user
    - Conflict: Create merge checkpoint
```

### Citation Processor

```yaml
citation_processor:
  purpose: "Manage citations and bibliography"

  inputs:
    - citation_key: "Unique citation identifier"
    - citation_data: "Full citation metadata"
    - in_text_format: "How citation appears in text"
    - location: "Where in document"

  process:
    1. Validate citation data completeness
    2. Add/update citation database
    3. Format for target style (APA, MLA, etc.)
    4. Insert in-text citation
    5. Update bibliography section
    6. Check for duplicates

  outputs:
    - Updated citation database
    - Formatted in-text citation
    - Updated bibliography

  citation_styles:
    - APA 7th
    - MLA 9th
    - Chicago (Author-Date)
    - Chicago (Notes-Bibliography)
    - Harvard
    - IEEE
    - Vancouver
```

### Structure Manager

```yaml
structure_manager:
  purpose: "Maintain document structure integrity"

  inputs:
    - structure_change: "Type of change"
    - affected_elements: "Chapters/sections affected"

  process:
    1. Parse structure change
    2. Validate new structure
    3. Update section ordering
    4. Renumber as needed
    5. Update all references
    6. Trigger TOC rebuild

  structure_operations:
    - add_chapter
    - remove_chapter
    - reorder_chapters
    - add_section
    - remove_section
    - move_section
    - merge_sections
    - split_section
```

### Figure Handler

```yaml
figure_handler:
  purpose: "Manage figures and visualizations"

  inputs:
    - figure_content: "Figure data or path"
    - figure_type: "chart|diagram|image|table"
    - caption: "Figure caption"
    - placement: "Section and position"

  process:
    1. Validate figure content
    2. Generate figure number
    3. Create figure entry
    4. Insert at placement
    5. Update list of figures
    6. Create cross-reference anchor

  figure_numbering:
    style: "chapter.figure"  # e.g., Figure 3.2
    reset_per_chapter: true
```

### TOC Generator

```yaml
toc_generator:
  purpose: "Generate and maintain table of contents"

  inputs:
    - document_structure: "Current structure"
    - heading_levels: "Levels to include"

  process:
    1. Traverse document structure
    2. Extract headings by level
    3. Generate page references
    4. Format TOC entries
    5. Build TOC section
    6. Insert at designated location

  toc_options:
    max_depth: 3
    include_page_numbers: true
    dot_leaders: true
    hyperlinks: true
```

### Backup Manager

```yaml
backup_manager:
  purpose: "Maintain version history and backups"

  backup_types:
    auto_save:
      frequency: 300s
      retention: 24h
      format: incremental

    checkpoint:
      trigger: milestone_complete
      retention: project_duration
      format: full

    named_version:
      trigger: user_request
      retention: permanent
      format: full

  process:
    1. Capture current state
    2. Generate version identifier
    3. Store backup with metadata
    4. Update version history
    5. Prune old auto-saves
    6. Verify backup integrity

  recovery:
    - List available versions
    - Preview version differences
    - Restore specific version
    - Merge from version
```

## Document State Management

### State Structure

```yaml
document_state:
  metadata:
    project_id: "{{project_id}}"
    document_type: "{{document_type}}"
    created: "{{timestamp}}"
    last_modified: "{{timestamp}}"
    version: "{{version_number}}"

  structure:
    chapters:
      - id: "ch-001"
        title: "Introduction"
        status: complete
        word_count: 1250
        sections:
          - id: "sec-001"
            title: "Background"
            status: complete
            content_hash: "{{hash}}"
          - id: "sec-002"
            title: "Problem Statement"
            status: in_progress
            content_hash: "{{hash}}"

  content:
    sections:
      "sec-001":
        raw_content: "{{content}}"
        compiled_content: "{{formatted_content}}"
        metadata:
          author: "Quinn"
          last_edited: "{{timestamp}}"
          edit_count: 5

  citations:
    database:
      "smith2020":
        type: "journal_article"
        formatted:
          apa: "Smith, J. (2020). Title..."
          mla: "Smith, John. \"Title...\"..."
        locations: ["sec-001", "sec-003"]
    bibliography:
      formatted: "{{bibliography_content}}"
      style: "APA"

  figures:
    registry:
      - id: "fig-001"
        number: "1.1"
        caption: "Research Framework"
        location: "sec-002"
        type: "diagram"

  metrics:
    word_count: 15420
    citation_count: 47
    figure_count: 8
    table_count: 5
    completion_percentage: 65
```

## Compilation Output

### Output Formats

```yaml
output_formats:
  markdown:
    use_case: "Working format, version control"
    features:
      - Full content
      - Embedded metadata
      - Cross-references as links

  docx:
    use_case: "Editing, collaboration, submission"
    features:
      - Styled headings
      - Formatted citations
      - Track changes ready

  pdf:
    use_case: "Final submission, sharing"
    features:
      - Print-ready formatting
      - Embedded fonts
      - Hyperlinked TOC and references

  html:
    use_case: "Web publication, preview"
    features:
      - Responsive layout
      - Interactive TOC
      - Linked citations
```

### Compilation Process

```yaml
compilation_process:
  1_gather:
    - Collect all section content
    - Resolve all cross-references
    - Gather all figures

  2_assemble:
    - Order by structure
    - Insert front matter
    - Insert body content
    - Insert back matter

  3_format:
    - Apply document template
    - Format headings
    - Style paragraphs
    - Format citations

  4_finalize:
    - Generate TOC
    - Number figures/tables
    - Create bibliography
    - Add page numbers

  5_export:
    - Convert to target format
    - Validate output
    - Store compiled version
```

## Integration with Harness

### Event Flow

```
User Action (via Agent)
        │
        ▼
Harness captures event
        │
        ▼
Event sent to Compiler
        │
        ▼
Compiler queues task
        │
        ▼
Task processor executes
        │
        ▼
Document state updated
        │
        ▼
User sees updated document
```

### Status Reporting

```yaml
compiler_status:
  current_task: "Merging section content"
  queue_depth: 3
  last_compile: "2 minutes ago"
  document_health: "good"

  recent_activity:
    - "Section 3.1 merged"
    - "Citation database updated (+2)"
    - "TOC regenerated"

  pending:
    - "Cross-reference update (queued)"
    - "Backup scheduled (4 min)"
```

## Error Handling

### Error Types and Recovery

```yaml
error_handling:
  content_conflict:
    detection: "Concurrent edits to same section"
    recovery: "Create merge checkpoint, notify user"

  citation_missing:
    detection: "In-text citation without database entry"
    recovery: "Flag for user attention, placeholder in bibliography"

  structure_invalid:
    detection: "Orphaned sections or circular references"
    recovery: "Rollback to last valid state, notify user"

  compilation_failure:
    detection: "Output generation fails"
    recovery: "Retry with fallback format, preserve raw content"
```

### Health Monitoring

```yaml
health_checks:
  structure_integrity:
    frequency: 600s
    check: "All sections have valid parent chapters"

  reference_validity:
    frequency: 300s
    check: "All cross-references resolve"

  citation_completeness:
    frequency: 300s
    check: "All in-text citations have bibliography entries"

  content_freshness:
    frequency: 60s
    check: "Compiled output matches latest content"
```

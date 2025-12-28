---
name: research-discovery
description: |
  Systematic literature search and source discovery for research documents.
  Use this skill when you need to find academic papers, industry reports,
  grey literature, data sources, or expert commentary. Supports search
  strategy design, database querying, source screening, and relevance filtering.
  Trigger on: "find sources", "literature search", "research on", "discover papers",
  "what does the literature say", "find evidence for".
---

# Research Discovery Skill

Systematic approach to finding high-quality sources for research documents.

## Quick Start

1. **Define search needs** - What claims need evidence? What gaps exist?
2. **Design search strategy** - Keywords, databases, filters
3. **Execute searches** - Run queries across sources
4. **Screen results** - Filter by relevance and quality
5. **Extract findings** - Pull key information from selected sources

## Search Strategy Design

### Keyword Development

Start with your research question and break it into concepts:

```
Research Question: "How does remote work affect employee productivity?"

Concepts:
- Remote work (synonyms: telecommuting, work from home, distributed work)
- Employee productivity (synonyms: worker performance, output, efficiency)
- Effects/impacts (synonyms: influence, relationship, correlation)
```

### Boolean Query Construction

Combine concepts with operators:
- **AND** - Both terms must appear (narrows results)
- **OR** - Either term can appear (broadens results)
- **NOT** - Exclude term (filters results)
- **" "** - Exact phrase matching
- ***** - Wildcard for word variations

Example query:
```
("remote work" OR "telecommuting" OR "work from home")
AND ("productivity" OR "performance" OR "efficiency")
AND (employee* OR worker*)
```

## Source Databases

### Academic Sources
| Database | Best For | Access |
|----------|----------|--------|
| Google Scholar | Broad academic search | Free |
| Semantic Scholar | AI-enhanced discovery | Free |
| PubMed | Medical/health research | Free |
| JSTOR | Humanities/social sciences | Subscription |
| Web of Science | Citation analysis | Subscription |
| Scopus | STEM research | Subscription |

### Grey Literature
- Government publications (data.gov, government agency sites)
- Think tank reports (Brookings, RAND, etc.)
- International organizations (World Bank, UN, OECD)
- Industry associations and trade groups
- Conference proceedings

### Industry Sources
- Market research reports (Gartner, Forrester, IBISWorld)
- Company filings (SEC EDGAR, annual reports)
- Trade publications
- News archives

## Search Execution Process

### Step 1: Initial Broad Search
Run your query across primary databases. Aim for 100-500 initial results.

### Step 2: Title/Abstract Screening
Quickly scan titles and abstracts. Apply inclusion/exclusion criteria:
- Relevance to research question
- Publication date range
- Source type acceptability
- Language requirements

### Step 3: Full-Text Review
For promising sources, review full text:
- Does it actually address your question?
- Is the methodology sound?
- What are the key findings?
- How does it relate to other sources?

### Step 4: Snowball Search
Mine reference lists of highly relevant sources for additional papers.
Search for works that cite key papers.

## Source Quality Assessment

### Academic Source Criteria
- **Peer reviewed?** - Published in recognized journal
- **Citation count** - How often cited by others
- **Author credentials** - Expertise in the field
- **Methodology rigor** - Sound research design
- **Recency** - How current is the work

### Grey Literature Criteria
- **Organizational reputation** - Credible institution?
- **Methodology transparency** - Methods disclosed?
- **Potential bias** - Conflicts of interest?
- **Data sources** - Evidence-based claims?

## Output Format

Document discovered sources in structured format:

```yaml
source:
  title: "Paper Title"
  authors: ["Author 1", "Author 2"]
  year: 2023
  type: journal_article | report | book | website
  publication: "Journal Name"
  doi_or_url: "https://..."

  relevance:
    score: high | medium | low
    connection: "How it relates to research question"

  key_findings:
    - "Finding 1"
    - "Finding 2"

  methodology: "Brief description"

  limitations: "Any noted limitations"

  use_for: ["section name", "argument support"]
```

## Integration with Other Skills

- **citation-manager**: Pass discovered sources for formatting
- **academic-analysis**: Send sources for synthesis
- **narrative-coherence**: Map sources to argument structure
- **source-validator**: Verify source quality

## Tips for Effective Discovery

1. **Start broad, then narrow** - Cast wide net first
2. **Use multiple databases** - No single source has everything
3. **Track your searches** - Document queries for reproducibility
4. **Know when to stop** - Diminishing returns signal saturation
5. **Save everything** - Better to over-collect than miss sources

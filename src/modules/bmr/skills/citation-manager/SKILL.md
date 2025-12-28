---
name: citation-manager
description: |
  Reference management and citation formatting for research documents.
  Use this skill for formatting citations, building bibliographies,
  managing reference lists, converting between citation styles, and
  ensuring citation completeness. Trigger on: "cite", "reference",
  "bibliography", "citation style", "APA", "MLA", "Chicago", "format references".
---

# Citation Manager Skill

Comprehensive reference management and citation formatting.

## Quick Start

1. **Collect source metadata** - Gather complete citation information
2. **Store in standard format** - Use consistent internal structure
3. **Format for output** - Apply required citation style
4. **Verify completeness** - Check all citations match references
5. **Generate bibliography** - Create formatted reference list

## Citation Styles

### APA 7th Edition

**Journal Article**
```
Author, A. A., & Author, B. B. (Year). Title of article. Title of Periodical,
    volume(issue), page–page. https://doi.org/xxxxx
```

**Book**
```
Author, A. A. (Year). Title of work: Capital letter also for subtitle. Publisher.
```

**Chapter in Edited Book**
```
Author, A. A. (Year). Title of chapter. In E. E. Editor (Ed.), Title of book
    (pp. xx–xx). Publisher.
```

**Website**
```
Author, A. A. (Year, Month Day). Title of page. Site Name. URL
```

**In-text citations:**
- One author: (Smith, 2020)
- Two authors: (Smith & Jones, 2020)
- Three+ authors: (Smith et al., 2020)
- Direct quote: (Smith, 2020, p. 45)

### MLA 9th Edition

**Journal Article**
```
Author Last, First. "Article Title." Journal Title, vol. #, no. #, Year,
    pp. #–#.
```

**Book**
```
Author Last, First. Title of Book. Publisher, Year.
```

**Website**
```
Author Last, First. "Page Title." Website Name, Publisher, Day Month Year, URL.
```

**In-text citations:**
- (Smith 45)
- (Smith and Jones 45)
- (Smith et al. 45)

### Chicago (Author-Date)

**Journal Article**
```
Author Last, First. Year. "Article Title." Journal Title volume (issue): pages.
    https://doi.org/xxxxx.
```

**Book**
```
Author Last, First. Year. Title of Book. Place: Publisher.
```

**In-text citations:**
- (Smith 2020)
- (Smith 2020, 45)

### Chicago (Notes-Bibliography)

**Footnote - First Reference**
```
1. First Last, Title of Book (Place: Publisher, Year), page.
```

**Footnote - Subsequent**
```
2. Last, Short Title, page.
```

**Bibliography Entry**
```
Last, First. Title of Book. Place: Publisher, Year.
```

### IEEE

**Format**
```
[1] A. Author and B. Author, "Article title," Journal Title, vol. X, no. X,
    pp. XX–XX, Month Year.
```

**In-text:** [1], [2], [1]–[3]

### Harvard

**Journal Article**
```
Author, A.A. (Year) 'Article title', Journal Title, volume(issue), pp. xx–xx.
```

**In-text:** (Author, Year) or (Author, Year, p. X)

## Internal Citation Format

Store citations in standardized YAML:

```yaml
citations:
  - id: smith2020
    type: journal_article
    authors:
      - family: Smith
        given: John A.
      - family: Jones
        given: Mary B.
    year: 2020
    title: "The impact of remote work on productivity"
    container_title: "Journal of Management Studies"
    volume: 45
    issue: 3
    pages: "234-256"
    doi: "10.1000/example"
    accessed: "2024-01-15"

  - id: brown2019
    type: book
    authors:
      - family: Brown
        given: Sarah
    year: 2019
    title: "Organizational Behavior in the Digital Age"
    publisher: "Academic Press"
    place: "New York"
    isbn: "978-0-000-00000-0"
```

## Citation Type Templates

### Journal Article
Required: authors, year, title, container_title, volume, pages
Optional: issue, doi, url

### Book
Required: authors, year, title, publisher
Optional: place, edition, isbn

### Book Chapter
Required: authors, year, title, container_title, editors, publisher, pages
Optional: place, edition

### Conference Paper
Required: authors, year, title, event, location
Optional: pages, doi, publisher

### Report/Working Paper
Required: authors, year, title, institution
Optional: report_number, url

### Website
Required: authors (or organization), year, title, url
Optional: site_name, accessed_date

### Thesis/Dissertation
Required: author, year, title, institution, type
Optional: url

## Citation Verification Checklist

### Completeness Check
- [ ] Every in-text citation has matching reference
- [ ] Every reference is cited in text
- [ ] All required fields present for each type
- [ ] DOIs included where available
- [ ] URLs accessible (for web sources)
- [ ] Page numbers included for direct quotes

### Formatting Check
- [ ] Correct style applied throughout
- [ ] Consistent author name formatting
- [ ] Correct punctuation and italics
- [ ] Proper capitalization
- [ ] Correct ordering (alphabetical/numerical)
- [ ] Hanging indent in reference list

### Quality Check
- [ ] Primary sources used where possible
- [ ] Recent sources for current topics
- [ ] Authoritative sources prioritized
- [ ] Balanced representation of viewpoints

## Style Conversion

To convert between styles:

1. Store in internal YAML format
2. Apply target style formatting rules
3. Verify output against style guide

```
Input: Internal YAML
    ↓
Style Rules: [APA | MLA | Chicago | IEEE | Harvard]
    ↓
Output: Formatted citation
```

## Bibliography Generation

### Alphabetical (APA, MLA, Chicago Author-Date, Harvard)
Sort by: First author last name, then year, then title

### Numerical (IEEE)
Sort by: Order of first citation in text

### Sectioned Bibliography (Chicago Notes)
Group by: Source type (Primary Sources, Secondary Sources, etc.)

## Common Citation Errors

| Error | Example | Fix |
|-------|---------|-----|
| Missing year | (Smith) | (Smith, 2020) |
| Wrong et al. | Smith, Jones, and Brown (2020) for 3+ authors | Smith et al. (2020) |
| Inconsistent names | Smith (2020) vs. J. Smith (2020) | Use consistent format |
| Missing page | Direct quote without page | Add page number |
| URL without date | Website without access date | Add accessed date |
| DOI as URL | http://doi.org/... | https://doi.org/... |

## Integration with Other Skills

- **research-discovery**: Receives sources for citation storage
- **content-writer**: Provides formatted in-text citations
- **report-formatter**: Generates bibliography section
- **quality-reviewer**: Validates citation completeness

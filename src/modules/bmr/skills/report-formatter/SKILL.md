---
name: report-formatter
description: |
  Format and style research documents for professional presentation.
  Use this skill for document layout, typography, page formatting,
  table of contents, headers/footers, and final polish. Trigger on:
  "format document", "layout", "styling", "table of contents",
  "headers", "page numbers", "final formatting", "make it look professional".
---

# Report Formatter Skill

Transform content into professionally formatted documents.

## Quick Start

1. **Identify requirements** - Style guide, page limits, format specs
2. **Apply structure** - Headings, sections, page breaks
3. **Format elements** - Tables, figures, lists, citations
4. **Add navigation** - TOC, headers, footers, page numbers
5. **Final polish** - Consistency check, print test

## Document Structure

### Standard Report Structure

```markdown
# Title Page
- Title
- Author(s)
- Affiliation(s)
- Date
- [Funder acknowledgment if applicable]

# Front Matter
- Abstract/Executive Summary
- Table of Contents
- List of Figures
- List of Tables
- Acknowledgments

# Body
- Introduction
- [Body Sections...]
- Conclusion

# Back Matter
- References
- Appendices
- Glossary [if needed]
- Index [if needed]
```

### Heading Hierarchy

```markdown
# Level 1: Major Sections (Title Case, Bold)
## Level 2: Subsections (Title Case, Bold)
### Level 3: Sub-subsections (Sentence case, Bold)
#### Level 4: Paragraphs (Sentence case, Bold, run-in)
##### Level 5: Sub-paragraphs (Sentence case, Italic, run-in)
```

## Formatting Standards by Document Type

### Academic Paper (APA Style)

```
Page Setup:
- Margins: 1 inch all sides
- Font: Times New Roman 12pt (or Calibri 11pt)
- Spacing: Double throughout
- Alignment: Left (ragged right)

Header:
- Running head: SHORT TITLE (left)
- Page number (right)

Title Page:
- Centered, bold title
- Author name(s)
- Affiliation
- Author note (if applicable)
```

### Grant Proposal (Common Format)

```
Page Setup:
- Margins: Per funder guidelines (often 0.5-1 inch)
- Font: Per guidelines (often Arial 11pt or TNR 12pt)
- Spacing: Often single or 1.15
- Page limit: STRICTLY enforced

Structure:
- Follow exact funder template
- Number all pages
- Use required section headers
- Include all required components
```

### Business Report

```
Page Setup:
- Margins: 0.75-1 inch
- Font: Arial or Calibri 11pt
- Spacing: 1.15 or 1.5
- Alignment: Justified or left

Elements:
- Professional header with logo
- Clear section breaks
- Executive summary upfront
- Visual emphasis on key findings
```

### Technical Report

```
Page Setup:
- Margins: 1 inch
- Font: Consistent sans-serif 11pt
- Spacing: 1.15-1.5
- Two-column option for longer reports

Elements:
- Detailed table of contents
- Numbered sections (1.0, 1.1, 1.1.1)
- Figure/table numbering by section
- Cross-references throughout
```

## Element Formatting

### Tables

```markdown
Table [N]
[Title in italics above table]

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data     | Data     | Data     |
| Data     | Data     | Data     |

Note. [Explanatory note below table]
```

**Table Design Principles:**
- Horizontal lines: top, below header, bottom only
- No vertical lines (usually)
- Align numbers by decimal point
- Clear, concise column headers
- Consistent number formatting

### Figures

```markdown
[Figure visual]

Figure [N]. [Caption describing the figure in sentence case.]
```

**Figure Principles:**
- High resolution (300 DPI for print)
- Consistent sizing
- Clear labels
- Readable text
- Accessible colors

### Lists

**Bulleted Lists** (items not sequential):
- First item
- Second item
- Third item

**Numbered Lists** (sequential or ranked):
1. First step
2. Second step
3. Third step

**Nested Lists:**
1. Main item
   a. Sub-item
   b. Sub-item
2. Main item

### Block Quotes

For quotes over 40 words:
```
     Lorem ipsum dolor sit amet, consectetur adipiscing elit.
     Sed do eiusmod tempor incididunt ut labore et dolore magna
     aliqua. Ut enim ad minim veniam, quis nostrud exercitation.
     (Author, Year, p. XX)
```

## Page Elements

### Headers and Footers

```
Header Options:
- Document title (short form)
- Section title
- Author name
- Organization logo

Footer Options:
- Page number (centered or right)
- Document date
- Confidentiality notice
- Version number
```

### Page Numbers

```
Placement: Bottom center or bottom right
Front matter: Roman numerals (i, ii, iii)
Body: Arabic numerals (1, 2, 3)
Start count: Title page = page i (not shown)
```

### Table of Contents

```markdown
Table of Contents

Abstract .................................................. ii
List of Figures .......................................... iii
List of Tables ........................................... iv

1. Introduction ........................................... 1
   1.1 Background ......................................... 2
   1.2 Research Questions ................................. 4
2. Literature Review ...................................... 6
   2.1 Theoretical Framework .............................. 7
   2.2 Previous Studies ................................... 9
3. Methodology ........................................... 12

[Use dot leaders for page alignment]
```

## Final Polish Checklist

### Consistency Check
- [ ] Heading styles consistent throughout
- [ ] Font consistent (no accidental font changes)
- [ ] Spacing consistent between sections
- [ ] Indentation consistent
- [ ] Number formatting consistent
- [ ] Date formatting consistent
- [ ] Terminology consistent

### Navigation Check
- [ ] Table of contents accurate
- [ ] Page numbers correct
- [ ] Cross-references work
- [ ] Figure/table numbers sequential
- [ ] Hyperlinks functional (for digital)

### Quality Check
- [ ] No widows (single line at top of page)
- [ ] No orphans (single line at bottom)
- [ ] No rivers (white space paths in text)
- [ ] Images high quality
- [ ] Tables fit page margins
- [ ] Appropriate page breaks

### Compliance Check
- [ ] Meets page limits
- [ ] Uses required fonts
- [ ] Includes all required sections
- [ ] Follows margin requirements
- [ ] Headers/footers per requirements

## Output Formats

### PDF (Recommended for Submission)
- Preserves formatting exactly
- Universally readable
- Print-ready
- Can be secured

### Word (.docx)
- When editing expected
- Track changes needed
- Collaborative review
- Template-based submissions

### Markdown
- For web publication
- Version control friendly
- Converts to other formats
- Simple and portable

### LaTeX
- Complex mathematical content
- Publication-ready academic papers
- Precise typographical control
- Consistent professional output

## Integration with Other Skills

- **content-writer**: Receives final drafts for formatting
- **illustration-design**: Coordinates figure formatting
- **citation-manager**: Formats reference section
- **quality-reviewer**: Reviews final formatted document

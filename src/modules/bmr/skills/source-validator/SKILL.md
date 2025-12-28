---
name: source-validator
description: |
  Validate source quality, credibility, and appropriateness for research
  documents. Use this skill to assess source reliability, check for bias,
  verify citations, evaluate methodology, and ensure sources meet academic
  or professional standards. Trigger on: "validate source", "check credibility",
  "is this reliable", "source quality", "evaluate this source", "peer reviewed",
  "bias check".
---

# Source Validator Skill

Ensure your sources are credible, reliable, and appropriate.

## Quick Start

1. **Identify source type** - Academic, grey literature, news, etc.
2. **Assess credibility** - Author, publication, methodology
3. **Check for bias** - Funding, affiliation, perspective
4. **Verify currency** - Is information still current?
5. **Confirm appropriateness** - Suitable for your purpose?

## Source Credibility Framework

### The CRAAP Test

**Currency** - Timeliness of information
- When was it published/updated?
- Is the information current for your topic?
- Are links functional?

**Relevance** - Importance to your needs
- Does it relate to your research question?
- Who is the intended audience?
- Is it at an appropriate level?

**Authority** - Source of information
- Who is the author/publisher?
- What are their credentials?
- Is there contact information?

**Accuracy** - Reliability and truthfulness
- Is information supported by evidence?
- Has it been reviewed/refereed?
- Can claims be verified elsewhere?

**Purpose** - Reason for existing
- What is the purpose (inform, sell, entertain, persuade)?
- Is the intent clear?
- Are there obvious biases?

### Source Type Hierarchy

| Source Type | Credibility | Best For |
|-------------|-------------|----------|
| Peer-reviewed journal | Highest | Primary research claims |
| Academic book | High | Comprehensive coverage |
| Government report | High | Policy, statistics |
| Professional org report | Medium-High | Industry standards |
| Trade publication | Medium | Industry perspective |
| Quality news (NYT, etc.) | Medium | Current events |
| Website (.edu, .gov) | Varies | Depends on author |
| Blog/social media | Low | Opinion, discovery only |
| Wikipedia | Low (but useful) | Background only |

## Source Type Validation

### Peer-Reviewed Journal Articles

**Verification Checklist:**
- [ ] Published in recognized journal
- [ ] Journal has impact factor/ranking
- [ ] Article includes methodology section
- [ ] Clear data/evidence presented
- [ ] Limitations acknowledged
- [ ] Conflict of interest disclosed

**Red Flags:**
- Predatory journal indicators
- Methodology not described
- Results too good to be true
- No peer review process evident
- Journal not indexed in databases

### Books and Book Chapters

**Verification Checklist:**
- [ ] Published by academic press
- [ ] Author has relevant credentials
- [ ] Book is cited by other scholars
- [ ] Recent edition (if applicable)
- [ ] Contains references

**Assess Publisher Quality:**
- University presses (Oxford, Cambridge, etc.)
- Major academic publishers (Sage, Routledge, Springer)
- Professional association publishers
- Reputable trade publishers

### Grey Literature (Reports, Working Papers)

**Verification Checklist:**
- [ ] Issuing organization is credible
- [ ] Methodology disclosed
- [ ] Data sources identified
- [ ] Authors qualified
- [ ] Purpose stated clearly

**Strong Grey Literature Sources:**
- Government agencies
- International organizations (UN, World Bank)
- Major think tanks
- Professional associations
- Research institutions

### Websites and Online Sources

**Verification Checklist:**
- [ ] Author/organization identified
- [ ] Contact information provided
- [ ] Date of publication/update shown
- [ ] Sources/references cited
- [ ] Domain appropriate (.edu, .gov, .org)

**Domain Considerations:**
- **.gov** - Government, generally reliable
- **.edu** - Academic, varies by author
- **.org** - Varies widely, check organization
- **.com** - Commercial, assess carefully
- **.net** - Varies, assess carefully

## Bias Assessment

### Types of Bias to Check

**Selection Bias**
- Cherry-picked data or examples
- Incomplete representation of evidence
- Only favorable results reported

**Funding Bias**
- Research funded by interested parties
- Industry-sponsored studies
- Potential conflicts of interest

**Political/Ideological Bias**
- Organization has known perspective
- Language suggests predetermined conclusions
- Alternative views not represented

**Publication Bias**
- Positive results published more often
- Null results underrepresented
- Replication studies rarely published

### Bias Indicators

**Language Red Flags:**
- Emotional or loaded terms
- Absolutes ("always," "never," "proves")
- One-sided argumentation
- Ad hominem attacks
- Missing qualifiers

**Structural Red Flags:**
- No methodology section
- No limitations discussed
- No competing perspectives
- Funding source hidden
- Conflicts not disclosed

## Validation Workflows

### Quick Validation (2 minutes)

1. Who wrote it? → Credentials check
2. Where published? → Publication reputation
3. When published? → Currency check
4. Why written? → Purpose/bias check
5. What evidence? → Support assessment

### Deep Validation (15+ minutes)

1. **Author verification**
   - Search author's other publications
   - Check institutional affiliation
   - Look for conflicts of interest

2. **Publication verification**
   - Journal impact factor
   - Publisher reputation
   - Indexing in databases

3. **Content verification**
   - Cross-check key claims
   - Verify data sources
   - Compare with other sources

4. **Reception verification**
   - Citation count
   - Critical responses
   - Replication status

## Source Validation Record

```yaml
source_validation:
  source_id: "[citation key]"
  title: "[Source title]"
  validation_date: "[Date]"

  craap_assessment:
    currency:
      score: [1-5]
      notes: "[Assessment notes]"
    relevance:
      score: [1-5]
      notes: "[Assessment notes]"
    authority:
      score: [1-5]
      notes: "[Assessment notes]"
    accuracy:
      score: [1-5]
      notes: "[Assessment notes]"
    purpose:
      score: [1-5]
      notes: "[Assessment notes]"

  overall_score: [5-25]
  recommendation: "[Use/Use with caution/Don't use]"

  bias_check:
    potential_biases: ["list"]
    conflicts_of_interest: "[identified conflicts]"

  verification:
    claims_verified: [Y/N]
    cross_referenced: [Y/N]

  use_guidance: "[How to use this source appropriately]"
```

## Common Validation Scenarios

### "Is this study reliable?"
Check: Peer review, methodology, sample size, replication

### "Can I cite this website?"
Check: Author credentials, organization reputation, source of claims

### "Is this news article accurate?"
Check: Reporter expertise, multiple sources cited, primary source access

### "Is this think tank biased?"
Check: Funding sources, stated mission, ideological positioning

### "Can I use Wikipedia?"
Use for: Background, finding sources
Don't use for: Direct citation in academic work
Check: References at bottom of article

## Integration with Other Skills

- **research-discovery**: Validates discovered sources
- **citation-manager**: Updates validation status
- **academic-analysis**: Informs synthesis credibility
- **quality-reviewer**: Supports overall quality check

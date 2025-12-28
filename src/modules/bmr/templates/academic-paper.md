---
document_type: academic_paper
version: "1.0"
created: "{{date}}"
last_modified: "{{date}}"
title: "{{paper_title}}"
authors: {{authors}}
affiliations: {{affiliations}}
journal_target: "{{target_journal}}"
status: draft
stepsCompleted: []
---

# {{paper_title}}

{{#each authors}}
**{{this.name}}**^{{this.affiliation_number}}^
{{/each}}

{{#each affiliations}}
^{{@index}}^ {{this}}
{{/each}}

**Corresponding Author:** {{corresponding_author}}
**Email:** {{corresponding_email}}

---

## Abstract

<!--
Structured abstract (typically 150-300 words):
- Background/Context
- Objective/Purpose
- Methods
- Results
- Conclusions
-->

**Background:** {{abstract_background}}

**Objective:** {{abstract_objective}}

**Methods:** {{abstract_methods}}

**Results:** {{abstract_results}}

**Conclusions:** {{abstract_conclusions}}

**Keywords:** {{keywords}}

---

## 1. Introduction

<!--
Establish context and motivation:
- Broad context and importance
- Specific problem or gap
- Research questions/objectives
- Significance and contribution
- Paper structure (optional)
-->

### 1.1 Background and Context

{{introduction_background}}

### 1.2 Problem Statement

{{problem_statement}}

### 1.3 Research Questions

{{research_questions}}

### 1.4 Objectives

{{research_objectives}}

### 1.5 Contribution

{{paper_contribution}}

---

## 2. Literature Review

<!--
Situate work in existing scholarship:
- Theoretical foundations
- Previous empirical work
- Gaps in current knowledge
- How this study addresses gaps
-->

### 2.1 Theoretical Framework

{{theoretical_framework}}

### 2.2 Previous Research

{{previous_research}}

### 2.3 Synthesis of Literature

{{literature_synthesis}}

### 2.4 Research Gap

{{research_gap}}

---

## 3. Methodology

<!--
Enable replication and evaluation:
- Research design
- Data collection
- Analysis methods
- Validity considerations
-->

### 3.1 Research Design

{{research_design}}

### 3.2 Participants / Sample / Data Sources

{{sample_description}}

### 3.3 Data Collection

{{data_collection}}

#### 3.3.1 Instruments / Measures

{{instruments}}

#### 3.3.2 Procedures

{{procedures}}

### 3.4 Data Analysis

{{data_analysis}}

### 3.5 Validity and Reliability

{{validity_reliability}}

### 3.6 Ethical Considerations

{{ethics}}

---

## 4. Results

<!--
Present findings objectively:
- Organized by research question or theme
- Statistical results with effect sizes
- Tables and figures as appropriate
- No interpretation (save for discussion)
-->

### 4.1 Descriptive Statistics

{{descriptive_stats}}

### 4.2 Main Findings

#### 4.2.1 Research Question 1

{{rq1_findings}}

#### 4.2.2 Research Question 2

{{rq2_findings}}

#### 4.2.3 Research Question 3

{{rq3_findings}}

### 4.3 Additional Analyses

{{additional_analyses}}

---

## 5. Discussion

<!--
Interpret and contextualize findings:
- Summary of key findings
- Interpretation relative to literature
- Theoretical implications
- Practical implications
- Limitations
- Future research
-->

### 5.1 Summary of Findings

{{findings_summary}}

### 5.2 Interpretation

{{interpretation}}

### 5.3 Relation to Previous Research

{{relation_to_literature}}

### 5.4 Theoretical Implications

{{theoretical_implications}}

### 5.5 Practical Implications

{{practical_implications}}

### 5.6 Limitations

{{limitations}}

### 5.7 Future Research Directions

{{future_research}}

---

## 6. Conclusion

<!--
Concise summary and final thoughts:
- Restate main contribution
- Key takeaways
- Broader significance
-->

{{conclusion}}

---

## Acknowledgments

{{acknowledgments}}

---

## Funding

{{funding_statement}}

---

## Declaration of Interests

{{conflict_of_interest}}

---

## Author Contributions

{{author_contributions}}

---

## Data Availability

{{data_availability}}

---

## References

{{references}}

---

## Tables

### Table 1: {{table1_title}}

{{table1}}

*Note.* {{table1_note}}

### Table 2: {{table2_title}}

{{table2}}

*Note.* {{table2_note}}

---

## Figures

### Figure 1: {{figure1_title}}

{{figure1}}

*Figure 1.* {{figure1_caption}}

### Figure 2: {{figure2_title}}

{{figure2}}

*Figure 2.* {{figure2_caption}}

---

## Appendices

### Appendix A: {{appendix_a_title}}

{{appendix_a}}

### Appendix B: {{appendix_b_title}}

{{appendix_b}}

---

## Supplementary Materials

{{supplementary}}

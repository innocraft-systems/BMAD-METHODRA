---
document_type: research_proposal
version: "1.0"
created: "{{date}}"
last_modified: "{{date}}"
title: "{{research_title}}"
principal_investigator: "{{pi_name}}"
institution: "{{institution}}"
status: draft
stepsCompleted: []
---

# {{research_title}}

## Research Proposal

**Principal Investigator:** {{pi_name}}
**Institution:** {{institution}}
**Department:** {{department}}
**Proposed Duration:** {{duration}}
**Funding Requested:** {{funding_amount}}

---

## Abstract

<!--
Concise summary (typically 250-500 words):
- Research question
- Significance
- Methodology overview
- Expected outcomes
-->

{{abstract}}

**Keywords:** {{keywords}}

---

## 1. Introduction and Background

### 1.1 Research Context

{{research_context}}

### 1.2 Problem Statement

{{problem_statement}}

### 1.3 Significance of the Study

{{significance}}

---

## 2. Literature Review

### 2.1 Current State of Knowledge

{{current_knowledge}}

### 2.2 Theoretical Framework

{{theoretical_framework}}

### 2.3 Gap in the Literature

{{literature_gap}}

### 2.4 How This Study Addresses the Gap

{{addressing_gap}}

---

## 3. Research Questions and Objectives

### 3.1 Research Questions

{{#each research_questions}}
**RQ{{@index}}:** {{this}}
{{/each}}

### 3.2 Research Objectives

**Primary Objective:**
{{primary_objective}}

**Secondary Objectives:**
{{#each secondary_objectives}}
- {{this}}
{{/each}}

### 3.3 Hypotheses (if applicable)

{{#each hypotheses}}
**H{{@index}}:** {{this}}
{{/each}}

---

## 4. Methodology

### 4.1 Research Design

{{research_design}}

### 4.2 Study Population and Sampling

{{population_sampling}}

#### 4.2.1 Inclusion Criteria

{{inclusion_criteria}}

#### 4.2.2 Exclusion Criteria

{{exclusion_criteria}}

#### 4.2.3 Sample Size Justification

{{sample_size}}

### 4.3 Data Collection

#### 4.3.1 Data Sources

{{data_sources}}

#### 4.3.2 Instruments and Measures

{{instruments}}

#### 4.3.3 Data Collection Procedures

{{collection_procedures}}

### 4.4 Data Analysis

{{data_analysis}}

### 4.5 Validity and Reliability

{{validity_reliability}}

### 4.6 Ethical Considerations

{{ethical_considerations}}

---

## 5. Innovation and Contribution

### 5.1 Novel Aspects

{{novel_aspects}}

### 5.2 Expected Contribution to Knowledge

{{contribution_to_knowledge}}

### 5.3 Potential Applications

{{potential_applications}}

---

## 6. Work Plan and Timeline

### 6.1 Research Phases

{{#each phases}}
**Phase {{@index}}: {{this.name}}** ({{this.duration}})
{{this.description}}

Activities:
{{#each this.activities}}
- {{this}}
{{/each}}
{{/each}}

### 6.2 Timeline (Gantt Chart Description)

{{timeline_description}}

### 6.3 Milestones and Deliverables

| Milestone | Deliverable | Target Date |
|-----------|-------------|-------------|
{{#each milestones}}
| {{this.milestone}} | {{this.deliverable}} | {{this.date}} |
{{/each}}

---

## 7. Research Team

### 7.1 Principal Investigator

**{{pi_name}}**
{{pi_qualifications}}

Role: {{pi_role}}

### 7.2 Co-Investigators

{{#each co_investigators}}
**{{this.name}}**, {{this.institution}}
{{this.qualifications}}
Role: {{this.role}}
{{/each}}

### 7.3 Research Staff

{{research_staff}}

### 7.4 Collaborators and Advisors

{{collaborators}}

---

## 8. Resources and Facilities

### 8.1 Institutional Resources

{{institutional_resources}}

### 8.2 Equipment and Facilities

{{equipment_facilities}}

### 8.3 Data Resources

{{data_resources}}

---

## 9. Budget

### 9.1 Budget Summary

| Category | Year 1 | Year 2 | Total |
|----------|--------|--------|-------|
| Personnel | {{personnel_y1}} | {{personnel_y2}} | {{personnel_total}} |
| Equipment | {{equipment_y1}} | {{equipment_y2}} | {{equipment_total}} |
| Supplies | {{supplies_y1}} | {{supplies_y2}} | {{supplies_total}} |
| Travel | {{travel_y1}} | {{travel_y2}} | {{travel_total}} |
| Other | {{other_y1}} | {{other_y2}} | {{other_total}} |
| **Total Direct** | {{direct_y1}} | {{direct_y2}} | {{direct_total}} |
| Indirect | {{indirect_y1}} | {{indirect_y2}} | {{indirect_total}} |
| **Total** | {{total_y1}} | {{total_y2}} | {{grand_total}} |

### 9.2 Budget Justification

{{budget_justification}}

---

## 10. Dissemination Plan

### 10.1 Publication Strategy

{{publication_strategy}}

### 10.2 Conference Presentations

{{conference_plans}}

### 10.3 Other Dissemination Activities

{{other_dissemination}}

---

## 11. Risk Assessment

### 11.1 Potential Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
{{#each risks}}
| {{this.risk}} | {{this.probability}} | {{this.impact}} | {{this.mitigation}} |
{{/each}}

### 11.2 Contingency Plans

{{contingency_plans}}

---

## 12. Preliminary Studies (if applicable)

{{preliminary_studies}}

---

## References

{{references}}

---

## Appendices

### Appendix A: Instruments and Protocols

{{instruments_protocols}}

### Appendix B: Letters of Support

{{letters_of_support}}

### Appendix C: CVs of Key Personnel

{{cvs}}

### Appendix D: IRB/Ethics Approval (if available)

{{ethics_approval}}

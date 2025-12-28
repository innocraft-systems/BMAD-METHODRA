---
document_type: grant_proposal
version: "1.0"
created: "{{date}}"
last_modified: "{{date}}"
project_name: "{{project_name}}"
funder: "{{funder_name}}"
deadline: "{{deadline}}"
status: draft
stepsCompleted: []
---

# {{project_name}}

## Grant Proposal

**Submitted to:** {{funder_name}}
**Principal Investigator:** {{pi_name}}
**Institution:** {{institution}}
**Requested Amount:** {{requested_amount}}
**Project Period:** {{start_date}} - {{end_date}}

---

## Executive Summary

<!--
Write a compelling 1-page summary that includes:
- The problem/opportunity
- Your proposed solution
- Expected impact
- Why your team is uniquely qualified
-->

{{executive_summary}}

---

## 1. Statement of Need / Problem Statement

<!--
Establish the urgency and importance of the problem:
- What is the problem?
- Who is affected and how?
- What happens if nothing is done?
- Why is this the right time to address it?
-->

### 1.1 The Problem

{{problem_description}}

### 1.2 Affected Population

{{affected_population}}

### 1.3 Evidence of Need

{{evidence_of_need}}

### 1.4 Gap in Current Solutions

{{current_gap}}

---

## 2. Goals and Objectives

<!--
Clearly state what you will accomplish:
- Overall goal (broad impact)
- Specific objectives (measurable outcomes)
- SMART objectives recommended
-->

### 2.1 Project Goal

{{project_goal}}

### 2.2 Objectives

{{#each objectives}}
**Objective {{@index}}:** {{this.description}}
- Measurable outcome: {{this.outcome}}
- Timeline: {{this.timeline}}
{{/each}}

---

## 3. Methodology / Approach

<!--
Describe HOW you will achieve your objectives:
- Specific activities and methods
- Why this approach will work
- Innovation or unique elements
- How activities connect to objectives
-->

### 3.1 Approach Overview

{{approach_overview}}

### 3.2 Activities

{{#each activities}}
#### Activity {{@index}}: {{this.name}}

**Description:** {{this.description}}
**Methods:** {{this.methods}}
**Responsible Party:** {{this.responsible}}
**Timeline:** {{this.timeline}}
**Outputs:** {{this.outputs}}
{{/each}}

### 3.3 Innovation

{{innovation_description}}

---

## 4. Evaluation Plan

<!--
Explain how you will measure success:
- What will be measured
- How and when
- Who will evaluate
- How findings will be used
-->

### 4.1 Evaluation Approach

{{evaluation_approach}}

### 4.2 Indicators and Metrics

| Objective | Indicator | Data Source | Frequency |
|-----------|-----------|-------------|-----------|
{{#each evaluation_metrics}}
| {{this.objective}} | {{this.indicator}} | {{this.source}} | {{this.frequency}} |
{{/each}}

### 4.3 Data Collection Methods

{{data_collection}}

### 4.4 Use of Evaluation Results

{{evaluation_use}}

---

## 5. Organizational Capacity

<!--
Demonstrate your ability to execute:
- Organization background
- Relevant experience
- Key personnel
- Partnerships
-->

### 5.1 Organization Background

{{org_background}}

### 5.2 Relevant Experience

{{relevant_experience}}

### 5.3 Key Personnel

{{#each key_personnel}}
**{{this.name}}**, {{this.title}}
{{this.qualifications}}
Role in project: {{this.role}}
Time commitment: {{this.time_commitment}}
{{/each}}

### 5.4 Partners and Collaborators

{{partners}}

---

## 6. Budget and Budget Justification

<!--
Present a realistic, justified budget:
- Detailed line items
- Clear justification for each item
- Alignment with activities
-->

### 6.1 Budget Summary

| Category | Year 1 | Year 2 | Year 3 | Total |
|----------|--------|--------|--------|-------|
| Personnel | {{personnel_y1}} | {{personnel_y2}} | {{personnel_y3}} | {{personnel_total}} |
| Fringe Benefits | {{fringe_y1}} | {{fringe_y2}} | {{fringe_y3}} | {{fringe_total}} |
| Equipment | {{equipment_y1}} | {{equipment_y2}} | {{equipment_y3}} | {{equipment_total}} |
| Supplies | {{supplies_y1}} | {{supplies_y2}} | {{supplies_y3}} | {{supplies_total}} |
| Travel | {{travel_y1}} | {{travel_y2}} | {{travel_y3}} | {{travel_total}} |
| Other Direct | {{other_y1}} | {{other_y2}} | {{other_y3}} | {{other_total}} |
| **Total Direct** | {{direct_y1}} | {{direct_y2}} | {{direct_y3}} | {{direct_total}} |
| Indirect Costs | {{indirect_y1}} | {{indirect_y2}} | {{indirect_y3}} | {{indirect_total}} |
| **Total** | {{total_y1}} | {{total_y2}} | {{total_y3}} | {{grand_total}} |

### 6.2 Budget Justification

{{budget_justification}}

---

## 7. Timeline

<!--
Show the project schedule:
- Major milestones
- Activity timing
- Dependencies
-->

### 7.1 Project Timeline

{{timeline_visual}}

### 7.2 Milestones

| Milestone | Target Date | Deliverable |
|-----------|-------------|-------------|
{{#each milestones}}
| {{this.name}} | {{this.date}} | {{this.deliverable}} |
{{/each}}

---

## 8. Sustainability Plan

<!--
Explain life after the grant:
- How will impact continue?
- Funding strategies
- Institutionalization plans
-->

### 8.1 Sustainability Strategy

{{sustainability_strategy}}

### 8.2 Future Funding

{{future_funding}}

### 8.3 Institutionalization

{{institutionalization}}

---

## 9. References

{{references}}

---

## Appendices

### Appendix A: Letters of Support

{{letters_of_support}}

### Appendix B: Organizational Documents

{{org_documents}}

### Appendix C: Key Personnel CVs

{{cvs}}

### Appendix D: Additional Supporting Materials

{{additional_materials}}

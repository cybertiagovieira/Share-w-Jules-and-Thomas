# Prompt Library and Execution Templates

| Library field | Purpose |
|---|---|
| **Purpose** | Provide ready-to-use prompts for running, scheduling, validating, recovering, and updating an evidence-led agentic research and PowerPoint workflow. |
| **Primary users** | Any team member responsible for creating sector reports or presentations. |
| **Usage model** | Copy a template, replace placeholders in braces, and send it in a new agent chat. |
| **Default output language** | English (US). |
| **Default audience** | 1LoD operational management and Risk Committee. |

## 1. How to use this library

Select the template that matches the required operation. Replace every `{PLACEHOLDER}` before submitting the prompt. Do not remove mandatory controls unless the process owner has approved a documented exception.

| If you need to... | Use template |
|---|---|
| Produce a full report and PowerPoint manually | Template A |
| Produce an H1/H2 recurring report | Template B |
| Use a specific existing GitHub repository | Template C |
| Create or reuse the default private repository | Template D |
| Apply a corporate PowerPoint template | Template E |
| Run research only | Template F |
| Generate slides from an approved evidence package | Template G |
| Perform final quality assurance | Template H |
| Diagnose GitHub delivery access | Template I |
| Recover from a failed run | Template J |
| Update the reusable skill | Template K |

## 2. Parameter dictionary

| Placeholder | Required value | Example |
|---|---|---|
| `{SECTOR}` | Sector or subsector being analysed. | `European Healthcare` |
| `{PERIOD}` | Reporting period. | `H2 2026` |
| `{REPORT_DATE}` | Date used as evidence cut-off. | `31 October 2026` |
| `{GEOGRAPHY}` | Applicable geography. | `European Union` |
| `{CASE_STUDY_TITLE}` | Completed event used on Slide 4. | `Change Healthcare Ransomware Event` |
| `{SECTOR_SLUG}` | Lowercase path-safe sector identifier. | `european-healthcare` |
| `{REPOSITORY_URL}` | Full GitHub repository URL, when one is required. | `https://github.com/OWNER/cyber-risk-reports` |
| `{DELIVERY_PATH}` | Repository destination path. | `reports/european-healthcare/2026-H2/` |
| `{TEMPLATE_FILE}` | Attached approved corporate PowerPoint template. | `corporate_template.pptx` |
| `{SCHEDULE}` | Required recurrence. | `1 January and 1 July at 09:00` |

## 3. Mandatory controls block

Add this block to every full workflow prompt. It contains the controls that make outputs traceable, current, and suitable for executive use.

```text
MANDATORY CONTROLS

Language:
1. Never use these words in the final report, presentation, source notes, chart labels, speaker notes, file names, or manifest: "serious", "critical", "extreme", "verified".
2. Never use the em dash character. Use " - " instead.
3. Use precise, evidence-led wording. State limitations, proxies, uncertainty, methodology, and scope explicitly.

Evidence:
4. Set the evidence cut-off to {REPORT_DATE}.
5. Prioritise current-year sources by newest publication date. Then use H2 of the preceding year, followed by H1 of the preceding year.
6. Treat sources older than 18 months as contextual or historical. State their continuing relevance.
7. Prefer official, regulatory, statutory, law-enforcement, victim, and institutional sources with transparent methodology.
8. Create a source register and claim ledger before drafting the report or presentation.
9. Do not invent sources, metrics, dates, financial impacts, case-study details, regulatory requirements, quality results, or delivery confirmations.
10. Distinguish observed facts, assessments, and planning scenarios.

Quality:
11. Generate exactly five analytical slides with the required titles.
12. Complete content, temporal, language, visual, export, and delivery checks before any final delivery.
13. Return NEEDS_REVIEW if material evidence, a required input, GitHub access, export validation, or another quality gate is insufficient.
```

## 4. Mandatory slide titles block

Add this block to any prompt that requests a full presentation or presentation-only execution.

```text
Use exactly these five analytical slide titles, in this sequence:
1. Key Threats & Top 5 Cyber Attacks
2. Financial Impact: {SECTOR}
3. Financial Impact: Worst-Case Scenarios
4. Case Study: {CASE_STUDY_TITLE}
5. Mitigation Strategies & Security Framework
```

## 5. Template A - Full manual end-to-end execution

Use this template for the standard manual workflow. It creates the complete evidence-led output package and uses the default private GitHub repository.

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}
Case study title: {CASE_STUDY_TITLE}
Audience: 1LoD operational management and Risk Committee
Output language: English (US)

Create or reuse the authenticated GitHub account's private cyber-risk-reports repository.
Deliver the completed run to reports/{SECTOR_SLUG}/{PERIOD}/.

Produce, in this exact order:
1. evidence_pack.md with source register, source tiers, temporal relevance, limitations, and claim ledger;
2. research_data.json, executive_story.md, and slide_spec.json;
3. report.md and the five-slide PowerPoint presentation;
4. presentation_qc.json and manifest.json;
5. presentation.pptx and GitHub delivery evidence.

{MANDATORY_CONTROLS_BLOCK}

{MANDATORY_SLIDE_TITLES_BLOCK}
```

## 6. Template B - Semi-annual scheduled execution

Use this template when configuring a recurring H1/H2 process.

```text
Create a scheduled task that runs the cyber-sectorial-analysis skill on {SCHEDULE}.

Default inputs:
Sector: {SECTOR}
Geography: {GEOGRAPHY}
Audience: 1LoD operational management and Risk Committee
Output language: English (US)

At each run:
1. Derive the current report period, H1 or H2, and set the report date to the execution date.
2. Run the full evidence-led workflow, including wide research, source register, claim ledger, structured data, executive narrative, slide specification, PowerPoint, quality checks, and delivery manifest.
3. Create or reuse the authenticated GitHub account's private cyber-risk-reports repository.
4. Deliver to reports/{SECTOR_SLUG}/{CURRENT_PERIOD}/.
5. Associate the authenticated GitHub connector with this scheduled task.
6. Return NEEDS_REVIEW if the connector is unavailable, evidence is insufficient, a quality gate fails, or delivery cannot be confirmed.

{MANDATORY_CONTROLS_BLOCK}

{MANDATORY_SLIDE_TITLES_BLOCK}
```

## 7. Template C - Delivery to an existing repository

Use this template when the final artefacts must go to a named personal or organisation repository.

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}
Case study title: {CASE_STUDY_TITLE}

Delivery repository: {REPOSITORY_URL}
Delivery path: {DELIVERY_PATH}

Before starting delivery, confirm read and write access to the exact repository URL. Do not create a repository in an organisation namespace unless the owner is explicitly provided and the authenticated account has permission.

{MANDATORY_CONTROLS_BLOCK}

{MANDATORY_SLIDE_TITLES_BLOCK}
```

## 8. Template D - Default private repository provisioning

Use this template when a team member has not created a repository yet.

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}
Case study title: {CASE_STUDY_TITLE}

Do not require a pre-existing GitHub repository. First confirm the authenticated GitHub account. Then resolve the account's cyber-risk-reports repository. If it does not exist, create it as private. Confirm the full repository URL and private visibility before delivery. Reuse the same repository in future runs.

Deliver the final package to reports/{SECTOR_SLUG}/{PERIOD}/.

{MANDATORY_CONTROLS_BLOCK}

{MANDATORY_SLIDE_TITLES_BLOCK}
```

## 9. Template E - Corporate-template execution

Attach the approved corporate PowerPoint template before sending this prompt.

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow with the attached corporate PowerPoint template.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}
Case study title: {CASE_STUDY_TITLE}
Corporate template: {TEMPLATE_FILE}

Before slide generation, analyse the template and record its approved master layouts, fonts, page geometry, footer, classification, cover-page, colour, and chart requirements. Use the corporate template for the final PPTX. If a requested corporate element cannot be reproduced, record the limitation in the quality record.

Create or reuse the private cyber-risk-reports repository and deliver to reports/{SECTOR_SLUG}/{PERIOD}/.

{MANDATORY_CONTROLS_BLOCK}

{MANDATORY_SLIDE_TITLES_BLOCK}
```

## 10. Template F - Research and evidence package only

Use this template when an analyst wants to review sources before report or slide generation.

```text
Use the cyber-sectorial-analysis skill to conduct research only. Do not create a report, presentation, export, or GitHub delivery yet.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}

Produce an evidence_pack.md containing:
1. research scope and evidence cut-off;
2. wide-research search themes and source register;
3. source tier, publication date, reporting period, geography, methodology, and limitation for every source;
4. facts grouped by threats, financial and operating impact, scenarios, case-study candidates, controls, and regulation;
5. claim ledger with source locators;
6. data gaps and NEEDS_REVIEW items.

Apply the evidence section of the mandatory controls block. Do not draft conclusions that are not supported by the claim ledger.
```

## 11. Template G - Presentation production from approved inputs

Use this template only when the evidence package and slide inputs are already complete and approved.

```text
Create the five-slide PowerPoint presentation from the attached or available files:
- evidence_pack.md
- research_data.json
- executive_story.md
- slide_spec.json
- presentation_design.yaml or approved corporate template

Do not conduct new research or introduce new facts. Use only content that appears in the approved evidence package and structured data.

Create these slides in the exact sequence:
1. Key Threats & Top 5 Cyber Attacks
2. Financial Impact: {SECTOR}
3. Financial Impact: Worst-Case Scenarios
4. Case Study: {CASE_STUDY_TITLE}
5. Mitigation Strategies & Security Framework

Apply the defined white background, dark text, emerald-green accent system unless the approved corporate template overrides it. Do not use rounded cards, shadows, gradients, generic imagery, decorative icons, or unsupported charts.

Run visual, language, source-coverage, and export checks. Save presentation_qc.json. Stop with NEEDS_REVIEW if a required data field or source is missing.
```

## 12. Template H - Final quality assurance and release review

Use this template before delivery when a human reviewer needs a documented release decision.

```text
Perform a final release review for the following run package:
- evidence_pack.md
- research_data.json
- report.md
- executive_story.md
- slide_spec.json
- presentation_qc.json
- manifest.json
- presentation.pptx

Check and report each gate separately:
1. Input completeness;
2. source register and claim-ledger traceability;
3. temporal relevance and historical-source rationale;
4. language controls;
5. exact slide title set and slide count;
6. visual design, text clipping, overlap, legibility, source IDs, and chart consistency;
7. PowerPoint export integrity;
8. GitHub repository URL, private visibility, commit SHA, and final file paths.

Return RELEASE_READY only when every gate passes. Otherwise return NEEDS_REVIEW with the failed gate, affected file, evidence of the issue, and the required corrective action.
```

## 13. Template I - GitHub access diagnostic

Use this template when repository access is uncertain. It performs a non-destructive access check.

```text
Check GitHub access for this repository only:
{REPOSITORY_URL}

Confirm:
1. authenticated GitHub account;
2. repository owner and visibility;
3. read access;
4. write access;
5. whether the repository can be created if it is absent.

Do not create, modify, commit, push, or delete any repository or file. Return a concise status table and the next required action.
```

## 14. Template J - Failed-run recovery

Use this template after a failed or incomplete run. Attach or identify the existing run artefacts.

```text
Recover the failed cyber-sectorial-analysis run.

Run identifier: {RUN_ID_OR_PATH}
Sector: {SECTOR}
Period: {PERIOD}

First inspect the evidence pack, quality record, manifest, presentation project, export status, and GitHub delivery status. Identify the first failed gate in the workflow.

Do not repeat completed work unless the upstream artefact is invalid. Apply the smallest corrective action required, then rerun all downstream quality checks.

If evidence is missing, return NEEDS_REVIEW. If the presentation failed, rebuild only from approved structured data. If GitHub delivery failed, do not regenerate the report or deck; restore access and deliver the existing passing artefacts.

Update presentation_qc.json and manifest.json with the recovery actions, final result, and delivery evidence.
```

## 15. Template K - Skill update request

Use this template when a process owner needs to change permanent workflow rules.

```text
Update my cyber-sectorial-analysis skill with the following approved changes:

1. Change type: {LANGUAGE_RULE | SOURCE_POLICY | SLIDE_STRUCTURE | DESIGN_RULE | DELIVERY_POLICY | QUALITY_GATE | SCHEDULE_POLICY}
2. New rule: {EXACT_RULE_TEXT}
3. Reason: {BUSINESS_OR_GOVERNANCE_REASON}
4. Applies to: {REPORT | PRESENTATION | BOTH | DELIVERY | SCHEDULE}
5. Effective date: {DATE}

Update the appropriate skill instruction, template, reference, or validation script. Preserve existing controls unless the new rule explicitly replaces them. Validate the updated skill and deliver the new skill package for installation.
```

## 16. Sector example prompts

### 16.1 European healthcare

```text
Use Template A with these values:
{SECTOR} = European Healthcare
{PERIOD} = H2 2026
{REPORT_DATE} = 31 October 2026
{GEOGRAPHY} = European Union
{CASE_STUDY_TITLE} = Change Healthcare Ransomware Event
{SECTOR_SLUG} = european-healthcare
```

### 16.2 Energy and utilities

```text
Use Template A with these values:
{SECTOR} = European Energy and Utilities
{PERIOD} = H1 2027
{REPORT_DATE} = 30 June 2027
{GEOGRAPHY} = European Union
{CASE_STUDY_TITLE} = {SELECT_A_COMPLETED_EVIDENCE_LED_EVENT}
{SECTOR_SLUG} = european-energy-utilities
```

### 16.3 Retail banking

```text
Use Template A with these values:
{SECTOR} = European Retail Banking
{PERIOD} = H2 2026
{REPORT_DATE} = 31 December 2026
{GEOGRAPHY} = European Union
{CASE_STUDY_TITLE} = {SELECT_A_COMPLETED_EVIDENCE_LED_EVENT}
{SECTOR_SLUG} = european-retail-banking
```

### 16.4 Telecommunications

```text
Use Template A with these values:
{SECTOR} = European Telecommunications
{PERIOD} = H2 2026
{REPORT_DATE} = 31 December 2026
{GEOGRAPHY} = European Union
{CASE_STUDY_TITLE} = {SELECT_A_COMPLETED_EVIDENCE_LED_EVENT}
{SECTOR_SLUG} = european-telecommunications
```

## 17. Operator pre-submission checklist

| Check | Confirm before sending |
|---|---|
| Inputs | Sector, period, report date, geography, and case-study scope are filled in. |
| Delivery | Use the default private repository or include the full repository URL and destination path. |
| Prompt type | Select the prompt that matches manual, scheduled, research-only, slide-only, or recovery use. |
| Corporate design | Attach the approved template when corporate fidelity is required. |
| Controls | Retain the mandatory controls and slide-title blocks in full workflow prompts. |
| Timing | Set the report date to the intended evidence cut-off, not merely the date the prompt was copied. |

## 18. Expected response contract

A complete agent response must state the execution status, final artefacts, quality-gate result, delivery location, and unresolved issue where relevant.

| Status | Meaning | Operator action |
|---|---|---|
| `RELEASE_READY` | All inputs, quality gates, export checks, and delivery confirmation passed. | Retrieve or review the final artefacts. |
| `NEEDS_REVIEW` | A material input, evidence requirement, quality gate, export, or delivery condition remains unresolved. | Address the named issue, then rerun the relevant template. |
| `RESEARCH_COMPLETE` | Research-only package is complete and ready for review. | Approve the evidence package or request revision before presentation production. |
| `RECOVERY_COMPLETE` | The failed run was corrected and all downstream checks passed. | Review the updated manifest and delivery evidence. |

Use this library as an operational shortcut, not as a substitute for evidence review, quality assurance, or management approval.

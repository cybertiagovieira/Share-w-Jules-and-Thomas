# Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation

| Document field | Value |
|---|---|
| **Purpose** | Define the complete, reproducible workflow for producing an evidence-led cyber risk report and a five-slide executive PowerPoint presentation, from initial request through GitHub delivery. |
| **Primary audience** | Cyber risk intelligence practitioners, 1LoD operational management, Risk Committee support teams, and agent operators. |
| **Output language** | English (US), unless the request states otherwise. |
| **Default presentation audience** | 1LoD operational management and Risk Committee. |
| **Default delivery destination** | Authenticated GitHub user's private `cyber-risk-reports` repository. |
| **Analytical deck format** | Five analytical slides. A corporate cover is added only where the approved corporate template requires it. |
| **Version** | 1.0 |

## 1. Purpose and operating principle

This SOP converts a sector question into a decision-grade PowerPoint package. It does not convert a generic narrative directly into slides. The workflow creates a controlled chain of artefacts: research evidence, structured data, executive narrative, slide specification, presentation, quality record, and delivery manifest.

> **Operating principle:** No final slide statement, chart value, date, case-study detail, regulatory observation, or delivery confirmation may appear unless it is traceable to a recorded source or execution record.

The process is complete only when the final PowerPoint has passed content, visual, export, and delivery checks, and the delivery repository contains the complete run package.

## 2. Scope

Use this SOP for sectorial cyber risk reports and presentations addressing a defined sector, geography, and reporting period. It covers manual execution on request, scheduled execution, and GitHub delivery.

| Included | Excluded |
|---|---|
| Sector-wide threat assessment | Live incident response or digital forensics |
| Research, source assessment, and claim traceability | Legal advice or formal legal interpretation |
| Executive narrative and five-slide PowerPoint production | Internal control testing within the target organisation |
| PowerPoint export, quality assurance, GitHub upload, and manifest creation | Unauthorised access to private data sources |
| Reuse of a corporate template when supplied | Assumptions presented as facts |

## 3. Expected end-state

A completed run produces the following artefacts in one period and sector folder.

```text
reports/{SECTOR_SLUG}/{REPORT_PERIOD}/
├── evidence_pack.md
├── research_data.json
├── report.md
├── executive_story.md
├── slide_spec.json
├── presentation_qc.json
├── manifest.json
└── presentation.pptx
```

The evidence pack preserves source and claim traceability. The structured research data preserves metrics, scenarios, case-study facts, and control data. The PowerPoint is the executive-facing output. The quality record and manifest provide the audit trail.

## 4. Roles and responsibilities

| Role | Responsibilities | Decision rights |
|---|---|---|
| **Requestor** | Defines sector, period, geography, audience, corporate-template requirement, and any delivery exception. | Approves scope and final business use. |
| **Agent operator** | Starts or schedules the workflow, monitors status, resolves environment or connector issues. | May rerun a failed workflow after correcting configuration. |
| **Research agent** | Builds the source register, evidence pack, and claim ledger. | May exclude weak, stale, or unsupported material. |
| **Presentation agent** | Converts only approved structured data into the slide specification and presentation. | May stop if required slide content is absent. |
| **Quality reviewer** | Reviews content, language, visual, export, and delivery gates. | Blocks release when a gate fails. |
| **GitHub delivery agent** | Resolves or provisions the private repository, commits the run package, and records delivery evidence. | May create the default private repository when it is absent. |

The same agent can perform several roles in an automated run. The separation remains conceptual and must be reflected in the artefacts and quality gates.

## 5. Manus capabilities and tools used

| Capability | Purpose in this SOP | Typical output or use |
|---|---|---|
| **Reusable skill library** | Loads the `cyber-sectorial-analysis` workflow, templates, source policy, language controls, and delivery policy. | Consistent execution rules across new chats and scheduled runs. |
| **Web research and page extraction** | Conducts broad research across official, regulatory, institutional, victim, law-enforcement, and reputable research sources. | Source register, citations, current metrics, incident details, regulatory status. |
| **Browser session** | Opens a supplied template, a page requiring visual review, or an authenticated website when text extraction is insufficient. | Corporate-template review or limited manual inspection. |
| **File workspace** | Stores durable research, structured data, narrative, specifications, QA records, and run manifests. | Markdown, JSON, YAML, PPTX, and supporting files. |
| **Shell workspace** | Runs deterministic checks, validates files, manages repositories, and executes approved command-line utilities. | Language scan, slide export check, GitHub repository status, commit history. |
| **Presentation workspace** | Creates slide projects, builds each slide, renders presentation pages, and presents the finished deck. | Five analytical slides and a presentation identifier. |
| **PowerPoint export utility** | Exports the completed presentation into a `.pptx` file after presentation completion. | `presentation.pptx`. |
| **GitHub integration and GitHub CLI** | Confirms access, creates the private repository if required, commits, and pushes artefacts. | Repository URL, commit SHA, delivery evidence. |
| **Connector and schedule configuration** | Enables GitHub access for scheduled runs and defines H1/H2 or other recurrence. | New isolated scheduled run with required connector access. |

## 6. Pre-run prerequisites

Complete these controls before the first production run.

| Prerequisite | Requirement | Evidence of completion |
|---|---|---|
| **Reusable skill** | Add `cyber-sectorial-analysis` to the user's skill library. | Skill is selectable in a new chat. |
| **GitHub authentication** | Connect the GitHub account that will own or write to the delivery repository. | Read and write access test passes. |
| **Repository policy** | Permit creation of the private default repository `cyber-risk-reports` when it does not exist. | Delivery policy is present in the skill. |
| **Corporate template** | Provide an approved PowerPoint template or reference deck if exact corporate styling is required. | Template is attached and reviewed before slide design. |
| **Output location** | Confirm the default path pattern `reports/{SECTOR_SLUG}/{REPORT_PERIOD}/`. | Path recorded in the run inputs. |
| **Scheduled run connector** | Associate the GitHub connector with the scheduled task. | Scheduled configuration shows the connector association. |

## 7. Mandatory input contract

The following inputs are required at the start of a run. A missing material analytical input requires `NEEDS_REVIEW`. A pre-existing GitHub repository is not required because the workflow creates or reuses the default private repository.

| Input | Required use | Example |
|---|---|---|
| `SECTOR` | Defines industry scope, assets, threat landscape, and mitigation priorities. | `European Healthcare` |
| `PERIOD` | Defines the analytical reporting period. | `H2 2026` |
| `REPORT_DATE` | Sets the evidence cut-off and source-relevance reference point. | `31 October 2026` |
| `GEOGRAPHY` | Limits regulation, incidents, and exposure analysis. | `European Union` |
| `CASE_STUDY_TITLE` | Defines the completed real-world event used on Slide 4. | `Change Healthcare Ransomware Event` |
| `CORPORATE_TEMPLATE` | Optional. Provides the actual master, fonts, footer, classification, and cover requirements. | `corporate_template.pptx` |
| `DELIVERY_DESTINATION` | Optional. Overrides the default private repository only when a specific destination is approved. | `https://github.com/OWNER/repository` |

## 8. Initial prompt and execution request

Use a complete request so the agent receives all inputs, language constraints, evidence rules, slide titles, and delivery intent before research begins.

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
Deliver the completed run to reports/{SECTOR_SLUG}/{REPORT_PERIOD}/.

Apply the approved corporate PowerPoint template if supplied. Otherwise apply the defined white, dark-text, emerald-green design system.

Use the five mandatory slide titles in the exact order defined in Section 15.

Apply the skill's language rules, source-recency policy, research, quality, export, and delivery controls. Stop with NEEDS_REVIEW if material evidence is insufficient or a quality gate fails.
```

The request should contain the full owner and repository URL only when the run must use a non-default repository or organisation namespace.

## 9. Language and wording controls

Apply the following rules to the report, presentation, source notes, chart labels, speaker notes, file names, and run-manifest entries.

1. Do not use the four prohibited adjectives defined in the reusable skill.
2. Do not use the long dash character. Use a spaced hyphen, ` - `, when a dash is needed.
3. Use precise evidence-led language. State the limitation, proxy, uncertainty, source scope, or methodology rather than using broad risk descriptors.
4. Separate observed activity, assessed exposure, and plausible scenarios. Do not describe scenarios as observed outcomes.
5. Reference source IDs next to material claims, metrics, charts, and case-study observations.
6. Scan every final text artefact and extracted PowerPoint text with the skill's language-control script before delivery.

## 10. Evidence freshness and source-quality policy

### 10.1 Source-recency order

Set an evidence cut-off at `REPORT_DATE`. Prioritise current and reliable evidence in this order.

| Priority | Evidence period | Permitted use |
|---|---|---|
| **1** | Report year, ordered by most recent publication date | Primary source base for threat activity, incidents, metrics, technology changes, and regulatory status. |
| **2** | H2 of the preceding year | Supporting contemporary context and trend continuity. |
| **3** | H1 of the preceding year | Supporting context when more recent material is unavailable. |
| **4** | More than 18 months old | Only for completed case studies, stable legal background, comparable benchmarks, or enduring context. Label as `contextual` or `historical`. |

For a report issued in H2 2026, information published in 2026 is the primary evidence base. H2 2025 follows, then H1 2025. Older material remains permissible only where its relevance is documented.

### 10.2 Source hierarchy

| Tier | Source standard | Primary use |
|---|---|---|
| **Tier 1** | Official regulators, statutory sources, law-enforcement bodies, victim disclosures, government bodies, and institutions with transparent methodology. | Material claims, regulation, incident details, published metrics. |
| **Tier 2** | Reputable independent research with disclosed methodology and traceable data. | Benchmarks, trend analysis, and comparative evidence. |
| **Tier 3** | Reliable secondary reporting or commentary. | Lead generation, context, and corroboration only. |

Use a newer source only where it is sufficiently reliable for the claim. A weak recent article must not override an older authoritative source.

### 10.3 Required source-register fields

For each source, record title, publisher, URL, publication date, access date, reporting period, geography, sector applicability, source tier, methodology or disclosure basis, temporal relevance, facts used, and limitations.

## 11. Step 1 - Research plan and wide research

Create a research plan before drafting the report. The plan defines the questions, required evidence, source tiers, search themes, and expected slide use.

| Research workstream | Required research question | Expected evidence |
|---|---|---|
| **Threat landscape** | What are the five sector-relevant attack patterns and exposed dependencies? | Official sector guidance, current threat reports, incident advisories. |
| **Financial and operational impact** | What evidence exists for financial impact, disruption duration, detection, containment, and recovery? | Comparable studies with methodology, official disclosures, sector benchmarks. |
| **Worst-case scenarios** | How could a compromise propagate into material operational, systemic, financial, or regulatory impact? | Evidence-supported dependency chains and scenario assumptions. |
| **Case study** | What recent completed event provides transferable lessons? | Victim, regulator, law-enforcement, or corroborated evidence. |
| **Controls and regulation** | Which controls and requirements apply to the sector and geography? | Primary regulatory sources, official guidance, sector-specific requirements. |

Conduct broad research using several queries per workstream. Search terms should cover the sector, geography, current year, cyber incidents, ransomware, supply chain, cloud or OT dependencies, regulation, recovery, and operational disruption as appropriate. Open multiple relevant sources. Do not rely on search-result summaries alone.

Create the evidence pack during research. Do not wait until slide drafting to record sources.

## 12. Step 2 - Build the evidence pack and claim ledger

Create `evidence_pack.md` containing a source register, material facts, source limitations, and a claim ledger.

### 12.1 Evidence pack structure

```text
# Evidence Pack - {SECTOR} - {PERIOD}

## Scope and evidence cut-off
## Source register
## Facts by research workstream
## Quantitative metric register
## Case-study fact record
## Regulatory evidence
## Evidence limitations and conflicts
## Claim ledger
```

### 12.2 Claim ledger structure

| Field | Required content |
|---|---|
| `claim_id` | Unique identifier such as `C01`. |
| `claim_text` | Exact wording proposed for the report or slide. |
| `source_id` | One or more source-register IDs. |
| `locator` | Page, paragraph, table, section, or URL anchor where available. |
| `date_or_period` | Date to which the evidence applies. |
| `claim_type` | Observed fact, metric, regulation, control recommendation, assessment, or scenario assumption. |
| `limitations` | Scope, geography, comparability, or methodology constraint. |
| `slide_use` | Intended slide number or report section. |

Remove or reframe any claim that cannot be supported. If the unsupported claim is required for a slide, stop the workflow with `NEEDS_REVIEW`.

## 13. Step 3 - Create the structured research data model

Translate the evidence pack into `research_data.json`. The purpose is to prevent the presentation from relying on unstructured narrative or model memory.

| Data domain | Required structured content |
|---|---|
| **Threats** | Threat name, technical vector, exposed asset or process, operational vulnerability, impact pathway, source IDs. |
| **Metrics** | Value, unit, currency, period, geography, sector, definition, methodology, source ID, and comparability note. |
| **Scenarios** | Trigger, dependency, propagation path, potential impact, assumptions, and source IDs. |
| **Case study** | Entity or event, date, timeline facts, control failure, confirmed impact, transferable lessons, and source IDs. |
| **Controls** | Control name, threat addressed, operational objective, dependency, implementation horizon, regulatory mapping, and source IDs. |

Do not calculate a sector average, risk-reduction percentage, ROI, probability, cost estimate, or maturity score unless the calculation and all underlying data are documented in the evidence pack.

## 14. Step 4 - Write the executive narrative

Create `executive_story.md` before layout. Each slide needs one decision-oriented conclusion that explains why the evidence matters to 1LoD operational management and the Risk Committee.

| Slide | Decision question | Required narrative output |
|---|---|---|
| **1** | Where is the most material operational exposure? | A conclusion about the five threat patterns and the sector dependencies that can disrupt operations or concentrate risk. |
| **2** | What is the evidence-led financial and operational impact? | A conclusion about loss drivers, comparable metrics, and limitations. |
| **3** | Which plausible scenarios can create the largest disruption? | A conclusion about propagation paths, impact drivers, and resilience assumptions. |
| **4** | What did a real event demonstrate? | A conclusion about control failure, operating consequence, and transferable lesson. |
| **5** | Which management actions should be prioritised? | A conclusion about controls, dependencies, regulatory mapping, and requested decision. |

Apply the analytical translation below without losing the link to the source evidence.

| Technical observation | Executive risk translation |
|---|---|
| Technical vector | Operational vulnerability |
| Exploitation vector | Systemic or concentration risk |
| Threat-actor intent | Geopolitical or macro-financial threat |
| Immediate cyber impact | Material financial and regulatory impact |

## 15. Step 5 - Create the slide specification

Create `slide_spec.json` from the evidence pack, research data, and executive narrative. The specification fixes the title, decision conclusion, required data fields, chart type, source IDs, and visual layout before slide construction.

Use exactly these analytical slide titles and sequence.

1. `Key Threats & Top 5 Cyber Attacks`
2. `Financial Impact: {SECTOR}`
3. `Financial Impact: Worst-Case Scenarios`
4. `Case Study: {CASE_STUDY_TITLE}`
5. `Mitigation Strategies & Security Framework`

| Slide | Layout master | Required content | Minimum evidence condition |
|---|---|---|---|
| **1** | `L01_Threat_Matrix` | Five threats, exposed processes, operational vulnerabilities, material impact, source IDs, and 1LoD implication. | Each threat line has at least one source ID. |
| **2** | `L02_Metrics_Charts` | Main metric, comparator, data chart, loss-driver explanation, methodology note, and 1LoD implication. | Every number is in the metric register. |
| **3** | `L03_Scenario_Triptych` | Three scenarios, trigger, propagation path, impact driver, resilience control, source IDs, and risk appetite question. | Assumptions are labelled and evidence-anchored. |
| **4** | `L04_Case_Timeline` | Event profile, dated timeline, control failure, confirmed impact, lessons, source IDs, and 1LoD implication. | Timeline dates and impact facts have sources. |
| **5** | `L05_Control_Roadmap` | Prioritised controls, threat addressed, regulatory mapping, 90/180/365-day roadmap, decision request, and source IDs. | Regulation and control claims have primary or authoritative sources. |

## 16. Step 6 - Apply the presentation design system

### 16.1 Design tokens

| Element | Standard |
|---|---|
| **Canvas** | 16:9 widescreen, 1280 x 720 px or PowerPoint equivalent. |
| **Background** | Solid white `#FFFFFF`. |
| **Primary text** | Black or near-black `#171717`. |
| **Accent** | Emerald green `#00915E`. Use for metrics, headings, priorities, and decision calls. |
| **Secondary text** | Medium grey `#6B7280` for notes and sources. |
| **Rules** | Light grey `#D1D5DB`, 1 px. |
| **Typography** | Approved corporate font. Use Arial or Inter only when no corporate font is available. |
| **Title size** | 34 to 42 pt, bold, maximum two lines. |
| **Body text** | 14 to 18 pt. Source notes may use 8 to 10 pt. |
| **Margins** | 48 to 60 px lateral margins with consistent alignment. |

### 16.2 Mandatory visual constraints

Use open layouts, strong alignment, typographic hierarchy, tables, timelines, and data visualisations. Do not use rounded cards, shadows, gradients, animations, hover effects, decorative stock images, decorative icons, or web-interface styling. Do not place long references in the body of a slide. Use short source IDs such as `[S01]` and retain the full source record in the evidence pack.

Use a chart only where a numeric data series exists in `research_data.json` and the source, unit, period, geography, and limitation are known. Do not create charts from estimated or invented data.

### 16.3 Corporate template procedure

Where an approved corporate template is available, review it before slide generation. Record the master layouts, fonts, typography weights, headers, footers, classification labels, confidentiality notices, slide numbers, margins, and approved chart conventions. Apply those requirements to the generated deck. The colour palette alone is not enough to reproduce the corporate standard.

## 17. Step 7 - Build and render the PowerPoint

1. Initialise one presentation project with all five analytical slides before editing individual pages.
2. Assign the five master layouts in the slide specification to the relevant pages.
3. Build each slide from its approved specification, not from a direct Markdown conversion.
4. Add the executive conclusion, evidence-led content, visible source IDs, and 1LoD implication to each slide.
5. Generate charts only from the structured data model.
6. Use a varied layout across pages while keeping the design tokens constant.
7. Add the corporate cover, classification label, footer, or page numbering only when the template requires it.
8. Finalise all slides and render the presentation for visual inspection.

## 18. Step 8 - Execute quality assurance

Do not export or deliver until every gate passes.

| Gate | Blocking test | Evidence retained |
|---|---|---|
| **Input** | Required sector, period, date, geography, and case-study scope are present. | Run inputs in `manifest.json`. |
| **Evidence** | Every material assertion, value, timeline event, and control claim maps to the claim ledger. | Evidence pack and claim ledger. |
| **Temporal** | Sources use the recency order and older material has a relevance rationale. | Source register. |
| **Narrative** | Each slide contains an executive conclusion and 1LoD implication. | Executive story and slide specification. |
| **Language** | Final files pass the language-control scan. | Language-control output. |
| **Visual** | Five required slide titles, correct colours, legible text, no clipping, no overlap, no prohibited visual patterns. | Rendered slide review and `presentation_qc.json`. |
| **Chart** | Each chart matches data values, units, periods, labels, and source IDs. | Research data and slide render. |
| **Export** | The PPTX opens, has the expected number of slides, and contains readable source notes. | Export validation record. |
| **Delivery** | Repository URL, visibility, commit SHA, final paths, and transmitted files are confirmed. | GitHub commit and manifest. |

Create `presentation_qc.json` after the checks.

```json
{
  "presentation_id": "{PRESENTATION_ID}",
  "expected_slide_count": 5,
  "exported_slide_count": 5,
  "input_qc": "pass",
  "content_qc": "pass",
  "temporal_qc": "pass",
  "language_qc": "pass",
  "visual_qc": "pass",
  "export_qc": "pass",
  "delivery_ready": true
}
```

A failed check requires correction and rerun. Do not mark the presentation ready on the basis of partial checks.

## 19. Step 9 - Export the final PowerPoint

1. Present the completed slide project through the presentation workspace.
2. Capture the presentation identifier or URI.
3. Export the presentation to `.pptx` only after the content and visual gates pass.
4. Open or inspect the exported file and confirm the slide count, titles, source notes, visual rendering, and absence of clipping.
5. Extract the PowerPoint text and run the final language-control scan.
6. Add the export result, file name, file checksum where available, and quality result to `presentation_qc.json` and `manifest.json`.

## 20. Step 10 - Provision the GitHub repository and deliver

Read the GitHub delivery policy before any repository action. A missing default repository is a provisioning requirement, not a missing analytical input.

### 20.1 Repository decision flow

| Condition | Required action |
|---|---|
| No delivery repository supplied | Resolve the authenticated user's `cyber-risk-reports` repository. Create it as private if it does not exist. |
| Existing default repository found | Reuse it. Do not create a duplicate repository. |
| Full personal repository URL supplied | Test read and write access to the exact repository. |
| Explicit organisation owner supplied | Attempt creation in that organisation only if the account has permission. Do not infer an organisation namespace. |
| Access or creation fails | Stop with `NEEDS_REVIEW`, record the owner and failed operation, and do not claim delivery. |

### 20.2 GitHub delivery procedure

1. Confirm the GitHub authentication state and determine the authenticated personal namespace.
2. Resolve or create the repository as private.
3. Confirm the resulting full URL and private visibility.
4. Clone the repository or initialise the working copy in the isolated runtime.
5. Create `reports/{SECTOR_SLUG}/{REPORT_PERIOD}/`.
6. Copy only the final artefacts that passed all quality gates.
7. Add a concise commit message, for example: `Add European Healthcare H2 2026 cyber risk analysis`.
8. Commit and push the run package.
9. Capture the commit SHA, repository URL, branch, paths, and delivery timestamp.
10. Write these results to `manifest.json`.

### 20.3 Required manifest fields

```json
{
  "sector": "{SECTOR}",
  "period": "{PERIOD}",
  "report_date": "{REPORT_DATE}",
  "evidence_cutoff": "{REPORT_DATE}",
  "artefacts": ["evidence_pack.md", "research_data.json", "report.md", "executive_story.md", "slide_spec.json", "presentation_qc.json", "manifest.json", "presentation.pptx"],
  "quality_gates": {"content": "pass", "visual": "pass", "export": "pass", "delivery": "pass"},
  "repository_url": "{REPOSITORY_URL}",
  "repository_visibility": "private",
  "commit_sha": "{COMMIT_SHA}",
  "delivery_path": "reports/{SECTOR_SLUG}/{REPORT_PERIOD}/",
  "delivery_status": "complete"
}
```

## 21. Scheduled execution

For H1/H2 or other recurring production, use the environment scheduling capability to create a new isolated run. Attach the GitHub connector to the schedule and include the complete execution instruction in the scheduled task.

The schedule instruction must require this fixed sequence:

```text
1. Confirm inputs and set evidence cut-off.
2. Conduct wide research and create the evidence pack.
3. Create structured research data, executive narrative, and slide specification.
4. Generate and validate the five-slide PowerPoint.
5. Export the PPTX.
6. Resolve or create the private delivery repository.
7. Commit all final artefacts and record the manifest.
8. Return NEEDS_REVIEW if evidence, quality, export, or delivery checks fail.
```

Do not rely on files from an earlier sandbox session. Every scheduled execution must rebuild its working package from repository-held templates, the current reusable skill, and current research.

## 22. Manual execution

For manual production, open a new chat and use the request template in Section 8. The agent should carry out the full workflow without requiring an existing delivery repository. If the user needs to rerun only the presentation stage, the evidence pack, structured data, executive narrative, slide specification, and template must be supplied or located first.

## 23. Exception handling and `NEEDS_REVIEW`

Use `NEEDS_REVIEW` whenever a material item cannot be resolved without human input. The response must state the failed step, reason, affected artefact, evidence already available, and required action.

| Exception | Response | Resume condition |
|---|---|---|
| Missing sector, period, geography, report date, or case-study scope | Stop before research. | Requestor provides the missing input. |
| Insufficient current evidence for a required claim | Remove, reframe, or flag the claim. | New source or approved alternative scope is available. |
| Metric is not comparable | Use a labelled proxy or remove the comparison. | Methodology and scope support comparison. |
| Corporate template is missing | Use the standard design system and disclose the limitation. | Approved template is provided for rerendering. |
| Slide has clipping or unreadable content | Correct layout and rerender. | Visual quality gate passes. |
| Export fails | Correct presentation state and re-export. | PPTX opens and matches the project. |
| GitHub access or repository creation fails | Stop before delivery and identify the owner and failed action. | Authentication, owner path, permission, or organisation approval is corrected. |
| Push fails after export | Preserve all local artefacts and delivery record. | Repository access is restored and commit completes. |

## 24. Completion criteria

A run is complete only when all conditions below are met.

1. The evidence pack contains the source register, temporal classification, limitations, and claim ledger.
2. The research data, executive story, and slide specification preserve traceability.
3. The presentation contains the five required analytical slides in the required sequence.
4. Each slide contains an executive conclusion, evidence-led content, an operational implication, and source IDs.
5. The design follows the white, dark-text, emerald-green system and any supplied corporate template.
6. The language scan passes for final text and PowerPoint text.
7. The PowerPoint exports successfully and passes visual inspection.
8. The delivery repository is private, contains the complete run package, and has a recorded commit SHA.
9. `manifest.json` and `presentation_qc.json` record passing results.

## 25. Post-run review and continuous improvement

After each run, record feedback from the presentation user, 1LoD owner, and Risk Committee secretariat. Capture which content was retained, which evidence required challenge, which visuals required editing, and which decisions were requested. Use this feedback to update the reusable skill, source policy, slide specification, corporate-template mapping, or quality checks.

Maintain the following reusable assets in the repository or skill library: approved source hierarchy, sector-specific search patterns, corporate template mapping, slide-layout library, language controls, delivery policy, and a small library of accepted examples. This creates a controlled improvement cycle without weakening evidence or visual standards.

## 26. Operator checklist

| Stage | Operator confirmation |
|---|---|
| Inputs | Sector, period, report date, geography, case study, audience, and template status are known. |
| Research | Wide research complete; source register, dates, tiers, and limitations recorded. |
| Evidence | Claim ledger covers all material statements and data. |
| Content | Research data, executive story, and slide specification completed before slide generation. |
| Slides | Five exact titles, required layouts, evidence IDs, and 1LoD implications present. |
| Quality | Content, temporal, language, visual, chart, and export gates pass. |
| Delivery | Private repository resolved or created; artefacts committed and pushed. |
| Closure | Manifest contains repository URL, commit SHA, delivery path, and final status. |

> **Final control:** Do not describe the report or PowerPoint as complete until the operator can point to the exported `.pptx`, the passing `presentation_qc.json`, and the delivery commit recorded in `manifest.json`.

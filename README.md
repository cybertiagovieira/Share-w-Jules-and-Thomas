# Share-w-Jules-and-Thomas
Share w/ Jules and Thomas 

> An evidence-led, end-to-end framework for producing sectorial cyber risk research, executive PowerPoint presentations, quality records, and GitHub-delivered artefacts.

## Repository Purpose

This repository contains the operating documentation, reusable workflow assets, and reference materials needed to configure, run, review, and improve an agentic AI system for sectorial cyber risk analysis.

The system is designed to transform a defined sector, geography, and reporting period into a controlled production package:

```text
Initial request
  -> wide research
  -> evidence pack and claim ledger
  -> structured research data
  -> executive narrative
  -> slide specification
  -> PowerPoint production
  -> quality assurance
  -> private GitHub delivery and run manifest
```

The intended audience is 1LoD operational management and Risk Committee stakeholders. The framework is also suitable for analysts, reviewers, presentation owners, and system operators who need a repeatable process with clear evidence and delivery controls.

## Start Here

| If you are... | Read this first | Then use |
|---|---|---|
| **New to the system** | [Agentic AI System Setup Guide](docs/Agentic_AI_System_Setup_Guide.md) | [Prompt Library and Execution Templates](docs/Prompt_Library_and_Execution_Templates.md) |
| **Running a report or deck** | [Prompt Library and Execution Templates](docs/Prompt_Library_and_Execution_Templates.md) | [End-to-End PowerPoint Creation SOP](docs/SOP_End_to_End_PowerPoint_Creation.md) |
| **Reviewing evidence** | [Evidence and Source Policy](docs/Evidence_and_Source_Policy.md) | Run evidence pack, claim ledger, and final presentation review |
| **Reviewing slide quality or corporate design** | [Presentation Design Specification](docs/Presentation_Design_Specification.md) | [End-to-End PowerPoint Creation SOP](docs/SOP_End_to_End_PowerPoint_Creation.md) |
| **Configuring the platform from scratch** | [Agentic AI System Setup Guide](docs/Agentic_AI_System_Setup_Guide.md) | Create the reusable skill, connect GitHub, and run the first manual test |
| **Maintaining or improving the system** | [Generic End-to-End Agentic AI Blueprint](docs/Generic_End_to_End_Agentic_AI_Blueprint_EN.md) | [Agentic AI Blueprint Improvement Assessment](docs/Agentic_AI_Blueprint_Improvement_Assessment.md) |

## Quick Operational Path

Use this path when the platform, reusable skill, and GitHub connection are already configured.

1. Open a new agent chat.
2. Use a full-workflow prompt from the [Prompt Library](docs/Prompt_Library_and_Execution_Templates.md).
3. Provide the sector, reporting period, report date, geography, and case study title.
4. The agent creates the evidence pack and claim ledger before drafting content.
5. The agent generates exactly five analytical slides and applies the approved presentation design.
6. The agent completes content, temporal, language, visual, export, and delivery checks.
7. The agent creates or reuses the private `cyber-risk-reports` repository and pushes the final run package.

A run is complete only when the PowerPoint file, quality record, manifest, and GitHub commit are all available.

## Repository Structure

Use the following directory structure when organising this repository.

```text
.
├── README.md
├── docs/
│   ├── Agentic_AI_System_Setup_Guide.md
│   ├── SOP_End_to_End_PowerPoint_Creation.md
│   ├── Evidence_and_Source_Policy.md
│   ├── Presentation_Design_Specification.md
│   ├── Prompt_Library_and_Execution_Templates.md
│   ├── Generic_End_to_End_Agentic_AI_Blueprint_EN.md
│   ├── Agentic_AI_Blueprint_Improvement_Assessment.md
│   └── archive/
│       ├── SOP_Stage1_IntelligenceEngine.md
│       ├── SOP_Stage2_VisualGeneration.md
│       ├── SOP_Stage3_EndToEnd_Integration.md
│       ├── SOP_Final_EndToEnd_System.md
│       ├── CyberSectorialAnalysis_Architecture.md
│       ├── CyberAnalysis_UserGuide.md
│       └── Playbook_Melhoria_PowerPoint_Sectorial.md
├── skill/
│   └── cyber-sectorial-analysis.skill
├── templates/
│   ├── corporate-template-reference.pptx
│   └── presentation-design-assets/
├── examples/
│   ├── Cyber_Risk_Analysis_Energy.md
│   ├── example_energy_cyber_evidence.md
│   ├── executive_story.md
│   └── slide_spec.json
└── reports/
    └── {sector-slug}/{report-period}/
        ├── evidence_pack.md
        ├── research_data.json
        ├── report.md
        ├── executive_story.md
        ├── slide_spec.json
        ├── presentation_qc.json
        ├── manifest.json
        └── presentation.pptx
```

The `docs/` directory contains the current operating documentation. The `archive/` folder retains earlier stage documents and original process artefacts for historical reference. The oldest documents can remain in the repository, but the current documents listed in the next section take precedence whenever instructions differ.

## Current Documentation Set

| Document | Status | What it does | Primary users |
|---|---|---|---|
| [Agentic AI System Setup Guide](docs/Agentic_AI_System_Setup_Guide.md) | **Current setup guide** | Configures the whole system from a base account, including GitHub connector, reusable skill, repository, schedule, and first-run test. | System operators and new team members |
| [End-to-End PowerPoint Creation SOP](docs/SOP_End_to_End_PowerPoint_Creation.md) | **Current operating SOP** | Documents the full workflow from initial prompt through research, PowerPoint production, quality assurance, and GitHub upload. | Analysts, operators, reviewers |
| [Evidence and Source Policy](docs/Evidence_and_Source_Policy.md) | **Current evidence standard** | Defines source tiers, temporal relevance, source register, claim ledger, proxy disclosure, non-invention, and review requirements. | Analysts, reviewers, secretariat |
| [Presentation Design Specification](docs/Presentation_Design_Specification.md) | **Current visual standard** | Defines slide titles, colour tokens, typography, L01-L05 layouts, content density, visual restrictions, and review criteria. | Presentation reviewers, communications, template owners |
| [Prompt Library and Execution Templates](docs/Prompt_Library_and_Execution_Templates.md) | **Current operator shortcut** | Provides copy-ready prompts for manual runs, schedules, research-only runs, delivery, recovery, and skill updates. | Any team member running the workflow |
| [Generic End-to-End Agentic AI Blueprint](docs/Generic_End_to_End_Agentic_AI_Blueprint_EN.md) | Reference architecture | Explains the generic architecture, governance, and operating model for agentic AI systems. | Process owners and system designers |
| [Agentic AI Blueprint Improvement Assessment](docs/Agentic_AI_Blueprint_Improvement_Assessment.md) | Improvement roadmap | Identifies maturity enhancements for controls, testing, observability, and operating resilience. | Process owners and maintainers |

## Documentation Precedence

Use the following precedence order when two documents appear to give different instructions.

1. **Current policies and specifications** - Evidence and Source Policy, Presentation Design Specification, and the installed reusable skill.
2. **Current operating documentation** - End-to-End PowerPoint Creation SOP and Prompt Library.
3. **Current setup documentation** - Agentic AI System Setup Guide.
4. **Reference architecture and improvement materials** - Generic blueprint and improvement assessment.
5. **Archived stage documents** - Retained for historical context only.

## Reusable Skill

The operational workflow is packaged as the `cyber-sectorial-analysis` reusable skill. The skill should be added to the agent platform's permanent skill library.

The skill is responsible for:

- Collecting current, source-tiered research.
- Building an evidence pack and claim ledger before narrative drafting.
- Applying temporal relevance and source-quality controls.
- Producing the report, structured research data, executive narrative, and slide specification.
- Generating the five-slide executive presentation.
- Applying language, visual, export, and delivery quality gates.
- Creating or reusing a private `cyber-risk-reports` GitHub repository when no destination is supplied.
- Recording repository URL, commit SHA, paths, and final delivery status in the run manifest.

Store the exported skill package in `skill/`. After a skill update, replace the package and note the change in the release history.

## Presentation Standard

The analytical deck uses exactly the following titles in this order:

1. `Key Threats & Top 5 Cyber Attacks`
2. `Financial Impact: {SECTOR}`
3. `Financial Impact: Worst-Case Scenarios`
4. `Case Study: {CASE_STUDY_TITLE}`
5. `Mitigation Strategies & Security Framework`

The baseline visual system uses a white background, dark text, emerald-green accent `#00915E`, light grey structural rules, and open analytical layouts. The deck does not use rounded cards, shadows, gradients, decorative icons, generic cyber imagery, or web-interface patterns.

See the [Presentation Design Specification](docs/Presentation_Design_Specification.md) for the full L01-L05 master-layout definitions and review checklist.

## Evidence Standard

Every material claim, metric, chart value, case-study statement, regulatory observation, and delivery status must be traceable to a recorded source or execution record.

The standard source-recency order is:

1. Current report year, prioritised by newest publication date.
2. H2 of the preceding year.
3. H1 of the preceding year.
4. Older material only where it provides enduring context, a completed case study, stable legal background, or a comparable benchmark.

The evidence pack must include a source register, limitations, source tiers, temporal classification, and a claim ledger. See the [Evidence and Source Policy](docs/Evidence_and_Source_Policy.md) for the complete reviewer standard.

## First Manual Run

After installing the reusable skill and connecting GitHub, start with a supervised manual run. Copy Template A or Template D from the [Prompt Library](docs/Prompt_Library_and_Execution_Templates.md).

A minimal request is:

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow.

Sector: {SECTOR}
Analysis period: {PERIOD}
Report date: {REPORT_DATE}
Geography: {GEOGRAPHY}
Case study title: {CASE_STUDY_TITLE}

Create or reuse the authenticated GitHub account's private cyber-risk-reports repository.
Deliver the completed run to reports/{SECTOR_SLUG}/{PERIOD}/.
```

The system should return `NEEDS_REVIEW` when a material input, source, quality gate, export check, or delivery condition is missing. This is a controlled stop condition, not a completed run.

## Quality Gates

Do not publish or distribute a presentation until every gate below passes.

| Gate | Release condition |
|---|---|
| **Evidence** | Every material item maps to the evidence pack and claim ledger. |
| **Temporal relevance** | Source use follows the recency policy, with rationale for older material. |
| **Language** | Final text passes the language-control checks configured in the reusable skill. |
| **Visual** | Slide titles, layout, colours, source IDs, legibility, and page boundaries meet the design specification. |
| **Export** | The PPTX opens and matches the completed slide project. |
| **Delivery** | Private repository, artefact paths, commit SHA, and manifest status are confirmed. |

## GitHub Delivery

The default delivery target is the authenticated user's private `cyber-risk-reports` repository. If it does not exist, the workflow provisions it as private. If a different repository is required, provide the full owner and repository URL.

Each completed run should be committed under:

```text
reports/{sector-slug}/{report-period}/
```

Do not claim completion until the repository URL, private visibility, commit SHA, final paths, and run manifest are available.

## Scheduled Runs

The system supports scheduled H1/H2 or other periodic execution. The scheduled task must include the full workflow instruction and the GitHub connector association. Scheduled runs should rebuild their working package from the reusable skill, repository-held templates, and current research. They must not rely on files from an earlier sandbox session.

## Contributing and Change Control

| Change type | Required action |
|---|---|
| Evidence rule or source hierarchy | Update the Evidence and Source Policy and the reusable skill. |
| Slide title, design token, or layout | Update the Presentation Design Specification and the reusable skill. |
| Prompt wording or operating route | Update the Prompt Library. |
| Platform setup, connector, or scheduling change | Update the Agentic AI System Setup Guide and the End-to-End PowerPoint Creation SOP. |
| Skill logic or delivery behaviour | Export and validate a new skill package before replacing the installed version. |

Use pull requests or an equivalent review process for changes to current documents, templates, skills, and system configuration. Retain earlier versions in the Git history or `archive/` directory.

## Suggested Repository Setup

1. Create a private repository named `cyber-risk-reports` or an approved team equivalent.
2. Add this README at the repository root.
3. Create the directory structure shown above.
4. Place the current documents in `docs/`.
5. Place older stage documents in `docs/archive/`.
6. Add the exported reusable skill to `skill/`.
7. Add an approved corporate template to `templates/` only where repository access controls permit it.
8. Run one supervised manual test before enabling scheduled execution.

## Security and Handling

This repository may contain sector analysis, source records, internal interpretations, and presentation outputs. Keep the repository private unless an approved sharing model exists. Do not store secrets, access tokens, confidential source material, or personal data in the repository. Use platform connectors and secret-management facilities for credentials.

## Status Definitions

| Status | Meaning |
|---|---|
| `RELEASE_READY` | Evidence, quality, export, and delivery requirements passed. |
| `RESEARCH_COMPLETE` | Research package is ready for evidence review before presentation production. |
| `NEEDS_REVIEW` | A material requirement remains unresolved. |
| `RECOVERY_COMPLETE` | A failed run was corrected and all downstream checks passed. |

## Maintainer Checklist

| Review period | Required action |
|---|---|
| **Before every report run** | Check the prompt inputs, report date, delivery path, and corporate-template requirement. |
| **After every report run** | Review the manifest, quality record, and GitHub commit. |
| **Quarterly** | Review the source policy, prompts, and skill for changes in reporting needs or platform behaviour. |
| **After a material process change** | Update the relevant document, validate the skill, and record the change in Git history. |

## License and Ownership

Add the applicable team ownership statement, confidentiality classification, licence, and contribution rules before sharing this repository beyond the approved user group.

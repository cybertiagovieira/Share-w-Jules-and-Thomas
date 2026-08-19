# Share with Jules and Thomas
> A documentation set for configuring and operating an evidence-led agentic workflow that produces sectorial cyber risk analysis and executive PowerPoint presentations.

## Repository Scope

This repository currently contains five core documents. Together, they explain how to set up the system, research and assess evidence, create executive slides, apply quality controls, and run the workflow consistently.

The repository is documentation-first. It does not yet include a reusable skill package, corporate PowerPoint template, example report, completed presentation, scheduled-task configuration, or run artefacts.

## Start Here

| If you are... | Read this first | Then read |
|---|---|---|
| **New to the process** | [Agentic AI System Setup Guide](./Agentic_AI_System_Setup_Guide.md) | [Prompt Library and Execution Templates](./Prompt%20Library%20and%20Execution%20Templates.md) |
| **Running a report or presentation** | [Prompt Library and Execution Templates](./Prompt%20Library%20and%20Execution%20Templates.md) | [Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation](./Standard%20Operating%20Procedure%20-%20End-to-End%20Cyber%20Risk%20PowerPoint%20Creation.md) |
| **Reviewing research quality** | [Evidence and Source Policy for Agentic Research Outputs](./Evidence%20and%20Source%20Policy%20for%20Agentic%20Research%20Outputs.md) | [Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation](./Standard%20Operating%20Procedure%20-%20End-to-End%20Cyber%20Risk%20PowerPoint%20Creation.md) |
| **Reviewing presentation quality** | [Presentation Design Specification - Evidence-Led Cyber Risk Decks](./Presentation%20Design%20Specification%20-%20Evidence-Led%20Cyber%20Risk%20Decks.md) | [Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation](./Standard%20Operating%20Procedure%20-%20End-to-End%20Cyber%20Risk%20PowerPoint%20Creation.md) |
| **Setting up the platform from scratch** | [Agentic AI System Setup Guide](./Agentic_AI_System_Setup_Guide.md) | [Prompt Library and Execution Templates](./Prompt%20Library%20and%20Execution%20Templates.md) |

## Core Documentation

| Document | Purpose | Primary users |
|---|---|---|
| [Agentic AI System Setup Guide](./Agentic_AI_System_Setup_Guide.md) | Explains how to configure the system from a base account, including the reusable skill, GitHub connection, repository setup, scheduling, and first manual run. | System operators and new team members |
| [Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation](./Standard%20Operating%20Procedure%20-%20End-to-End%20Cyber%20Risk%20PowerPoint%20Creation.md) | Defines the full process from initial prompt and research through PowerPoint production, quality assurance, export, and GitHub upload. | Analysts, operators, and reviewers |
| [Evidence and Source Policy for Agentic Research Outputs](./Evidence%20and%20Source%20Policy%20for%20Agentic%20Research%20Outputs.md) | Defines source tiers, temporal relevance, evidence packs, claim ledgers, proxy disclosure, and review controls. | Analysts, reviewers, and Risk Committee secretariat |
| [Presentation Design Specification - Evidence-Led Cyber Risk Decks](./Presentation%20Design%20Specification%20-%20Evidence-Led%20Cyber%20Risk%20Decks.md) | Defines page structure, typography, colour system, L01-L05 layouts, visual restrictions, and design review requirements. | Presentation reviewers, corporate communications, and template owners |
| [Prompt Library and Execution Templates](./Prompt%20Library%20and%20Execution%20Templates.md) | Provides copy-ready prompts for manual runs, scheduled runs, research-only work, slide production, quality checks, recovery, GitHub diagnostics, and skill updates. | All team members running the workflow |

## Operating Model

The workflow transforms a defined sector, reporting period, report date, geography, and case study into a controlled output package.

```text
Initial request
  -> wide research
  -> evidence pack and source register
  -> claim ledger
  -> structured research data
  -> executive narrative
  -> slide specification
  -> PowerPoint production
  -> quality assurance
  -> PowerPoint export
  -> GitHub delivery
```

A final presentation should not be described as complete until the evidence, visual, export, and delivery checks have passed.

## Expected Presentation Structure

The process uses five analytical slides in the following sequence:

1. `Key Threats & Top 5 Cyber Attacks`
2. `Financial Impact: {SECTOR}`
3. `Financial Impact: Worst-Case Scenarios`
4. `Case Study: {CASE_STUDY_TITLE}`
5. `Mitigation Strategies & Security Framework`

The baseline design uses a white background, dark text, emerald-green highlights, light-grey structural rules, readable typography, and evidence-led tables, charts, timelines, and scenario chains. See the presentation design specification for the full visual standard.

## Evidence Standard

The evidence standard requires a source register and claim ledger before substantive report or slide drafting. Source use follows this recency order:

1. Current report year, prioritised by newest publication date.
2. H2 of the preceding year.
3. H1 of the preceding year.
4. Older material only where it provides durable context, completed case-study evidence, stable legal background, or a comparable benchmark.

Every material claim, metric, chart value, case-study statement, regulatory observation, and delivery status must be traceable to a source record or execution record.

## Quick Start

1. Read the Agentic AI System Setup Guide.
2. Configure the reusable skill and GitHub connection.
3. Select the full manual execution prompt in the Prompt Library.
4. Replace the sector, period, report date, geography, and case-study placeholders.
5. Run one supervised end-to-end test before enabling scheduled execution.
6. Review the evidence pack, claim ledger, PowerPoint, quality record, and GitHub delivery record.

## Repository Handling

Keep the repository private when it contains internal analysis, source records, operating interpretations, or presentation outputs. Do not store access tokens, passwords, confidential source material, or personal data in the repository.

Use the platform's connector and secret-management capabilities for authentication. The GitHub delivery workflow should create or reuse a private `cyber-risk-reports` repository when no alternative repository is provided.

## Future Additions

The following items may be added later when they are ready for controlled sharing:

| Future item | Intended purpose |
|---|---|
| Reusable skill package | Installs the end-to-end workflow into the agent's permanent skill library. |
| Approved corporate PowerPoint template | Provides exact master layouts, fonts, footer, classification, and visual conventions. |
| Example evidence pack and report | Demonstrates the source register, claim ledger, and structured data model. |
| Example PowerPoint | Demonstrates the five-slide visual output. |
| Scheduled-task configuration | Documents the operating schedule and connector association. |
| Change log | Records updates to the operating rules, design standard, prompts, and skill. |

## Contribution and Change Control

Update the relevant core document whenever a process rule changes.

| Change type | Document to update |
|---|---|
| Evidence hierarchy, source recency, proxy use, or claim traceability | Evidence and Source Policy for Agentic Research Outputs |
| Slide titles, design tokens, layout, or visual review criteria | Presentation Design Specification - Evidence-Led Cyber Risk Decks |
| Prompt wording, delivery route, recovery, or scheduling request | Prompt Library and Execution Templates |
| Platform configuration, skill installation, GitHub connection, or first-run process | Agentic AI System Setup Guide |
| Full workflow sequence, quality gates, export, or delivery process | Standard Operating Procedure - End-to-End Cyber Risk PowerPoint Creation |

Review changes before merging them into the repository. Keep a clear commit message that states what changed and why.

## Status Definitions

| Status | Meaning |
|---|---|
| `RESEARCH_COMPLETE` | Research package is ready for evidence review before presentation production. |
| `RELEASE_READY` | Evidence, quality, export, and delivery requirements passed. |
| `NEEDS_REVIEW` | A material input, evidence requirement, quality gate, export, or delivery condition remains unresolved. |
| `RECOVERY_COMPLETE` | A failed run was corrected and all downstream checks passed. |

## Ownership

Add the applicable team ownership statement, confidentiality classification, licence, and contribution rules before sharing the repository beyond the approved user group.

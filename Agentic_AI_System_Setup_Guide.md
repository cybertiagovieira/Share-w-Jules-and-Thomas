# End-to-End Agentic AI System Setup Guide

| Document field | Value |
|---|---|
| **Purpose** | Provide a comprehensive guide for configuring an end-to-end agentic AI workflow from scratch. It covers skill creation, GitHub connector setup, automated repository provisioning, scheduling, and execution. |
| **Primary audience** | Agent operators, AI system administrators, and risk intelligence practitioners. |
| **Output language** | English (US) |
| **Version** | 1.0 |

## 1. Quick-Start Summary

For experienced operators familiar with agentic platforms, complete these steps to deploy the system.

1. **Connect GitHub:** Run `gh auth login` in the agent environment or configure a Personal Access Token. Enable the GitHub connector in the platform's configuration manager.
2. **Create the reusable skill:** Use the platform's skill-creation tool (e.g., `/skill-creator`) to package the cyber-sectorial-analysis workflow. Include the execution rules, evidence hierarchy, design tokens, and the GitHub delivery policy.
3. **Save the skill:** Instruct the agent to export the skill package and add it to your permanent skill library.
4. **Configure scheduling:** Use the platform's scheduling manager to create a recurring task (e.g., `H1/H2` runs). Bind the GitHub connector UID to the scheduled task.
5. **Run the first execution:** Trigger the workflow manually. Provide the sector, period, report date, and geography. The agent will automatically provision the private `cyber-risk-reports` repository, conduct research, generate the PowerPoint, and push the final package.

## 2. Introduction and System Architecture

This guide explains how to take a base AI agent account (such as Manus) and configure it into a fully autonomous production system. The resulting system can conduct deep research, synthesise executive narratives, generate compliant PowerPoint presentations, and deliver them to a private version-controlled repository without human intervention.

The architecture relies on three pillars:
- **Durable procedural knowledge:** A reusable skill that persists the workflow, quality gates, and design rules across ephemeral sandbox sessions.
- **Authenticated delivery:** A configured GitHub connector that allows the agent to provision repositories and commit artefacts.
- **Orchestration:** Scheduled or manual triggers that execute the complete pipeline deterministically.

## 3. Step 1: GitHub Connector Authentication

The agent requires authenticated access to deliver final artefacts. Because agent sandboxes are ephemeral, the authentication state must be managed at the platform level.

### 3.1 Interactive authentication

1. Open a new chat session with the agent.
2. Issue the command: `Authenticate GitHub using the gh auth login command.`
3. The agent will execute the command and return an 8-character device code (e.g., `ABCD-1234`) and a login URL.
4. Open the URL in your local browser, enter the device code, and authorise the application.
5. Return to the chat and instruct the agent to confirm the authentication status.

### 3.2 Connector activation

Even when authenticated, the platform may require the connector to be explicitly enabled for automated runs.

1. Instruct the agent: `Check the platform configuration for the GitHub connector and ensure it is enabled.`
2. The agent will read the configuration (e.g., using `manus-config`), locate the GitHub entry, and set `enabled: true`.
3. The agent must save the configuration. The platform will typically prompt you to approve this change.

## 4. Step 2: Creating the Reusable Skill

A reusable skill transforms the agent from a general-purpose assistant into a specialised production engine. It ensures every execution follows the same rules for evidence, language, design, and delivery.

### 4.1 Initialise the skill structure

1. Open a new chat session.
2. Instruct the agent: `Use the skill-creator to initialise a new skill named cyber-sectorial-analysis.`
3. The agent will create a directory structure containing the main instruction file (`SKILL.md`) and folders for templates and references.

### 4.2 Define the execution rules

Instruct the agent to populate `SKILL.md` with the following mandatory sections:

*   **Required inputs:** Define `SECTOR`, `PERIOD`, `REPORT_DATE`, `GEOGRAPHY`, and `CASE_STUDY_TITLE`.
*   **Language controls:** Prohibit specific adjectives (e.g., serious, critical, extreme, verified) and enforce precise, evidence-led phrasing.
*   **Evidence workflow:** Define the source-recency order, source-tier hierarchy, and the requirement to build a claim ledger before drafting.
*   **Slide specification:** Fix the five mandatory analytical slide titles and the requirement for an executive conclusion on each page.
*   **Quality gates:** Define blocking checks for content, temporal relevance, language, visual rendering, export success, and delivery confirmation.

### 4.3 Add the GitHub delivery policy

The skill must contain instructions for automated repository provisioning. Instruct the agent to create a template file (e.g., `templates/github_delivery_policy.yaml`) with the following rules:

1. If no destination is provided, resolve the authenticated user's private repository named `cyber-risk-reports`.
2. If the repository does not exist, create it as a private repository using the GitHub CLI.
3. Confirm the full URL and private visibility before proceeding.
4. Commit only artefacts that have passed all quality gates.
5. Record the repository URL, commit SHA, and delivery path in the run manifest.

### 4.4 Save and install the skill

1. Instruct the agent: `Validate the cyber-sectorial-analysis skill and deliver the final package.`
2. The agent will run its internal validation script and present the skill as a downloadable card or attachment.
3. Click **Add to My Skills** (or the platform equivalent) to save it to your permanent library.

## 5. Step 3: Configuring Scheduled Execution

To run the analysis automatically (e.g., semi-annually), you must configure a scheduled task and bind the GitHub connector to it.

1. Open a new chat session.
2. Instruct the agent: `Create a scheduled task to run the cyber-sectorial-analysis workflow semi-annually (on 1 January and 1 July).`
3. Provide the required inputs for the scheduled run (e.g., `Sector: Energy and Utilities`, `Geography: European Union`).
4. **Crucial step:** Instruct the agent to associate the GitHub connector UID with the scheduled task. Without this association, the scheduled sandbox will not inherit the authentication state.
5. The agent will use the platform's scheduling utility (e.g., `manus-config schedule update`) to register the task, the playbook, and the connector binding.

## 6. Step 4: First-Run Execution and Validation

It is essential to validate the end-to-end system manually before relying on scheduled execution.

1. Open a new chat session.
2. Issue the execution command:

```text
Use the cyber-sectorial-analysis skill to run the full end-to-end workflow.

Sector: European Healthcare
Analysis period: H2 2026
Report date: 31 October 2026
Geography: European Union
Case study title: Change Healthcare Ransomware Event

Create or reuse the authenticated GitHub account's private cyber-risk-reports repository.
Deliver the completed run to reports/European-Healthcare/2026-H2/.
```

3. Monitor the agent's progress. It should sequentially produce the evidence pack, structured research data, executive narrative, slide specification, and the final PowerPoint.
4. Verify that the agent executes the quality gates and provisions the private GitHub repository.
5. Upon completion, navigate to your GitHub account. Confirm that the `cyber-risk-reports` repository exists, is private, and contains the complete run package including the `.pptx` file.

## 7. Maintenance and Continuous Improvement

As reporting requirements evolve, you can update the system without rebuilding it from scratch.

*   **Updating rules:** Open a new chat, attach the existing skill, and instruct the agent to update specific sections (e.g., `Add a new mandatory slide layout for regulatory mapping`). Validate and save the updated skill to your library.
*   **Adding corporate templates:** Attach an approved corporate `.pptx` file in a chat and instruct the agent to extract its master layouts, fonts, and colours into the skill's design system.
*   **Managing failures:** If a run fails due to missing evidence or repository access issues, the agent is programmed to halt and return a `NEEDS_REVIEW` status. Review the run manifest, correct the underlying issue (e.g., reauthorise GitHub), and trigger a new run.

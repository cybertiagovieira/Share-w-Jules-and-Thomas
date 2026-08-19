# Evidence and Source Policy for Agentic Research Outputs

| Policy field | Requirement |
|---|---|
| **Purpose** | Establish the minimum evidence, source-quality, temporal relevance, traceability, and disclosure standards for research outputs produced by people or AI agents. |
| **Applies to** | Sector reports, executive presentations, evidence packs, quantitative charts, case studies, regulatory mappings, and delivery manifests. |
| **Primary users** | Analysts, reviewers, Risk Committee secretariat, presentation owners, and agent operators. |
| **Default output language** | English (US), unless a specific request requires another language. |
| **Evidence cut-off** | The report date specified in the execution request. |

## 1. Policy objective

This policy ensures that every material conclusion in a report or presentation can be traced to a source, evaluated for reliability, assessed for temporal relevance, and understood within its limitations. It enables a reviewer to challenge an AI-produced output without needing to reconstruct the entire research process.

> **Policy rule:** A source is not evidence merely because it is recent, well written, or widely circulated. It becomes usable evidence only when its authority, scope, date, methodology, and relevance to the claim are recorded.

## 2. Core principles

| Principle | Operating rule |
|---|---|
| **Traceability** | Link every material claim, number, date, event, regulatory statement, chart value, and case-study statement to one or more source IDs. |
| **Source fitness** | Select the source that is fit for the exact claim, not simply the highest-ranked source available. |
| **Temporal relevance** | Use the newest reliable source available for current threat activity, regulation, technology, and market conditions. |
| **Scope accuracy** | State the sector, geography, population, period, and methodology limits of the evidence. |
| **Non-invention** | Do not create values, dates, attribution, causal links, scenarios, or regulatory requirements that are not supported by recorded evidence. |
| **Transparent uncertainty** | Label estimates, proxies, assumptions, and incomplete information. |
| **Independence** | Do not allow a preselected narrative or desired recommendation to determine which facts are selected. |

## 3. Evidence classification

### 3.1 Source tiers

| Tier | Source characteristics | Permitted use | Examples |
|---|---|---|---|
| **Tier 1** | Official, statutory, regulator, law-enforcement, victim disclosure, government body, or institution with transparent methodology. | Material claims, financial data, legal requirements, event timelines, and primary incident facts. | Official regulator pages, legislation, court filings, company disclosures, CISA advisories, ENISA publications. |
| **Tier 2** | Independent research with disclosed methodology, identifiable sample, clear time period, and traceable underlying evidence. | Benchmarks, trend analysis, comparative context, and corroboration. | Research reports with methodology sections and cited data sources. |
| **Tier 3** | Reputable secondary reporting, commentary, or analyst interpretation. | Context, lead generation, or corroboration. Do not use as the sole support for a material assertion. | Quality journalism, expert commentary, and conference summaries. |
| **Unacceptable** | Anonymous content, unverifiable screenshots, claims without source links, promotional material without methodology, or data with unknown origin. | Do not use as evidence. | Unattributed social-media claims, unsourced charts, copied text without origin. |

### 3.2 Source selection rule

A Tier 1 source is preferred for a fact that it directly supports. A Tier 2 source may be appropriate for a benchmark when no Tier 1 source publishes comparable data. A Tier 3 source can identify a lead but requires corroboration before it supports a material report statement.

## 4. Temporal relevance policy

### 4.1 Recency order

Set the evidence cut-off equal to the report date. Rank candidate sources in this order before drafting findings.

| Priority | Publication period | Use in analysis |
|---|---|---|
| **1** | Current report year, ordered by newest publication date | Primary evidence base for active threat patterns, incident developments, current regulations, technology changes, and market benchmarks. |
| **2** | H2 of the preceding year | Supporting contemporary evidence and trend continuity. |
| **3** | H1 of the preceding year | Supporting context where more recent evidence is unavailable. |
| **4** | More than 18 months old | Use only for historical events, completed case studies, stable legal background, longitudinal comparison, or enduring sector context. |

For an H2 2026 report, sources from 2026 should drive the assessment. Sources from H2 2025 follow, then H1 2025. Earlier material requires a written continuing-relevance rationale.

### 4.2 Current-source rule

Use current evidence for the following subjects wherever possible: threat activity, attack methods, victim impacts, regulatory implementation status, market benchmarks, AI or technology developments, and supplier exposure. Do not use old reports to describe a current threat landscape if newer reliable material exists.

### 4.3 Historical-source rule

Label a source more than 18 months old as either `contextual` or `historical`. State why it remains relevant. A completed case study may remain useful when its documented control failure and operating consequence are transferable to the sector under review.

## 5. Source register requirements

Create the source register before drafting substantive findings. Assign each source a unique identifier such as `S01`.

| Field | Mandatory content |
|---|---|
| `source_id` | Unique ID, for example `S01`. |
| `title` | Exact title of the source. |
| `publisher` | Issuing entity. |
| `url` | Permanent or stable source location where available. |
| `publication_date` | Date the source was published or updated. |
| `access_date` | Date the analyst or agent accessed it. |
| `reporting_period` | Period covered by the facts or data. |
| `geography` | Geography to which the information applies. |
| `sector_scope` | Sector or subsector applicability. |
| `source_tier` | Tier 1, Tier 2, Tier 3, or unacceptable. |
| `temporal_status` | Current-year, H2 preceding year, H1 preceding year, contextual, or historical. |
| `methodology_or_basis` | Sample, disclosure basis, legal status, research method, or data-collection method. |
| `facts_used` | Exact facts or metrics permitted for use. |
| `limitations` | Scope, comparability, data quality, or methodology constraints. |

### 5.1 Source-register template

| ID | Publisher | Publication date | Tier | Temporal status | Facts approved for use | Limitations |
|---|---|---:|---|---|---|---|
| S01 | {PUBLISHER} | {YYYY-MM-DD} | Tier 1 | Current-year | {FACT OR METRIC} | {LIMITATION} |

## 6. Claim ledger requirements

Create a claim ledger after the source register and before report or slide drafting. The ledger is the control point between raw research and final language.

| Field | Mandatory content |
|---|---|
| `claim_id` | Unique identifier such as `C01`. |
| `claim_text` | Exact proposed wording. |
| `claim_type` | Observed fact, metric, regulatory requirement, control recommendation, assessment, or scenario assumption. |
| `source_ids` | One or more source register IDs. |
| `locator` | Page, paragraph, table, section, timestamp, or URL anchor. |
| `date_or_period` | Date or period supported by the source. |
| `scope` | Geography, sector, organisation type, and population where relevant. |
| `limitations` | Qualification, proxy status, comparability, or uncertainty. |
| `intended_use` | Report section, slide number, chart, source note, or speaker note. |
| `review_status` | Approved, revise, remove, or needs review. |

### 6.1 Claim classification

| Claim type | Required wording control |
|---|---|
| **Observed fact** | State only what the source directly establishes. |
| **Metric** | State value, unit, period, geography, sample or population, and source limitation where material. |
| **Assessment** | Use clear analytical wording and identify the evidence basis. Do not represent the assessment as an observed fact. |
| **Scenario assumption** | Identify it as a planning scenario and state the source-supported mechanism. |
| **Control recommendation** | Link the control to the threat, operating objective, and authoritative guidance where available. |
| **Regulatory statement** | Use the primary legal or regulator source and identify jurisdiction and applicability. |

## 7. Quantitative metric policy

A quantitative metric may be used only when its definition and comparability are understood.

| Control | Requirement |
|---|---|
| **Definition** | Record what the metric measures. |
| **Unit** | Record currency, percentage, duration, count, or ratio. |
| **Time period** | Record the measurement period and publication date. |
| **Population** | Record sector, geography, sample size, organisation type, or dataset. |
| **Methodology** | Record the calculation basis or study method if disclosed. |
| **Comparability** | Compare only metrics with compatible definitions, populations, units, and periods. |
| **Visualisation** | Include the source ID and methodology note when a chart uses a proxy, global sample, or cross-sector benchmark. |

### 7.1 Proxy disclosure

Use a proxy only when a sector-specific measure is unavailable and the proxy materially improves decision understanding. Label the proxy in the body of the chart or source note. State why it was selected and where comparability is limited.

> **Example:** “Global cross-sector benchmark used as a proxy because no current EU energy-sector estimate was identified. Scope differs from the target population.”

Do not aggregate unrelated sources into a new average. Do not infer a financial effect, risk reduction, return on investment, or probability from a general benchmark.

## 8. Case-study evidence standard

A case study should demonstrate a transferable control lesson, not simply describe an incident. Record the event profile, initial access or failure mechanism where supported, chronological milestones, operating consequence, confirmed financial or regulatory consequence, and transferable control lessons.

| Case-study field | Evidence requirement |
|---|---|
| Event identity | Source from the organisation, regulator, law-enforcement, or corroborated authoritative reporting. |
| Date and timeline | Link each material date or milestone to a source. |
| Cause and control failure | State only what the evidence supports. Distinguish causation from correlation. |
| Financial consequence | Separate confirmed values from estimates. |
| Operational consequence | Describe service interruption, recovery effort, or decision impact where sourced. |
| Transferable lesson | Link to a control, process, or operating dependency relevant to the target sector. |

## 9. Scenario evidence standard

Scenarios are planning tools, not forecasts. Each scenario must contain a trigger, exposed dependency, propagation path, plausible operating impact, and control assumption. The scenario must reference evidence for the mechanism, even when no numerical probability or loss value is available.

| Scenario element | Minimum standard |
|---|---|
| Trigger | Evidence-supported attack pattern or failure event. |
| Dependency | Sector process, technology, supplier, facility, or information dependency. |
| Propagation | Explain the causal chain from compromise to operating impact. |
| Consequence | Use source-supported impact drivers. Avoid unsupported exact loss values. |
| Assumptions | State assumptions and distinguish them from observed facts. |
| Source linkage | Identify source IDs supporting the scenario mechanism. |

## 10. Non-invention policy

The following actions are prohibited.

1. Creating a metric, date, financial loss, recovery duration, regulatory fine, percentage, attribution, or source citation that does not exist in the source register.
2. Converting an unsourced general observation into a sector-specific statement.
3. Presenting a proxy as a direct sector measure.
4. Presenting a scenario as an observed event or predicted outcome.
5. Treating a media report as the only source for a material claim when an authoritative primary source is obtainable.
6. Inferring a causal relationship when the evidence records only timing or association.
7. Claiming a delivery, approval, quality check, or system action without execution evidence.

If a material item cannot be supported, remove it, reframe it as a limitation, request further evidence, or return `NEEDS_REVIEW`.

## 11. Evidence conflict resolution

When sources disagree, do not select the result that best supports the desired narrative. Assess the conflict using the following order.

| Assessment factor | Question |
|---|---|
| Authority | Which source is closest to the original event, data, or legal requirement? |
| Methodology | Which source discloses a reliable collection and calculation method? |
| Scope | Which source best matches the sector, geography, organisation type, and period? |
| Recency | Which source best reflects the report cut-off date? |
| Precision | Which source provides the exact fact being claimed? |
| Independence | Is the source affected by commercial, legal, or self-reporting incentives? |

Record the conflict and resolution in the evidence pack when it affects a material claim.

## 12. Citation and presentation rules

Use concise source IDs such as `[S01]` next to material claims or in slide footers. Do not place long URLs in the main body of an executive slide. Keep full source details in the evidence pack and map every source ID to the claim ledger.

Charts must display the source ID, title, unit, measurement period, and methodology note where necessary. A slide source ID does not replace the requirement to retain a complete source record in the evidence pack.

## 13. Review and approval controls

| Review stage | Reviewer test | Pass condition |
|---|---|---|
| **Source review** | Assess source tier, date, scope, and limitation. | All sources meet the policy or are restricted to permitted context use. |
| **Claim review** | Check claim wording against the source locator. | Each material claim is accurately stated and traceable. |
| **Metric review** | Check definition, unit, period, geography, and comparability. | Metric is suitable for use or labelled as a proxy. |
| **Scenario review** | Check evidence basis and assumption label. | Scenario is not represented as fact or forecast. |
| **Presentation review** | Check source IDs on relevant slides and charts. | Executive output preserves traceability without excessive citation text. |
| **Final review** | Check evidence pack, claim ledger, and final deck together. | No material output content is absent from the traceability record. |

## 14. Exception and escalation process

Return `NEEDS_REVIEW` when a material claim, metric, case study, regulatory position, or delivery statement cannot meet this policy. State the failed policy requirement, affected artefact, available evidence, and the action needed to resume.

| Failure condition | Required action |
|---|---|
| No current reliable evidence for a required theme | Narrow the claim, use a labelled historical context source, or request a different scope. |
| No comparable financial metric | Remove the comparison or use a proxy with explicit disclosure. |
| Source date is unknown | Do not treat it as current evidence. Use only as non-material context if source quality permits. |
| Regulatory applicability is unclear | Cite the primary regulator text, identify the jurisdiction, and request legal or compliance review where required. |
| Case study lacks authoritative detail | Use it only as contextual background or select another case. |

## 15. Reviewer checklist

| Question | Yes / No |
|---|---|
| Is the report date and evidence cut-off recorded? |  |
| Does every source have publication date, tier, scope, and limitation? |  |
| Does the source register follow the temporal relevance order? |  |
| Is every material claim in the claim ledger? |  |
| Are proxy metrics visibly labelled? |  |
| Are scenarios identified as scenarios and linked to evidence? |  |
| Are financial values and dates directly supported by cited sources? |  |
| Are material source conflicts documented? |  |
| Do slides and charts show concise source IDs? |  |
| Does the final deck match the evidence pack and claim ledger? |  |

## 16. Required retained artefacts

Retain the evidence pack, source register, claim ledger, structured research data, report, slide specification, final presentation, quality record, and run manifest in the delivery repository. These artefacts allow an analyst, reviewer, or secretariat member to reconstruct the evidential basis of the final output without access to the original chat.

# Presentation Design Specification - Evidence-Led Cyber Risk Decks

| Specification field | Standard |
|---|---|
| **Purpose** | Define the visual system, page architecture, layout masters, typography, and review controls for executive cyber risk presentations. |
| **Applies to** | Five-slide analytical sector reports and optional corporate cover slides. |
| **Primary users** | Presentation reviewers, corporate communications, template owners, analysts, and AI presentation agents. |
| **Default audience** | 1LoD operational management and Risk Committee. |
| **Design objective** | Deliver decision-oriented, information-dense, evidence-led pages that look like a corporate analytical pack rather than a consumer web interface. |

## 1. Design intent

The presentation must support senior decision-making. It should not resemble a document pasted onto slides, a generic infographic, or a software dashboard. Each page must use structure, type, alignment, and evidence to make one decision-oriented message clear.

> **Design rule:** The visual hierarchy must make the executive conclusion visible first, the supporting evidence visible second, and the source trail available without distracting from the decision.

## 2. Required page set

The analytical presentation contains five pages in this exact sequence. A corporate cover is added only when the approved template requires one.

| Page | Fixed title | Page purpose | Master layout |
|---|---|---|---|
| **1** | `Key Threats & Top 5 Cyber Attacks` | Show the leading threat patterns, sector dependencies, operational vulnerabilities, and material impact paths. | `L01_Threat_Matrix` |
| **2** | `Financial Impact: {SECTOR}` | Show financial and operational benchmarks with clear methodology limits. | `L02_Metrics_Charts` |
| **3** | `Financial Impact: Worst-Case Scenarios` | Show three plausible impact pathways and the resilience assumptions that affect them. | `L03_Scenario_Triptych` |
| **4** | `Case Study: {CASE_STUDY_TITLE}` | Show a real event, control failure, operating consequence, and transferable lessons. | `L04_Case_Timeline` |
| **5** | `Mitigation Strategies & Security Framework` | Show controls, regulatory mapping, implementation roadmap, and a management decision request. | `L05_Control_Roadmap` |

## 3. Canvas and geometry

| Element | Standard |
|---|---|
| **Aspect ratio** | 16:9 widescreen. |
| **Working canvas** | 1280 x 720 px or equivalent PowerPoint widescreen size. |
| **Background** | Solid white. |
| **Outer margins** | 48 to 60 px on left and right. Maintain the same visual margins on all analytical pages. |
| **Vertical rhythm** | Use a title zone, a main evidence zone, and a source or decision zone. |
| **Alignment** | Align text baselines, rules, charts, and visual anchors to a shared grid. |
| **Spacing principle** | Use whitespace to separate concepts, not decorative boxes. |

## 4. Colour system

Use only the following baseline palette unless the approved corporate template provides a different authorised palette.

| Role | Colour | Use |
|---|---|---|
| **Canvas** | `#FFFFFF` | Full page background. |
| **Primary text** | `#171717` | Main headings, body copy, labels, and structural text. |
| **Accent** | `#00915E` | Section labels, executive metrics, selected data points, priority labels, and decision calls. |
| **Secondary text** | `#6B7280` | Methodology notes, source notes, secondary labels, and non-primary annotations. |
| **Structural rule** | `#D1D5DB` | Dividers, table rules, chart gridlines, and timeline tracks. |
| **Light fill** | `#F3F4F6` | Reserved for a minimal methodology label or neutral emphasis band when necessary. |

Use emerald green sparingly. It is an attention signal, not a substitute for a full severity colour scale. Do not add red, amber, or decorative accent colours unless the corporate design system explicitly requires them.

## 5. Typography

Use the approved corporate font when supplied. If no corporate font is available, use Arial or Inter as a fallback. Maintain a strong type hierarchy.

| Text role | Size and style | Usage standard |
|---|---|---|
| **Eyebrow / section label** | 10 to 12 pt, uppercase, tracked, bold | Sector, period, or page category. |
| **Slide title** | 34 to 42 pt, bold, maximum two lines | Fixed page title. |
| **Executive conclusion** | 18 to 24 pt, bold | The most important decision message on the page. |
| **Subheading** | 14 to 18 pt, bold | Content-zone hierarchy. |
| **Body text** | 14 to 18 pt, regular | Evidence explanation and operating implication. |
| **Table / chart label** | 11 to 14 pt | Maintain legibility at presentation distance. |
| **Source note** | 8 to 10 pt | Use source IDs and concise methodology notes. |

Avoid more than three type weights on a page. Do not use condensed text to fit content. If the content does not fit at readable size, reduce the content, split the topic, or redesign the layout.

## 6. Information-density standard

The deck is deliberately information-dense. Density must remain controlled through hierarchy and evidence selection.

| Content element | Target per slide | Design control |
|---|---:|---|
| Executive conclusion | 1 | Place at the top, immediately below the slide title. |
| Main evidence items | 3 to 5 | Use a table, chart, timeline, or scenario chain. |
| Supporting implications | 1 to 3 | Use direct operational language. |
| Source IDs | As needed | Keep concise and aligned to the associated fact or footer. |
| Charts | 0 to 2 | Use only where numeric evidence exists. |
| Decorative images | 0 | Omit unless an image is itself evidence. |

A presentation slide is complete when it can be read as a decision page: conclusion, evidence, implication, and source trail.

## 7. Visual prohibitions

The following visual patterns are not permitted in analytical pages.

| Prohibited pattern | Reason |
|---|---|
| Rounded cards or containers | Creates a consumer application appearance and fragments the analytical page. |
| Drop shadows | Adds decoration without supporting information hierarchy. |
| Gradients | Weakens the corporate analytical style. |
| Stock photography or generic cyber imagery | Consumes space without adding evidence. |
| Decorative icons | Do not use unless the icon is necessary to interpret a data model. |
| Web-interface widgets | Avoid tabs, badges, hover states, button-like elements, and dashboard chrome. |
| Animations or transitions | The deck is a static decision artefact. |
| Dense source URLs on the page body | Use source IDs and retain full links in the evidence pack. |
| Unsupported charts | Do not display a chart when a numeric source series is absent. |

## 8. Shared page anatomy

Every analytical page uses the same basic hierarchy while varying the content structure.

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ [A] Eyebrow: Sector | Period | Page category                                │
│ [B] Fixed slide title                                                        │
│ [C] Executive conclusion                                                     │
│ ─────────── accent rule ─────────────────────────────────────────────────── │
│ [D] Primary evidence zone                                                    │
│ [E] 1LoD implication or decision request                                     │
│ [F] Source IDs and methodology note                                          │
└─────────────────────────────────────────────────────────────────────────────┘
```

| Annotation | Role | Review question |
|---|---|---|
| **A** | Provide orientation without competing with the title. | Does it state sector, period, or page type concisely? |
| **B** | Use the required page title. | Is the title exact and readable? |
| **C** | State the decision-oriented conclusion. | Can a senior reader understand the page point in one sentence? |
| **D** | Display evidence through the relevant layout master. | Does every visual element support the conclusion? |
| **E** | Convert evidence into an operating implication or requested decision. | Does it identify an action, dependency, or risk appetite issue? |
| **F** | Preserve traceability and limitations. | Can the page be traced back to the evidence pack? |

## 9. Layout master L01 - Threat Matrix

### 9.1 Purpose

Use `L01_Threat_Matrix` for Page 1. It compares five threat patterns with the operating vulnerabilities and dependencies that enable them.

### 9.2 Layout structure

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Title and executive conclusion                                               │
├───────────────────────────────────────┬─────────────────────────────────────┤
│ [A] Five-row threat matrix             │ [B] Operational vulnerability panel │
│ 01 Threat | exposure | impact | [Sxx]  │ Legacy operating estate              │
│ 02 Threat | exposure | impact | [Sxx]  │ IT/OT or digital dependencies         │
│ 03 Threat | exposure | impact | [Sxx]  │ Supplier and concentration exposure   │
│ 04 Threat | exposure | impact | [Sxx]  │ Service continuity consequence         │
│ 05 Threat | exposure | impact | [Sxx]  │                                     │
├───────────────────────────────────────┴─────────────────────────────────────┤
│ 1LoD implication                                              Sources        │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 9.3 Content rules

| Zone | Required content | Design rule |
|---|---|---|
| **A** | Five threats, exposed process or asset, operating vulnerability, material impact, and source ID. | Use horizontal 1 px rules. Do not turn each threat into a card. |
| **B** | Three to four sector dependencies or concentration points. | Use an open text panel separated by one vertical rule. |
| **Footer** | One operating implication and short source note. | Keep the implication left-aligned and source note right-aligned. |

## 10. Layout master L02 - Metrics and Charts

### 10.1 Purpose

Use `L02_Metrics_Charts` for Page 2. It communicates the scale and drivers of financial or operating impact using only comparable evidence.

### 10.2 Layout structure

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Title and executive conclusion                                               │
├───────────────────────┬─────────────────────────────────────────────────────┤
│ [A] Hero metric        │ [B] Main chart                                      │
│ $X.Xm                  │ Comparable cost, duration, or trend series          │
│ Unit and scope         │ Unit, period, source ID, methodology note           │
│ Limitation note        │                                                     │
├───────────────────────┴─────────────────────────────────────────────────────┤
│ [C] Two or three contextual indicators with concise interpretation           │
├─────────────────────────────────────────────────────────────────────────────┤
│ 1LoD implication                                              Sources        │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 10.3 Chart rules

| Requirement | Standard |
|---|---|
| **Chart types** | Bar, stacked bar, waterfall, line, or dot plot when suitable to the evidence. |
| **Data source** | Each value must originate from the structured research data. |
| **Axes and units** | Display units, time period, and scope. |
| **Colour use** | Use emerald green for the focal series and grey for comparator series. |
| **Methodology** | State proxy, global sample, non-sector data, or comparability constraints. |
| **Legend** | Use only when more than one series needs identification. |
| **No data case** | Use an evidence-led comparison table or narrative. Do not fabricate a chart. |

## 11. Layout master L03 - Scenario Triptych

### 11.1 Purpose

Use `L03_Scenario_Triptych` for Page 3. It shows three plausible pathways from initiating event to operating impact.

### 11.2 Layout structure

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Title and executive conclusion                                               │
├───────────────────┬───────────────────┬─────────────────────────────────────┤
│ [A] Scenario 01   │ [B] Scenario 02   │ [C] Scenario 03                     │
│ Trigger           │ Trigger           │ Trigger                             │
│ Propagation       │ Propagation       │ Propagation                         │
│ Consequence       │ Consequence       │ Consequence                         │
│ 1LoD control      │ 1LoD control      │ 1LoD control                        │
│ [Sxx]             │ [Sxx]             │ [Sxx]                               │
├───────────────────┴───────────────────┴─────────────────────────────────────┤
│ Risk appetite question and sources                                           │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 11.3 Content rules

Each column must identify a scenario as a planning scenario. Use a visible sequence: trigger, propagation, operating consequence, and control. Separate columns with vertical rules. Do not use numerical probability or loss figures unless supported by source data and methodology.

## 12. Layout master L04 - Case Timeline

### 12.1 Purpose

Use `L04_Case_Timeline` for Page 4. It converts a completed event into a transferable operating lesson.

### 12.2 Layout structure

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Title and executive conclusion                                               │
├───────────────────────┬─────────────────────────────────────────────────────┤
│ [A] Event profile      │ [B] Dated timeline                                  │
│ Organisation / event   │ • Initial access or event trigger                   │
│ Control failure        │ • Detection or operating decision                   │
│ Operating consequence  │ • Service or process interruption                    │
│ Lessons                │ • Recovery and disclosed consequence                │
│ [Sxx]                  │ • Transferable lesson                                │
├───────────────────────┴─────────────────────────────────────────────────────┤
│ 1LoD implication                                              Sources        │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 12.3 Content rules

Use 40 percent of the page for the event profile and 60 percent for the timeline. Timeline dates require source IDs. Separate confirmed impact from estimates. Place the transferable lesson in the profile area or final milestone, not as a detached card.

## 13. Layout master L05 - Control Roadmap

### 13.1 Purpose

Use `L05_Control_Roadmap` for Page 5. It transforms the analysis into prioritised management actions.

### 13.2 Layout structure

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Title and executive conclusion                                               │
├─────────────────────────────────────────────────────────────────────────────┤
│ [A] Control matrix: control | threat addressed | operating objective | rule  │
│     1. Control and source                                                     │
│     2. Control and source                                                     │
│     3. Control and source                                                     │
├─────────────────────────────────────────────────────────────────────────────┤
│ [B] 90 days              [C] 180 days              [D] 365 days              │
│     Immediate actions        Operating tests            Integrated maturity  │
├─────────────────────────────────────────────────────────────────────────────┤
│ Management decision request                                   Sources         │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 13.3 Content rules

| Zone | Required content | Design rule |
|---|---|---|
| **A** | Three to seven controls, threat addressed, operating objective, and regulatory or policy mapping. | Use a continuous matrix with rules, not detached boxes. |
| **B-D** | 90, 180, and 365-day actions. | Use three aligned columns separated by vertical rules. |
| **Footer** | Explicit management decision request. | Use emerald green for the decision lead-in only. |

## 14. Corporate-template adaptation procedure

When an approved corporate PowerPoint template is supplied, review it before designing the deck. Extract the items below into a design handoff record.

| Template item | Record and apply |
|---|---|
| Slide master and layouts | Use approved page masters, placeholders, and geometry. |
| Typeface | Use font family, weights, sizes, and fallback. |
| Header and footer | Use the authorised logo placement, classification, date, slide number, and confidentiality text. |
| Colour system | Map corporate colours to the roles defined in Section 4. |
| Chart conventions | Use approved chart colours, gridlines, source note format, and legend position. |
| Cover page | Use only where required and keep analytical content outside the cover. |
| Accessibility | Apply approved contrast, font size, reading order, and colour-independence rules. |

Do not infer a full brand system from one colour. If the template is unavailable, use the default system in this specification and record that the corporate template was not applied.

## 15. Build instructions for AI agents and designers

1. Read the evidence pack, structured research data, executive narrative, slide specification, and design handoff before creating any page.
2. Select the correct layout master for the page. Do not replace it with a generic template.
3. Create the page title and executive conclusion first.
4. Place the evidence model next: threat matrix, chart, scenario chain, timeline, or control matrix.
5. Add the 1LoD implication or management decision request.
6. Add source IDs and any necessary methodology note.
7. Inspect text size and line count. Rework content or layout rather than reducing fonts below the standard.
8. Render the page and inspect clipping, overlap, chart labels, rule alignment, and source visibility.
9. Repeat for every page, then inspect the deck as a sequence for design consistency.

## 16. Visual review checklist

| Review question | Pass condition |
|---|---|
| Is the page title exact? | Matches the mandatory title set. |
| Is the executive conclusion visible first? | Sits immediately below the title and can be understood in one read. |
| Is the evidence model appropriate? | Matrix, chart, scenario, timeline, or control roadmap matches the page purpose. |
| Is information readable? | Title, body, labels, and source notes meet the type scale. |
| Is the source trail visible? | Source IDs appear on material claims or in the page footer. |
| Is the page free of clipping and overlap? | All elements remain inside the canvas and visible at presentation scale. |
| Does the page avoid prohibited patterns? | No rounded cards, shadows, gradients, stock imagery, or interface widgets. |
| Are colours controlled? | White canvas, dark text, emerald-green highlights, and grey structural rules. |
| Does the page contain a decision implication? | 1LoD implication or management decision request is present. |

## 17. Approval criteria

The deck meets this specification when all five analytical pages use their intended master layout, share the defined visual tokens, preserve evidence traceability, remain readable at full-slide view, and provide a decision-oriented operating implication. The design review must be completed before PowerPoint export and delivery.

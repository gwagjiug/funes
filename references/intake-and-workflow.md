# Intake and Workflow

Use this reference to resolve project-specific decisions without turning dashboard work into a preference survey.

## Inspect First

Before asking the user, inspect what is available:

- dataset schema, representative values, nulls, ranges, and cardinality;
- metric definitions, units, denominators, aggregation, time grain, and refresh cadence;
- existing pages, navigation, filters, chart components, and data tables;
- design tokens, typography, semantic colors, breakpoints, and accessibility patterns;
- target deployment surface and any screenshot, export, or embedding requirements;
- data source, methodology, uncertainty, privacy, and publication constraints.

Use existing evidence as the answer. Ask only about consequential gaps.

## Dashboard Brief

Record the result before designing:

```text
Primary audience:
Primary question:
Intended decision or action:
Usage mode: monitoring | exploration | explanation
Key metric definitions and units:
Supporting questions:
Required comparisons:
Target surfaces and viewports:
Data source and refresh cadence:
Uncertainty or interpretation risks:
Existing design system:
Explicit assumptions:
```

A dashboard may support several tasks, but one task must determine its first-screen hierarchy.

## Question Router

Do not ask every question in this table. Ask only when the answer is unavailable and changes the design.

| Unresolved decision | Ask | Safe default |
| --- | --- | --- |
| Purpose | What decision or action should this screen support? | No safe default if it cannot be inferred. |
| Primary question | What must the first screen answer first? | If the task is explicitly exploratory, show a compact overview and controls; do not invent a hero insight. |
| Audience | Who uses this, and how familiar are they with the domain? | Plain language with the precise term in parentheses. |
| Usage mode | Is this mainly monitoring, exploration, or explanation? | Infer from the product flow and request. |
| Comparison | Is comparing entities or following each entity's trend more important? | Infer from the primary question; otherwise ask. |
| Intended action | What should the user do when a value is high, low, or unusual? | Present the finding without an action control. Do not invent a workflow. |
| Metric semantics | What are the unit, denominator, aggregation, time window, and missing-data rules? | No safe default when they affect interpretation. |
| Axis emphasis | Is absolute magnitude or small change more important? | Choose the domain that preserves the task and disclose a non-zero baseline. |
| Uncertainty | Does an interval show estimate uncertainty, outcome variability, or an observed range? | No safe default. Labeling an unknown interval “confidence interval” is prohibited. |
| Information density | What are the three most frequent tasks? | Overview first; move raw detail behind a table, drill-down, or export. |
| Domain language | Does the audience require formal terminology? | Preserve the precise term and add a short plain-language explanation. |
| Surface | Desktop, mobile, wallboard, embedded chart, or static export? | Reuse the existing application's supported viewports. |
| Brand | Is there an existing design system or required palette? | Minimal neutral system from `dashboard-rules.md`. |
| Reproduction | Can underlying data, metadata, and code be exposed? | Show source and method; keep restricted assets private. |

Ask related questions together, recommend the least risky default, and explain only the consequence that makes the answer necessary.

## From Brief to Dashboard

### 1. Write the question hierarchy

Use this order when applicable:

1. Primary answer or current state
2. Most important comparison or change
3. Explanation or decomposition
4. Exceptions and uncertainty
5. Detailed records and provenance

Stop when the user's task is complete. Do not create sections merely to fill a page.

### 2. Decide what belongs above the fold

Include only what the user needs to recognize the state and choose the next step. Filters belong above the fold only when they change the primary answer and are frequently used. Do not spend prime space on a low-density chart, duplicated KPI, decorative summary, or exhaustive control set.

### 3. Write a chart specification

For every proposed chart, complete:

```text
Question answered:
Metric, definition, and unit:
Chart type and why it fits:
Primary visual encoding:
Comparison or reference point:
Category order:
Axis domain and reason:
Direct labels or legend:
Value to emphasize:
Uncertainty treatment:
Annotation or reading guidance:
Source, date, and method context:
Interaction and keyboard behavior:
Responsive behavior:
```

If a field is irrelevant, omit it. If the question, metric, or encoding cannot be stated, remove the chart.

### 4. Resolve competing views

One chart does not have to carry every interpretation. When absolute values, rates, shares, cumulative values, distributions, or spatial patterns answer different necessary questions, use separate coordinated views. Do not layer unrelated encodings into one chart merely to save space.

### 5. Record assumptions

Distinguish:

- **Confirmed** — present in the data, code, or user answer.
- **Assumed** — a reversible design default chosen to proceed.
- **Blocked** — missing semantics that could make the result misleading.

Only `Blocked` items require further user input.
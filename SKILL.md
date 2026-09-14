---
name: data-dashboard-design
description: "Designs and reviews data dashboards by turning user goals into information hierarchy, chart specifications, accessible visual systems, and evidence-based audits. Use when creating a dashboard from data, choosing or revising charts, improving a vibe-coded dashboard, reviewing dashboard screenshots or code, or checking labels, axes, uncertainty, hierarchy, tables, color, and reproducibility."
---

# Data Dashboard Design

A dashboard is a path to an answer, not a collection of charts. Decide the user, question, and action before choosing layout, chart type, color, or typography.

## Choose the Work Mode

- **Create** — turn data and a user goal into a dashboard brief, hierarchy, and chart specifications.
- **Review** — inspect a rendered dashboard and report prioritized, evidence-backed problems.
- **Refine** — preserve the useful structure and make the smallest changes that improve comprehension or correctness.

## Required Workflow

1. **Inspect before asking.** Read the data schema, representative values, metric definitions, existing UI, design tokens, chart patterns, target viewports, and provenance that are available. Do not ask for information the project already provides.
2. **Establish the brief.** Identify the audience, primary question, intended action, usage mode, key metrics, target surface, provenance, and uncertainty. Read [references/intake-and-workflow.md](references/intake-and-workflow.md).
3. **Build the journey.** Order content from the primary answer to supporting comparisons and then details. Use one clear first-screen focus; a hero chart is optional, never filler. Read [references/dashboard-rules.md](references/dashboard-rules.md).
4. **Specify each chart.** Give every chart one question, defined metric and unit, justified visual encoding, comparison, axis domain, labels, uncertainty treatment, context, and source. Read [references/chart-decisions.md](references/chart-decisions.md).
5. **Apply a coherent visual system.** Reuse the product's tokens. If none exist, use the minimal fallback system in `dashboard-rules.md`; do not invent a second design language.
6. **Verify the actual surface.** For implementation work, render and exercise the dashboard at its target viewports. Check the first-screen journey, clipping, density, interactions, color-independent comprehension, labels, units, and source context. A static code inspection is not visual verification.

## Question Policy

- Ask only unresolved questions whose answers materially change the result.
- Ask at most five related questions at a time and include a recommended default when one is safe.
- Treat user answers as the project brief; do not ask them again.
- Proceed with an explicit assumption when a safe default exists.
- Do not guess when ambiguity could make the visualization misleading, especially metric definitions, denominators, units, aggregation, time windows, comparison baselines, or uncertainty semantics.
- Do not ask aesthetic preference questions before purpose and audience are known.

## Non-Negotiable Rules

- Every dashboard names a primary user, primary question, and intended action.
- Every visible chart or KPI serves a distinct question; remove filler and unexplained duplication.
- Important estimates use the primary visual encoding instead of being buried in tooltips, abbreviations, or secondary text.
- Labels, units, time periods, and relevant denominators are readable where the value is interpreted.
- Visual choices must not distort or imply unsupported conclusions. Decorative 3D is prohibited; dual axes require an explicit, defensible reason and a failed simpler alternative.
- Never imply that a group average describes every individual. Distinguish confidence intervals, prediction intervals, observed ranges, and distributions.
- Do not rely on color alone. Use direct labels, position, shape, line style, or another redundant cue where needed.
- Show data provenance and the context needed to interpret a shared chart. Link data, metadata, and reproduction code when permissions and product constraints allow.
- Reuse an existing design system. Consistency is a constraint, not decoration.

## Output Contracts

### Create

Return, in order:

1. Dashboard brief
2. User journey and first-screen hierarchy
3. Chart specifications
4. Visual-system decisions
5. Assumptions and unresolved data risks
6. Verification evidence when a surface was implemented

### Review

Use [references/audit-checklist.md](references/audit-checklist.md). Report only evidenced findings, ordered `Blocker`, `Major`, then `Minor`. For each finding provide the location, evidence, user impact, and smallest viable fix. Do not manufacture a numeric score.

### Refine

State what stays, what is removed, what changes, and why. Prefer deletion, direct labeling, clearer ordering, or a better encoding over new cards, controls, explanations, or dependencies.

## Reference Router

| Need | Read |
| --- | --- |
| Decide what to ask and write the brief | `references/intake-and-workflow.md` |
| Plan journey, hierarchy, density, tables, and visual tokens | `references/dashboard-rules.md` |
| Choose and validate charts, labels, axes, units, and uncertainty | `references/chart-decisions.md` |
| Audit an existing dashboard or verify a new one | `references/audit-checklist.md` |

## Source Basis and Limits

This skill synthesizes, rather than reproduces, principles from:

- Adam Kucharski, [“Ten reasons your vibe-coded dashboard looks terrible”](https://kucharski.substack.com/p/ten-reasons-your-vibe-coded-dashboard)
- Saloni Dattani, [“Saloni's guide to data visualization”](https://www.scientificdiscovery.dev/p/salonis-guide-to-data-visualization)

The sources provide design judgment, not universal numerical standards. Project data, audience, domain conventions, accessibility requirements, and an existing design system take precedence where they create a real constraint.
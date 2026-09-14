# Data Dashboard Design

[한국어](README.ko.md)

An Agent Skill for designing, reviewing, and refining data dashboards. It turns user goals into a clear information hierarchy, justified chart choices, accessible visual rules, and evidence-backed review findings.

## Use It For

- designing a dashboard from a dataset or API;
- choosing charts, metrics, labels, axes, and comparisons;
- improving a generated or “vibe-coded” dashboard;
- reviewing hierarchy, information density, tables, color, and typography;
- checking uncertainty, provenance, standalone context, and reproducibility.

## How It Works

The skill supports three modes:

- **Create** — produces a dashboard brief, user journey, chart specifications, visual-system decisions, and explicit assumptions.
- **Review** — reports evidenced findings as `Blocker`, `Major`, or `Minor`, each with the smallest viable fix.
- **Refine** — preserves useful structure and makes the minimum changes needed for clarity or correctness.

It follows this order:

```text
User question → metric → visual encoding → dashboard hierarchy → presentation
```

Before asking questions, the agent inspects the available data, code, UI, and design system. It asks only unresolved questions that materially change the design or prevent a trustworthy interpretation.

## Core Principles

- A dashboard is a path to an answer, not a collection of charts.
- Every chart and KPI must serve a distinct question.
- Important estimates must not be buried in tooltips, abbreviations, or secondary text.
- Labels, units, periods, denominators, uncertainty, and provenance must be clear where they affect interpretation.
- Color cannot be the only cue.
- Existing product tokens take precedence over a new visual language.
- Decorative 3D is prohibited; dual axes require explicit justification.
- Implemented dashboards must be verified on the actual rendered surface.

## Usage

Ask your agent naturally. The skill should activate for requests such as:

```text
Design a dashboard for this sales dataset.
Review this dashboard and prioritize the smallest useful fixes.
Which chart should compare regional trends and current values?
Refine this dashboard without replacing the existing design system.
```

For an ambiguous request such as “make this CSV into an attractive dashboard,” the agent first resolves the audience, primary question, intended action, metric semantics, and target surface instead of immediately generating a grid of charts.

## Files

| File | Purpose |
| --- | --- |
| [`SKILL.md`](SKILL.md) | Trigger, workflow, non-negotiable rules, and output contracts |
| [`references/intake-and-workflow.md`](references/intake-and-workflow.md) | Project discovery, decision questions, dashboard brief, and chart-spec template |
| [`references/dashboard-rules.md`](references/dashboard-rules.md) | User journey, hierarchy, hero, KPI, table, color, typography, spacing, and responsive rules |
| [`references/chart-decisions.md`](references/chart-decisions.md) | Question-to-chart selection, labels, scales, uncertainty, standalone context, and reproducibility |
| [`references/audit-checklist.md`](references/audit-checklist.md) | Severity-based dashboard review and implementation verification |

## Source Basis

This skill synthesizes design principles from:

- Adam Kucharski, [“Ten reasons your vibe-coded dashboard looks terrible”](https://kucharski.substack.com/p/ten-reasons-your-vibe-coded-dashboard)
- Saloni Dattani, [“Saloni's guide to data visualization”](https://www.scientificdiscovery.dev/p/salonis-guide-to-data-visualization)

It does not reproduce either article or its images. The skill converts their dashboard- and chart-level guidance into an operational design workflow.
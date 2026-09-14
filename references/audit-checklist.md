# Dashboard Audit Checklist

Audit the rendered surface first. Use source code and data definitions to verify causes and semantics, not as a substitute for seeing the interface.

## Evidence Required

Collect what is available:

- target audience, primary question, and intended action;
- rendered dashboard at supported viewports;
- representative interaction states, including filtered, empty, loading, and error states when relevant;
- metric definitions, data source, units, aggregation, time grain, and uncertainty semantics;
- existing design tokens and component conventions.

Do not report a visual defect from code alone when rendering can confirm it. Do not report a semantic defect without checking the metric definition when it is available.

## Severity

- **Blocker** — likely to mislead, hide essential context, prevent the primary task, expose restricted data, or make content inaccessible.
- **Major** — materially increases cognitive effort, buries the primary answer, breaks the journey, or fails a supported viewport.
- **Minor** — local inconsistency or polish issue with limited task impact.

Do not assign a numeric score. Severity must follow user impact, not the number of checklist violations.

## Gate 1: Purpose and Meaning

- [ ] The primary audience, question, and intended action are identifiable.
- [ ] Each chart or KPI answers a distinct question.
- [ ] Counts, rates, shares, cumulative values, and standardized measures are not conflated.
- [ ] Units, denominators, aggregation, population, and time window are available where needed.
- [ ] The chart type and visual encoding match the intended comparison.
- [ ] Titles and annotations do not imply unsupported causality, continuation, or precision.
- [ ] Group averages are not presented as individual outcomes.
- [ ] Confidence intervals, prediction intervals, observed ranges, and distributions are distinguished.

Any failure that changes the conclusion is a `Blocker`.

## Gate 2: Journey and Hierarchy

- [ ] The first viewport has one obvious starting point.
- [ ] The primary answer appears before supporting comparisons and raw detail.
- [ ] A hero view, if present, earns its space and remains informative at the target aspect ratio.
- [ ] Filters appear where they affect the task and do not overwhelm the initial state.
- [ ] Primary, supporting, and detailed content have distinct visual weight.
- [ ] Equal cards, borders, or backgrounds do not flatten importance.
- [ ] The same KPI or explanation is not repeated without a separate purpose.
- [ ] Empty space is intentional rather than an artifact of a poor chart or grid choice.

## Gate 3: Chart Comprehension

- [ ] Labels and units are adjacent to the marks or axes they explain.
- [ ] Text follows the expected reading direction and avoids unnecessary rotation.
- [ ] Direct labels replace a distant legend when categories are few and unique.
- [ ] Legends and categories use inherent, task-relevant, or alphabetical order.
- [ ] Key estimates are visually encoded or directly annotated, not hidden in tooltips or suffixes.
- [ ] Dense overlapping series are split, deemphasized, or otherwise made traceable.
- [ ] Multiple necessary perspectives are separated instead of overloaded into one chart.
- [ ] Non-zero, log, or transformed axes are visible and defensible.
- [ ] Bar baselines, areas, angles, perspective, and color scales do not distort magnitude.
- [ ] Complex charts explain how to read them and identify the important pattern.

## Gate 4: Tables and Detail

- [ ] The main table contains task-relevant columns rather than the entire source schema.
- [ ] Comparable numbers use consistent alignment, unit, and precision.
- [ ] Sorting, filtering, and search serve actual lookup or comparison tasks.
- [ ] Long or secondary fields move to detail views or export without hiding essential context.
- [ ] Headers, focus order, keyboard interaction, and narrow-screen behavior remain usable.

## Gate 5: Visual System and Accessibility

- [ ] Existing typography, spacing, radius, border, elevation, and semantic colors are reused.
- [ ] Accent colors carry stable meanings and are not decorative noise.
- [ ] Neutral concepts do not receive accidental positive or negative color semantics.
- [ ] Data remains distinguishable under common color-vision deficiencies.
- [ ] Color is not the only cue for state or category.
- [ ] Text contrast, focus indicators, accessible names, hit targets, and keyboard paths are adequate.
- [ ] Content does not clip, overlap, or become unreadably dense at supported viewports.

## Gate 6: Standalone Context and Reproducibility

- [ ] A shared chart retains its subject, metric, population, period, units, and source.
- [ ] Consequential caveats are prominent enough to survive skimming or resharing.
- [ ] Data date and refresh state are clear where freshness matters.
- [ ] Authorized maintainers can trace transformations and chart configuration.
- [ ] Data, metadata, and reproduction code are linked when permitted.
- [ ] Restricted or personal data are not exposed to satisfy transparency goals.

## Review Output

List findings in severity order. Use this exact information shape, but concise prose is fine:

```text
[Blocker | Major | Minor] <location and problem>
Evidence: <what was observed or verified>
Impact: <what the user may misunderstand or fail to do>
Smallest fix: <one concrete correction>
```

Then include:

```text
Primary journey: <one sentence>
What already works: <only evidenced strengths worth preserving>
Verification: <viewports, interactions, and data semantics actually checked>
Unverified: <anything unavailable that limits the conclusions>
```

If no material problem exists, say so. Do not create findings to fill categories.

## Implementation Verification

After changes:

1. Render the actual dashboard.
2. Exercise the primary task and the interactions changed.
3. Check every supported viewport affected by the layout.
4. Confirm key labels, units, sources, filters, and uncertainty in the rendered output.
5. Confirm the task remains understandable without color.
6. Re-run the original failure scenario and record what changed.

A screenshot alone is sufficient only for a static exported chart. Interactive dashboards require interaction checks.
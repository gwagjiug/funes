# Chart Decisions

Choose a chart from the question and comparison, not from a gallery or dashboard template.

## Start with a Precise Question

A broad topic is not a chart question. Split it until the metric has one interpretation.

Example: “How do outcomes vary?” may require separate views for:

- What outcomes make up the total? → share
- How many outcomes occurred? → count
- What is the chance of an outcome? → rate or risk

Counts, rates, shares, cumulative values, and standardized measures are not interchangeable. Define the denominator, population, period, aggregation, and unit before choosing the chart.

## Question-to-Chart Guide

| Question | Start with | Decision and caution |
| --- | --- | --- |
| How does a value change over ordered time? | Line chart | Direct-label a few series. Use small multiples when overlap prevents following individual trends. |
| How do categories compare? | Bar or dot plot | Sort by a meaningful order or value. Use alphabetical order when no other order exists and lookup matters. |
| What is the distribution? | Histogram, strip/dot plot, box plot, or density plot | Do not replace the distribution with an average. Explain unfamiliar summaries. |
| How are two quantitative variables related? | Scatter plot | Show outliers, clustering, and enough data to reveal nonlinearity; do not treat correlation as a single pattern. |
| How is a whole composed? | 100% stacked bar or aligned shares | Show counts or denominators too when shares alone can hide scale. |
| How did entities move between two states? | Range or dumbbell plot | Encode the endpoints and difference clearly; sort by the comparison relevant to the question. |
| Where is a spatial pattern? | Map | Pair with a ranked view or histogram when precise comparison or distribution matters. Color area is poor for reading exact differences. |
| What is each entity's trend? | Small multiples | Keep comparable scales when cross-panel comparison matters. Accept that panels reduce point-by-point entity comparison. |
| What is the difference between two lines? | Plot the difference, or use a range view | Parallel or steep lines can make a constant gap look smaller. |
| How uncertain or variable is the estimate? | Labeled interval or distribution | Name what the interval represents. Confidence intervals and prediction intervals answer different questions. |

When two views answer distinct necessary questions, show coordinated views rather than overloading one chart.

## Overlay or Small Multiples

- Keep entities together when comparing their values at the same point is primary and labels remain readable.
- Split entities into panels when following each trend is primary or lines overlap heavily.
- Keep the same axis domain across panels when magnitude comparison matters.
- If panel-specific domains are necessary, mark them clearly; do not invite false magnitude comparison.

## Labels and Category Order

- Keep text horizontal when that matches the audience's writing system.
- Prefer direct labels for a small number of lines, points, or unique categories.
- Use a legend when categories repeat across many marks or direct labels would collide.
- Place the unit on the axis, value, or nearby label—not in a distant explanatory paragraph.
- Use full, plain names instead of unexplained abbreviations such as `gpm`.
- Preserve precise domain terms where distinctions matter, then add a short plain-language definition or example.
- Use inherent order first, then task-relevant value order, then alphabetical order for lookup. Do not shuffle ordinal categories.

## Color

- Match stable conceptual associations when they help interpretation.
- Do not assign evaluative colors to neutral categories.
- Use a color-blind-friendly palette and a redundant cue such as labels, position, shape, or line style.
- Use gray for context and saturation for the series or value being discussed.
- Do not use many bright colors merely to distinguish many overlapping series; change the structure instead.

## Axes and Scale

- Bar length encodes magnitude from a baseline; use zero unless a different encoding makes the truncation explicit and defensible.
- Line and point charts do not universally require zero. Include breathing room beyond observed minima and maxima so the plot boundary is not mistaken for a possible limit.
- If the observed minimum is already near a meaningful zero or physical bound, include it.
- State or visibly signal a non-zero or transformed scale when it changes interpretation.
- Use log scales only when ratios or multiplicative change are the intended comparison and the audience can read them; annotate or provide an alternate view otherwise.
- Avoid dual axes. Prefer aligned panels, normalized values, or a direct relationship plot. Use dual axes only when the shared view is essential and cannot create a false relationship.
- Avoid decorative 3D; perspective changes apparent position, area, and length.

## Units, Averages, and Uncertainty

- Prefer familiar or practically meaningful units over standardized values when both answer the question.
- If a standardized measure is necessary, define it and explain what a meaningful magnitude means.
- Distinguish an average group effect from individual outcomes or causal effects.
- A confidence interval expresses uncertainty about an estimate; it does not show the range of individual outcomes.
- A prediction interval or distribution is more appropriate when outcome variability is the question.
- If individual-level data needed for variability are unavailable, say so and consider displaying familiar absolute values alongside relative measures.
- Show both relative and absolute risk when either alone could mislead.

## Guide Complex Charts

Complexity is acceptable when the chart answers a question that a simpler chart cannot. Then:

1. explain how to read the encodings in a first panel or concise annotation;
2. label the key pattern where it appears;
3. separate explanation from optional detail;
4. provide a simpler companion view when the unfamiliar form is not essential.

Do not make the reader memorize a legend, method, and takeaway from distant text.

## Standalone Context

A shared or exported chart should contain, as applicable:

- a title that states the subject or takeaway without overstating causality;
- a subtitle that defines the metric, population, period, and comparison;
- readable labels and units;
- annotations for key events or interpretation hazards;
- source and data date;
- brief method, sample, or measurement context when it changes interpretation;
- a link to deeper metadata or reproduction materials when permitted.

Put the most consequential caveat in a prominent label or title, not an easy-to-miss footnote.

## Reproducibility

At minimum, preserve the source, retrieval date, transformations, metric definition, filters, and chart configuration. When permissions allow, link the underlying data, metadata, and runnable code. Never expose private or restricted records for the sake of reproducibility.

## Final Six-Gate Check

Before accepting a chart, answer:

1. **Meaningful:** Does this chart and metric answer a precise question?
2. **Clear:** Can the reader focus on the data rather than decode the presentation?
3. **Guided:** If unfamiliar or dense, does it teach the reader where to look and how to read it?
4. **Standalone:** Does it carry the context likely to be lost when shared?
5. **Justifiable:** Can every consequential choice—metric, encoding, scale, color, comparison—be defended?
6. **Reproducible:** Can an authorized person trace and recreate the result?

A failure in meaning, scale, uncertainty, or provenance is not visual polish; fix it before styling.
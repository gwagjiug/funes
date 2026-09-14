# Dashboard Composition Rules

Use these rules for screen-level structure. They convert common dashboard failure modes into decisions and checks.

## Failure-to-Rule Map

| Failure mode | Rule | Check |
| --- | --- | --- |
| No user journey | Order the screen around one primary question and intended action. | Can the user tell where to start and what to inspect next? |
| Flat visual hierarchy | Give primary, supporting, and detailed content visibly different weight. | Would the page still have an obvious starting point in grayscale? |
| Wasteful hero chart | Use a hero only when it answers the primary question and earns the space. | Does it carry more decision value than the content pushed below it? |
| Main-table data dump | Expose task-relevant columns first; move exhaustive records to drill-down or export. | Can the common task be completed without horizontal hunting? |
| Detached or unclear labels | Put labels, units, and meanings next to the values they explain. | Can the chart be read without searching a subtitle or distant legend? |
| Key estimate buried | Give the important estimate the primary encoding or a clear annotation. | Is the takeaway visually comparable rather than hidden in suffix text or tooltips? |
| Repeated information | Show a fact once unless repetition supports a distinct task or context. | Does removing a duplicate change any decision? |
| Arbitrary “tech” colors | Use color as a coherent semantic language, not atmosphere. | Does each accent have a stable meaning? |
| Generic typography without intent | Reuse the product type system or choose one readable family with explicit roles. | Do typography changes communicate hierarchy rather than novelty? |
| Inconsistent spacing and scales | Use a small token set for type, spacing, radius, border, and elevation. | Can every value be named from the same system? |

## Journey and Information Architecture

Start with content, not containers.

1. **Primary** — the answer, state, or exception that drives the user's decision.
2. **Supporting** — comparisons or trends that explain the primary state.
3. **Detail** — records, methodology, secondary dimensions, and provenance.

A card is warranted only when it groups related information or supports an interaction boundary. Do not wrap every chart and sentence in equal cards; equal containers flatten hierarchy.

## Hero Gate

Use a hero chart only when all are true:

- it directly answers the primary question;
- it has enough information density to justify first-screen space;
- its aspect ratio fits the data rather than creating large accidental voids;
- it remains useful at the target viewport;
- it deserves priority over the content displaced below the fold.

Otherwise use a smaller primary view or no hero. A dashboard title and concise state can be sufficient.

## KPI Rules

- A KPI must support a decision, threshold, comparison, or state change; otherwise it is decoration.
- Add a comparison period or reference only when it has a defensible meaning.
- Do not repeat the same KPI in the header, summary strip, and chart.
- Do not present precision unsupported by the source data.
- Pair status colors with text or symbols.

## Table Rules

- Choose columns from user tasks, not from the source schema.
- Put identifiers and decision-critical measures first.
- Use human-readable names, units, and formats.
- Align comparable numbers and use consistent precision.
- Keep sorting and filtering only where they support real lookup or comparison tasks.
- Provide detail expansion or export for exhaustive fields.
- Preserve keyboard access, focus visibility, header associations, and readable narrow-screen behavior.

## Visual Hierarchy

Create hierarchy with the fewest cues that work:

1. position and grouping;
2. scale and whitespace;
3. typographic weight;
4. contrast and color;
5. border or elevation only when separation remains unclear.

Do not increase every cue simultaneously. Excess borders, shadows, rounded containers, and accent colors compete with the data.

## Minimal Fallback Visual System

Existing product tokens always win. When none exist, begin with this reversible fallback rather than inventing a custom theme:

- **Type:** one readable family; four roles—page title, section heading, body/data, metadata.
- **Spacing:** `4, 8, 16, 24, 32` CSS pixels; use the smallest set the layout needs.
- **Radius:** at most one control radius and one container radius.
- **Borders:** one subtle neutral border; do not use borders around every region.
- **Color:** neutral canvas and text, one emphasis color, and semantic status colors only when the semantics exist.
- **Elevation:** none by default; add one level only for actual overlays or stacking.
- **Width:** choose chart dimensions from label length, density, and target viewport—not a uniform card grid.

These values are skill defaults, not claims from the source articles. Replace them with project tokens when available.

## Color Language

- Match familiar concepts when the association is stable: water with blue, vegetation with green, established party colors, or product status colors.
- Do not use red or green for neutral categories merely because they are visually distinct.
- Reserve saturated colors for the data or action that deserves attention.
- Test common color-vision deficiencies and retain non-color cues.
- A dark theme is a product-context choice, not a shortcut to a “technical” appearance.

## Responsive Composition

- Verify the first-screen answer at each supported viewport.
- Prefer wrapping or stacking over shrinking text and hit targets.
- Keep labels horizontal where the writing system and language expect horizontal reading.
- Reconsider the chart form when narrow width makes labels, comparisons, or interactions unusable.
- Do not hide essential context only on mobile; shorten or restructure it.
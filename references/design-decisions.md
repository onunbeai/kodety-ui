# Design decisions

Use these standards to resolve competing visual choices. Follow the current request and product contracts, preserve suitable existing conventions, and choose the treatment that makes the task clearer. Polish comes from coherent relationships and usable states, not a fixed palette or universal component shape.

## Color by role

Assign separate tokens to actions, selection, semantic states, categories, and data. A dark primary button can coexist with blue selection and pastel category chips. Keep each category mapping stable and pair status color with text or an icon.

Use strong saturation where attention has a purpose: a primary action, active state, warning, or data signal. Avoid spreading one accent across every border, icon, and heading. A stronger color field is appropriate when the content itself needs emphasis; verify text contrast and preserve the action hierarchy.

Judge changes by the metric's meaning. A decrease in latency may be favorable; an increase in errors is not. Do not assign success or failure from the sign of a number alone.

## Quiet surfaces, explicit interaction

| Decision | Default | Exception or limit |
| --- | --- | --- |
| Separate content regions | Spacing, alignment, a subtle divider, or a small tonal change. | Add a container when the region is an independent object or needs a clear boundary. Avoid a card around every field. |
| Show depth | Restrained exterior elevation with intentionally composed inner stages and metadata wells. | A short contact shadow or inner highlight can define a control or shell. Avoid unrelated shadows and decorative relief across the page. |
| Define a field | A calm fill or border that still identifies the editable area. | Increase boundary or focus contrast when needed. Subtle styling does not justify an invisible field or focus state. |
| Add texture | Keep work surfaces quiet. | A faint grid may support a canvas or spatial task. Do not place it behind dense text or every table and form. |

## Shape and density follow the task

Use a related family of radii across shells, panels, controls, and chips. Adjust nested corners to their inset and apparent size. Pills suit compact tags or particular actions; they are not mandatory for every input and button. A strict geometry rule may be relaxed when optical alignment produces a more coherent result.

Compose nested surfaces when their roles differ: a visualization stage gathers number, delta and graph; a property well aligns metadata; a footer provides identity or next action. Use a small, consistent inset and related radii so the card reads as one designed object. Reject multiple identical outlines that add no hierarchy, not composition itself.

Choose density from content and interaction. Compact desktop tools can place related controls close together; touch targets, long labels, validation, and multiline values require more room. Derive row height from the actual text, controls, and padding. Do not shrink type or targets to imitate a reduced screenshot.

Give major regions room to separate while keeping labels near their values and actions near their context. Large editorial gaps belong where reading or presentation benefits from them; they are not the default spacing inside an operational panel.

## Legible hierarchy

Use a concise type scale and weights that remain clear at normal usage size. Establish emphasis through size, weight, placement, and moderate contrast; avoid making secondary text simultaneously tiny, thin, and pale. Large metrics need not enlarge every heading.

Use tabular figures for comparisons and monospace for code, IDs, or shortcuts when it helps recognition. Preserve distinctive typography where it suits the product, while keeping controls and data readable. Tune tracking optically; aggressive display tracking is not a rule for small labels.

## Select patterns by the work

| User task | Prefer | Avoid or reconsider |
| --- | --- | --- |
| Compare many records | Aligned tables, stable columns, and distinct selection, hover, and focus states. | Decorative card grids that make comparison harder. |
| Follow progress through stages | A board with real states, counts, and consistent card metadata. | Columns invented only to fill a layout. |
| Inspect or edit one record | A detail panel with predictable label/value alignment and editing near the value. | Full-page forms for every small change; ambiguous row actions. |
| Narrow a collection | A clear search or compound filter with visible criteria and removal. | Elaborate custom controls when a simple field answers the task. |
| Complete a bounded workflow | Meaningful field groups and a clear completion action. | Competing primary actions or one card per field. Independent regions may each need their own action. |

## Appearance and behavior must agree

Screenshots establish visual relationships, not keyboard, persistence, or animation behavior. Define opening, selection, confirmation, cancellation, saving, loading, errors, and recovery from the task. Preserve familiar control semantics even when the appearance is custom. Do not claim that a static reference demonstrates interactions it cannot show.

Custom presentation is mandatory for every authored input, selector, dropdown, and other control, including its open states. Reuse accessible behavior primitives and design their slots. Use Keyline for UI glyphs and authentic SVG artwork for company/app logos; neither existing generic defaults nor aesthetic convenience overrides these requirements.

Use brief motion to clarify a change without delaying work; honor reduced motion. Validate the chosen treatment with real content, long values, empty results, failure states, and the intended viewport. When two options look equally polished, prefer the one with clearer behavior and less interaction cost.

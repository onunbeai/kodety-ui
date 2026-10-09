---
name: kodety-ui
description: "Design and refine product interfaces with composed cards, deliberate sidebars, precise typography, layered surfaces, and fully custom controls. Use for dashboards, workspaces, tables, property panels, forms, SaaS flows, or explicit Kodety UI requests. Requires Keyline Icons for UI glyphs and authentic SVGs for company/app logos. Complements the existing implementation stack; not a deployment or backend skill."
---

# Kodety UI

Deliver a product interface that feels carefully designed and pleasant to use. Its signature is **calm composition, precise details, and character in the controls**. Refinement should appear in alignment, density, surface relationships, and input behavior, rather than an added layer of decoration.

The Activity and Workstreams visual anchors define the required level of craft. A tidy dashboard with rounded white boxes is not sufficient. Design the internal composition of each important region: navigation rhythm, dominant data, subordinate context, purposeful inset surfaces, and an intentional relationship between body and footer. Use the [quality review](references/quality-review.md) to reject under-composed work before delivery; never claim that passing a build or applying tokens proves visual quality.

## Mandatory design requirements

- **Keyline Icons only for UI glyphs.** Use the real Keyline stroke, fill, or duotone assets, selected by role. Do not silently substitute another icon library, emoji, Unicode glyph, or hand-drawn approximation. See [icons and logos](references/icons-and-logos.md).
- **Authentic SVG company/app logos.** Use actual verified vector artwork. Initials, colored letter tiles, generic icons, approximate redraws, and raster images wrapped in SVG do not satisfy this requirement. Human avatars are a separate category.
- **Every authored control has a custom visual treatment.** Inputs, textareas, selects, dropdowns, comboboxes, date pickers, checkboxes, radios, switches, sliders, upload controls, and menus must fit the same designed system, including their open and non-default states. Raw browser chrome and unmodified library defaults are not final UI. Keep native semantics and accessible primitives underneath the custom presentation.
- **Compose sidebars and cards explicitly.** Read their recipes whenever they appear in scope. Purposeful nested surfaces are encouraged; redundant boxes are not. A number and a label floating inside a large blank rectangle are not a composed metric card.

These requirements are part of the user's requested Kodety UI identity. Preserve the project's architecture and business behavior, but do not use existing generic visuals or a different icon package as an excuse to bypass them in the authored scope. A later explicit user instruction can override a requirement. Do not redesign unrelated screens merely to enforce it globally.

## Decision precedence

1. The current request, the product's purpose, and accessibility requirements.
2. These mandatory design requirements, together with the project's brand, theme, architecture, and functional contracts.
3. A specific reference supplied for the current screen, when available.
4. This skill's three screenshots as a guide to visual finish.
5. This skill's presets and recipes, adapted to context.

Use the [design decisions](references/design-decisions.md) to resolve tradeoffs between color, shape, density, and interaction. Apply these standards according to their functional role and the current product context.

## Visual direction

When no direction already exists, start with a light UI: an off-white canvas, white surfaces, graphite text, understated borders, and localized color for selection, data, status, and tags. Do not automatically turn every screen into a dashboard or a dark interface into a light one.

Characteristics to preserve across adaptations:

- Establish hierarchy through position, spacing, and contrast before excessive size or weight.
- Keep density comfortable: related items close together, distinct groups with clear breathing room.
- Compose related surface levels, proportional radii, and short, low-opacity shadows. An inset stage or metadata well is a useful part of the card, not automatically redundant nesting.
- Give controls their own finish: compact chips, aligned icons, useful prefixes, and fields integrated with the content.
- Give color a function. Category, action, selection, and status have distinct roles.
- Build character into the task: a composed metric stage, an inset property well, a refined filter sentence, or an identity footer. Do not stop at one decorative flourish on an otherwise generic page; do not add meaningless charts or fake data to manufacture detail.

## Reading by task

| Task | Required resources |
|---|---|
| New screen or substantial refinement | [Visual language](references/visual-language.md), [tokens](references/tokens.md), and [UI contract](references/ui-contract.md) |
| Sidebar or navigation rail | [Sidebar composition](references/sidebars.md) |
| Metric, record, task, event, or summary card | [Composed cards](references/composed-cards.md) |
| Any UI glyph or company/app identity | [Keyline Icons and authentic SVG logos](references/icons-and-logos.md) |
| Input, form, filter, menu, selector, or inline editing | [Custom controls](references/custom-controls.md) and the relevant contract states |
| Small visual adjustment | The relevant visual-language/token sections; do not rebuild the whole screen |
| Choosing between visual patterns or resolving competing requirements | [Design decisions](references/design-decisions.md) |
| Implementation or audit ready for handoff | [Quality review](references/quality-review.md) |

The [visual anchors and rejected baseline](references/visual-language.md#the-three-visual-anchors) are included with the skill. For a new screen or broad refinement, inspect Activity and Workstreams plus the rejected baseline before designing; revisit the relevant crop during review. The [base CSS](assets/kodety-ui.css) is optional and provides tokens and visual primitives; applying it alone does not meet the visual standard or implement control behavior.

## Workflow

### 1. Understand the actual screen

Identify the main task, the object being edited, the primary action, the density, and the required states. In an existing codebase, inspect tokens, components, fonts, and integrations before replacing anything. Make straightforward inferences without interrupting the work; ask only when missing information would materially change the result.

Choose composition based on content: a table to compare records, a board for stages, a property panel to edit an object, or a form for sequential entry. Metrics need useful data. Do not add navigation, statistics, or generic cards without a product need.

For a substantial screen, record a short map of regions, components, actions, states, and responsive behavior in the project's existing format or working notes. A small change does not need a separate document.

### 2. Calibrate a representative slice

Resolve the shell/navigation junction, one fully composed primary card, and one custom control with realistic content before repeating patterns. When the requested screen has no sidebar or card, use its dominant component instead. Calibrate hierarchy, typography, density, surface layers, icons, and at least one open/focused state. For small changes, the edited component itself is the slice.

Render this slice and compare its internal structure with the relevant visual anchor. If it still resembles the rejected baseline, redesign its composition before propagating it. Do not try to repair an empty card by adding arbitrary shadows or spacing. If rendering is unavailable, continue the useful work but leave visual acceptance explicitly unverified.

Suggested measurements are CSS starting points, not measurements of enlarged or tilted screenshots. Compare at normal usage scale. The result must hold up without wallpaper, perspective, a device mockup, or dramatic shadows.

### 3. Build controls with intent

Read the applicable [control recipes](references/custom-controls.md). Every control must have a custom presentation while preserving semantics, keyboard behavior, focus, validation, and submission. Icons, prefixes, values, units, clear actions, loaders, and errors need distinct slots and a clear hierarchy. A styled select trigger with an untouched browser dropdown is incomplete.

Define behavior alongside appearance: what opens, what is selected, when changes are confirmed or canceled, how they are saved, and how failures are recovered. The screenshots are static; they do not establish any of these behaviors.

### 4. Implement for the correct destination

Reuse the existing stack, accessible behavior primitives, and styling system. Restyle those primitives to the required custom presentation and use Keyline for UI icons. No particular framework, remote font, or service is required. If using the base CSS, map its roles to existing tokens before duplicating them.

The name Kodety UI does not imply modifying a project in Kodety Builder. When the requested deliverable is **in the Builder**, combine this visual direction with the available operational skill: `kodety-site-code` for native elements, `kodety-widgets` for Code Components, or `kodety-motion` for Interactions v2. Use only the skill that matches the task. For local code, work in the local project. For implementing an app from Figma, combine with `figma-app-code` and its extraction workflow; for writing to Figma, use the appropriate Figma skill.

The destination's operational contracts take precedence over this skill's generic snippets. Do not duplicate behavior or animation across CSS, JS, and the Builder's native runtime.

### 5. Review the actual result

Inspect the rendered interface at normal usage scale and in relevant states. Check keyboard use, a narrow viewport, long content, empty states, errors, and loading as appropriate to the scope. Adjust hierarchy and density first, alignment and surfaces next, and microinteractions last.

When a preview is available, capture and inspect it, fix observed problems, and check what changed. If rendering is unavailable, perform the structural review possible and disclose that limitation. Do not claim visual parity or tests you did not perform.

## Firm rules

- A button is a real button or link. Do not deliver a clickable `div` without semantics and keyboard support as a finished control.
- Inputs have accessible names and identifiable labels; a placeholder alone is insufficient. Icons without text need accessible names.
- Focus, selection, error, and the primary action must remain distinguishable. Refinement must never erase the indication of interactivity.
- Do not use an image of the screen as the implementation or absolutely position the entire UI to imitate a snapshot.
- Preserve existing data and functionality. A visual change does not authorize replacing integrations with fixtures, inventing successful saves, or changing business rules.
- Identify simulations as local. Real success feedback appears only after real success; failures keep work recoverable.
- Do not scatter magic values and overrides across components. Fix the source tokens, layout, or shared variant.
- Do not use brands, avatars, or logos from the screenshots as product assets unless supplied for that purpose.
- Do not treat creating a UI as authorization to publish, modify another project, or send messages.

## Defaults and exceptions

| Prefer | Avoid by default | When to adapt |
|---|---|---|
| Readable sans, weights 400–600, a short type scale | Ultralight text, faint microcopy, oversized headings in tools | An existing identity or editorial screen may need another voice |
| Understated fields with a clear outline or affordance | Invisible inputs, placeholders used as labels | Inline editing can be borderless at rest if it remains discoverable |
| Soft borders and tonal surfaces | Shadows everywhere, blur and glass in every region | Overlays need elevation; a brand effect can be localized |
| Composed shell, inset stage, and useful footer | Repeated identical boxes with duplicated padding, borders, and titles | Nesting is useful when each layer has a distinct content role |
| Radii by role | Every action as a pill | Tags, status indicators, and avatars can support more rounding |
| Keyline stroke/fill/duotone by role | Other UI icon libraries, fabricated icons, random style mixing | Authentic company/app SVGs and human avatars are separate assets |
| Brief motion that explains a change | Bouncing inputs, long entrances, animation on every row | A requested expressive experience may justify its own motion |

## Delivery and evidence

Complete the requested artifact. Summarize what changed, what was verified, and concrete limitations. Separate visual finish, functionality, and integration: none proves the others. Do not add a design manual to the response when the user requested a change.

The completion standard is the [quality review](references/quality-review.md), including the visual rejection checks, mandatory icon/logo sourcing, and custom-control states. Do not call generic card grids “premium” because spacing and contrast pass. A screen must remain well resolved with long names, larger numbers, and intermediate states, without depending on the short text in the screenshots.

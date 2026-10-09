# Quality review — Kodety UI

Review the rendered product and the behavior that changed. The goal is consistent polish in actual use; do not assign an automated aesthetic score or claim “pixel perfect” fidelity based on enlarged or tilted screenshots.

## Visual acceptance gate

Activity and Workstreams define the required visual ambition. A well-aligned page of plain white cards can still fail. For a new screen or broad refinement, open those anchors and the [rejected baseline](images/04-insufficient-composition.png), render the representative slice, and compare equivalent regions before duplicating the pattern. Make the following judgment from actual rendering, not from a list of CSS values:

| Area in scope | Pass condition | Reject and repair |
|---|---|---|
| Sidebar | Compact identity/header, consistent row slots, deliberate group rhythm, controlled active state, quiet footer | Duplicate oversized brand/workspace blocks, large sparse link tiles, random spacing, filler to occupy blank space |
| Dominant card | Readable main stage, subordinate context, useful inset or evidence, resolved footer/edge; strong shared internal axes | Label + number + unrelated corner icon in a large blank rectangle; every card repeats identical geometry regardless of data |
| Layering | Shell, stage/well and supporting edge have distinct functions and related radii | Flat indistinguishable planes or redundant nested outlines with identical padding |
| Inputs/selects/menus | Custom anatomy and coordinated closed/open states, with actual options and feedback | Browser-default control chrome, native dropdown/date popup, untouched component-library theme, custom trigger over a generic popup |
| UI icons | Actual Keyline assets, valid glyph/style exports, purposeful stroke/fill/duotone roles | Another pack, Unicode/emoji substitution, handmade approximation, fabricated variants |
| Company/app logos | Authentic vector SVG, verified source, correct variant and preserved artwork | Initial tiles, generic symbols, guessed logos, raster/PNG-in-SVG, or unresolved placeholders presented as finished |

Correct the observed composition failure and inspect the affected region again. Do not accept a known failure merely because the app runs, color contrast passes, or all boxes align. If no rendering is possible, complete what can be completed and state that visual acceptance is unverified; do not claim the benchmark has been reached.

## 1. Define the scope and evidence

- **Always:** identify the changed component/flow, its relevant states, and the source of truth for its data. Preserve the existing baseline when there is one.
- **Small adjustment:** check the changed region, its neighbors, and the risk introduced. Changing a radius does not require testing the entire app; changing a field's height requires checking that field's alignment, text, and focus.
- **Shared change:** if a token, variant, or component serves multiple screens, check representative consumers with different densities or states.
- **New screen/broad refinement:** check the complete composition, main flow, and adaptation to a narrow width. Add other widths when an actual layout change warrants them.
- **Preview available:** open the rendered interface, capture a representative state, inspect it visually, and fix the issues you observe. Capture it again after corrections that affect the composition. DOM and CSS alone do not prove visual polish.
- **No preview:** review the structure, tokens, semantics, and logic you can assess; state that visual inspection was unavailable. Do not invent a screenshot, keyboard result, measurement, or tested viewport.

Keep evidence in the project's existing work location if needed. Briefly record the state, width/context, and result. Do not create a dossier for a trivial change or expose private data in delivery screenshots.

## 2. Resolve the overall composition

Make this pass at normal usage scale before correcting isolated pixels.

1. Locate the current object, task, and primary action without relying on external explanatory text.
2. Check the relationship between navigation, title, toolbar, content, and detail. Every region needs a purpose; remove redundant decorative containers.
3. Observe grouping: a record's metadata stays together; different groups have recognizable breathing room. Encourage meaningful inset stages and metadata wells; remove redundant wrappers that repeat the same group without adding hierarchy.
4. Check density with plausible content: a table supports comparison; a board reveals stage and progress; properties align labels and values; a form follows an understandable order.
5. Check hierarchy without color: weight, position, and proximity should remain useful. Color reinforces meaning; it does not repair a confusing structure.
6. Check whether the UI works visually without wallpaper, perspective, blur, or a presentation frame. The screenshots calibrate quality, not measured dimensions.

**Use:** a record title near its actions, filters near results, metadata in a consistent order. **Avoid:** an oversized hero in a dense tool, four purposeless metrics, and a box around every label.

## 3. Make the optical pass

- **Typography:** consistent baselines; proportionate headings; distinguishable weights; legible secondary text. Routinely read metadata, status and category labels should normally remain around 12–13px, not become a field of 10px microtext. Do not simultaneously reduce size, weight, and contrast to make text recede.
- **Alignment:** compare icon/text, label/value, and the apparent height of neighboring controls. Fix the cause in the component before scattering offsets throughout the interface.
- **Spacing:** follow the token rhythm; confirm internal padding and distance between groups. Small optical adjustments are acceptable when they have a clear purpose.
- **Surfaces:** canvas, shell, inset stage/well, footer and overlay have clear roles. Card exteriors remain restrained while interiors have deliberate composition; menus and drawers appear layered above content. Avoid a different shadow on every component.
- **Borders and radii:** a delicate outline must not erase a field's identity. Check the corners of nested surfaces and content clipping.
- **Icons:** inspect actual Keyline imports/SVG provenance, style coverage, apparent size, and aligned slots. A small glyph can have a larger hit area. Check library-internal chevrons, ticks, close controls and feedback too; visual similarity to Keyline is insufficient.
- **Brand logos:** confirm actual SVG vector content and official/verified provenance, correct symbol/wordmark variant, viewBox and proportions. Do not accept a renamed raster, `<image>` wrapper, fabricated letter tile or traced substitute.
- **Color:** tags retain a stable mapping; status includes text/an icon; focus differs from selection and hover. Check contrast for the actual color pair when there is uncertainty or a relevant color change.
- **Text/data:** consistent units, decimal places, dates, and numeric alignment. Truncation does not hide decisive information; the full value remains accessible.
- **Evidence scale:** a visualization and its containing stage should feel proportionate. Reject a tiny graph stranded in a wide empty card or oversized blocks created by stretching a low segment count. Resize the stage/track together and keep the actual numbers truthful.

**Use:** a pastel chip with dark text, a soft border, and a subtle selected row. **Avoid:** nearly white text, a misaligned icon compensated for with spaces in the label, compressed tracking in microtext, and a glow on every input.

## 4. Validate the changed controls

Visual inspection and functional validation are separate passes. Exercise the states the control actually has; do not add artificial states to fill out a checklist.

| Control/risk | Practical check |
|---|---|
| Button/link | Correct name and destination/action; keyboard activation matches its semantics; disabled controls do not execute actions; an icon without text has an accessible name. |
| Input | Identifiable label, accessible name, editable value, working selection/copy and Tab; prefix/unit does not overlap text; clearing does not trigger a neighboring action. |
| Field with an error | Error is associated with the field and understandable; value is preserved; correction is possible; the indication does not rely on color alone. |
| Combobox/menu | Opens from its trigger; options are navigable according to the pattern; the active option differs from the selected one; choosing updates the value; Escape closes and focus returns appropriately. |
| Multi-select/chips | Adding/removing does not duplicate or lose items; long names fit; removal has an accessible name; Backspace does not delete an item while text is still being edited. |
| Inline editing | Discovery, entry, confirmation, and cancellation are clear; Escape restores when that is the contract; leaving the field does not cause ambiguous saving or silent loss. |
| Dialog/drawer | Identifiable content and title; useful initial focus; modals contain focus; closing returns focus to a logical destination. Non-modal overlays do not trap keyboard focus. |
| Search/filter | Results match the filter; clearing restores the expected state; no results is distinct from a loading failure; delayed queries do not overwrite a newer result. |
| Save/asynchronous action | Pending state is recognizable; repeated clicks do not cause unintended duplicate submissions; errors preserve work; visual success follows actual confirmation. |

Review every control family present, not only the first input. Open selects, menus, date/time panels and upload states as applicable; verify their custom surfaces, rows, marks, focus, error, disabled and loading treatments. A styled closed field does not prove the open-state requirement.

Make a brief **keyboard-only** pass through the affected flow: enter, operate, correct, confirm/cancel, and exit. Check Tab order, visible focus, absence of traps, and focus not obscured by fixed elements. Do not impose custom arrow-key behavior or shortcuts on native controls unnecessarily.

Test empty, filled, and failure states when they belong to the flow; include loading when there is an asynchronous operation. Use identified fixtures or a test environment when appropriate. Do not submit a real form, change external data, or trigger a purchase, publication, or message merely to produce UI evidence.

**Use:** an error beside the field with its value preserved; a loader in the action slot without moving the text. **Avoid:** a “Saved” toast after a local timeout, a permanent spinner, a beautiful button without an action, and a menu that only works with a mouse.

## 5. Stress-test content and responsiveness

For a new/broad layout, check at least the normal working width and a narrow width relevant to the product. For a localized adjustment, use widths at which the component or its container could fail; do not repeat an entire matrix without a new risk.

- Use a long name, multiple chips, and a larger number in the changed elements. Real content must not depend on the screenshots' short phrases.
- Check toolbar wrapping, accessible primary actions, and absence of overlaps. Do not hide an essential function to make the screen fit.
- Tables/boards may intentionally scroll within their own container; do not accept accidental page overflow or clipped actions.
- Menus near an edge must remain visible; the panel should scroll when necessary. Sticky headers/footers do not cover content, focus, or error messages.
- On touch devices, check hit areas and separation; hover cannot be the only way to discover an essential action.
- When layout/dimensions change, check text enlargement/zoom in the relevant area. Do not fix wrapping by shrinking all typography.
- When motion changes, check the reduced-motion preference; the interaction remains understandable without decorative movement.

**Use:** chips wrap, the toolbar reorganizes groups, and the drawer occupies the usable width on a narrow screen. **Avoid:** global scaling to shrink the app, `overflow: hidden` that conceals clipping, and a fixed width based on the screenshot.

## 6. Separate appearance, functionality, and integration

| Evidence | What it demonstrates | What it does not demonstrate |
|---|---|---|
| Inspected screenshot | Composition, visible content, and the state captured in that rendering | Keyboard behavior, persistence, responsiveness at other widths |
| Exercised interaction | Behavior observed in the flow/environment used | Correctness of the entire application or an external integration that was not exercised |
| Relevant test/build | Properties verified by the test and compilation when performed | Good visual polish or actual API success |
| Confirmed real response | The result of that authorized operation in the specified environment | All failure scenarios or durability that was not checked |

Run the checks required by the project and those relevant to the change's risk. If validation, selection, or saving logic changed, use focused functional tests when available. For a reversible visual adjustment, direct inspection may suffice; do not write tests that merely repeat CSS classes or values. Do not expand the suite without a change, failure, or new uncertainty that warrants it.

## 7. Fix failures and conclude precisely

Do not declare the affected area ready while a visual acceptance gate fails, a required Keyline or authentic logo asset is unresolved, a control remains visually generic, or there is a known focus/keyboard failure, clipped content, an illegible control, an action without a contract, lost edits, simulated success presented as real, or a regression caused by the change. Fix the problem within scope and check the affected area again.

If a limitation depends on an unavailable tool, access, or integration, complete the work that is possible and identify what remains unverified; do not turn absence of evidence into approval. A preexisting bug outside the scope may be recorded without silently expanding the task.

The delivery summarizes: **what changed**, **what was actually checked**, and **what limitation remains**, if any. Examples: “I reviewed the filter open and closed in the preview and exercised selection/cancellation by keyboard”; “The layout was reviewed in code; with no preview available, the rendered polish was not validated”. Do not use “ultra premium”, a fidelity percentage, or an aesthetic score as substitutes for evidence.

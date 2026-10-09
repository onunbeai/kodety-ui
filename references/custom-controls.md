# Inputs and controls — Kodety UI

A reference guide for clear, precise, subtly expressive product interfaces.
Choose recipes according to the task. Every actual control must have a custom visual treatment; ordinary non-interactive information can remain text.

## Mandatory custom presentation

Custom controls are required throughout the authored UI, not an optional upgrade for one prominent field. This applies to text, search, email, password and numeric inputs; textareas; selects and comboboxes; dropdown and contextual menus; date/time/range pickers; switches; checkboxes; radios; sliders; and upload controls.

Customize the complete anatomy: label and helper, field shell, value, Keyline prefix/trailing icons, action slots, popup/list/calendar where present, option rows, selection indicator, error, disabled, read-only, loading, hover, pressed, and focus states. A custom closed trigger opening an untouched browser menu or default library popup fails the requirement. An unmodified component-library theme also fails, even if technically accessible.

Keep native elements for text editing, form values, labels, autofill, selection, and submission. Use established accessible primitives for complex behavior, then author their visual slots. “Custom” means a deliberate product-specific presentation, not replacing an input with `contenteditable` or rebuilding keyboard behavior without need. Do not suppress browser/OS security dialogs, password managers, or accessibility services; those are outside the authored UI.

| Control | Required visual work | Reject |
|---|---|---|
| Text/search/textarea | Chosen tonal/inline/outlined shell, baseline, padding, radius, caret space, focus and validation; autoresize/scroll when needed | Unstyled input, browser bevel, label supplied only by placeholder |
| Select/combobox | Custom trigger and custom listbox, Keyline chevron/check, active and selected options, empty/loading/error | Native OS dropdown or a CSS-skinned `<select>` whose popup remains unstyled |
| Dropdown/context menu | Designed surface, item grid, groups, separators, disabled/destructive states, focus and placement | A generic browser menu or untouched vendor demo |
| Date/time/range | Designed entry and custom accessible calendar/time panel when a picker is exposed | Relying on the browser's `type="date"` popup as the final picker |
| Checkbox/radio/switch | Authored mark/track, actual semantic state, hit area, focus and disabled treatment | Raw browser checkbox, image-only toggle, color-only state |
| Number/slider | Authored track/thumb or increment controls where applicable; units and limits remain clear | Default spinner chrome, hidden native controls without equivalent operation |
| Upload | Custom accessible trigger/drop region, filenames, progress and error/retry | Exposed unstyled file-input button as the final upload UI |

Use Keyline glyphs inside controls, including chevrons, search, clear, calendars, and selection marks. A progress spinner can be a neutral progress shape or a suitable Keyline glyph; do not introduce a second pictogram family. See [icons and logos](icons-and-logos.md).

## Select a field treatment deliberately

- **Tonal:** a shallow, quiet inset surface with an identifiable editable region, clear label, and reserved leading/trailing slots. Good for search, filters, and dense product forms. Use one shell, not an outlined input nested inside another outlined wrapper.
- **Inline:** value-aligned editing inside a property row, with persistent edit affordance and a custom editing surface on activation. Good for record details, not for hiding a first-time onboarding field.
- **Outlined:** a restrained but explicit edge where the field boundary needs extra clarity. Good for standalone forms or low-affordance contexts; do not stamp a strong gray outline around every control in a composed card.
- All treatments share a clear focus language, aligned text baselines, readable value/helper hierarchy, and the same error/disabled contract. Never use low contrast to disguise the absence of composition.

## Evidence and interpretation
- **Observed in the screenshots:** light surfaces with closely related tones, thin dividers, small icons, tinted pills, segmented filters, and property editing in rows.
- **Observed in the screenshots:** compact groupings, soft borders, neutral buttons, and color concentrated in states, data, and small details.
- **Not observable:** keyboard navigation, validation, persistence, exact contrast, actual dimensions, and behavior on small screens.
- The interactions and dimensions below are **implementation recommendations**, not verified behaviors of the products shown.
- Match the level of care; create anatomy, content, and identity suited to the product, without copying brands or screens.

## Visual and semantic foundation
- Use native semantic elements underneath a custom presentation; never leave their browser-default appearance as the finished design.
- For popovers, comboboxes, and complex selections, use accessible primitives already available in the project and customize every visible slot, including the open panel.
- Reserve expressive finishing for details: a subtle inset, status marker, prefix icon, or well-proportioned chip.
- Start with a white surface, graphite text, a neutral border, and one functional color; adapt to the existing system.
- Distinguish surfaces, dividers, and interactive boundaries. A very faint decorative border must not be the only cue for a field.
- As a starting point, use an 8–10 px radius, 13–14 px text, and 10–12 px internal spacing; calibrate to the actual density.
- Desktop controls can have a visual height of 32–36 px; for touch, ensure targets of approximately 44 px or larger, without overlap.
- In dense bars, enlarge the clickable area through the container; do not stretch the icon or conceal targets that collide with one another.
- Use 14–16 px Keyline Icons optically aligned with the text; choose stroke, fill, or duotone by role and keep equivalent actions visually consistent.
- Prefer stable label text; a placeholder provides an example or hint, never the field's only name.
- Do not lighten instructions, placeholders, or values until they disappear. Check readability in context and under actual usage conditions.
- Show a clear, continuous, unclipped `:focus-visible` indicator. A 2 px outline with an offset is a starting point, not a universal token.
- Preserve focus identification across themes and high-contrast modes; do not rely exclusively on box-shadow.
- Keep decorative icons out of the accessibility tree; icon-only buttons need a specific accessible name.
- Group related controls with structure and a shared label, without adding tab stops to decoration.

## Minimum state contract
- **Display:** a readable value and an editing cue when editable; an absent value appears as a contextual “Add…”.
- **Hover:** a slight surface or border adjustment, without changing width, type weight, or the position of other items.
- **Focus:** an unmistakable highlight on the current target, independent of hover state.
- **Editing:** preserve the caret and selection; the label, instructions, and confirmation action remain discoverable.
- **Invalid:** a message explaining the correction, programmatically associated with the field; keep the entered value.
- **Read-only:** the value remains available to read and copy; do not use a disabled appearance for information that is still relevant.
- **Disabled:** actually block interaction; explain the reason when needed to understand the flow.
- **Saving:** keep the value visible and show local progress; block only actions that truly conflict.
- **Saved:** discreet confirmation when useful, without repeated toasts for every keystroke or small change.
- **Failure:** preserve the draft, identify what was not saved, and offer a retry; do not simulate success.
- **Rollback:** keep the confirmed value separate from the draft; roll back the persisted representation and retain the intent for recovery.
- **Conflict:** if a remote update occurs, explain the discrepancy; never silently replace the current edit.
- Do not display all these states at once. Implement the relevant ones and check at least focus, error, waiting, and recovery.

## 1. Composite field with a prefix and actions
- **Anatomy:** external label → wrapper → optional prefix → flexible input → suffix/action → help or error below.
- Examples: URL with protocol, search with shortcut, budget with currency, identifier with a type selector.
- Keep a single outer border; use internal dividers only when they clarify units or independent actions.
- Use `min-width: 0` on the text area; long values should scroll inside the input without pushing the trailing button outward.
- Informational prefixes are not buttons. If they change the unit or type, use a real button/select with a name and state.
- Actions such as clear, copy, or reveal are buttons with their own clickable area; never nest one button inside another.
- Clicking a decorative region may focus the input; preserve text selection and the behaviors of internal actions.
- Use `type`, `autocomplete`, `inputmode`, and `spellcheck` according to the data; do not impose generic combinations on every field.
- Let the input participate in the form with the correct `name` and value; custom controls also need to submit their data.
- `Enter` follows the form's contract. A clear/reveal button must use `type="button"` to avoid accidental submission.
- Reserving space for errors/progress can prevent jumps; do not impose large empty areas for rare states.

## 2. Editable property row
- **Anatomy:** optional discreet icon + width-controlled label + flexible value + contextual action.
- Use rows within one continuous region; avoid enclosing each property in an independent card.
- Clicking or pressing `Enter`/`Space` on the actual trigger starts editing; informational rows do not receive `tabindex` without a reason.
- On desktop, the value can become an input in place. On mobile, the label and value can stack without changing their meaning.
- When editing starts, move focus to the editor. Selecting all is useful for short, replaceable values, but poor for long text.
- Single-line fields can confirm with `Enter` and cancel with `Escape`; do not intercept confirmation during IME composition.
- Multiline fields preserve `Enter` as a newline and offer explicit confirmation or a clearly indicated shortcut.
- For low-risk changes, saving on exit may work; for important values, prefer visible Save/Cancel actions.
- Clicking a popover option does not mean editing has definitively ended; coordinate focus before saving or closing on blur.
- On cancellation, restore the confirmed value. On completion, return focus to the equivalent trigger if it still exists.
- During network failure, retain the edit and allow correction or retry; do not clear the field or silently close the region.
- Describe formats before requiring correction: units, limits, currency, or date format appear near the value.
- A glow, pencil, or underline on hover can provide an additional cue; editing must also be available through focus and touch.

## 3. Searchable single or multiple select
- **Anatomy:** label → trigger/field → aligned popover → search when needed → options → status message.
- Compose the popup as carefully as a card: a restrained outer shell, optional inset search row, grouped options, and a small feedback/action edge only when needed. Do not enlarge every option into its own card.
- Useful starting geometry: 4–6px trigger offset, 10–12px outer radius, 4–6px inner gutter, 28–32px desktop option rows and larger touch rows. Match width to content/trigger and viewport; these are calibration points, not exact screenshot measurements.
- Use stable option slots, such as `16px minmax(0, 1fr) 16px` for Keyline glyph, label, and selection mark. Reserve the check slot even when unselected. Optional descriptions sit under the label, not under the icon.
- A grouped menu can put a compact search field above a fine divider; section labels use quiet sentence case. Hover/active gets a small neutral wash; selected gets a real Keyline check and clear text. Focus remains separately visible.
- For short, stable lists, use the project's simplest accessible select primitive with a custom trigger and custom option panel; search is not mandatory. A hidden native select may provide form integration, but the visible control and popup must be custom.
- In an editable combobox, the input retains focus and points to the active option; expose expansion and the relationship with the list according to the primitive.
- For a button with a list, maintain the focus model defined by the primitive; do not mix two keyboard patterns.
- Arrow keys navigate options; `Enter` confirms; `Escape` closes the open layer first; `Tab` follows the flow without trapping focus.
- Do not turn selection options into an action menu. Choose roles and semantics according to the actual function.
- For single selection, show a check or equivalent mark without shifting label alignment; selection must not depend only on color.
- For multiple selection, keep the list open when it speeds up the task and announce selection/deselection proportionately.
- Show chips up to a space limit, followed by “+N”; all items remain accessible for inspection and removal.
- Give the chip removal button a name such as “Remove Design”; clicking it must not unintentionally open the selector.
- Do not hide the only removal method in a tiny “x” that appears only on hover.
- An empty query, no results, loading, and failure are different states, with different messages and actions.
- For remote search, discard old responses after a newer query; avoid uncontrolled result changes beneath the active option.
- Offer new-option creation only when the product allows it; creation and selection of an existing option must be distinguishable.
- Use a maximum height with internal scrolling and popover repositioning; do not crop results at the viewport edge.
- Preserve the link between a stable ID and its label; renaming an option must not change the identity of an already selected value.

## 4. Filters with tokens and clauses
- **Anatomy:** property → operator → value → remove; the bar may end with “Add filter”.
- The visual reference suggests compact parts within a light strip; recommend behavior for each step without assuming the screenshot's behavior.
- Use three understandable segments, for example “Assignee / is / Ana”; do not force an opaque text expression.
- The property determines valid operators and the editor type. Changing it requires explicit reconciliation of an incompatible value.
- Each editable part has a trigger, contextual label, and sufficient clickable area; the entire clause does not become one ambiguous target.
- `Escape` closes the current popover and returns to the originating segment; it does not automatically delete the clause.
- When removing a clause, move focus to the next one or to “Add filter”; never leave focus on the document without a reference point.
- `Backspace` in an empty search field may focus the previous token; require a second deliberate gesture to remove it.
- Show AND/OR intelligibly when multiple conditions exist; explicitly group more complex precedence relationships.
- Distinguish an active filter from an incomplete draft. Automatic updates are appropriate only when cost and feedback are predictable.
- For expensive queries, use Apply and Clear with a pending-changes state; preserve the current query during editing.
- On narrow screens, allow whole clauses to wrap or offer a summary + panel; do not create cropped, inaccessible chips.
- A result count helps confirm the effect, but must not dominate the bar or announce every typed letter.

## 5. Number, currency, and unit
- **Anatomy:** label → editable value → identified unit/currency → constraint or contextual message.
- Use `type="number"` when number semantics are appropriate, with custom appearance and increment controls if needed; native spinner chrome is not the final UI. Preserve keyboard operation. Identifiers are not mathematical numbers.
- For currency with controlled formatting, a text input with the appropriate `inputmode` may be better; implement parsing and errors explicitly.
- Separate the text being edited from the normalized value. Allow intermediate states such as a sign, separator, and empty value when they make sense.
- Format confirmed values using the product/user locale and currency; do not infer preferences from this guide's language.
- Do not silently interpret `1,234` without a clear locale rule; preserve the input and explain relevant ambiguities.
- Avoid reformatting on every keystroke in ways that move the caret; format on confirmation/exit when this better preserves typing.
- Store amounts with precision appropriate to the domain; do not make critical monetary operations depend on visual rounding.
- Distinguish zero, absent, and invalid. A “0” placeholder must not generate a persisted zero.
- Steppers need names such as “Increase…” and “Decrease…” and must respect step size/limits; show them only when discrete increments are useful.
- Do not apply mouse-wheel changes to a focused value without considering the risk of unintentional changes while scrolling.
- When limits are exceeded, explain the range; do not replace the entered value with a limit without warning.

## 6. Date and range
- **Anatomy:** label → readable input + optional calendar trigger → format/context hint.
- Use a custom date/time field and an accessible custom calendar/time panel when a picker is exposed. A native date value can support form serialization behind the interface; its browser popup is not the finished visual treatment.
- A custom calendar requires keyboard navigation, indicators for today and the selected date, visible focus, and full date names.
- On opening, focus the selected date or a relevant starting position; on closing, return to the trigger without losing the edit.
- Allow typing when possible; do not force users to traverse dozens of months to enter a known date.
- Distinguish a calendar date from an instant: a birthday/daily deadline must not shift to another day because of an inappropriate time-zone conversion.
- For times, make the time zone explicit where it affects the decision and handle calendar ambiguities according to the domain.
- For ranges, identify the start and end, explain limits, and display incomplete ranges without inventing the second date.
- Unavailable dates need an understandable reason when that reason matters; color alone does not explain the restriction.
- Do not automatically mark the current date as a saved value merely because the calendar opened on it.

## 7. Segmented control
- **Anatomy:** discreet track → 2–5 short options → selection indicated by a stable surface, text, and/or mark.
- Use for closely related, mutually exclusive alternatives; long or numerous options call for another structure.
- If it chooses a form value, use radio group semantics; if it switches panels, use tabs and associate each panel.
- If it triggers independent actions, use separate buttons; do not apply selection semantics based on visual similarity.
- Arrow keys and tabbing follow the chosen pattern; for radios, maintain one tab stop within the group according to expected behavior.
- Provide a group label outside the track. Icons may complement labels, not make them cryptic.
- Animate the indicator only when it is simple and stable; preserve understanding with reduced motion or animation disabled.
- Equal widths are useful for comparable options; do not compress different labels until they become unreadable just for symmetry.

## 8. Switches, checkboxes, and binary choices
- A switch communicates an on/off setting; a checkbox communicates selection, consent, or membership in a set.
- Use a custom-styled real input or accessible primitive; explicitly design the mark/track, selection, focus and disabled states, and connect the label and help text. Do not leave the default browser checkbox/radio visible.
- `Space` toggles the focused control; clicking the label also works and increases the interaction target.
- Give it a stable name such as “Receive updates”; avoid changing the full name with each state.
- Indicate state beyond color: thumb position, checkmark, and correct semantic information.
- A mixed checkbox represents partial selection of a set; do not use a dash merely as decoration.
- A switch may save immediately; if it depends on Save in the form, make that contract clear in context.
- A save failure requires nearby feedback and a reliable state: revert to the confirmed value or explicitly keep it pending, with a retry.
- Do not present a setting as saved when the request failed. Avoid repeated toggles whose responses arrive out of order.
- In groups, keep rows and spacing consistent; do not draw an entire card for each small option by default.

## 9. Search and command palette
- **Anatomy:** contextually named field → result groupings → item with a useful title/description/shortcut → empty state.
- Search filters or finds content; a palette executes actions. Explain the distinction when both coexist in the interface.
- A visual shortcut such as `⌘K` appears only when implemented and adapted to the platform; keep a clickable trigger.
- Do not intercept common shortcuts inside inputs or individual letters during normal typing.
- In a modal dialog, identify the window, place focus usefully, contain it correctly, and restore focus on closing.
- If the experience is not modal, do not trap focus; allow a natural return to the rest of the page.
- Arrow keys traverse results, `Enter` activates the indicated result, and `Escape` closes the layer; visual selection follows logical focus.
- Subtly highlight the matching portion without fragmenting the accessible name or reducing readable context.
- Asynchronous queries need cancellation/discarding of obsolete results and separate empty, loading, and failure messages.
- Results lacking permission and destructive actions require the product's actual handling; the palette must not bypass existing rules.
- Do not announce every result update while the person types; communicate useful changes without excessive noise.

## Composition and final verification
- Show density variants only when needed; keep the same focus, error, and persistence contracts.
- Inspect every control family actually present, including its open popup. Reject mixed browser defaults, untouched library themes, missing custom states, or icons outside Keyline.
- Test empty, long, accented, partially entered, duplicate, invalid, and read-only values.
- Complete an entire flow using only the keyboard; confirm order, opening, selection, cancellation, and focus restoration.
- Check touch, zoom, narrow viewports, internal scrolling, and popovers near edges.
- Simulate latency and failure; confirm draft preservation, the absence of false success, and functional recovery.
- Check labels, roles, states, and messages with the accessibility tools available in the project.
- Avoid aggressive validation before the person has a chance to finish; choose validation timing appropriate to the field.
- Do not use a toast as the only error location, a tooltip as the only label, color as the only state indicator, or hover as the only access method.
- Avoid making every control a pill, adding glow to every border, an icon to every field, a shadow to every row, or unnecessarily nesting cards.
- Final refinement comes from alignment, hierarchy, proportion, complete states, and predictable responses, not from the number of effects.

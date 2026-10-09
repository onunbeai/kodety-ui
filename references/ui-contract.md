# Composition and behavior contract

Use when creating a new screen or substantially refining a region. For a small repair, apply only the affected parts. Visual scope does not authorize new business rules.

## Choose the right pattern

| Need | Use | Avoid |
|---|---|---|
| Compare attributes across records | Semantic table, aligned columns, consistent density | Huge cards repeating labels for every value |
| Track work stages | Board with actual columns or a grouped list | Decorative kanban when order and stages do not exist |
| Edit an object's properties | Label/value rows, inline input, or a detail panel | A modal for every simple property |
| Enter a sequence of data | Form with semantic groups and clear progression | Every field in a card and multiple competing CTAs |
| Choose among a few stable values | Custom select, styled native radios, or custom segments according to their function | Browser-default widgets or searchable combobox for yes/no |
| Choose among many records | Combobox with search and asynchronous states | Dropdown that occupies the entire page and does not filter |
| Filter by several properties | Property/operator/value clauses | Decorative chips that do not change results |
| Choose several categories | Multiselect with chips and accessible removal | Apparently removable tags with no real action |
| Switch panels | Tabs with an associated panel | Visually selected buttons without an accessible state |
| Perform actions on an item | Action menu | `listbox` used as a menu for visual convenience |
| Show summarized activity | Metric with context and unit, mini chart if useful | Invented KPI to fill space |

## Screen structure

Use normal flow, Grid/Flex, and content constraints. Reserve absolute positioning for overlays and small adornments. The app must work beyond the screenshot's exact width.

Establish a dominant alignment across the title, toolbar, filters, and content. Give the primary action a predictable position. Do not design a header with four visually equivalent areas if only one drives the task.

Cards group only an object, a functional block, or a meaningful region. If two cards share a title, background, and action, consider one surface with dividers. If a table already organizes the data, avoid an additional card for every cell.

Within a meaningful card, deliberately compose layers: outer shell → inset metric stage or property well → quieter identity/action footer. These layers have different jobs. Do not interpret the warning against redundant boxes as a ban on nested design. Read [composed cards](composed-cards.md) before creating cards, and [sidebars](sidebars.md) before creating navigation shells.

Data determines structure: the title and ID do not compete; metadata follows a stable order; empty values have meaning. Show zero when the value is zero, absence when a value is missing, and an error when reading fails.

## Component anatomy

**Button:** short label, optional icon, consistent height and padding. Primary for the main completion action; secondary for an alternative action; ghost for a contextual action. Include an icon only when it helps identify the action. Loading maintains width and provides an accessible state; auxiliary buttons in a form use `type="button"`.

**Work card:** authentic SVG identity when it represents an app/company, legible title, subtle ID, an inset metadata well, and a compact utility footer when those data exist. Read [the card recipes](composed-cards.md) for surface hierarchy and slot alignment. Do not nest buttons inside a link covering the entire card; use a dedicated link with independent actions.

**Table row:** selectors and actions have their own targets. Hover helps track the row; selection uses a persistent indicator; focus identifies the current cell/control. Menus do not change row height. Sorting and filters actually update the presentation.

**Tabs:** subtle active line or surface, count when useful, clear relationship to the panel. On overflow, preserve access through localized scrolling or an overflow control. Do not shrink labels indefinitely.

**Popover:** originates from its trigger, has enough width for its content, and a height limit. Repositions near edges and is not clipped by an ancestor's `overflow`. `Escape` closes the innermost layer and returns focus. Do not add a focus trap to a non-modal popover.

**Drawer/modal:** title, accessible close control, scrollable area, and visible actions when needed. Modals contain focus and have a non-interactive background; non-modal panels preserve access to the rest of the interface. Closing must not silently discard an important draft. Preserve the exit behavior already defined in the product.

**Metric/progress:** number, unit, and time context when known. Visually segment a bar only if the chosen resolution represents the data usefully. Provide the actual value in text; do not invent a denominator or trend. A decorative sparkline receives an appropriate text alternative; an informative chart communicates scale and meaning.

## Content-driven responsiveness

First check the minimum width needed by content and controls; choose breakpoints based on actual failures. Do not import the screenshot's width as a universal contract.

- A sidebar may become a rail or navigation opened by a control, preserving accessible names. Do not remove routes merely to fit.
- A toolbar may wrap onto multiple lines or collapse secondary actions into a menu; the primary action remains findable.
- A properties panel stacks labels and values when two columns make reading cramped; inputs use the available width.
- A table may retain horizontal scrolling within an identifiable region when comparison requires columns. If adapting it to a list, preserve labels, actions, and meaningful order.
- A board may have localized scrolling and an indication that more content follows. The entire document should not overflow accidentally.
- Popovers fit the viewport; a sheet is an alternative on mobile when it improves selection. Do not impose a clipped desktop popover.
- Zoom, translations, and long names expand components; avoid fixed heights that clip text.

## States and data

For each interaction in scope, establish: input → local change → confirmation or response → failure → recovery. In a prototype, this cycle may be local and explicitly identified as such. In a real product, connect the result to the existing integration.

Loading preserves a recognizable structure; a skeleton mimics the content's volume without inventing values. An initial empty state offers a useful next step; an empty state caused by a filter offers adjusting/clearing filters; a loading error offers a retry. Do not use the same message for all three.

Disabled and read-only have different meanings. Read-only information remains legible and copyable. Disable only controls that are actually unavailable; when the reason is not obvious, explain it near the relevant context.

Validation preserves input, explains how to correct it, and does not depend on a toast. On submission, focus should take the person to the problem predictably. Avoid interrupting every keystroke with an error before the person has finished.

Asynchronous editing keeps the confirmed value separate from the draft; failure does not erase intent. Prevent delayed responses from overwriting newer changes. Use the existing concurrency handling and do not invent optimistic success without recovery.

## Accessibility as part of polish

Use native semantic elements and established accessible primitives beneath a fully custom visual presentation. Customize inputs, selectors, menus, calendars, option rows and every state; do not accept browser-default controls or unmodified library themes. Reuse behavior instead of rebuilding a calendar, combobox, or dialog solely to style it. ARIA roles do not implement keyboard behavior on their own.

Actionable targets must be reachable without a mouse and sufficiently large for the device. Choose a DOM order consistent with the visual reading order. Outlines must survive clipping, error, selection, and high contrast. Do not remove all outlines to compensate for browser CSS.

As internal contrast targets, verify at least 4.5:1 for ordinary text and 3:1 for indicators necessary to identify/focus controls against adjacent colors. These thresholds do not constitute a complete accessibility audit. Decorative separators may be softer. Measure the final pairs; alpha, hover, and theme change the result.

Text, icons, position, or semantics complement color. Tooltips supplement explanations rather than being the only explanation. Interfaces with motion remain understandable with reduced motion.

## Examples of translating a request into implementation

**“Make this form more premium.”** Correct grouping, labels, heights, rhythm, and feedback; a compound field may improve currency/URL entry. Do not introduce a dashboard, proprietary font, entrance animations, or navigation redesign unnecessarily.

**“I want filters similar to screenshot 2.”** Use compact clauses and an anchored popover, preserving actual data and operators. Implement selection, removal, keyboard behavior, no results, and responsiveness. Do not copy brands or the surrounding scenery.

**“I want the deal panel from screenshot 3.”** Adopt property rows, soft tags, editing near the value, and clear selection. The tilt belongs to the presentation; the operable panel remains orthogonal.

**“Apply Kodety UI to this dark app.”** Preserve the theme and structure; translate the roles and refinement, calibrating surfaces, borders, and states for the dark theme. Do not inject the light preset.

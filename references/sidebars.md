# Sidebars and navigation rails

A sidebar is a compact navigation instrument with a deliberate hierarchy. Build its header, row anatomy, grouping, and bottom anchor together; a pale column with a logo, a boxed workspace, and three oversized links is not a finished sidebar.

Use the [workspace reference](images/02-workstreams.png) for expanded navigation and the [activity reference](images/01-activity.png) for a compact rail. Observe relationships, density, and state treatment. The dimensions below are intended CSS starting points, not measurements extracted from those screenshots.

## Choose the structure from the navigation

- **Expanded workspace sidebar:** use when labels, teams, saved items, or nested destinations need simultaneous visibility. A few routes can still justify labels; do not force a rail solely to remove empty space.
- **Compact rail:** use when a small set of global destinations has recognizable icons and the current workspace remains identifiable. It is an optional navigation mode, not a substitute for meaningful hierarchy.
- **No persistent sidebar:** use only when the actual product structure favors another navigation pattern. Preserve routes and discoverability; never delete navigation just to resemble a reference.
- Map only real destinations, groups, and account actions. Do not invent starred records, teams, unread counts, or settings to make the column look populated.

## Expanded workspace recipe

| Region | Starting dimensions | Construction |
|---|---|---|
| Shell | 208–248px inline size; 12–16px outer gutters | A quiet surface adjacent to the work area; one subtle boundary if needed. Adapt width to real labels and available space. |
| Workspace header | 44–56px high; 24–28px brand slot | Authentic app/company SVG, workspace name, optional switch chevron, and a separate collapse action when supported. |
| Navigation row | 28–32px desktop height; 6–8px radius | Fixed icon slot, flexible text slot, optional count/action slot. Compact internal padding rather than large tiles. |
| Icon slot | 16–18px wide; 14–17px visible glyph | Fixed alignment column; balance glyphs optically without changing row geometry. |
| Group heading | 11–12px type; 16–24px space before a new group | Quiet sentence-case label, optional disclosure; no oversized all-caps section banner. |
| Row text | 12–14px type; 400–500 weight | One legible line with controlled truncation; active text may gain moderate emphasis. |
| Bottom account area | 44–56px; 24–28px avatar when available | Account name, optional secondary identity line, and an accessible account trigger. |

Use three shell regions: `auto minmax(0, 1fr) auto` for header, navigation scroller, and account footer. Give the middle region `min-block-size: 0` and intentional vertical scrolling. Keep header and footer in layout flow; do not absolutely position them over the links.

For ordinary rows, start with `grid-template-columns: 18px minmax(0, 1fr) auto`, an 8px gap, and 8px inline padding. Use `min-inline-size: 0` on the label. Reserve a consistent trailing slot when neighboring rows need counts or actions; an absent badge must not move the label column.

Align the workspace name, navigation text, group labels, and profile text into a small number of intentional columns. The shell's left edge is not every element's text edge: icons need a slot, while group labels may align with the row's outer inset. Choose these alignments once instead of nudging each row independently.

Place the first destination group 12–20px below the header. Keep neighboring rows 2–4px apart. Separate semantic groups with space before reaching for a divider. A heading directly precedes its children; a long gap must not disconnect it from them.

**Use:** one restrained workspace row, compact destinations, clear group rhythm, and a grounded profile control. **Avoid:** a large marketing wordmark above a second oversized workspace card, 48–64px desktop link tiles, and stretched vertical spacing between three routes.

## Custom workspace, account, and search controls

Every authored input, select, dropdown, and related control must have a composed visual treatment, including its **open popup states**. Keep native semantic inputs/buttons and established accessible primitives underneath. Raw browser dropdowns and unstyled library menus are not finished sidebar components; custom appearance does not mean rebuilding keyboard and focus behavior from scratch.

- **Workspace switcher:** one compact trigger with authentic SVG, name, and Keyline chevron. Its custom popover repeats aligned logo/name/check slots, distinguishes the current workspace, and groups actual management actions separately. Give the surface, item padding, hover, selection, focus, scrolling, and empty/search states the same deliberate finish as the trigger.
- **Account menu:** anchor a custom menu to the bottom account trigger; open upward when space requires. Separate identity from account actions with restrained spacing or a divider. Use consistent icon/text slots and a clear focused item, without a giant profile card inside another card.
- **Sidebar search, when the product has it:** use a 30–34px starting height, a Keyline search icon slot, legible placeholder, accessible label, and a quiet focus treatment. Show a shortcut hint only for a working shortcut. Clear/loading states keep text alignment stable; any result popup receives custom rows, selected/focused states, empty feedback, and controlled overflow.

Style trigger and popup as a single component family. Check the opened state in the actual sidebar; a polished closed field above a browser-default or generic untouched popup is a failed result. Do not add workspace switching, account actions, or search functionality that the product does not have.

## Expanded hierarchy and nested teams

Treat global destinations, saved records, teams, and account controls as different levels of navigation. A typical real hierarchy is global links → saved items → teams and their destinations; omit levels the product does not have.

- Use a team parent row with a disclosure control and an intelligible name. Its child destinations share a consistent 16–24px indentation relative to the parent text structure.
- Indent the branch once. Do not add fresh padding at every nested wrapper and drift labels across the column.
- Distinguish parent context from the selected child. A selected “Workstreams” row does not require highlighting both “Engineering” and “Workstreams” as equally active pages.
- If the parent both navigates and expands, provide separate link and disclosure targets; do not nest a button inside a link or make the click contract ambiguous.
- Show counts only when real and useful. Use compact tabular text or a quiet badge; no bright capsule for every number.
- Saved records may use a meaningful status glyph and a truncated title. Make the full title accessible and preserve an explicit route; do not manufacture saved content.
- Show collapse/expand state accessibly. Collapsing a group must not strand focus inside hidden content.

**Use:** a short “Teams” heading, one team row, then compact subordinate destinations. **Avoid:** another card around the team, bold headings at every level, duplicate active backgrounds, and decorative tree connectors with no informational role.

## Navigation states

| State | Expanded row | Rail item |
|---|---|---|
| Rest | Transparent/quiet surface, readable neutral label, restrained glyph | Neutral glyph on the rail surface; no permanent tile around every icon |
| Hover | Slight neutral surface change across the hit area | Subtle local tile; no scale jump |
| Current route | Modest text/icon emphasis with a white or softly tinted surface; short inset edge/contact shadow only if needed | Clear local selected tile or purposeful filled glyph, with persistent state |
| Keyboard focus | Visible focus indicator around the actionable target, distinct from selection | Visible focus indicator around the full hit area |
| Pressed | Brief surface response without moving adjacent rows | Brief contained response without spring or bounce |

Use `aria-current="page"` for the current destination. Hover must not look selected, and keyboard focus must remain visible on an already-selected row. Keep geometry stable across states: avoid heavier borders that shift text or active font changes that reflow labels.

The expanded reference's selected row feels close to the surrounding navigation: a small white surface with restrained definition. Do not translate it into a tall floating card with a dark shadow, a saturated side stripe, and an oversized colored icon simultaneously.

## Compact rail recipe

Start with a 56–72px rail, 32–40px control boxes, 16–20px glyphs, and 6–10px spacing between related destinations. Use a 24–30px authentic app mark at the top. These are working ranges; increase hit areas and separation for touch rather than merely enlarging the icon artwork.

1. Top: authentic app/company SVG in one restrained brand slot. Add a quiet divider only when it separates the brand/workspace from navigation.
2. Middle: a small number of actual destinations on one centered vertical axis. A selected item gets a deliberate local surface; the entire rail does not become a stack of cards.
3. Bottom: account and truly global utility actions, grouped deliberately. Preserve consistent control geometry and accessible names.
4. Every icon-only control has an accessible name and a tooltip available on focus as well as hover. A tooltip supports discovery; it does not replace route state or a needed expanded view.
5. Offer expansion when labels or nested destinations are needed. Preserve the current route, relevant group state, and focus when switching modes.

Do not copy the reference's very pale inactive glyphs if they become illegible. Do not place a generic glyph in the brand slot or use the rail to hide routes whose meanings are impossible to recognize.

## Icon and identity rules

Use **Keyline Icons only for UI glyphs**, including navigation, chevrons, search, collapse, settings, and status symbols. Select actual Keyline assets and keep a coherent optical size and weight. Do not substitute another family, emoji, a hand-drawn approximation, or a generic icon package when an asset is unavailable.

Choose stroke, fill, or duotone with purpose: stroke is a quiet navigation default; a filled variant can strengthen a selected rail destination; restrained duotone may clarify a category or status. Do not mix treatments randomly or change every icon's style on hover. A variation must preserve recognizable geometry and consistent weight.

**Company and app logos always use authentic SVG assets.** Brand marks are distinct from UI glyphs and do not come from a generic icon substitution. Use the supplied or verified authentic company/app SVG, preserve its proportions and identity, and give it a consistent optical slot. No letter tiles, initials, generic symbols, fabricated logos, traced guesses, or PNG/raster images embedded in an SVG wrapper.

If the authentic SVG is unavailable, identify the missing asset and leave that branding incomplete rather than inventing a substitute. Plain text may identify the item while the asset is unresolved; it is not a completed logo treatment. Personal avatars are a separate content type and must not be used as an excuse to replace company/app logos with initials.

## Space, scrolling, and mobile

Natural empty space below a short navigation list is acceptable. Resolve excessive visual emptiness by reducing oversized header blocks, row heights, shell width, and unnecessary group spacing first. Then consider a collapsible rail if the navigation supports it. Never add a slogan, motivational footer, fake activity, or empty cards to fill the column.

Keep account controls visually quiet and predictably anchored at the bottom; do not separate a few links with `justify-content: space-between`. In a short viewport, the navigation body scrolls while the header/footer retain their roles. If those anchors themselves no longer fit, allow the whole panel to scroll rather than making destinations unreachable.

Use native vertical scrolling or an equally operable implementation. Do not hide overflow to erase a scrollbar. Reserve a stable gutter when needed to prevent width jumps; menus must escape the scroll clip and remain within the viewport. Check the last item, keyboard focus, and a long expanded team near the bottom.

On narrow screens, use an explicit navigation trigger and a drawer/sheet when a persistent rail would steal useful content width. Keep all authorized destinations accessible. A modal drawer manages focus and background interaction, closes predictably, and returns focus to its trigger. Preserve the selected route and expanded groups across responsive changes. Use comfortable touch targets—44px is a useful starting point—without importing the desktop's tight gaps unchanged.

## Accept or reject the rendered result

Inspect the sidebar together with its adjacent toolbar and content at normal usage scale. Open a real nested group, hover one row, focus another by keyboard, activate a route, and view a long label. Check a short and a narrow viewport. The shell must preserve the workspace identity, row alignment, group rhythm, active destination, and usable scroll behavior in these actual states.

**Reject** a result that still reads as a huge empty column dominated by duplicate header cards, large generic links, arbitrary whitespace, improvised logos, or inconsistent icon families. Also reject clipped destinations, indistinguishable selected/focused states, or a footer covering the final links. Correct the observed construction problem; adding a gradient, more filler, or a stronger shadow does not resolve it.

**Accept** when the rendered header, rows, groups, and footer share deliberate alignment and proportion; the navigation remains legible and operable under real content; brand SVGs and Keyline glyphs are authentic; and the sidebar supports the work area without visually dominating it. Record what was actually inspected and what remains unverified. If no preview is available, report that visual review is incomplete; do not replace evidence with an aesthetic score.

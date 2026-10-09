# Visual language — Kodety UI

## The three visual anchors

The images are references supplied by the user. Descriptions of appearance are observations; measurements and behaviors suggested in this skill are design decisions, not exact extractions from the files.

| Reference | What to observe | What to carry forward |
|---|---|---|
| [01 — Activity](images/01-activity.png) | Narrow navigation rail, breadcrumb, branded title, airy metrics, orange segmented bars, pink chart, tabs with an active underline, dotted area | Scale between title and number, localized color, data grouping, quiet navigation |
| [02 — Workstreams](images/02-workstreams.png) | Light sidebar, white main area, small toolbar, tokenized filter, anchored menu, groups by stage, cards with metadata | High density with hierarchy, consistent icons, filters near content, legible progress |
| [03 — Properties](images/03-properties.png) | Panel over a table, label/value rows, icons in small squares, pastel tags, blue selected row, neutral actions | Editing near the data, contextual selection, compound values, drawer with restrained depth |

Activity and Workstreams are the required craft benchmarks for dashboards and workspaces. Properties adds the detail-editor vocabulary. Open the relevant images before a broad design and during visual review. The [insufficient-composition example](images/04-insufficient-composition.png) is a rejected baseline, not another style to emulate.

## Why a tidy layout can still fail

The rejected baseline has orderly sections and usable information, but its visible composition falls short of the benchmark. This is a criticism of design relationships, not a claim about its code or unseen interaction behavior.

| Observed weakness | Required correction |
|---|---|
| A large brand block, a separate large workspace tile, and sparse oversized navigation dominate the sidebar | Resolve one compact identity row, a repeatable icon/text/trailing grid, measured group spacing and a quiet account anchor; use the [sidebar recipes](sidebars.md) |
| Broad summary cards repeat label, number and isolated corner glyph with little internal organization | Compose a dominant data stage, close supporting context, meaningful evidence when available, and a coordinated identity/footer; use [composed cards](composed-cards.md) |
| Large outer rectangles, flat inner space, and similar borders make every region feel equivalent | Establish shell, inset well/stage and supporting edge with distinct roles, related radii and intentionally unequal emphasis |
| A segmented bar appears as a row of blocks added to a generic box | Tune segment slenderness, gap, cap radius and track relative to the data stage; attach it to actual values and context |
| Repeated initial-letter tiles stand in for recognizable apps | Retrieve authentic SVG logos with preserved geometry and color; do not fabricate identity |
| A conventional long search box and separate dropdown do not express a filter composition | When the query is structured, design a compact property/operator/value clause and coordinated custom popup; a simple search can still remain simple |
| Secondary information and helper lines consume similar attention across the screen | Establish fewer type roles, shorten duplicated context, and keep the decisive value/title close to its meaning |

Do not “fix” this by making everything smaller, whiter, rounder, or more shadowed. Correct the actual grouping and hierarchy. The benchmark has purposeful density, strong silhouettes, composed interiors, and confident focal points; it is not merely a low-contrast skin.

## Comparing fairly

Screenshots differ in crop, zoom and canvas size. Compare equivalent regions at normal operating scale: a sidebar row, a card's interior, or an open filter. Use the relationship between slots, hierarchy, surface geometry and density, not the raw screenshot pixel size. Activity and Workstreams include presentation context outside the app; Properties is tilted. Do not reproduce wallpaper, perspective, or cropping in the operable interface, and do not mistake a screenshot enlargement for a required CSS font size.

## Composition before components

**Workspace:** distinguish navigation from the work area through a coordinated shell and content surface. The content can have an inset upper corner or fine boundary while the sidebar remains quieter. Align the workspace header with the adjacent toolbar and the page title with its content grid. Use [sidebar anatomy](sidebars.md); a blank tinted column is not a sidebar recipe. If there is no global navigation, do not invent one.

**Detail panel:** create a predictable label column and a value column; align baselines rather than centering boxes of different heights. Allow chips to wrap. Headers and footers may remain fixed when useful, without hiding content or focus.

**Table:** subtle horizontal dividers, consistent row height, right-aligned numbers. Distinguish hover, selection, and focus. An editable cell is not a giant button spanning the whole row; separate opening a record from editing a value.

**Board:** columns represent real states; each header combines a name, count, and action. Card metadata follows the same order. In a narrow viewport, use a list/single column when it serves the task better; intentional horizontal scrolling is acceptable to preserve comparisons across columns.

**Form:** do not box every field into a card. Use spacing, labels, and a continuous surface to relate fields; separate groups by meaning. One clear completion action per flow is usually enough.

## Scale and density

- Use 2px for optical adjustments and 4px as the main rhythm. Gaps of 4–8px connect icons and text; 12–16px connect fields; 24–32px separate regions. Adapt to the actual scale.
- Working text at 13–15px on desktop; labels at 12–13px; object titles at 20–28px. Long-form reading needs larger type and more line spacing.
- Metrics can use 28–40px without enlarging the other headings. Use tabular figures for comparable data; monospace for identifiers and code when useful.
- Metadata recedes through moderate contrast, position, and size, rather than an extreme combination of all three. Delicacy does not mean illegible type.
- On touch devices, increase the actionable area and breathing room. An icon's size does not define its touch target.

## Surface and depth

Distinguish canvas, surface, and inner surface through small differences in lightness. Structural borders can be quiet; field boundaries and active states need to be clear. Do not use the lightest token for every outline.

A thin line, a short contact shadow, and, when appropriate, a subtle inner highlight give a button its finish. A field can appear slightly recessed without looking carved. Restrict this effect to controls; do not spread relief across every block.

Keep card exteriors quiet but compose their interiors. A metric can have a pale inset stage and white identity footer; a record can have a logo/title region, inset metadata well, and utility row. Nested surfaces with different roles create sophistication without heavy elevation. Popovers and drawers gain elevation because they overlap the work. Keep shadows coherent; different shadows on every card fragment the composition.

Radii express family resemblance. As a starting point, inner radius ≈ outer radius − inset, constrained to the component's visual range. A panel with a 20px radius and 12px inset can contain controls with an 8px radius. Adjust optically rather than turning this into inflexible arithmetic.

## Color with meaning

Separate action, selection, semantic state, and category. A graphite button can coexist with blue selection, an amber warning, and lavender/green/pink tags. These roles need neither the same color nor the screenshots' exact colors.

Tags have a soft background and dark text from the same color family. Map categories to colors consistently. Status includes text or an icon; it does not rely solely on red/green. Whether a change is positive or negative depends on the metric: lower latency can be good.

Segmented orange, a pink line, pastel chips, and avatars are observed accents. Choose those that serve the data. Do not copy logos or people from the screenshots as product assets.

## Icons and optical polish

- Keyline is the required icon family, generally 14–18px in dense UI. Use genuine stroke, fill, and duotone variants by role. Compare apparent area, not just the bounding box; do not distort the paths or silently substitute a different library.
- Keep chevrons, handles, and indicators on the control's axis. Prefixes/units have slots; values do not shift position when an action appears.
- Human avatars can use a separating ring, consistent overlap, and a count. Initials may identify people without supplied photos; company/app identity always uses authentic SVG logos and never initial tiles.
- Truncation is intentional: preserve decisive information and provide an accessible way to read the full value. Do not shrink all typography to accommodate one case.
- Dots or texture belong to a specific canvas when useful. They are not mandatory backgrounds for forms or tables.

## Microinteractions

The screenshots do not demonstrate animation. As a proposed direction, use brief color, border, and opacity transitions: 120–180ms as a starting point. Panels can enter in 160–220ms with a small displacement. Do not animate table layout, focus, or numbers in ways that delay the work.

A pressed state can change the surface or move a button by up to 1px; avoid elastic scaling on inputs. Feedback follows the action: marked selection, removed chip, error on the correct row, quiet confirmation. Respect reduced motion and keep states instantly legible.

## Adaptation

In a dark theme, preserve roles and proportions while recalibrating lightness, contrast, and overlays; do not use an inversion filter. For a playful brand, bring personality to small controls without importing the full bulk of a landing page. For an editorial brand, preserve its distinctive typography in appropriate places and keep data legible.

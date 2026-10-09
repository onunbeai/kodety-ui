# Composed cards — Kodety UI

Build cards as small, deliberately arranged interfaces: a dominant content stage, supporting structure, and a resolved edge or footer.
A rounded white rectangle with a label, number, and corner icon is a starting box, not a finished composition.
Use this reference when summary cards, records, or collaboration blocks feel generic despite clean spacing.

## Visual anchors and diagnosis
- In `images/01-activity.png`, the metric card separates a pale upper stage from a white footer; the number, delta, visualization, and footer identity occupy distinct positions.
- In `images/02-workstreams.png`, a record card combines genuine app identity, title and ID, a quiet inset property well, and a small utility footer.
- The activity reference also shows collaborators above an inset event entry; the visible crop establishes layering, not the unseen lower content or behavior.
- These screenshots establish relationships and finish. All CSS values below are proposed implementation starting points, not extracted measurements.
- The rejected direction used broad, largely uniform white cards: small labels above values, unrelated icons in corners, and excess undifferentiated interior space.
- A segmented meter alone did not resolve that composition. Neither did repeating initial-letter badges as app identity or enclosing every region in the same shell.
- Repair hierarchy and surface anatomy first; adding stronger shadows, more icons, or another chart does not resolve a flat composition.

## The three-layer rule
- **Shell:** establishes the object's outer silhouette, shared boundary, and position in the page grid.
- **Content stage:** groups the main reading or working area through a slight surface shift, intentional inset, or distinct geometry.
- **Supporting edge:** finishes the object with identity, properties, participants, time, or a compact action region.
- These are compositional roles, not a demand for three bordered rectangles. A footer can be unboxed; a stage can be separated entirely by tone.
- Let adjacent layers differ clearly in purpose and subtly in appearance: white shell, near-white stage, readable graphite content.
- Use a fine outer stroke; avoid giving every interior region the same stroke, elevation, padding, and radius.
- An inset needs a reason: numerical evidence, grouped properties, an event entry, or a contained editing area.
- Nested surfaces are welcome when they reveal hierarchy. Sophisticated composition often needs a shell, a well, and a footer.
- Redundant nesting repeats the same semantic group at successive levels, consumes space, and adds no reading order or interaction boundary.
- Test each layer: “What does this group contain, and what becomes less clear if its surface disappears?” Keep layers with a concrete answer.

## Proportion before decoration
- Establish one primary content axis. Number, delta, chart start, footer icon, and inset rows should align deliberately rather than inherit unrelated padding.
- Begin a medium metric shell at a 20 px radius with a 6 px inset; the nested stage can use 14 px corners so the two curves feel related.
- For compact records, try a 12–14 px shell radius and a 7–9 px property-well radius, with 10–12 px outer content padding.
- Keep radii related to inset and scale; do not mechanically reuse the large shell radius for tiny wells, buttons, and logos.
- Use approximately 6–8 px within a close relationship, 12–16 px between content groups, and 18–24 px around the dominant stage.
- Optical spacing matters: a logo's visible bounds and a large numeral's sidebearing may need small adjustments beyond CSS box alignment.
- Prefer a 1 px quiet shell boundary and, if needed, a shallow shadow. Separate the upper stage by fill before adding another outline.
- Reserve saturated color for a meaningful data series, delta, status, or event marker. Avoid tinting the entire card to compensate for weak hierarchy.
- Fit the object to its content and grid role; do not stretch three unrelated summaries into equally empty rectangles simply for symmetry.
- Give comparable cards matching slots and baselines; permit different internal rhythms when the information genuinely differs.
- Keep routinely read metadata, category labels and status text around 12–13px at normal desktop scale. Reserve smaller captions for genuinely secondary notation; do not shrink the whole supporting hierarchy to 10px to make a card appear sophisticated.
- Give adjacent card bands an intentional shared alignment or a clearly justified different width. A large unexplained gap at the end of one band can make the shell feel unfinished.

## Variant A — metric with an evidence stage
```text
┌─ shell ────────────────────────────────┐
│ ┌─ pale content stage ───────────────┐ │
│ │ PRIMARY VALUE                     │ │
│ │ delta + concise context           │ │
│ │                                   │ │
│ │ meaningful segmented meter/series │ │
│ └───────────────────────────────────┘ │
│   Keyline glyph  Metric identity      │
└───────────────────────────────────────┘
```
- **Reading order:** value → change/context → evidence → metric identity. The footer labels the card; do not repeat the same label at the top by habit.
- Start the value around 36–44 px with a compact line height and tabular numerals; use weight and spacing appropriate to the chosen typeface.
- Keep currency/unit attached to the value, with a controlled smaller scale where useful; avoid making the unit so faint that the value becomes ambiguous.
- Place the delta immediately below, sharing the value's left edge. Combine a Keyline directional glyph, signed value, and context with one coherent baseline.
- Give the evidence region its own breathing room, approximately 18–24 px after the support line, rather than distributing every row evenly.
- For a segmented meter, try narrow vertical capsules: 3–5 px width, 3–4 px gaps, and 22–30 px height, with active and remaining segments sharing geometry.
- Calculate filled segments from a real ratio; ensure the displayed value and denominator explain what the meter measures.
- The remaining segments should be quiet but visible. Do not make every segment a thick, square orange tile when the target calls for fine rhythm.
- Use a sparkline only when a real ordered series supports it; preserve consistent line weight and an uncluttered baseline.
- Without valid comparison or series data, omit the corresponding delta/graph and shorten the stage; a defined supporting amount can carry the second reading.
- A footer around 42–52 px can hold an 18–20 px Keyline fill or duotone glyph and a 14–16 px label on the same content axis.
- Keep the footer white and visually attached to the shell. Its stable identity anchors the more expressive upper stage.

## Variant B — task or record with a property well
```text
┌─ shell ────────────────────────────────┐
│ authentic brand SVG / object glyph    │
│ Record title                          │
│ Record ID                             │
│ ┌─ quiet property well ─────────────┐ │
│ │ glyph  Property       Value       │ │
│ │ glyph  Property       Value       │ │
│ │ glyph  Property       Value       │ │
│ └───────────────────────────────────┘ │
│ attachment count · updated time       │
└───────────────────────────────────────┘
```
- When the record represents an app/company and a logo belongs in the design, use its genuine SVG as a small identity anchor, typically 20–24 px, above or beside the title. An unbranded task may instead use a relevant Keyline object glyph or a text-only identity; never present that glyph as a company logo.
- Give the title the strongest text emphasis in this card, typically 13–15 px at compact density; place the muted record ID directly below.
- Avoid oversized headings on dense boards. Let title length and line count reflect the actual task names rather than uniform placeholder copy.
- Leave approximately 10–14 px between identity/title and the property well; use closer spacing between title and ID.
- Build the well as one near-neutral inset surface, not a separate bordered card for each property.
- Use a stable three-column grid: `14px minmax(64px, 0.8fr) minmax(0, 1.2fr)` as an initial compact desktop structure.
- Keep glyphs quiet, labels secondary, and values darker. Align repeated values along one column; do not center each row independently.
- Start with 24–28 px row height and 8–10 px well padding; tune to language, content length, and density.
- Display 2–4 useful properties rather than filling a quota. Avoid repeating the title, board status, or visible group heading without purpose.
- Finish with a small unboxed utility row: a Keyline attachment/comment glyph with a real count, then a time glyph and actual update time where available.
- Keep footer metadata visually subordinate to the well; tiny utilities must not compete with the record's name.
- Let sibling cards share logo/title/well/footer slots; reserve room for expected title variation so property wells align across the row.

## Variant C — collaboration block with an event inset
```text
┌─ collaboration shell ──────────────────┐
│ overlapping avatars   participant text│
│                                       │
│ ┌─ event inset ─────────────────────┐ │
│ │ ▎ Event title                     │ │
│ │ ▎ time / location / linked record │ │
│ │                         action    │ │
│ └───────────────────────────────────┘ │
└───────────────────────────────────────┘
```
- Give the outer card one job: communicate who is involved. Let the inset communicate what happens next.
- Use genuine participant imagery when supplied; keep avatar overlap modest and separate edges with the surrounding surface color.
- Attach the participant count or scheduling sentence to the avatar group, not to a distant corner of the card.
- A compact overflow count may complete the avatar group when derived from actual participants; never fabricate faces or attendance.
- Use the event inset's surface and narrow semantic color marker to establish a second level without giving it a competing heavy border or shadow.
- A 3–4 px marker, 10–14 px inset padding, and 12–16 px separation from the participant row are useful starting points.
- Make the event title the inset's anchor; align time, location, and related-record metadata beneath it, rather than scattering badges around the perimeter.
- Add an action only if the workflow needs one; keep it attached to the event, with placement that survives title wrapping.
- Multiple events can repeat within one collaboration shell when their relationship is real. Do not add nested shells around every metadata line.
- This is a proposed extension of the visible reference, not a claim about content hidden below the screenshot crop.

## A concrete shell and stage scaffold
```css
.metric-card {
  padding: 6px;
  border: 1px solid #e9eaec;
  border-radius: 20px;
  background: #fff;
  display: grid;
  grid-template-rows: auto auto;
}
.metric-stage {
  padding: 18px;
  border-radius: 14px;
  background: #fafafa;
  min-width: 0;
}
.metric-evidence { margin-top: 22px; }
.metric-footer {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px 18px 10px;
}
```
The stage and footer share a content axis 24 px inside the shell's border: 6 px shell inset + 18 px content padding. Adapt these values as a coordinated set.

## Exact weak → strong repairs
- **Weak:** “Monthly cost” above a large amount, with an unrelated wallet icon in the opposite corner of one empty white box. **Strong:** put the amount and real supporting annual amount in a pale stage, shorten it to fit, then place a Keyline glyph and “Monthly cost” together in the white footer. Add evidence only when available.
- **Weak:** a budget value followed by heavy square segments filling a wide generic card. **Strong:** establish the stage/footer split, replace blocks with proportioned narrow capsules, connect the meter to the actual used/limit values, and align number, support line, meter start, and footer identity.
- **Weak:** a short tiny meter stranded in a wide stage. **Strong:** size the card and track together. Use a sensible normalized segment resolution with the actual value available in text, or make the stage narrower; do not stretch a small number of ticks into large blocks or invent additional data.
- **Weak:** app initials, task title, and three loose metadata lines floating in a white card. **Strong:** genuine SVG logo → title/ID group → one inset, column-aligned property well → understated utility footer.
- **Weak:** a participant count, oversized event title, and button distributed across equal empty rows. **Strong:** a close avatar/text header above a compact event inset with a narrow marker and grouped event metadata.
- **Weak:** nested card wrappers with identical borders, radii, and padding. **Strong:** retain the purposeful outer object and inner information group; remove duplicate strokes, vary radii with inset, and make the supporting footer unboxed.

## Identity and finish gate
- UI glyphs must come from **Keyline**, using its fill, stroke, or duotone variants deliberately; do not substitute generic icon packs or improvised Unicode symbols.
- App/company identities must use **genuine SVG logos**. Never substitute typed initials, generic glyphs, invented marks, or PNG logos inside decorative wrappers.
- Preserve the authentic SVG's shape, proportions, and supplied colors; use its own intended background when present instead of adding an arbitrary badge container.
- If the required SVG is unavailable, obtain the genuine asset before declaring identity treatment finished; do not disguise a placeholder as a logo.
- Every embedded input, select, dropdown, date picker, number field, and related control must have a custom visual treatment, including its expanded popup, options, calendar, and states; raw browser controls and unstyled library defaults are unfinished.
- Preserve native semantics beneath the custom skin or use accessible primitives; match control surfaces, selection marks, spacing, and Keyline glyphs to the card while retaining real keyboard, focus, and editing behavior.
- Inspect cards at normal viewing size: the dominant value/title, inset group, and supporting edge must read immediately without zooming.
- Verify aligned internal axes, related corner radii, restrained borders, deliberate empty space, and coherent slots across siblings.
- Check real long titles, wide values, missing data, and narrow widths. Reflow or simplify slots deliberately; never shrink every element to preserve a desktop miniature.
- Keep the page's surrounding surface quiet enough to reveal card anatomy; judge the cards in the complete layout, not only as isolated components.

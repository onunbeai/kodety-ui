# Icons and logos

Use **Keyline Icons for every interface glyph** and **authentic SVG artwork for company and app logos**. These are separate asset classes. A generic icon cannot stand in for a brand mark, and a brand logo is not a substitute for an action icon. Apply this standard throughout custom controls, navigation, tables, panels, empty states, and feedback.

## Keyline is the required icon family

Use the actual [Keyline Icons library](https://keylineicons.com/), not a similarly named set or the general idea of drawing on keylines. Obtain glyphs from a verified installed package, the official registry, official SVGs, or the verified Keyline collection through a compatible adapter. Do not silently substitute another library, emoji, Unicode pictograms, CSS-drawn glyphs, or hand-drawn approximations.

The verified React package is `@keyline-icons/react`. Use the project's package manager and dependency conventions. Each style has its own entry point; the following exports are documented:

```tsx
import { Bell as BellStroke } from "@keyline-icons/react";
import { Bell as BellDuotone } from "@keyline-icons/react/duotone";
import { Bell as BellFill } from "@keyline-icons/react/fill";
```

Do not invent a `weight` or `variant` prop to switch styles. Verify the actual glyph export in the installed version before importing it. Stroke coverage is broader than duotone or fill; an available stroke glyph does not prove the other variants exist. Sharp corner variants have separate paths, including `/sharp`, `/sharp/duotone`, and `/sharp/fill`. Keep corner treatment consistent within the interface. [Official installation guide](https://keylineicons.com/install)

Components use standard SVG props plus `size` and inherit `currentColor`. Check the component's CSS when a size prop appears ineffective: classes can override width/height attributes. Preserve native geometry and optical weight at compact sizes; do not thin strokes merely to make the UI look delicate. [React package](https://www.npmjs.com/package/%40keyline-icons/react)

## Source options and verification

| Delivery method | Verified route | Check before use |
| --- | --- | --- |
| React dependency | `@keyline-icons/react` and its style entry points. | Installed exports, supported SVG props, dependency lockfile, build output. |
| Local SVG / JSX | Copy from the official browser or the official repository's `icons/<style>/<name>.svg`; sharp assets use `icons/sharp/<style>/<name>.svg`. | Exact glyph, style, viewBox, paths, and asset provenance. |
| Official CLI | `npx @keyline-icons/cli search arrow`; `npx @keyline-icons/cli add bell --out src/icons`. | Confirm names first; inspect generated files rather than assuming variant coverage. |
| shadcn registry | Register `"@keyline": "https://keylineicons.com/r/{name}.json"`; add `@keyline/bell` or `@keyline/fill/bell`. | Existing registry configuration and the generated component source. |
| Iconify adapter | Collection prefix `keyline-icons`; examples include `keyline-icons:bell` and `keyline-icons:bell-fill`. | Actual collection entry and variant; bundling or network-loading behavior for the chosen adapter. |

These routes are documented by the [official repository](https://github.com/keyline-icons/keyline-icons) and [installation guide](https://keylineicons.com/install). Use the current project version's real assets; do not hardcode a catalog count or assume a newly documented glyph already exists locally. Preserve applicable notices when distributing copied SVGs under the repository's [MIT license](https://github.com/keyline-icons/keyline-icons/blob/main/LICENSE).

## Purposeful style selection

| Style | Preferred role | Constraint |
| --- | --- | --- |
| Stroke | Dense toolbars, input adornments, chevrons, row actions, secondary navigation. | Maintain enough visual weight to remain clear at actual size. |
| Fill | Selected navigation, an active toggle, or a compact emphasis signal. | Use a real fill asset. Keep shape and meaning stable across states. |
| Duotone | Object/category cues and selected places where a soft secondary plane improves recognition. | Preserve the supplied geometry and opacity treatment; avoid applying it to every tiny control. |

These mappings establish consistent roles, not a requirement to show all three styles on every screen. Confirm that a state transition has the required genuine variants. Do not fabricate fill or duotone by forcing `fill` onto stroke paths, and do not choose an unrelated glyph merely to obtain a different weight.

Custom checkboxes, radio controls, selects, comboboxes, date fields, search fields, and clear buttons must use Keyline for their visible glyphs while retaining appropriate native or accessible primitive semantics. Audit internal defaults from component libraries: checkmarks, arrows, close buttons, validation symbols, and loading icons are part of this requirement too.

Use a verified suitable Keyline glyph for icon-based loaders; do not assume an export such as `Loader` exists. Keep loading text and busy state accessible, preserve layout, and respect reduced motion. A custom-styled native progress element or non-icon progress bar remains a data/control visualization, not permission to expose browser-default styling or introduce another icon family.

## Icon accessibility and optical checks

- Put interaction semantics on the button, input, or other control; the SVG alone does not create an accessible control.
- Hide decorative glyphs from assistive technology when adjacent text or the control label already names the action. Give icon-only controls a specific accessible name.
- Keep focus visible and targets usable independently of glyph size. Selected, invalid, and loading states must not rely solely on icon style or color.
- Use consistent icon slots and align apparent ink area, not only SVG boxes. Preserve `viewBox`, paths, caps, and joins; adjust placement and size rather than distorting the drawing.

## Authentic SVG company and app logos

Whenever a company or app logo is shown, always use its real vector SVG artwork. This does not require adding a logo beside every textual mention of a company. Do not create branded initial tiles, generic substitutes, emoji marks, guessed wordmarks, traced redraws, or raster images embedded inside an SVG wrapper. Renaming a PNG or wrapping it in `<svg><image>` does not satisfy this rule.

Follow this sourcing order:

1. Reuse an approved existing SVG asset whose identity and provenance are known.
2. Obtain the correct SVG variant from the company's or app's official brand resources, press kit, or official product assets.
3. Use an exact vector from a trustworthy package only after verifying the asset's identity and provenance against an official source. Record the package/version, original source URL, and selected variant.

Do not infer authenticity from a filename, search thumbnail, or resemblance. Do not purchase assets, invent download URLs, extract private files, or rely on unverified logo data. Confirm whether the intended asset is a symbol, wordmark, app icon, or lockup and use the authentic variant that fits the context.

Preserve the SVG's paths, viewBox, proportions, clear space, and supplied multicolor treatment. Do not apply blanket `currentColor`, grayscale, clipping, extra strokes, or arbitrary corner rounding to a logo. Use an official monochrome or dark-surface variant when available and appropriate. Size logos optically within a consistent slot without stretching or reconstructing them.

A decorative logo beside the visible company/app name can be hidden from assistive technology. A standalone identity needs an accessible name. Keep source and variant information in the asset manifest or implementation notes so another reviewer can verify it.

## Missing assets: explicit, limited fallback

For a missing Keyline variant, first check other official delivery routes or verified local assets. An available stroke version or equivalent Keyline glyph may be used only when it preserves meaning and the requested style allows it; document the choice. If the exact variant is required, report the missing asset instead of silently changing it. Never fall back to another icon family.

For an unavailable logo that the design requires, temporarily show the plain textual company/app name. Do not style initials as a substitute logo. Mark that logo requirement as unresolved in the review or delivery notes, keep the result visibly identifiable as text, and do not claim the asset work is complete. A deliberately text-only identity with no logo requirement is valid; it is not permission to remove a required logo merely to avoid sourcing it.

Continue independent layout, behavior, and refinement work while resolving assets. Ask for the exact missing asset or user direction only when official sourcing and verified local options are exhausted and completion depends on it. Keep usable text actions where possible; never disguise a missing asset with forged artwork.

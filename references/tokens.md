# Tokens, proportions, and usage

This is a starting preset for the screenshots' light direction. These values define Kodety UI's default roles. [kodety-ui.css](../assets/kodety-ui.css) implements this preset within the `.kodety-ui` scope. Integrate by role and adapt to the existing system.

Tokens are not the design recipe. Select the sidebar and card anatomy first, then tune these values together. Reusing one generic card radius, padding and border everywhere will not reach the required visual standard.

## Color by role

| CSS token | Value | Use for | Do not use for |
|---|---|---|---|
| `--ku-canvas` | `#f6f6f5` | Outer background and chrome | Text |
| `--ku-surface` | `#ffffff` | Workspace, card, overlay | Every region indiscriminately |
| `--ku-surface-soft` | `#f9f9f8` | Tonal field, internal grouping | The only indication of selection |
| `--ku-surface-hover` | `#f0f0ee` | Hover and secondary actions | Saved/error states |
| `--ku-line` | `#e7e7e4` | Dividers and decorative outlines | The only way to identify an input |
| `--ku-control-edge` | `#858580` | Field boundaries when needed for identification | Outlining every card |
| `--ku-ink` | `#222321` | Primary content | Text on a dark surface |
| `--ku-secondary` | `#565952` | Labels and secondary information | Indicating disabled state on its own |
| `--ku-muted` | `#696c65` | Metadata and readable placeholders | Primary values that need emphasis |
| `--ku-action` / `--ku-on-action` | `#252623` / `#ffffff` | Neutral primary action | Every toolbar button |
| `--ku-focus` | `#2563eb` | Perceptible focus and active indication | Repeated decorative backgrounds |
| `--ku-selection` / `--ku-selection-ink` | `#eff6ff` / `#1d4ed8` | Selected row/item | Error or success |
| `--ku-danger` / `--ku-danger-soft` | `#b4233a` / `#fff1f2` | Errors and contextual destructive actions | Arbitrary accents |
| `--ku-success` / `--ku-success-soft` | `#246347` / `#eaf6ee` | Success state | Numeric changes without semantic interpretation |
| `--ku-warning` / `--ku-warning-soft` | `#875507` / `#fff5de` | Attention and pending states | Promotional CTAs by default |
| `--ku-data-accent` | `#f36b21` | Segmented progress/chart | Small text on white |

A light border can organize a card without identifying an input. If the field's appearance relies on an outline, use a distinguishable border. If the project's implementation already provides sufficient affordance through shape and surface, adapt the outline and check the rendering. Do not reduce everything to near-white gray merely to resemble the image.

### Soft category colors

| Family | Background | Text |
|---|---|---|
| Lavender | `#f0edff` | `#5743a6` |
| Green | `#eaf6ee` | `#246347` |
| Pink | `#fcecf5` | `#98366a` |
| Blue | `#eaf2ff` | `#285da5` |
| Amber | `#fff5de` | `#875507` |

Choose one family per category. Keep names and states readable without relying on color. Do not use tag background tints as text colors without checking the final pair. When changing theme, recalibrate every pair, including hover and selected states.

## Typography

Use the project's approved font. If none is defined, start with a system sans; Inter or Geist are options when available and appropriate. The skill does not distribute fonts or require a download.

| Role | Starting point | Note |
|---|---|---|
| Label/metadata | 12–13px, 400–500, line-height 1.4 | Never fade out necessary information |
| Main UI | 14px, 400, line-height 1.45 | Compact desktop baseline |
| Input | 14px desktop; 16px for touch when appropriate | The value should fit without looking like a caption |
| Object title | 24px, 500–600, line-height 1.2 | Slight tracking of −0.02em, calibrated to the font |
| Section | 16–18px, 500–600, line-height 1.35 | Not every section needs a huge heading |
| Metric | 32px, 500–600, line-height 1.1 | Tabular numerals and a proportional unit |
| ID/shortcut | 12px, optional mono | Do not turn all body text into mono |

Avoid negative tracking in microcopy and weight 300 as artificial refinement. Use approved, available fonts instead of introducing a proprietary font dependency for appearance alone. Do not use font smoothing as a substitute for appropriate weight or contrast.

## Geometry

| Family | Initial values |
|---|---|
| Gaps | 4, 6, 8, 12, 16, 24, 32px |
| Radii | Tag 6px; input/button 8px; record card 12–14px; popover 12px; metric shell/panel 20px; inset metric stage 14px |
| Heights | Compact control 32px; default 36px; touch 44px or larger |
| Padding | Field 10–12px horizontal; card 16–20px; panel 20–24px |
| Icons | 14–16px in controls; 18–20px in navigation |
| Property/table row | 36–44px for a simple case; grows for chips or text |
| Metric composition | 6px shell inset + 18px stage/footer padding; coordinated content axis, not independent offsets |
| Sidebar | 208–248px expanded; 56–72px rail; desktop rows 28–32px with shared icon/text/trailing slots |

These are references, not a mandatory grid. Field height becomes `min-height` when content can grow. Do not clip translated or zoomed content to preserve measurements. Chips can wrap; elements within a clause must remain grouped intelligibly.

## Elevation

| Role | Initial recipe |
|---|---|
| Static card | 1px border, usually no shadow |
| Secondary button | `0 1px 2px rgb(20 25 20 / 5%)` + a subtle inner highlight |
| Popover | `0 12px 32px rgb(20 25 20 / 10%), 0 2px 6px rgb(20 25 20 / 5%)` |
| Floating drawer | A slightly broader shadow only when overlaying content |
| Input | Subtle surface; inset is optional, not necessary |

Focus uses a visible outline, not just a shadow. Border, hover, invalid, and focus states must compose without canceling each other. Do not increase a 1px border to 2px on hover and change geometry; reserve space or use an outline.

## CSS integration

The CSS provides local tokens and opt-in `ku-*` classes. It does not include a global reset, popover positioning, events, focus management, or persistence. Those remain application responsibilities. All final controls must be custom styled, including their open popups; using this file does not excuse leaving a native select or date popup in the UI.

Available classes: `ku-surface`, `ku-panel`, `ku-popover`, `ku-button` (`data-variant="primary"` and `"ghost"` variants), `ku-label`, `ku-field`, `ku-input`, `ku-affix`, `ku-help`, `ku-error`, `ku-chip`, `ku-property`, `ku-property-value`, and `ku-metric`. The focus selector also works on native controls within the scope.

Composition primitives are also available:

- `ku-composed-card` → `ku-card-stage` with `ku-card-value`, `ku-card-context`, and optional `ku-card-evidence` → `ku-card-footer`.
- `ku-record-card` → identity/title with `ku-record-heading` → `ku-property-well` containing aligned `ku-property-well-row` groups → `ku-record-footer`.
- `ku-sidebar` → `ku-sidebar-header` → `ku-sidebar-scroll` with `ku-nav-group`, `ku-nav-group-label`, and `ku-nav-item` → `ku-sidebar-footer`.
- `ku-icon` sizes a genuine Keyline SVG; `ku-brand-logo` preserves an authentic SVG logo's aspect ratio. These classes do not create or source artwork.

Use valid semantics with these classes. For example, a metadata well can be a `dl` whose row `div`s contain a `dt` (with its decorative icon and label) and a `dd`. A navigation item is a real link or button; the current route uses `aria-current="page"`. The application supplies the shell height, responsive navigation trigger/drawer, actual routes, and disclosure behavior.

For a compound field, apply `data-invalid="true"` to the wrapper **and** `aria-invalid="true"` to the input. Associate help/error text through `aria-describedby`; appearance does not create semantics. To disable a control, apply `disabled` to the actual control; `data-disabled` only styles the wrapper. Do not use a `label` wrapper around several independent buttons.

This preset is light. For a dark theme, override every surface/text/state role and check contrast; do not place the unchanged light CSS on a dark product. For Kodety Builder, adapt classes and cascade to the native contract and let its own runtime handle motion.

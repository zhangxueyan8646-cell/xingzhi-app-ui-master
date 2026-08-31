# Icon 图标

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Icon 图标` (`6:5259`) and `Icon 图标 - 组件` (`6:8607`).

## Purpose

Use icons as visual representations of sub-functions. Reuse the documented icon component whenever one exists; do not redraw an existing concept or substitute a merely similar glyph.

## Drawing grid

- Default drawing canvas: `20 × 20px`.
- Keep `2px` of elastic space on each edge. The normal artwork keyline is therefore approximately `16 × 16px`, centered in the canvas.
- The elastic area may be used when the icon's visual weight or silhouette needs optical compensation. Preserve the `20 × 20px` outer canvas and keep the result visually centered.
- The line-icon example is labeled `20 × 20`, stroke weight `1px`.
- Align icons by optical center as well as by their outer box; do not mechanically stretch artwork to touch every keyline.

## Icon families

### 面型 icon

Filled or filled-plus-detail artwork may combine one or more elements and may use gradients. Use it for prominent entry points, especially the home-page 金刚区 and important first-level modules.

| Context | Component size | Guidance |
|---|---:|---|
| 金刚区 | `60 × 60px` | Rich, multicolor or gradient module-entry icon |
| 信息流 | `20 × 20px` | Compact colored category marker |
| 个人中心 primary shortcuts | `32 × 32px` | Prominent personal-center shortcut |

Treat the colors and gradients inside these components as part of the asset. Use the existing component instead of recoloring individual paths or recreating the palette.

### 线型 icon

Use line icons on second- and third-level pages or before supporting prompt information. The personal-center line set is documented at `20 × 20px` with a `1px` stroke.

- Keep stroke weight, corner treatment, line caps, and visual density consistent with the source component.
- Use a single semantic foreground color unless an approved component contains a deliberate accent.
- Do not mix unrelated icon libraries or line weights in the same interface.

### 面线交互

Use paired outline and filled states when an icon has an interactive selected or activated state. The component page includes state pairs for navigation entries and actions such as collection, like, filter, self-selected, add, sort, and directional arrows.

- Default or unselected: use the documented outline/quiet treatment.
- Selected, highlighted, or activated: switch to the corresponding filled or cyan-highlight component.
- Keep the icon's outer box and optical position stable between states; do not create a visible layout jump.
- Do not communicate state with color alone when adjacent text, labels, or accessibility semantics are available.

### 系统 icon

System icons are globally reusable actions and status controls. Prefer the existing large or small component rather than scaling one family to imitate the other.

| Family | Typical source sizes | Examples |
|---|---|---|
| 系统大图标 | `20 × 20px` | close, share, password, WeChat, search, calendar, pause, more, warning, message, end, settings, question |
| 系统小图标 | `12 × 12px`, `14 × 14px`, `16 × 16px`, or `20 × 20px` according to component | close, share, switch, refresh, delete, check, sort, search, add, like, heat, phone, help, filter, arrow, edit, settings, comment |

Do not infer a size from the word “大” or “小” alone. Select the exact documented component and retain its native box.

## Color and state

- Use the main text hierarchy for neutral system icons: `#222222`, `#555555`, `#999999`, or `#BBBBBB`, chosen by semantic emphasis.
- Use the approved cyan family for active and highlighted states; follow [colors.md](colors.md) for semantic color assignment.
- Preserve deliberate multicolor/gradient fills in 金刚区 and 信息流 components.
- Disabled or unavailable states must remain visibly distinct from default and active states and should follow the documented disabled color token.
- Do not use the specification-page annotation colors or sample-cell borders as product icon tokens.

## Component selection and naming

Choose by semantic family first, then exact action or state:

- `icon/金刚区/{name}` for first-level module entrances.
- `icon/信息流/{name}` for information-feed categories.
- `icon/个人中心/{name}` for personal-center actions and shortcuts.
- `icon/系统大图标/{name}` or `icon/系统小图标/{name}` for global controls.
- State-specific components use suffixes or nested names such as `未选中`, `高亮`, `激活`, `上`, and `下`.

The selected component board contains 34 金刚区 icons, 29 信息流 icons, 35 个人中心 icons, 15 system-large entries, 22 system-small entries, and 9 explicit compact state variants. This inventory describes the selected source snapshot; verify the current MasterGo component library before treating it as exhaustive.

## Implementation rules

- Preserve SVG aspect ratio and render at the component's documented box size.
- Do not stretch, skew, add shadows, or apply arbitrary rounded containers to the icon artwork.
- Keep interactive hit areas separate from artwork size; expanding the touch target must not scale the icon itself.
- Use consistent alignment and spacing when icons appear in a row, navigation bar, list, or action group.
- Give actionable icons an accessible name. When the meaning is not universally clear, pair the icon with a visible label or tooltip.
- If no documented icon matches the required meaning, use the nearest family as a style reference and explicitly disclose that a new asset is required.

## Review checklist

- Correct semantic family and exact component selected.
- Native component size retained.
- `20 × 20px` grid and `2px` elastic margin respected for new default-grid artwork.
- `1px` stroke retained for the documented `20 × 20px` line-icon family.
- Default, highlighted, selected, and disabled states mapped consistently.
- Neutral and active colors match [colors.md](colors.md).
- Multicolor and gradient assets are not improvised or recolored.
- Optical alignment is stable across state changes.
- Actionable icons have adequate interaction semantics and accessible naming.

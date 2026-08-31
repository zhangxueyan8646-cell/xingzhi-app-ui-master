# Dot 徽标

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Dot 徽标` (`6:05832`) and `Dot 徽标 - 组件` (`6:05813`).

## Purpose

Use Dot badges as compact numeric or status markers beside buttons, icons, tabs, navigation items, and feature entrances. The source description is: “通常出现在按钮、图标旁的数字或状态标记。”

Badges supplement their host element; they do not replace the host label, status explanation, or destination.

## Component family

The `徽标` component family defines five variants:

| Variant | Size | Content | Treatment |
|---|---:|---|---|
| 红点徽标 / 小 | `6 × 6px` | none | Red circle |
| 红点徽标 / 中 | `8 × 8px` | none | Red circle |
| 红点徽标 / 大 | `14 × 14px` | none | Red circle |
| 数字徽标 | minimum `14 × 14px` | numeric count | Red full-pill with white number |
| 自定义徽标 | example `28 × 14px` | short text such as `NEW` | Red full-pill with white text |

- Use badge red `#F24949`.
- Use a full-pill radius (`20px` in the source component) for numeric and custom badges.
- Do not scale dot variants to arbitrary intermediate sizes.

## Selecting a type

- Use a plain red dot when only the presence of an unread, new, or changed state matters.
- Use a numeric badge when the exact outstanding count helps the user prioritize or understand scope.
- Use a custom-text badge for a very short status such as `NEW` when a dot would be ambiguous.
- Do not show both a dot and a numeric/text badge on the same host for the same state.
- Remove the badge when the represented state is cleared; do not leave stale urgency markers.

## Numeric badge

- Base height: `14px`.
- One-digit example: `14 × 14px`.
- Overflow example: `99+`, `23 × 14px`.
- Text: PingFang SC, `10px`, weight `600`, line height `14px`, centered, `#FFFFFF`.
- Apply `2px` horizontal padding as content expands; the one-digit component preserves a minimum `10px` content width.
- Cap displayed counts above `99` as `99+`. Keep the exact value available to assistive technology or the destination screen when useful.
- Let one- and two-digit badges grow naturally while preserving `14px` height and the pill silhouette.
- Do not abbreviate financial values or unrelated metrics as notification badges.

## Custom-text badge

- Base height: `14px`; source `NEW` example is `28px` wide.
- Text: PingFang SC, `10px`, weight `600`, line height `14px`, centered, `#FFFFFF`.
- Horizontal padding: `2px` per side in the source component.
- Keep copy extremely short and stable. Prefer `NEW` or another established product label; do not place sentences in a badge.
- If translated copy cannot fit compactly, use a dot or explain the status in the host content instead of shrinking the type.

## Dot sizes

| Size | Use guidance |
|---|---|
| `6px` small | Tight text/tab contexts or subtle status marking |
| `8px` medium | Standard icon or navigation marking |
| `14px` large | Larger icon/feature entrance or prominent status marking |

Choose size according to the host component, not according to the perceived urgency of the same status. Keep equal hosts on one screen consistent.

## Placement

- Anchor the badge to the host element's upper-right visual corner.
- Maintain optical alignment with the actual icon or label shape, not merely the outer layout frame.
- Keep badge placement stable as the host changes state; avoid layout shifts when the badge appears or disappears.
- Allow the badge to overlap the host boundary where documented, but do not clip it with the host container.
- Preserve enough separation to read the badge as attached without obscuring essential icon strokes or text.
- The source combination examples annotate `4px`, `8px`, and `16px` relationships in different host types. Treat these as host-specific compositions rather than one universal offset; reuse the exact assembled component or the host specification whenever available.

## Documented host patterns

The source shows badges used with:

- Top-bar action icons: dot, number, or text badge at the icon's upper-right.
- Tabs: a small red dot immediately after or above a tab label without replacing the active indicator.
- Circular feature entrances: status mark at the upper-right of the icon circle.
- Grid/service shortcuts: `NEW`, dot, or count badge over feature icons.
- Search/header controls: badge attached to the adjacent action icon, not the search field content.

Keep the host's own selected, active, disabled, and focus states independent from its badge state.

## Behavior and accessibility

- Define what event creates and clears each badge before implementation.
- Update the visible count atomically with the underlying unread or pending data.
- Do not make the badge itself a separate tap target unless it represents a distinct action; normally the host remains the interactive target.
- Provide an accessible host label that includes the status, for example “消息，8 条未读” or “财富管理，新功能”.
- Do not rely on red alone. Expose unread/new/count semantics programmatically and retain the number or short text where present.
- Avoid animating badges continuously. If an entrance animation is used, keep it brief and respect reduced-motion preferences.

## Review checklist

- Badge communicates a compact status or count attached to a clear host element.
- Correct variant selected: `6px`, `8px`, `14px`, numeric, or custom text.
- Background is `#F24949`; numeric/custom text is white `10px` semibold with `14px` line height.
- Numeric values above `99` display as `99+` without losing the exact underlying count.
- Custom copy remains short and the badge keeps a `14px` full-pill shape.
- Badge is anchored optically at the upper-right, remains unclipped, and does not obscure the host.
- Host layout, selected state, focus state, and tap target remain stable when the badge changes.
- Visible badge, accessible status, clearing rule, and underlying data remain synchronized.

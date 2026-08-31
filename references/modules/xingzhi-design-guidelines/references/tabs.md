# Tabs 标签导航

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-Tabs 标签` (`6:01511`).

## Purpose

Use Tabs for navigation and selection between related content groups at the same information level. Switching a tab changes the content region while preserving the surrounding page context.

The selected specification defines two visual levels: 一级标签 and 二级标签. It does not document a separate third-level style.

## Shared container

- Reference mobile width: `375px`.
- Navigation region height: `44px`.
- Background: `#FFFFFF`.
- Keep one active item at a time for a single-selection tab group.
- Preserve the user's current selection when content refreshes unless the product flow explicitly resets it.

## 一级标签

Use the primary text-tab style for the main content grouping within a page.

### Item states

| State | Text | Typography | Indicator |
|---|---|---|---|
| Selected | `#222222` | PingFang SC, `16px`, weight `500`, line height `24px` | `14 × 3px`, `#00D2F0`, radius `3px` |
| Unselected | `#555555` | PingFang SC, `14px`, regular, line height `22px` | Transparent / absent |

### Layout

- Container height: `44px`.
- Content starts `16px` from the left in the assembled examples.
- Gap between adjacent text tabs: `16px`.
- Align the selected indicator to the horizontal center of its label.
- Place the indicator at the bottom of the navigation region; the source positions the `3px` indicator from `y = 37px` to `40px` in a `44px` region.
- Keep selected and unselected item boxes stable enough that changing state does not cause the whole row to jump.

## 二级标签

Use compact pill tabs for a subordinate filter or content subdivision below the primary level.

### Item states

| State | Height | Horizontal padding | Background | Text |
|---|---:|---:|---|---|
| Selected | `24px` | `12px` in the base component | `rgba(0, 210, 240, 0.1)` | `#00D2F0`, `12px`, line height `18px` |
| Unselected | `24px` | `8px` in the base component | `#F5F7FA` | `#999999`, `12px`, line height `18px` |

- Pill radius: `13px` in the component set; assembled examples also use fully rounded values such as `20px`. Treat the intended shape as a full pill rather than an arbitrary rounded rectangle.
- Content starts `16px` from the left.
- Gap between adjacent pills: `8px`.
- Vertically center the `24px` pills in the `44px` navigation region. The assembled row uses a `40px` inner region offset `2px` from the top, with pills at `y = 8px` inside it.
- Let width follow the label and documented padding; do not force equal-width pills unless the product requirement explicitly calls for segmented control behavior.

## Overflow behavior

When all tabs do not fit in the available width, the source shows:

- a right-side white gradient mask, `88px` wide;
- a fixed menu/more affordance at the right edge;
- the tab row continuing beneath the fade, indicating additional options.

Keep the active item visible whenever practical. Do not compress labels, reduce the documented font sizes, or shrink the item gaps to force every tab on screen. The selected source does not define the exact gesture or menu behavior, so preserve the product's established horizontal-scroll or overflow-menu interaction instead of inventing a new one.

## Content and interaction

- Use concise, parallel labels that describe mutually exclusive content groups.
- Do not wrap tab labels onto multiple lines.
- Do not use Tabs for sequential steps or for actions that do not switch content.
- Make the entire tab item interactive, not only the visible text or indicator.
- Keep keyboard/focus semantics and selected-state accessibility synchronized with the visual state in implemented interfaces.
- Announce the active item programmatically; do not rely only on color or the underline.

## Implementation guidance

- Reuse `导航/一级导航/字` for primary text-tab states and `导航/二级导航/字` for pill-tab states when the MasterGo component is available.
- Preserve the outer `44px` navigation height and the native component metrics.
- Use [colors.md](colors.md) and [typography.md](typography.md) rather than substituting similar colors or fonts.
- Keep the underline centered under the selected label during animation or state changes.
- If the tab content is loaded asynchronously, keep the selected label and indicator stable while showing loading feedback in the content region.

## Review checklist

- Correct level selected: 一级 text tab or 二级 pill tab.
- One clear selected state per single-selection group.
- Container height, left inset, item gap, type scale, and colors match this reference.
- 一级 indicator is `14 × 3px`, cyan, rounded, and centered.
- 二级 pills are `24px` high with `8px` gaps and full-pill geometry.
- Labels remain single-line and readable.
- Overflow does not hide the active item or silently truncate available choices.
- Visual, focus, and accessibility selected states remain synchronized.

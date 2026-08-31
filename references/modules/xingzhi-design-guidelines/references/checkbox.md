# Checkbox 多选框

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Checkbox 多选框` (`6:03596`) and `Checkbox 多选框 -组件` (`6:03561`).

## Purpose

Use Checkbox when the user may select zero, one, or multiple items from a group of available options. Do not use it for exactly one mutually exclusive choice, an immediate on/off setting, or an action.

The source description is: “一般应用于用户在一组可选项中进行多选操作的场景。”

## Component sizes

The `checkbox-多选框` component family has two native sizes:

| Size variant | Native size | Recommended role |
|---|---:|---|
| 大 | `20 × 20px` | Standard mobile lists, forms, bottom sheets, and primary selection tasks |
| 小 | `16 × 16px` | Compact or information-dense layouts where the smaller control remains clear |

- Keep one size within a single option group.
- Preserve the native icon artwork and proportions; do not redraw it as a square checkbox.
- Increase the interactive hit area around the visual control as needed without scaling the icon artwork.

## States

The source defines five visual states in both sizes:

| State | Meaning | Source treatment |
|---|---|---|
| 未选 / 默认 | Available and not selected | Circular neutral outline; source color `#E6EBF0` |
| 选中 / 激活 | Selected and removable from the selection | Cyan filled circle with a white check |
| 选中不可取消 | Selected by rule and cannot be cleared | Checked appearance with reduced cyan emphasis; remains selected |
| 半选 | A parent or aggregate represents a partially selected child set | Cyan filled circle with a white horizontal minus |
| 禁用 | Unavailable for interaction | Low-emphasis neutral filled circle |

- Use `#00D2F0` as the active cyan in the documented screen; keep colors aligned with [colors.md](colors.md).
- Do not communicate state by cyan alone: check, minus, neutral outline/fill, programmatic value, and interaction availability must agree.
- “选中不可取消” is not another selected value. It is a selected item whose availability is locked.
- “半选” is an aggregate state, not a third user-selectable value for an ordinary standalone option.

## Group behavior

- Each available option toggles independently; selecting one item must not clear another selected item.
- The group may validly contain zero, one, or multiple selected items unless product rules specify a minimum or maximum.
- If a parent or “select all” control represents children, derive its state from the child set:
  - no available children selected → 未选;
  - every available child selected → 选中;
  - some but not all available children selected → 半选.
- When the user activates a half-selected parent, apply the product-defined bulk action consistently, normally selecting all currently available children. Make the resulting state unambiguous.
- Locked selected items remain included when users change other selections. Do not make them look enabled if they cannot be cleared.
- Disabled items cannot toggle. Preserve their current value in data rather than silently changing it.

## Layout and content

- Give the option set a clear title or field label when its purpose is not already obvious.
- Use short, parallel option labels. Keep selectable and unavailable choices understandable without relying on color.
- Make the entire option row interactive for available items, not only the circular icon.
- Align controls consistently with single-line labels or the top of multi-line content.
- Keep icon-to-label spacing and row rhythm consistent throughout a group; use the surrounding screen or form specification when it defines exact spacing.
- Do not mix Checkbox and Radio visuals in one semantic selection group.

## Combined bottom-sheet pattern

The documented combined example places a multi-select list inside a mobile bottom sheet:

- The sheet uses rounded top corners and a centered title with a close action.
- Options form a vertical list; multiple rows may be active at the same time.
- A bottom action area contains `取消` and `确定` buttons.
- The confirm action is visually low-emphasis when no valid change or selection is ready, and becomes the cyan primary action after a valid selection is present.
- Keep the current working selection visible while the sheet is open. Commit it according to the product flow when the user confirms; cancel must not unexpectedly persist staged changes.

Treat the phone mockups as a composition example, not a source for undocumented spacing or typography tokens. Use the dedicated color, typography, and radius references for implementation values.

## Accessibility and implementation

- Reuse the MasterGo `checkbox-多选框` component family and its exact size/state variant when available.
- Expose programmatic checked, unchecked, disabled, and mixed/indeterminate states on platforms that support them.
- Keep focus, keyboard, screen-reader, and touch behavior synchronized with the visible state.
- Announce locked selected items and disabled choices clearly when the reason is not self-evident.
- Do not shrink the visual component below `16 × 16px` or use the large and small variants as arbitrary decorative icons.

## Review checklist

- Checkbox is used for zero-to-many selection, not single selection or an immediate setting.
- The whole group uses the correct native size: `20 × 20px` or `16 × 16px`.
- Unselected, selected, selected-immutable, half-selected, and disabled states are visually and behaviorally distinct.
- Multiple standard options can remain selected simultaneously.
- Half-selection is derived from a child set and is not used as an ordinary standalone value.
- Locked and disabled values cannot be changed but remain accurately represented in submitted data.
- The option-row hit area, label alignment, focus behavior, and accessible state are clear.
- In the bottom-sheet pattern, staged selection, cancel, confirm, and confirm-button emphasis remain synchronized.

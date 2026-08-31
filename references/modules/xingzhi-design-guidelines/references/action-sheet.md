# Action Sheet 动作条

## Purpose

- Use Action Sheet to expose multiple related operations while optionally carrying a short title or a small amount of supporting information.
- Present it from the bottom of the screen over a `40%` black mask.
- Choose a vertical text list for command choices and a horizontal icon layout for visually distinct tool or source choices.

## Vertical layout

- Use a `359px`-wide action group with `8px` screen-side margins on a `375px` mobile canvas.
- Each option row is `359 × 56px`, centered, with `16px` PingFang SC text, `20px` line height, and default color `#222222`.
- Separate adjacent options with a `1px` `#E6EBF0` divider. Round the list container to `8px`.
- Place Cancel in its own `359 × 56px` white row, separated from the option list by an `8px` gap; use an `8px` radius.
- A five-option list is `359 × 280px`; together with the separated Cancel row the action group is `359 × 344px`.
- Keep labels concise and unambiguous. Avoid wrapping ordinary action labels.

## Supporting information and destructive actions

- When clarification is necessary, place a short centered reminder in the top area of the option list rather than adding another selectable row.
- Supporting text uses `12px`, `15px` line height, and `#BBBBBB`; allow wrapping only for this reminder text.
- Use `#D62B1F` for destructive or irreversible actions. Do not style Cancel as destructive.
- Visually separate destructive actions from neutral actions when the consequences differ materially.

## Horizontal layout

- Use a `375px`-wide bottom sheet with `16px` top-left/top-right radius and a total reference height of `166px`, including the `34px` Home Indicator safe area.
- The title row is `375 × 44px`. Center the title with `16px`, medium (`500`), `22px` line height, and `#222222`.
- The action row is `375 × 72px`. Each action item is `56px` high with `6px` vertical padding, `4px` icon-to-label gap, and `8px` radius.
- Use a `28 × 28px` icon and a centered `14px` label with `16px` line height and `#555555`.
- For three actions, distribute three `109px` items evenly across the row.
- For four actions, use `60px` items with `18px` horizontal row padding and equal distribution.
- When actions exceed the available width, keep `60px` items and horizontally scroll the entire row; do not pin the first or last item.

## Interaction

- Tapping an action closes the sheet and starts that action unless the operation requires an explicit confirmation flow.
- Tapping Cancel or the mask closes the sheet and restores the underlying page without changes.
- Preserve bottom safe-area clearance and keep fixed navigation behind the mask.
- Announce the sheet as a modal group, move focus into it when opened, and return focus to the trigger when closed.

## Review checklist

- Confirm vertical versus horizontal layout matches the operation type.
- Confirm `8px` side margins, row dimensions, dividers, corner radius, and Cancel separation for vertical lists.
- Confirm title, icon, label, item, row, safe-area, and sheet geometry for horizontal layouts.
- Confirm three/four-item distribution and overflow scrolling behavior.
- Confirm reminder copy is non-interactive and destructive actions use the danger color.
- Confirm mask, selection, Cancel, outside-tap, focus, and return behavior.

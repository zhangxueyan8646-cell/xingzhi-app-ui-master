# Switch 开关

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Switch 开关` (`6:02452`) and `Switch 开关 - 组件` (`6:02412`).

## Purpose

Use Switch when the user directly enables or disables a function and the setting has two persistent states. The change should take effect immediately; do not use a Switch as a substitute for a checkbox, radio group, or submit action.

## Base component

- Native component size: `44 × 24px`.
- Keep the track fully rounded and the circular thumb vertically centered.
- Preserve the native thumb inset and travel distance by reusing the component; do not redraw or stretch it.
- Keep the visual control size separate from its larger interactive hit area.

Use the component set `switch-开关/打开、关闭、禁用、加载` when available.

## States

The selected component set defines four states:

### 打开

- Use the cyan active track and a white thumb positioned on the right.
- Map this state to the semantic value “on / enabled”.
- Use [colors.md](colors.md) for the active cyan token; do not substitute another bright blue or green.

### 关闭

- Use the neutral gray track and a white thumb positioned on the left.
- Map this state to “off / disabled by user”.
- Keep it interactive unless another product rule disables control.

### 禁用

- Use the documented light-gray treatment and reduced emphasis.
- Do not allow interaction or focus-driven changes.
- Preserve the underlying boolean value in semantics; disabled is an availability state, not a third value.
- When the reason is not obvious, explain it in adjacent text rather than inside the Switch.

### 加载

- Use the dedicated loading variant, which includes a progress treatment inside the control.
- Prevent repeated toggles while the change is pending.
- Keep the last confirmed setting until the operation succeeds; if it fails, restore the confirmed state and show feedback outside the control.
- Do not replace loading with the disabled variant because the two states communicate different meanings.

## Cell composition

Use `switch-开关/单元格开关` for list or settings rows.

| Property | Value |
|---|---:|
| Reference width | `375px` |
| Row height | `48px` |
| Horizontal padding | `16px` |
| Vertical padding | `12px` |
| Gap between row elements | `8px` |
| Background | `#FFFFFF` |
| Row radius | `8px` |
| Main label | `#555555`, PingFang SC, `14px`, line height `20px` |
| Optional status text | `#999999`, PingFang SC, `12px`, line height `18px` |
| Switch | `44 × 24px` |

- Let the main label take the flexible remaining width.
- Place optional state copy such as `已开通` or `未开通` immediately before the Switch.
- Keep status copy synchronized with the actual boolean state; do not show “已开通” beside a visually closed Switch.
- Keep the control right-aligned and vertically centered in the row.

## Content and behavior

- Write the label as the setting or capability being controlled, not as an instruction such as “点击开启”.
- Prefer positive labels whose on-state is easy to understand.
- Apply the change immediately after a deliberate toggle. If confirmation is required for a high-impact change, request confirmation before committing the new state.
- Do not use one Switch to control multiple unrelated settings.
- Make the state available programmatically and announce loading or failure when applicable.
- Do not rely only on track color; thumb position and accessible state must communicate the value too.

## Implementation guidance

- Reuse the exact MasterGo state variant instead of recoloring a generic platform Switch.
- Preserve `44 × 24px` artwork even when the row or touch target is larger.
- Keep animation between left and right positions brief and consistent; do not animate the surrounding row layout.
- In asynchronous flows, debounce repeated input and reconcile the visual state with the server-confirmed value.
- Use [typography.md](typography.md) for row labels and state text.

## Review checklist

- Switch is used for an immediate two-state setting.
- Native `44 × 24px` dimensions and full-pill geometry are retained.
- Open, closed, disabled, and loading variants are not conflated.
- Track treatment, thumb position, semantic value, and optional status text agree.
- Disabled controls are non-interactive; loading controls reject duplicate input.
- Cell rows use `48px` height, `16px` horizontal padding, and correct text hierarchy.
- The Switch has a sufficient interaction target and an accessible name and state.

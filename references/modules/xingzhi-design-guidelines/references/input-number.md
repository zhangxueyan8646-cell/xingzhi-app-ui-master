# InputNumber 计数器

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-inputNumber 计数器` (`6:04070`) and `inputNumber 计数器 - 组件` (`6:04269`).

## Purpose

Use InputNumber to input or adjust a numeric value within a defined range. The source description is: “在一定范围内输入、调整当前数值。”

Use it when stepwise increase and decrease actions are useful. Do not use it for free-form text, an unbounded numeric field, or a binary setting.

## Anatomy

The standard component is ordered as:

`减少按钮 → 当前数值 → 增加按钮`

| Part | Source specification |
|---|---|
| Reduce icon | `20 × 20px` circular minus control |
| Value | PingFang SC, `16px`, weight `500`, line height `18px`, `#222222` |
| Increase icon | `20 × 20px` circular plus control |
| Internal spacing | `8px` between each icon and the value |

- Keep the value centered between the step controls.
- Preserve the native `20 × 20px` icon artwork; enlarge only its interactive hit area when needed.
- Format the value according to the product domain, including allowed decimal precision. The combined examples show integer, two-decimal, and long decimal values, so the component must accommodate variable-width content.

## Step-control states

The `计数图标` component family defines four variants:

| Variant | Meaning | Treatment |
|---|---|---|
| 减少 / 激活 | The value may be decreased | Cyan filled circle with white minus |
| 减少 / 极限状态 | The current value is at the minimum | Neutral outline/minus, source color `#DDDDDD` |
| 增加 / 激活 | The value may be increased | Cyan filled circle with white plus |
| 增加 / 极限状态 | The current value is at the maximum | Neutral outline/plus, source color `#DDDDDD` |

- Disable only the direction that would cross a boundary. At the minimum, reduce is in the limit state while increase may remain active; at the maximum, increase is in the limit state while reduce may remain active.
- Do not treat an individual limit-state control as a disabled state for the whole InputNumber.
- When the whole field is unavailable, disable both controls and expose the field's disabled state programmatically.
- Keep visible state and actual increment/decrement availability synchronized.

## Default and filtered forms

### Default

- Source component size is `66 × 20px` at the sample value `0`.
- Use `8px` icon-to-value gaps.
- Let width grow with the formatted number rather than forcing all values into `66px`.

### With filter

The `带筛选` form appends a selector to the standard counter:

`减少 → 数值 → 增加` · `16px gap` · `筛选值 → 下拉箭头`

| Part | Source specification |
|---|---|
| Counter group | Same `20px` icons, `16px` value, and `8px` internal gaps |
| Counter-to-filter gap | `16px` |
| Filter label | Example `CNY`; PingFang SC, `14px`, line height `20px`, `#222222` |
| Filter internal gap | `4px` between label and arrow |
| Dropdown arrow | `12 × 12px` |

- Use this form only when the numeric value has a changeable unit, currency, or closely related filter.
- The filter must not change the numeric value silently. If changing units performs a conversion, disclose and apply a consistent conversion rule.
- Make the selector and step controls separate interactive targets with clear accessible names.

## Numeric behavior

- Define a minimum, maximum, and step in product logic before implementation.
- Add or subtract exactly one configured step per activation unless the product explicitly supports press-and-hold acceleration.
- Clamp or reject out-of-range values consistently; never display a value that the controls cannot represent.
- Keep button actions, direct numeric input, pasted values, and submitted data under the same range and precision rules.
- If direct entry is supported, accept only valid numeric syntax for the locale and domain, then normalize it on commit.
- Preserve decimal precision required by the business value. Do not round financial values merely to fit the visual component.
- For long values, allocate or grow horizontal space before reducing typography. The combined example uses `14px` for an unusually long value, but treat that as a responsive composition example rather than a new default token.
- Prevent cumulative floating-point drift in implementations that use decimal steps, especially for financial amounts.

## Combined row patterns

The documented examples place the counter at the right side of a `44px`-high mobile row with `15px` horizontal page padding.

- Use `8px` between counter parts.
- A `16px` measured gap is shown between adjacent content and the counter in one annotated example.
- Allow the leading content area to contract before crowding the counter.
- When showing currency, keep `CNY` and the `12 × 12px` dropdown arrow together as one filter target.
- Preserve the row's value alignment across adjacent rows even when numeric lengths differ.

Treat the mockup rectangles and long-number examples as layout demonstrations. Use [typography.md](typography.md), [colors.md](colors.md), and the actual host-row specification for final tokens.

## Accessibility and implementation

- Name the controls with their effect and unit where useful, such as “减少数量” and “增加金额”.
- Announce the current value, valid range, and disabled boundary control to assistive technology.
- Support keyboard increment/decrement behavior where the platform expects it.
- Do not rely only on cyan versus gray; the plus/minus symbol, disabled semantics, focus state, and action availability must agree.
- Keep the interactive target comfortably tappable without visually enlarging the `20 × 20px` icons.

## Review checklist

- InputNumber is used for a bounded numeric value with meaningful step actions.
- Minimum, maximum, step, precision, and unit/filter behavior are defined.
- Both icons remain `20 × 20px`, with `8px` gaps to the value.
- Value typography uses the documented default and accommodates variable-width numbers.
- Only the direction that has reached its boundary enters the limit state.
- Active and limit-state colors, symbols, interaction, and accessibility semantics remain synchronized.
- The filtered form uses a `16px` group gap, `4px` label-arrow gap, and `12 × 12px` arrow.
- Direct entry, step controls, validation, formatting, and submitted value follow the same numeric rules.
- Long or high-precision financial values are not silently truncated or rounded for layout convenience.

# Radio 单选框

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Radio 单选框` (`6:02987`) and `Radio 单选框 -组件` (`6:02949`).

## Purpose

Use Radio when the user must select exactly one option from a visible group of mutually exclusive choices. Do not use it for independent on/off settings, multi-select choices, or actions.

The selected specification provides three visual forms: circular Radio, small pill, and filter pill.

## Circular Radio

- Native icon size: `20 × 20px`.
- Place the option label `12px` from the icon in the assembled list example.
- Use `#222222`, PingFang SC, `14px`, line height `20px` for a normal option label.

Use `radio-单选框/勾选icon` when available.

| State | Treatment |
|---|---|
| 未选 | Neutral circular outline, source color `#E6EBF0` |
| 激活 | Cyan ring and inner dot, source color `#00D2F0` |
| 不可取消 | Selected appearance with reduced emphasis; remains selected and cannot be changed |
| 禁用 | Low-emphasis neutral appearance; unavailable for interaction |

Keep exactly one active item in a standard Radio group. “不可取消” and “禁用” are availability states, not additional values.

## Small pill Radio

Use `radio-单选框/胶囊小` for compact choices inside rows or constrained spaces.

| State | Height | Padding | Background | Text |
|---|---:|---:|---|---|
| 默认 | `26px` from `4px` vertical padding around `18px` text | `8px` horizontal | `#F5F7FA` | `#999999`, `12px`, line height `18px` |
| 激活 | same | `8px` horizontal | `rgba(0, 210, 240, 0.1)` | `#00D2F0`, `12px`, weight `500`, line height `18px` |
| 默认选择不可更改 | same | `8px` horizontal | cyan tint | active text plus `16 × 16px` lock/check indicator, `4px` gap |
| 禁用 | same | `8px` horizontal | `#F5F7FA` | `#DDDDDD`, `12px`, line height `18px` |

- Use full-pill radius (`100px` in the component).
- In the compact assembled example, pill choices are separated by `8px`.

## Filter pill Radio

Use `radio-单选框/筛选胶囊` when the choice is a larger, prominent filter.

| State | Size | Background | Text |
|---|---:|---|---|
| 已选 | `109 × 36px` example | `rgba(0, 210, 240, 0.1)` | `#00D2F0`, `14px`, weight `500`, line height `20px` |
| 未选 | `109 × 36px` example | `#F5F7FA` | `#555555`, `14px`, line height `20px` |
| 默认选择不可更改 | `109 × 36px` example | cyan tint | active text plus `16 × 16px` lock/check indicator |
| 不可选 | `109 × 36px` example | `#F5F7FA` | `#CCCCCC`, `14px`, line height `20px` |

- Base padding: `8px` vertical and `24px` horizontal.
- Keep the full-pill silhouette (`100px` radius; the unselected source also uses `22px`, which is fully rounded at `36px` height).
- Let width follow content and padding unless a fixed-width filter group is intentionally required.

## Group layout

- Keep all options within one semantic Radio group and give the group a clear label.
- For vertical circular options, the selected form shows `24px` between option rows and `12px` between the Radio icon and label/content.
- Allow rich option content, such as a thumbnail below a label, while keeping the Radio aligned with the top of the option content.
- Keep pill groups visually contiguous and use consistent spacing; do not mix small and filter pills within one group.
- Make the entire option row or pill interactive, not only the circular icon or text.

## Content and behavior

- Write short, parallel, mutually exclusive option labels.
- Present a reasonable default only when product logic supports it. If no default is appropriate, leave the group unselected until the user chooses.
- Selecting a different available option moves the active state; selecting the active standard option does not clear the group.
- Use “默认选择不可更改” only when the user genuinely cannot change the preset value. Explain why nearby if it is not self-evident.
- Use a disabled/unavailable state only for an option that cannot currently be selected; do not hide important alternatives without explanation.
- Keep the visual selection synchronized with the submitted value and accessible checked state.

## Implementation guidance

- Reuse the exact MasterGo component family instead of styling a checkbox or generic tag to look similar.
- Preserve native `20 × 20px` circular icons and `16 × 16px` immutable-state indicators.
- Use [colors.md](colors.md) and [typography.md](typography.md) for all labels and states.
- Support keyboard focus and arrow-key movement within implemented Radio groups where the platform expects it.
- Do not rely only on cyan color; ring/dot, pill background, optional indicator, and programmatic state must agree.

## Review checklist

- Radio is used for one choice from a mutually exclusive group.
- Correct form selected: circle, small pill, or filter pill.
- Native dimensions, padding, full-pill radius, and label typography are retained.
- Exactly one standard option is active after selection.
- Active, immutable-selected, disabled, and unselected states are not conflated.
- Option spacing and icon-to-label gap match the documented pattern.
- Visual selection, submitted value, and accessible checked state remain synchronized.

# Calendar 日历

Use Calendar when the user must choose a date from a pop-up or embedded date panel. Preserve the date model, availability constraints, and selection semantics instead of treating the calendar as a decorative grid.

## Anatomy

- Build a seven-column grid ordered `日、一、二、三、四、五、六`.
- Use a `375px` mobile calendar width with `16px` horizontal grid padding.
- Use `36 × 36px` date cells. Space date rows on a `56px` vertical rhythm when the secondary event-count label is present.
- Set weekday labels in PingFang SC at `14px / 20px`, color `#555555`.
- Set date numerals in DIN at `18px / 25px`.
- Allow an optional centered secondary label such as `7场` below the date, set in PingFang SC at `10px / 14px`.

## Date states

- Default current-month date: dark numeral on white. Use `#222222` in content implementations; `#555555` appears in the component specimen and is acceptable only when matching that specimen exactly.
- Adjacent-month or unavailable date: use `#BBBBBB`; apply the same quiet treatment to its optional secondary label.
- Today: replace the day numeral with `今` and use `#00D2F0` on white when it is not selected.
- Selected date: use a `36 × 36px` circular `#00D2F0` fill with a white numeral.
- Distinguish today from selection: today is a temporal marker; selection is the user's value. If today is selected, the selected treatment wins while accessible text still announces today.
- Support an exceptional semantic highlight only when the product meaning requires it. The specimen shows a pale red circular highlight `rgba(214,43,31,0.1)`; do not reuse it as a generic selection color.

## Range selection

- For a date range, use circular cyan endpoints and a continuous cyan band between them.
- Keep all dates inside the selected range legible in white.
- Round only the outer edges of the range; do not render disconnected circles for every intermediate day.
- If a range crosses a week or month boundary, continue the semantic range while respecting row edges and adjacent-month availability.

## Month controls

- Center the current year and month label, for example `2022年6月`, in PingFang SC at `16px / 22px`, color `#222222`.
- Place previous and next month controls symmetrically around the label and use the brand cyan for active arrow icons.
- Disable navigation when a configured minimum or maximum month is reached; do not rely on color alone to communicate the disabled state.
- Preserve the selected value when browsing months until the user explicitly changes or cancels it.

## Presentation patterns

### Bottom-sheet picker

- Use a dimmed page backdrop (`#222222` at `40%` opacity).
- Use a white bottom sheet with `16px` top-left and top-right radii.
- The reference sheet is `375 × 600px` and includes a `50px` title bar with centered `请选择日期`, a close action, a month header, the calendar grid, and a `68px` action area.
- Use two `166 × 44px` pill buttons with `16px` side margins and an `11px` gap: outlined cyan `取消` and filled cyan `确定`.
- Cancel restores the prior committed value. Confirm commits the current valid selection. Close follows the same non-committing behavior as Cancel unless the product explicitly specifies otherwise.

### Embedded or collapsible calendar

- The reference embedded calendar is `375 × 384px`.
- Allow a compact week strip when the page needs more content space, then expand to the full month grid on demand.
- Keep the current selection and today marker consistent between compact and expanded states.

## Data and interaction

- Treat date values as locale-aware calendar dates, not timestamps inferred from visual order.
- Make the full date cell a touch target and provide a larger invisible hit area when needed; the visual cell may remain `36px`.
- Announce full date, today status, availability, selected state, and optional event count to assistive technology.
- Prevent selection of unavailable dates and explain constraints when they are not self-evident.
- Keep event counts secondary to the date and never use the count alone to indicate availability.

## Review checklist

- Confirm weekday order, month boundaries, leap days, locale, and time-zone behavior.
- Confirm default, adjacent-month, unavailable, today, selected, range-start, range-middle, and range-end states.
- Verify the `36px` cell, typography, colors, and optional event-count alignment.
- Verify previous/next month controls, compact/expanded behavior, Cancel, Confirm, and Close.
- Verify keyboard or switch navigation, focus visibility, touch target size, and accessible announcements.

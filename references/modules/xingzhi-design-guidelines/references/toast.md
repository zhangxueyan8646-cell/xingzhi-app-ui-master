# Toast 提示

Use Toast for lightweight feedback about an operation result or short-lived status. It disappears without requiring user action and must not block the current task.

## Types

### Default text Toast

- Use for short, self-contained feedback such as `更多服务，敬请期待`.
- Use a content-sized dark surface with centered white text.

### Icon or loading Toast

- Use for a short process state such as `验证中` when a visual status indicator materially improves recognition.
- The documented example is `92 × 90px`, uses a dark `rgba(0, 0, 0, 0.64)` surface, places the indicator near the top, and centers the label below it.
- Use PingFang SC `12px / 18px` for the label.
- For an indeterminate process, animate the loading indicator and keep the status programmatically announced. Replace or dismiss the Toast when the process resolves.

## Text Toast style

- Use background `rgba(0, 0, 0, 0.8)`.
- Use `8px` corner radius.
- Use `24px` horizontal padding and `16px` vertical padding.
- Use centered white PingFang SC text at `16px / 24px`.
- Keep a one-line Toast content-sized; the documented specimen is about `86–87 × 54px` for the word `toast`.
- Wrap content that exceeds the one-line maximum. The documented multiline specimen is `287 × 80px` with `239px` text width, two centered lines, and the same `24px` horizontal and `16px` vertical padding.
- Do not truncate essential result text merely to force a one-line Toast.

## Placement and behavior

- Place the Toast centered horizontally over the active page. The combined mobile example uses a middle/lower-page position that remains clear of the status bar, home indicator, and main navigation.
- Render it above page content without dimming or blocking the page.
- Auto-dismiss after the message has been readable. Use a longer duration for multiline text; do not encode a fixed duration when the source specification does not provide one.
- Queue or replace repeated messages so multiple Toasts do not overlap. Prefer the newest relevant result and suppress exact duplicates.
- Do not add buttons, links, or close controls to this Toast family. Use a Snackbar, dialog, or other actionable component when user input is required.
- Do not use Toast for destructive confirmation, persistent errors, compliance notices, or information the user must retain.

## Accessibility

- Announce feedback through an appropriate live region without moving keyboard or screen-reader focus.
- Avoid repeated announcements from loading animation frames; announce the status only when its semantic message changes.
- Preserve sufficient contrast and do not rely on an icon alone to communicate the result.
- Respect reduced-motion preferences for loading indicators and entrance/exit transitions.

## Review checklist

- Verify default versus icon/loading type and ensure the message is lightweight and non-actionable.
- Verify dark surface, opacity, `8px` radius, `24px` horizontal padding, `16px` vertical padding, and text style.
- Verify one-line sizing and multiline wrapping without clipping.
- Verify horizontal centering, safe-area clearance, overlay order, duplicate handling, and automatic dismissal.
- Verify live-region behavior, loading resolution, contrast, and reduced motion.

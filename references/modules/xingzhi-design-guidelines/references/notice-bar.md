# Notice Bar 通知栏

## Purpose

Use a Notice Bar for information that must remain visibly associated with a page or module, such as trading-time notices, service updates, warnings, errors, and contextual prompts.

Do not substitute a Toast for a Notice Bar. A Notice Bar participates in the page layout and stays anchored to its context; a Toast is a transient overlay for short operation feedback.

## Page-level notice bar

- Use the full mobile viewport width: `375 × 36px` in the documented board.
- Use `rgba(242,186,73,0.04)` for the pale warning background.
- Use PingFang SC at `12px / 18px` and `#555555` for the message.
- Keep `16px` horizontal inset at the leading edge.
- For the default text-only variant, vertically center the text at `9px` from the top.
- For the icon variant, use a `20 × 20px` leading icon at `16px` from the left and `8px` from the top, followed by an `8px` gap before the message.
- When dismissal is allowed, place the close control at the trailing edge; the documented control begins at `343px`, leaving `16px` right inset.
- Keep the bar one line and `36px` high; do not increase its height to wrap long messages.

## Long-message scrolling

- Use horizontal scrolling only when the message overflows the available single-line region.
- The documented text viewport is `343 × 36px` for the text-only form, starting `16px` from the left.
- The documented text viewport is `291 × 36px` for the leading-icon plus close-control form, starting `44px` from the left.
- Clip overflowing content to the viewport and move the message horizontally; keep the type at `12px / 18px` and vertically centered at `9px`.
- Show the full text to assistive technology. Pause or stop motion on user interaction and respect reduced-motion preferences.
- Do not animate short copy that already fits.

## Module-level inline notices

Use the compact inline form beneath a module title or immediately before the affected content.

- Keep the line height at `18px` and use PingFang SC at `12px / 18px`.
- Use a `16 × 16px` semantic icon when the icon variant is selected.
- Keep a `4px` gap between icon and copy.
- Warning: `#F2BA49`.
- Error: `#F24949`.
- Prompt/info: `#00D2F0` in the source component. Existing application examples may use the product brand blue `#00A6FA`; preserve the component token used by the target product rather than mixing both in one context.
- Preserve the same page or module gutter as the surrounding content. A documented full-width application example uses `16px` horizontal padding and `8px` vertical padding.
- Communicate the status in text as well as color or icon.

## Placement and behavior

- Place a page-level bar directly beneath the navigation or header region and let it push page content downward; do not float it over content.
- Place a module-level notice close to the module title or control it explains.
- Avoid stacking duplicate notices at page and module level.
- Add a close control only for noncritical, dismissible information. Do not allow mandatory risk, error, or compliance information to disappear merely for visual convenience.
- If dismissal is remembered, scope it to the relevant message/version so that materially changed notices can reappear.
- Do not imply a tap action unless the product requirement explicitly defines a destination or action.

## Accessibility

- Use an appropriate status or alert semantic based on urgency; routine scrolling notices should not repeatedly announce themselves.
- Give the close control a clear accessible name such as “关闭通知”.
- Preserve a clear reading order: semantic icon, message, optional close control.
- Do not rely on motion, icon shape, or color alone to communicate meaning.

## Review checklist

- Confirm page-level dimensions, background, type, and `16px` leading inset.
- Confirm icon presence, `20 × 20px` size, `8px` gap, and optional close-control spacing.
- Confirm long copy remains single-line, clipped, and scrolls only when required.
- Confirm module-level warning, error, and prompt colors plus `16px` icon and `4px` gap.
- Confirm placement remains anchored to the page or module instead of behaving like a Toast overlay.
- Confirm dismissibility matches information severity and accessibility semantics are present.

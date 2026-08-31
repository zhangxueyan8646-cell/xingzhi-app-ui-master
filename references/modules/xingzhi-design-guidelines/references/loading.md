# Loading 加载

Source: MasterGo document `行知app-规范`, nodes `XingZhi App - Design System-Loading 加载` (`6:04605`) and `XingZhi App - Design System-Loading 加载-组建` (`6:04567`).

## Purpose

Use Loading during the waiting period after a business operation has been triggered. Provide immediate visual feedback so the user understands that work is in progress and feels less uncertainty while waiting.

Do not leave an indeterminate loader running after success, failure, cancellation, or timeout. Replace it with the correct result or recovery state.

## Component variants

The `loading-加载` component family combines four dimensions:

- Size: `小`, `中`, `大`
- Text: `off` or `on`
- Contrast: `灰` or `白`
- Text layout when enabled: `横` or `竖`

### Sizes

| Variant | Spinner size | Typical role |
|---|---:|---|
| 小 | `16 × 16px` | Buttons, list-footer loading, compact inline feedback |
| 中 | `20 × 20px` | Toast feedback, validation, pull-to-refresh, general local loading |
| 大 | `32 × 32px` | Full-page or prominent centered loading |

Use the smallest variant that remains clear in the host context. Do not scale a spinner to an undocumented intermediate size.

### Contrast

| Background | Variant | Text colors in source |
|---|---|---|
| Light | 灰 | Small/medium text `#BBBBBB`; large text `#555555` |
| Dark, cyan, image, or video | 白 | Text `#FFFFFF` |

- Match spinner and text contrast variants.
- Keep sufficient contrast against the actual background; do not place the gray variant over a dark surface or the white variant over white content without a contrasting container.
- Follow [colors.md](colors.md) rather than substituting similar grays or cyan tones.

## Text and layout

### Spinner only

Use when the host control or context already explains the pending action and space is limited.

### Horizontal text

- Place text to the right of the spinner.
- Canonical component gap: `8px`.
- Small: `16px` spinner; `12px` text, line height `18px`; example `加载中...`.
- Medium: `20px` spinner; `12px` text, line height `18px`; examples `加载中` and `验证中`.
- Large: `32px` spinner; `14px` text, line height `20px`; example `正在加载中`.

### Vertical text

- Center text below the spinner.
- Small and medium canonical gap: `8px`.
- Large canonical gap: `24px`.
- Use the same size-specific typography as the horizontal form.

Keep loading copy concise and tied to the actual operation. Use domain-specific copy such as `验证中` when it improves clarity. Do not use animated ellipsis as a substitute for the spinner animation.

## Scope selection

Choose the narrowest loading scope that matches the blocked operation:

| Scenario | Pattern | Blocking scope |
|---|---|---|
| Initial page or essential page data | 全局加载 | The affected page/content region |
| Fetching the next list page | 下滑加载 | List continuation only |
| Short modal operation or validation | Toast 加载 | Relevant action context; avoid unnecessary full-page blocking |
| User-initiated refresh | 下拉刷新 | Refresh gesture and affected content |
| Submitting one action | 按钮加载 | The initiating button; prevent duplicate submission |
| Buffering media | 视频加载 | Video surface only |

- Preserve usable unaffected content whenever the operation is local.
- Block the whole page only when continuing would be invalid or misleading.
- Keep existing content visible during refresh or pagination unless product logic requires replacement.

## Documented composition examples

### Global loading

- Use the large gray vertical form centered in the content area.
- Source composition places `24px` between the `32px` spinner and `正在加载中`.
- Keep the system/navigation chrome stable while the content waits.

### List-footer loading

- Use the small gray horizontal form at the bottom of the list.
- The example places `16px` vertical space between the final content and the loading indicator.
- Stop showing it when there is no request in progress; use a separate end-of-list treatment when applicable.

### Toast loading

- Use the medium white vertical form inside a dark translucent Toast container.
- Source composition uses `8px` between spinner and text.
- Use short task copy such as `验证中` and dismiss the Toast promptly when the task resolves.

### Button loading

- Use the small white spinner inside the cyan button.
- The documented example keeps the action label and places the spinner `8px` before it.
- Disable repeat activation while the request is pending. Preserve the button's width and label context to avoid layout shift.

### Video loading

- Use the medium white spinner and white text over the black video surface.
- The examples support status copy such as `加载中 请稍后` or a measurable transfer status such as `88.8KB/s`.
- Keep media controls and retry/error behavior distinct from the loading state.

## Pull-to-refresh motion

The specification documents this sequence:

1. Initial state: show the refresh indicator at the top of the content.
2. While the finger presses and drags downward, drive the first circular animation from gesture displacement.
3. At the trigger position, complete the circular animation.
4. Continuing to drag leaves the animation unchanged and gives a slight device vibration.
5. On release, fade the first animation from `100%` to `0%` opacity.
6. Rebound to a defined height and begin the second looping loading animation.
7. When refreshing completes, restore content and remove the loading state.

Keep motion gesture-driven before release and time-driven only after loading begins. Respect reduced-motion settings and avoid vibration where the platform or user settings disallow it.

## Behavior and feedback

- Show feedback quickly enough that repeated taps are unnecessary, but avoid a visible flash for operations that complete immediately.
- Keep the indicator active only while the corresponding request or processing task is active.
- Prevent duplicate submissions for button or Toast operations.
- Preserve user-entered data during loading and failure.
- Provide success, error, timeout, empty, or retry feedback after loading resolves; Loading alone is not an error state.
- When duration can be measured, prefer determinate progress or meaningful status over an indefinitely spinning indicator.
- Ensure concurrent requests do not dismiss another operation's still-active loading state.

## Accessibility and implementation

- Expose a programmatic busy state on the affected region or control.
- Announce meaningful changes without repeatedly announcing every spinner frame.
- Keep focus stable; move focus only when the completed operation changes the user's context.
- Animate the supplied spinner artwork smoothly and consistently. Do not replace it with an unrelated platform spinner unless platform requirements override the design system.
- Provide an accessible label even when the visible variant is spinner-only.

## Review checklist

- Loading appears only during a real pending operation and always resolves.
- The selected scope matches the affected operation: page, list, Toast, refresh, button, or video.
- Spinner size is exactly `16px`, `20px`, or `32px` for small, medium, or large.
- Gray is used on light backgrounds and white on dark/cyan/media backgrounds.
- Text size, line height, layout direction, and component gap match the selected variant.
- Full-page loading uses the documented large vertical treatment; button loading uses the small inline treatment.
- Pull-to-refresh follows the gesture, trigger, release, fade, rebound, and loop sequence.
- Duplicate actions are prevented and unaffected content remains usable where appropriate.
- Busy semantics, reduced motion, completion, error, timeout, and retry states are handled.

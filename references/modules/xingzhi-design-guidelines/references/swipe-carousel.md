# Swipe 轮播图

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-轮播图` (`6:1597`).

Use these rules for horizontally paged content, especially the `343 × 112px` operational Banner documented in [operations-banner.md](operations-banner.md).

## Types

Choose the indicator pattern from the content and user need:

| Type | Use |
|---|---|
| 无定位器 | Use when page position does not need to be exposed, such as a single item or a secondary horizontally paged treatment. |
| 有定位器 | Use when a compact current-page cue is sufficient. |
| 有多个定位器 | Use one position marker per slide when users need to understand the total set and current position. |

- Do not show an indicator for a single item unless the product specifically needs a progress cue.
- Keep the indicator centered near the lower edge of the carousel, following the source examples.
- Keep indicator count equal to the number of logical slides; update the active marker immediately after the settled page changes.
- Keep the indicator visually subordinate to slide content.

## Indicator appearance

The source defines two contrast modes:

| Mode | Container/background reference | Indicator treatment |
|---|---:|---|
| 浅色 | `#E6EBF0` example field | Use a high-contrast light/white pager treatment. |
| 深色 | `#555555` example field | Use a high-contrast light/white pager treatment with a visible inactive state. |

The indicator is rendered as a short active capsule with one or more small inactive dots. Match the compact proportions shown in the source; exact marker dimensions, opacity, and spacing are not explicitly documented, so do not invent them as fixed XingZhi tokens. When implementing, preserve the visual relationship: active marker wider than inactive dots, small even gaps, and clear contrast over the underlying slide.

If the image varies strongly in brightness, protect the indicator with a subtle localized gradient or choose the appropriate light/dark treatment per slide. Do not let the indicator disappear against imagery.

## Layout and content

- Use the standard Banner size `343 × 112px` and `8px` radius for the documented Banner carousel example.
- Clip slide content to the carousel container.
- Keep every slide the same width and height; do not resize the viewport between pages.
- Reuse the Banner safe-area, typography, crop, overlay, CTA, and live-time rules in [operations-banner.md](operations-banner.md).
- Keep interactive content inside each slide distinct from the swipe gesture. A normal tap activates the current slide or its CTA; a horizontal drag changes pages.

## Swipe interaction

The source demonstrates horizontal dragging from one Banner to the adjacent Banner.

- Support direct horizontal swipe/drag and snap to one settled page.
- During dragging, translate the current and adjacent slides together so the destination is visibly connected to the gesture.
- Prevent partial resting states after release; resolve to either the current or adjacent page.
- Update the indicator only to the settled page.
- Avoid triggering slide navigation when the user's movement is recognized as a horizontal swipe.
- Keep vertical page scrolling usable by resolving gesture direction rather than capturing every touch.
- Preserve the user's position when content refreshes whenever the corresponding slide still exists.

## Motion and automation

The source does not specify auto-play, interval, transition duration, easing, looping, drag threshold, velocity threshold, or pause behavior. Treat all of these as implementation/product decisions, not documented XingZhi tokens.

When auto-play is required:

- Confirm the interval and looping behavior with product requirements.
- Pause during touch/drag and resume only after interaction completes.
- Respect reduced-motion preferences and provide manual swipe access.
- Do not auto-advance while the carousel is off-screen or while the app is inactive.

## Accessibility

- Announce each settled slide's position, such as “第 2 项，共 4 项”.
- Provide meaningful labels for the slide and its primary action.
- Do not rely only on the indicator shape to communicate slide content.
- Keep the slide or its CTA keyboard/focus accessible on supported platforms.

## Review checklist

- Verify whether an indicator is necessary and whether its count matches the slides.
- Verify active/inactive state contrast over every slide.
- Verify all slides share dimensions, clipping, radius, and safe areas.
- Verify horizontal swipe, vertical scrolling, tapping, snapping, and settled indicator updates do not conflict.
- Verify any auto-play and motion values are identified as product decisions unless a later source page documents them.

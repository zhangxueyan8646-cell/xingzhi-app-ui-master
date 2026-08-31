# Tab Bar 底部标签栏

## Purpose

Use the Tab Bar for persistent navigation between the application's primary destinations. It is bottom app navigation, not the in-page content tabs documented in `tabs.md`.

## Container

- Use the full mobile viewport width: `375px` in the documented board.
- For the standard two-, three-, and four-item forms, use a total height of `82px`.
- Divide the standard form into a `48px` navigation-content region and a `34px` bottom safe-area region.
- Use a white background and a `0.5px` top separator in `#EBEBEB`.
- Include the platform Home Indicator in the safe-area region; do not place navigation content inside that region.
- Anchor the component to the bottom of the viewport while allowing page content to account for its full height.

## Standard item

- Use the matching `24 × 24px` Tab Bar icon asset.
- Place the item content `8px` from the top of the `48px` navigation region.
- Use PingFang SC at `10px / 11.7px` for the label.
- Keep icon and label centered on the same vertical axis. The documented item is approximately `36px` high; the selected Home variant uses a `1px` icon-to-label gap.
- Allow the label wrapper to fit short names such as two- or three-character Chinese labels without changing the native icon size.
- Treat the entire equal-width navigation slot as the touch target, not only the visible `24px` icon.

## Item count and distribution

- Use the documented two-, three-, or four-item variant for ordinary primary navigation.
- Distribute destinations into equal-width slots across the `375px` container.
- Keep icon-label groups centered in their slots rather than preserving showcase-board absolute coordinates.
- Keep destination order stable between screens. Do not reorder items to indicate selection.
- Use concise, mutually distinct labels. Avoid wrapping, truncation, or two-line labels.

## Five-item emphasized-center variant

- Use the five-item form only when the product requires a visually dominant central destination.
- Use the documented total height of `97px`, including the bottom safe area.
- Reserve the center slot for the elevated visual entrance and distribute the other four standard items symmetrically around it.
- The documented center treatment uses a `72 × 72px` visual frame with a `57.6 × 57.6px` circular inner surface.
- Preserve the supplied center artwork, glow, and circular treatment as component assets; do not approximate them with a generic standard icon.
- Do not use the emphasized-center form merely to decorate an ordinary destination. The prominence must reflect information architecture and product priority.

## States

- Support `normal` and `click` (selected) variants for each standard destination.
- Normal label color: `#555555` with the matching normal icon asset.
- Selected label color: `#00D2F0` with the matching selected icon asset.
- Keep exactly one destination selected whenever the Tab Bar represents the current top-level location.
- Change both icon asset/state and label color; do not communicate selection by color alone.
- Preserve the stateful icon pairs supplied by the Tab Bar component set instead of recoloring a single arbitrary glyph.

## Navigation behavior

- Tapping an unselected item switches to that top-level destination and updates the selected state.
- Tapping the already-selected item should preserve the product-defined behavior, such as returning to the destination root or scrolling to top; do not invent behavior when none is specified.
- Preserve each destination's navigation stack when the product architecture supports it.
- Keep the Tab Bar visible only on screens that belong to the primary navigation level. Hide it on immersive, modal, or deep-detail flows when required by the screen architecture.
- Ensure page content is not obscured by the `82px` or `97px` fixed navigation region.

## Badges and accessibility

- When a destination needs an unread dot or count, apply `dot-badge.md` and anchor the badge to the icon, not the full equal-width slot.
- Give every item an accessible label and selected/current state.
- Use a practical mobile touch target for each equal-width slot, even though the visible icon-label group is smaller.
- Preserve logical left-to-right reading and focus order.

## Review checklist

- Confirm the correct two-, three-, four-, or emphasized five-item variant.
- Confirm `375 × 82px` standard dimensions or `375 × 97px` emphasized-center dimensions.
- Confirm white surface, `0.5px` `#EBEBEB` separator, and `34px` safe area.
- Confirm `24 × 24px` standard icons and `10px / 11.7px` labels.
- Confirm equal slot distribution and centered icon-label groups.
- Confirm normal `#555555` and selected `#00D2F0` state pairs.
- Confirm exactly one current destination, stable ordering, and correct navigation behavior.
- Confirm the full Tab Bar height is reserved so content and controls are not covered.

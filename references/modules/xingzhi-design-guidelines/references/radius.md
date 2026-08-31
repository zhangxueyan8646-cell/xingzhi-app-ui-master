# Radius 圆角

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-Radius 圆角` (`6:1933`).

Use rounded corners to communicate the documented simple, optimistic, and open visual character. Choose radius by semantic component role, not by the component's arbitrary size.

## Radius scale

| Role | Source value | Implementation guidance |
|---|---:|---|
| Button | Pill / fully rounded | Set radius to at least half the component height; the source specimen is `60 × 20` with `20` radius. |
| Tag | `3pt` | Use for compact labels and tags. |
| Card | `8pt` | Use for cards, Banner containers, thumbnails, grouped surfaces, and similar content containers. |
| Drawer / dialog | `16pt` | Use for drawers, modal dialogs, sheets, and prominent floating surfaces. |

Treat source `pt` values as logical design units. Map them to the platform's equivalent logical unit (`px` in a 1× design implementation, `dp` on Android, or points on iOS) rather than multiplying by display density in the design token.

## Application rules

- Use a full pill for standard rounded buttons rather than assigning them the `8` or `16` surface radius.
- Use `3` only for compact labels/tags; do not apply it to cards or dialogs.
- Use `8` as the default content-container radius. This aligns with the documented Banner and thumbnail examples.
- Use `16` for drawers and dialogs to distinguish elevated, temporary surfaces from ordinary cards.
- Clip backgrounds, images, overlays, and interaction states to the same outer radius.
- Keep nested radii visually consistent. When an inner rounded element sits close to an outer edge, use a smaller radius or enough inset to avoid competing curves.
- Preserve continuous corners across state changes; hover, pressed, selected, loading, and disabled states must not change radius.
- For a surface attached to a screen edge, round only the exposed corners when the component pattern requires it. Use `16` on those exposed drawer/sheet corners.

## Exceptions and source boundaries

- A circular icon button, avatar, or status dot may use `50%` radius because its geometry requires a circle; do not treat this as an additional radius token.
- The source's red corner-measurement overlays and partial-corner blocks are annotations, not product elements.
- The `8px` radius on the documentation canvas and its display cards is presentation styling; it corroborates the card token but does not make every container a card.
- The page's upper “Layout 基础布局” diagram documents screen chrome placement and is not part of the Radius token scale.
- Do not infer additional tokens from the source's `11.5px`, `20px`, or `100px` annotation geometry. The semantic values are tag `3`, card `8`, drawer/dialog `16`, and fully rounded button.

## Review checklist

- Identify the component role before selecting a radius.
- Verify buttons are pill-shaped and tags/cards/dialogs use `3/8/16` respectively.
- Verify image masks, backgrounds, borders, and pressed states share the correct clipping radius.
- Verify attached drawers or sheets round only exposed corners where appropriate.
- Flag any intermediate radius as an exception instead of silently adding a new token.

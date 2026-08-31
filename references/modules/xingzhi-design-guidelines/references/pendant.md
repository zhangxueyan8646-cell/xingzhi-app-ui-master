# Pendant 挂件

## Purpose

Use a Pendant as a floating entrance to a time-sensitive or continuously relevant feature, such as an active livestream. Keep it visually attached to the viewport while the underlying page remains usable.

Do not use a Pendant for ordinary primary navigation, transient Toast feedback, or information that should remain in the page layout.

## Documented placement and movement

- Use the documented `375px` mobile viewport as the positioning reference.
- Use the documented `351px` horizontal movement span. The ruler is horizontal; do not reinterpret it as a vertical drag range.
- Preserve the documented `48px` vertical clearance at the adjacent placement boundary. The ruler is vertical; do not reinterpret it as left or right screen padding.
- Keep the full Pendant inside the usable viewport throughout its horizontal movement.
- Keep the Pendant within safe-area insets and below persistent top navigation.
- Keep it above the bottom action region. The application example includes a fixed `48px` bottom operation bar, which the Pendant must not cover.
- Recompute the valid horizontal span when the viewport, safe area, or Pendant width changes.

## Livestream pendant anatomy

The source example presents a live-status entrance with copy, status artwork, and a call-to-action:

- Status group: `72 × 60px`.
- Status copy: “正在直播”, PingFang SC, `18px / 26px`, medium weight, white.
- Status icon: `24 × 24px`, centered below the copy.
- Call-to-action: `104 × 32px` pill.
- Center the status group and CTA on the same horizontal axis. In the documented `375px` example, the status group begins at `151px` and the CTA begins at `135px`.
- Place the CTA at `91px` from the top of the Pendant application frame; the status group begins at `0px`.
- CTA background: `#00D2F0`; radius: `100px`.
- CTA shadow: `0 10px 30px -10px rgba(6,138,253,0.5)`.
- CTA label: PingFang SC, `14px / 20px`, medium weight, white, centered; example copy is “立即参与”.
- Preserve supplied artwork and branded background imagery as assets; do not replace it with a generic floating button.

## Side-edge pendant: source geometry

Use these values for the compact vertical image pendant shown in the live-detail example. This is a distinct form from the live-status/CTA entrance above.

- Artwork frame: `40 × 100px`.
- Wrapper: `40 × 122px`; reserve the top `22px` for the close-control overlap.
- Right inset: `12px` in the documented `375px` viewport (`left: 323px`).
- Artwork top: `115px` from the application-frame top (`wrapper top: 93px` + `22px`).
- Close control: `14 × 14px`, positioned at the wrapper’s top-right (`left: 26px; top: 0px`); in the `375px` viewport its page coordinate is `x: 349px, y: 93px`.
- Do not derive a bottom inset from this source: the reference defines top/right placement, not a bottom-edge distance.

## Movement behavior

- Constrain any horizontal motion to the approved `351px` span.
- Clamp the Pendant to the valid span; never leave the control partly outside the viewport.
- The source documents a movement range but does not establish user dragging, edge snapping, or persisted position. Do not invent those behaviors without a product requirement.
- If the Pendant moves automatically, use restrained motion, avoid continuous distraction, and respect reduced-motion preferences.
- If the product explicitly makes it draggable, distinguish drag from tap and revalidate the position after layout changes.

## Interaction and visibility

- Tapping the Pendant or its CTA opens the explicitly defined destination, such as the current livestream.
- Provide one clear primary action. Do not add competing actions to the floating surface.
- If dismissal or collapse is required, define it as a product behavior and preserve a discoverable restore path. Do not invent a close control when the source component does not provide one.
- Hide or suspend the Pendant when its destination is unavailable, expired, or already being viewed.
- Avoid showing multiple Pendants simultaneously; resolve priority at product level.
- Do not cover trading actions, text inputs, system gestures, Tab Bars, or other critical controls.

## Layering and accessibility

- Place the Pendant above scrolling content but below modal dialogs, sheets, system alerts, and blocking overlays.
- Provide an accessible name that includes status and action, such as “正在直播，立即参与”.
- Keep the visible control and its practical touch target large enough for reliable mobile interaction.
- Do not rely on animation or decorative artwork alone to indicate that a livestream is active.
- Announce meaningful status changes without repeatedly interrupting the user.

## Review checklist

- Confirm the `351px` horizontal movement span and `48px` vertical clearance; do not swap their axes.
- For the compact side-edge variant, confirm `40 × 100px` artwork, `12px` right inset, and the `14 × 14px` close control at the artwork’s upper-right overlap.
- Confirm the Pendant stays inside safe areas and above fixed bottom controls.
- Confirm the documented `72 × 60px` live-status group, `24px` icon, `104 × 32px` CTA, and shared center axis.
- Confirm `#00D2F0`, pill radius, shadow, and typography.
- Confirm movement and tap behavior do not conflict; add drag or snap behavior only when explicitly required.
- Confirm the control never obscures a critical action or input.
- Confirm destination availability, visibility lifecycle, layering, and accessibility semantics.

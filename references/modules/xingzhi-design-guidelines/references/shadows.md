# Shadow 阴影

Use shadows to separate an important module or control from the two-dimensional surface and create restrained depth. Do not use shadows as general decoration.

## Shadow families

### Button shadow

- Use for a prominent filled primary button that needs additional action emphasis.
- Match the cyan button shadow exactly: `0 12px 32px -10px rgba(0, 210, 240, 0.5)`.
- Pair it with the documented cyan button fill `#00D2F0`; do not place the cyan shadow under neutral, secondary, or disabled buttons.
- Remove or substantially reduce the shadow for disabled and inactive states so elevation does not imply availability.

### Card shadow

- Use the documented neutral card shadow to lift a white card from a light page surface.
- Keep the result soft and low contrast. Prefer borders or background separation when elevation is not semantically needed.
- Apply one shadow to the card container; do not shadow every child or combine it with another invented elevation.

### Dropdown shadow

- Use the documented dropdown shadow for menus, selectors, popovers, and other compact surfaces that temporarily float above their trigger and nearby content.
- Preserve a clear anchor to the trigger and keep the floating surface above surrounding content without using a heavy dark halo.
- Do not substitute the card or button shadow: a dropdown is a temporary overlay with a distinct elevation role.

### Sliding-panel shadow

- Use the documented sliding-panel shadow on the leading boundary of a sliding, horizontally moving, or overlaying panel where the boundary must remain visible over content.
- Apply the shadow only to the separating edge, not uniformly around the full viewport-width surface.
- Reverse the shadow direction when the panel enters from the opposite edge.

## Implementation rules

- Reuse the named MasterGo effects `特效组/按钮投影`, `特效组/卡片投影`, `特效组/下拉投影`, and `特效组/滑屏投影` whenever the design tool or component library exposes them.
- The source board exposes the exact button shadow numerically. The other three effects are supplied as reusable effect assets; preserve those assets instead of estimating new offset, blur, spread, or opacity values from the preview.
- Keep shadow geometry outside the component bounds and ensure parent containers do not clip it unintentionally.
- Use elevation consistently with interaction state and stacking order. A surface that visually floats above another must also be ordered above it for hit testing and accessibility.
- Avoid stacking multiple shadows, adding arbitrary black shadows, or using shadow as the sole indication of focus, selection, validation, or disabled state.
- Test shadows on the actual surface color. A shadow that works on `#F5F7FA` may become imperceptible or too strong on another background.

## Review checklist

- Confirm the component uses the correct named shadow family.
- Verify the button value, brand color, radius, active state, and clipping.
- Verify card elevation is necessary and remains restrained.
- Verify dropdown anchoring, overlay order, and dismissal behavior.
- Verify a sliding-panel shadow appears only on the separating edge and faces the correct direction.
- Check light surfaces, scrolling containers, reduced-transparency settings, and dark or tinted backgrounds.

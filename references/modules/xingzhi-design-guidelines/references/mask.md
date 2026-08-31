# Mask 遮罩

## Purpose

Use a Mask to darken or soften the underlying page so foreground content is visually prominent. Keep the mask behind the active dialog, sheet, toast, or confirmation surface.

## Mask variants

- Mobile reference viewport: `375 × 812px`.
- Cover the complete viewport: `375 × 812px`; the source layer is `375 × 814px` to avoid uncovered seams at the bottom.
- Position at the viewport origin: `left: 0; top: 0`.
- Dialog/drawer mask: black at `40%` opacity (`rgba(0,0,0,0.4)`).
- Guide/onboarding mask: black at `75%` opacity (`rgba(0,0,0,0.75)`).
- Unopened/unavailable-state mask: black at `75%` opacity (`rgba(0,0,0,0.75)`).
- Bottom background softening: add `backdrop-filter: blur(10px)` to the mask when the bottom surface requires a blurred background.
- Do not use the `10px` blur as a substitute for the mask opacity; apply the selected opacity and blur independently.
- Keep the mask above page content and below the foreground surface; it must not cover the active sheet/dialog itself.

## Foreground surface examples

- Centered confirmation surface: `270 × 92px`, white, capsule-like `16px` corner curvature; positioned at `left: 62px; top: 360px` in the `375px` viewport.
- Bottom sheet: `375 × 422px`, anchored to the bottom of the viewport; header `46px` high, list rows `44px` high, and bottom action region `102px` high.
- Bottom-sheet header: close icon group around `14 × 14px`, positioned near the right edge at `left: 338px; top: 13px`; title `16px / 22px`, centered.
- Two-action bottom bar: `375 × 102px`; each action button `165.5 × 44px`, bottom inset `12px`; left button outlined in cyan, right button cyan with `40%` opacity when unavailable.

## Layering and interaction

- Lock interaction with the underlying page while the mask is active.
- Dismiss only through the defined close/cancel action or the explicit product behavior; do not invent tap-outside dismissal.
- Preserve the bottom safe area and Home Indicator region in the foreground surface.

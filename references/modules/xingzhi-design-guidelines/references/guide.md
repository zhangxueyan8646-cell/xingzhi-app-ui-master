# Guide 引导

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-Guide 引导` (`6:2229`).

## Purpose

Use guide overlays for directional education during a user's first use or first login. Keep each step focused on one highlighted region and one short action.

## Mobile baseline

- Reference viewport: `375 × 812`.
- Status-bar reference height: `44px`.
- Use `PingFang SC` for standard Chinese UI copy.

## Overlay anatomy

Build every guide step from these parts:

1. Highlighted region
2. White indicator line with endpoint dot
3. Title
4. Description
5. Outline action button

Use a black overlay at `75%` opacity around the highlighted area. Preserve adequate contrast and keep the highlighted target visually unambiguous.

- Render the full-screen overlay above ordinary page content.
- Lift or reveal the highlighted region above the overlay so it retains its original appearance; do not merely recolor the target.
- Keep title, description, indicator, and action above the overlay.
- Highlight one region per step. The source demonstrates a `343 × 112px` content region, but the highlight must follow the actual target bounds.

## Typography and spacing

| Element | Font | Size | Weight | Line height | Color |
|---|---|---:|---:|---:|---:|
| Guide title | Alimama ShuHeiTi | `20px` | Regular | `24px` | `#FFFFFF` |
| Description | PingFang SC | `14px` | Regular | `22px` | `#FFFFFF` |
| Action label | PingFang SC | `16px` | `500` | `18–24px` | `#FFFFFF` |

- Title-to-description spacing: `8px`.
- Description-to-button spacing: `16px`.
- Center-align title, description, and action around the guide target when the layout permits.
- Keep description lines short and instructional.
- Treat `8px` and `16px` as the documented vertical spacing rhythm for this component, not as measurements to scale proportionally.

## Action button

- Reference size: `104 × 36px`.
- Use a `1px` white outline.
- Use a pill radius of `35px`.
- Use approximately `23px` horizontal padding.
- Use labels such as “下一步” for intermediate steps and “知道了” for the final step.
- Use `24px` label line height for the intermediate “下一步” specimen and `18px` for the final “知道了” specimen; keep both visually centered in the `36px` button.

## Indicator and highlighted action

- Use a slim white indicator line terminating in a visible circular dot. The source indicator occupies an approximately `8 × 52px` reference box; adapt line direction and length to the target/callout relationship rather than treating `52px` as a universal fixed length.
- Use primary cyan `#00D2F0` for a highlighted primary action.
- For an emphasized primary-action glow, use `0 12px 32px -10px rgba(0, 210, 240, 0.5)`.
- Keep ordinary content surfaces white and quiet grouped surfaces `#F5F7FA` with an `8px` radius.

## Step behavior

- Use “下一步” to advance to the next highlighted target without navigating away from the current guide flow.
- Use “知道了” to dismiss the final step and persist completion according to product requirements.
- Keep the target, indicator, callout copy, and action spatially connected when the highlighted region changes.
- Do not reuse a first-use guide as a blocking confirmation dialog; the guide explains existing UI and should remain dismissible at the documented final action.

## Review checklist

- Verify the overlay is black at `75%` opacity and the highlighted region sits visually above it.
- Verify anatomy includes highlight, line and dot, title, description, and action.
- Verify title/description/button typography, `8px` and `16px` spacing, button size, border, and pill radius.
- Verify intermediate steps say “下一步” and the final step says “知道了”.
- Verify callouts do not cover the highlighted target or become clipped by safe areas and device chrome.

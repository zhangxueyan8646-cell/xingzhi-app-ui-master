# Banner 横幅与运营规范

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-运营规范` (`12:35094`).

Use these rules for operational banners, campaign cards, article or video thumbnails, live-event promotions, and topic headers. Treat this palette as an operational-artwork palette, not as a replacement for the global semantic colors in [colors.md](colors.md).

## Asset types

Choose one dominant image treatment:

| Type | Pattern |
|---|---|
| 实景 | Use a real photograph with a tonal overlay or gradient that creates a quiet text region. |
| 插图 | Use an illustration over a restrained light field or a low-contrast atmospheric gradient. |
| 人物 | Keep the subject readable, normally toward the image side, and use tint/gradient layers to separate the subject from copy. |

Observed Banner examples place copy on the left and the main visual on the right. Preserve a clear copy region instead of placing detailed imagery beneath text.

## Export dimensions

| Asset | Dimensions |
|---|---:|
| Standard Banner | `343 × 112px` |
| Small image-text thumbnail | `92 × 58px` |
| Two-column image-text thumbnail | `167 × 94px` (source example measures `167.5 × 94px`) |
| Large image-text thumbnail | `341 × 192px` (source container example measures `343 × 192px`) |
| Topic header | `375px` wide, height unrestricted |

- Use `8px` corner radii for Banner and thumbnail containers where rounding is shown.
- Preserve the target aspect ratio when cropping; use cover-style cropping rather than stretching.
- For video thumbnails, place duration at the lower right over a bottom dark gradient. Use a centered play affordance on medium and large thumbnails.
- Treat the source's `7px` and `3.22px` mask radii as example-asset construction details. Prefer the documented `8px` product radius unless matching an existing legacy asset exactly.

## Operational palette

### Light backgrounds

| Source label | Value |
|---|---:|
| Light Gray | `#E4E8F0` |
| Light Red | `#F7DFDF` |
| Light Orange | `#F7E1DA` |
| Light Yellow | `#F1E7D4` |
| Light Green | `#D3E5E5` |
| Light Cyan | `#CBE9EF` |
| Light Blue | `#D6E0F3` |

### Dark backgrounds

| Source label | Value |
|---|---:|
| Dark Gray | `#393C40` |
| Dark Red | `#7E2020` |
| Dark Orange | `#814419` |
| Dark Yellow | `#72561E` |
| Dark Green | `#057461` |
| Dark Cyan | `#086382` |
| Dark Blue | `#335498` |

Some source labels contain typos or duplicate color names. Use the semantic labels above and preserve the exact hex values.

## Standard Banner anatomy

Build a `343 × 112px` Banner from these optional layers:

1. Background image, illustration, person, or color field
2. Directional overlay/gradient that protects the copy region
3. Optional category ribbon: reference size `52 × 16px`; label `11px / 14px`, Medium `500`
4. Title: `16px`, Semibold `600`, line height `20–24px`
5. Optional subtitle: `12px / 18px`, Regular `400`
6. Either a CTA or a live-time row

### CTA variant

- Reference CTA size: `68 × 24px`.
- Use label typography `12px / 18px`, Medium `500`.
- Use a short action such as “点击查看”.
- Match the CTA fill to the artwork palette while maintaining clear text contrast.

### Live variant

- Reference combined live-time row: `195 × 24px`.
- Use a distinct “直播时间” segment followed by date/time copy at `12px / 18px`.
- A translucent light surface may unite both segments; color the live segment with an accent derived from the artwork.

### Copy placement

- Use approximately `20px` left inset for standard Banner title and action content, following the examples.
- Keep copy compact; one-line titles use `22–24px` line height, and long titles may wrap to two lines at `20px` line height.
- On light artwork, use `#222222` title and `#555555` subtitle.
- On dark artwork, use `#FFFFFF` title and approximately `70%` white for secondary text.
- Select the overlay direction based on the copy side. When copy is on the left, make the left side calmer and fade toward the visual on the right.

## Topic header pattern

The topic-header example uses a `375px` mobile canvas and unrestricted source height. Its visible example includes:

- A full-bleed image with a bottom readability gradient from transparent to `rgba(34,34,34,0.75)`.
- `16px` horizontal content insets, yielding a `343px` content width.
- Main title `24px / 34px`, Semibold `600`, white.
- Supporting copy `12px / 16–18px`, white with reduced emphasis where appropriate.
- A `68 × 24px` pill action using primary cyan `#00D2F0`, with `12px / 18px` Medium `500` white label.
- A `0.5px` divider using `rgba(245,247,250,0.2)`.
- Metadata icons at `16 × 16px`, values `12px / 20px` Medium `500`, and descriptors `12px / 20px` Regular `400`.
- Compact tags at `16px` height, `4px` radius, `11px / 14px` text, and `4px` horizontal gaps.

Treat the status bar and home indicator in the example as platform chrome, not Banner content.

## Composition rules

- Start with one palette family and tune overlays, CTA, live label, and secondary text to that family.
- Use light text only on sufficiently dark or overlaid artwork; use dark text on light artwork.
- Keep subject faces and important image content out of the copy and CTA areas.
- Limit decoration to the imagery, gradient, one category ribbon, and one action pattern. Avoid stacking both CTA and live-time treatments unless the product requirement explicitly needs both.
- Do not promote operational palette colors into success, warning, error, link, or primary-action semantics elsewhere in the app.

## Review checklist

- Verify asset type and exact export dimensions.
- Verify crop quality, corner radius, copy safe area, and visual focal point.
- Verify title, subtitle, ribbon, CTA, live-time, duration, and topic-header typography against the values above.
- Verify foreground contrast on every point of the underlying image, not only on the flat color sample.
- Verify video duration is legible at the lower right and the play affordance does not obscure the subject.
- Flag any operational color outside the documented palette or explain why an artwork-derived exception is required.

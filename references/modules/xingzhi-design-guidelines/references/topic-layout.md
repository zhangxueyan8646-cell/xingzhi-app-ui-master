# Topic 专题布局

## Purpose

- Use Topic layouts to aggregate multiple content types around one subject, activity, research domain, expert, or campaign.
- The topic header may contain a title, share action, avatar/identity, description, view count, subscriber count, and subscribe/manage action.
- Keep the topic identity and follow state visible before the content taxonomy and feed.

## Page frame and topic header

- Use a `375px` mobile reference canvas with the system status area preserved.
- The immersive header reference occupies `375 × 351px`; its main visual/color field is approximately `375 × 269px`.
- Apply a controlled image tint or gradient to protect white text contrast. Do not allow photography to obscure the title, description, or actions.
- Use a `24px`, semibold (`600`), `34px` line-height topic title.
- Use `12px/18px` for the description and keep it concise. Place it within the `16px` page gutters.
- Use a `343px`, `0.5px` translucent divider between description and topic statistics when shown.
- Present view and subscriber metrics with `16px` icons and `12px/20px` text. Keep counts emphasized and unit labels slightly reduced in opacity.

## Subscribe and page actions

- Place Subscribe or Subscription Management in the topic header’s right-side action area.
- The reference subscribe control is approximately `68 × 24px`, pill-shaped, with `12px/18px` medium text.
- Before subscription, use “订阅” or “+订阅”; after subscription, provide “订阅管理” or a clear subscribed state.
- Keep Share as a separate page-level action. Do not merge sharing and subscription into one control.
- Update subscriber state and count consistently after an action; provide feedback and a recoverable error state.

## Content surface

- Overlay the white content surface on the lower part of the immersive header. The reference begins at about `227px` and uses `16px` top corner radii.
- Keep the content surface full width and ensure its top radius remains visible over the header background.
- For non-immersive/event variants, a white card-like content surface may carry a quiet top shadow; retain the same content grid and hierarchy.
- Use `16px` horizontal gutters, producing a `343px` content width.

## Category and filter row

- Use a `44px` category region with horizontally scrollable chips when all categories do not fit.
- Category chips are `26px` high with `13px` radius. Use `12px/18px` labels.
- The active example uses a `48px`-wide cyan-tinted pill with cyan text; inactive chips use `#F5F7FA` and `#999999`.
- Keep Filter on the right in a visually protected region with a fade edge when category content scrolls behind it.
- Preserve the selected category while opening/closing filters and when returning from content detail.

## Featured content and feed

- A featured topic card uses the `343 × 112px` reference size. Event header banners may use approximately `343 × 118px`; follow Banner rules for artwork and copy safety.
- Keep featured content above the repeated feed and below the category/filter controls unless the campaign explicitly requires it to lead the content surface.
- Standard feed rows use a `343 × 62px` structure with a `92 × 58px` right thumbnail and `8px` radius.
- Use a two-line maximum title with `14px`, medium (`500`), `20px` line height.
- Place type/source/author/date metadata below in `12px/18px` and `#999999`.
- Separate rows with a `343px`, `0.5px`, `#E6EBF0` divider and use a `10px` rhythm between repeated feed items.
- Mixed types such as research, articles, news, expert content, videos, and nested topics must preserve their type labels and relevant metadata.

## Interaction and scrolling

- Allow the header to scroll away with the page unless the product explicitly defines a condensed sticky topic bar.
- If category/filter controls become sticky, preserve their `44px` height and do not cover the first content row.
- Opening content and returning should restore the selected category, filter state, subscription state, and scroll position.
- Ensure empty category results, loading, errors, and end-of-list states use the documented feedback patterns.

## Review checklist

- Confirm topic title, identity, description, share, metrics, and subscription controls are complete and readable.
- Confirm immersive header height, text contrast, content-surface overlap, `16px` top radius, and `343px` grid.
- Confirm subscribe/subscribed/manage states and subscriber count remain synchronized.
- Confirm category chips, horizontal scrolling, active state, fixed Filter region, and state preservation.
- Confirm featured card/Banner and feed rows use the correct geometry and metadata hierarchy.
- Confirm sticky behavior, return state, loading, empty, error, and end-of-list handling.

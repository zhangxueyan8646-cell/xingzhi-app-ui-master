# Share 分享

## Purpose and entry points

- Share lets a user repost the current content or open it through another channel.
- Supported entry contexts include a share action in the top navigation, a share action at the bottom of an article/news/hotspot/image/video page, and document or file sharing.
- Keep the entry placement consistent with its host page; do not add multiple competing share entrances without a product reason.

## Share drawer anatomy

- Present sharing as a bottom drawer with a white surface and `16px` top-left/top-right radius.
- Use a `375px`-wide mobile reference. The standard drawer is `256px` high; the risk-reminder variant is `342px` high. Both include the `34px` bottom safe-area/Home Indicator region.
- The title region is `50px` high. Center “分享至” using PingFang SC, `16px`, medium (`500`), `22px` line height, and `#222222`.
- Each channel item uses a `48 × 48px` icon with an `8px` icon-to-label gap. The complete item is approximately `48 × 72px`.
- Channel labels use their official names and remain directly below the icons.
- The cancel region is `375 × 68px`. Center “取消” in `16px`, medium (`500`), `18px` line height, using the brand cyan shown in the component (`#00D2F0`). Separate this action from the channel row with the documented divider treatment.

## Channel layout

- Supported component variants are `2`, `3`, `4`, and `5+` channels.
- For two to four channels, distribute the channel items evenly across the `332px` content row. The two-channel specimen uses `63px` horizontal padding.
- When channels exceed four, use a horizontally scrolling row. The reference row is `332px` wide with a `32px` gap; neither edge item is fixed while scrolling.
- Preserve destination order according to the business scenario. Available examples are 微信好友、企业微信、朋友圈、分享海报、复制链接、保存到相册、邮箱.
- Use the destination-specific icon and label together; do not reuse a generic icon for channels with different outcomes.

## Risk-reminder variant

- For macro prediction, investment-risk, or other content that requires a forwarding warning, place the reminder between the title and the channel row.
- The reminder surface is `343px` wide with `16px` horizontal padding, `8px` vertical padding, `4px` radius, and `#F5F7FA` background.
- Reminder copy uses `12px` text, `18px` line height, and `#999999`; limit it to three lines.
- Compliance wording is controlled content. Preserve approved copy exactly and do not paraphrase it during UI implementation.

## Interaction

- Tapping a channel invokes that channel's share flow.
- Tapping “取消” or the area outside the drawer closes sharing and returns the user to the unchanged source page.
- Use the Popup/Mask rules for bottom-sheet layering; the drawer backdrop uses the documented `40%` black mask.
- Do not commit a share until the destination flow confirms it. Give success or failure feedback through the appropriate result or Toast pattern.

## Review checklist

- Confirm the correct entry context and channel set.
- Confirm drawer height, top radius, safe area, title, channel row, and cancel-region geometry.
- Confirm two-to-four channel equal distribution and `5+` horizontal scrolling without fixed edge items.
- Confirm every icon-label pair matches its destination.
- Confirm required risk wording is present, unchanged, and no longer than three lines.
- Confirm Cancel and outside-tap dismissal restore the original page without side effects.

# 直播落地页

## Source and scope

Derived from the selected MasterGo frames `H5` (`107:68705`) and `直播页-浅` (`107:69051`) in `行知app-规范`. They define an upcoming countdown and an active live state over the same event-detail structure. Current XingZhi foundation tokens override legacy typography and one-off radii.

## Page variants

### H5 / web-view

- Place a standard `44px` white navigation bar below the system status area.
- Use close on the left, centered title such as `云路演`, and a more action on the right. Close exits the web-view; it does not behave like an in-app back step.
- Start the full-width media region below the navigation bar.

### Immersive App page

- Extend the media artwork behind the status/navigation region and use high-contrast white controls.
- Use back on the left and one approved page-level action such as share on the right.
- Begin the white content surface before the media artwork ends so the surface overlaps the media. For new work, use `16px` on the exposed top corners; retain the sampled `12px` only for explicit pixel-for-pixel legacy reproduction.
- Keep status icons and navigation controls readable across every poster/video frame; add a restrained dark media overlay when required.

## Media region

- Use a full-width `375 × 298px` reference region for this landing-page family. Crop poster/video content proportionally; do not stretch it.
- Apply a dark overlay only to support white status text and controls. The sampled page uses roughly black `50%` over the poster; adapt to actual contrast without hiding event artwork.
- Keep the video state in the media region and repeat the state in accessible text outside the image when needed.
- Media controls must not conflict with page back, close, or share controls.

### Upcoming

- Show `距离开播` with days, hours, and minutes. Countdown values update against a server-authoritative start time and handle timezone explicitly.
- At zero, replace the countdown atomically with the live state; never display negative values or a stale upcoming CTA.
- Keep the compact media CTA around `104 × 36px` using the small primary-button pattern when an action is allowed.
- Use PingFang SC for countdown text and numbers in new work. The sampled DINPro numerals are a legacy exception and require an explicitly available/approved font to reproduce.

### Live

- Show `正在直播` at `18/26 500` in white and expose the valid live-entry action.
- If playback happens directly in the region, the CTA starts/resumes playback. If participation opens another stream or meeting, state that outcome in the label or supporting copy.
- Buffer only the media surface with the medium white video-loading treatment. Preserve the event information and other usable content.

### Replay and ended states

- Use a visible `回放中` or approved replay status and label the action `观看回放` when the event is no longer joinable.
- If no replay exists, show `直播已结束` and remove live-only actions. Do not leave `立即参与`, `拨号入会`, or countdown content active.
- Preserve related reports, introduction, and disclaimer after the live session ends.

### Failure and restrictions

- Distinguish network/buffering failure, stream unavailable, login required, permission restricted, and event ended. Each gets its own message and recovery action.
- Use retry only when retrying can change the outcome. Never treat access restriction as a generic network failure.

## Event identity and metadata

- Place the content within `16px` gutters (`343px` width).
- Put the event-state Tag before the title when it materially helps recognition. Use a proper live-status Tag rather than inserting `直播中/回放中` into the title string.
- Event title uses `18/26 500 #222222`, up to two lines before truncation. Provide access to the complete title when truncated.
- Place optional category/source Tags below the title, with `4px` gaps. Use the exact Tag component sizing and semantic colors; ordinary category tags do not inherit live-status styling.
- Present event data in a stable label-value structure: time, organizer, and speakers. Labels use `12/18 #555555`; values use `12/18 #222222` or `14/22` when longer text needs stronger readability.
- Keep multiple speakers on separate lines or clear semantic separators. Preserve titles and organizations from the data source.

## Telephone participation

- Use module title `电话入会` at `18/26 500` and a title-to-content gap of `8px`.
- Place the meeting number above or inside a quiet `343px` information card. Use `#F5F7FA` or the approved low-emphasis blue surface, `8px` radius, and `12px` padding.
- List each region/country label with exactly one associated phone number. Do not rely on spacing alone to communicate the association.
- `拨号入会` is a deliberate text action with a phone icon. Confirm the selected number before leaving the page when multiple regions exist; do not auto-dial from merely opening the page.
- `预约外呼` is a separate secondary action. Show it only when the service supports scheduling and the event/user state is eligible.
- Preserve international dialing prefixes and meaningful spaces. Keep the raw dial target separate from the display format.

## Related reports

- Use module title `相关研报（N）`, where `N` is the actual available count.
- The selected landing-page variant uses `343 × 66px` rows with a `104 × 66px` right thumbnail and a `12px` text-image gap. Keep `8px` thumbnail radius and proportional crop.
- Use report title `14/22 500`, up to two lines when space permits. Use source and date at `12/18 #999999`.
- Tapping a row opens the report detail. Returning restores the live-page scroll position and media state without restarting playback unexpectedly.
- Hide the module when there are no reports unless the PRD explicitly asks for an empty placeholder.

## Related introduction

- Use module title `相关介绍` at `18/26 500` and body copy at `14/22 400 #222222`.
- Keep paragraphs readable and content-driven; do not force the sampled fixed `228px` module height or clip long copy.
- Preserve organization names and factual descriptions. Do not convert the introduction into an investment endorsement.

## Disclaimer

- Use the shared light Disclaimer at `343px` width after the related introduction and before the bottom action region.
- Use title `14/22 #555555`, body `12/18 #999999`, gradient rules, and a `12 × 12px` disclosure chevron.
- Preserve approved copy exactly. Expand the layout rather than truncating legal text or reducing its size.
- If collapse is allowed, preserve the reading position and announce the expanded state. Mandatory immediately visible copy must not be collapsed.

## Persistent participation action

- Use a `375 × 68px` bottom container, or `375 × 102px` when it includes the `34px` Home Indicator safe area.
- Place one `343 × 44px` pill primary button with `16/18 500` text and `#00D2F0` background on the light page.
- Maintain at least `12px` visual inset above the safe area. Reserve equivalent content padding so the fixed bar does not cover the disclaimer.
- State mapping:
  - Upcoming and reservable: `预约直播` or the approved reservation action.
  - Upcoming and already registered: show the registered state and offer cancellation only if supported.
  - Live and joinable: `立即参与` or `观看直播`, based on the actual destination.
  - Replay available: `观看回放`.
  - Ended without replay: remove or disable the action with a clear ended state.
- Use button loading for submission/join preparation and prevent duplicate activation. Resolve into success, error, timeout, or the destination state.

## Share and return behavior

- Keep a single share entry in the top navigation. Use the shared Share drawer and include a risk reminder only when approved compliance rules require it.
- Close/cancel sharing returns to the same scroll and media position.
- H5 close exits the current web-view; App back returns one navigation level. Neither should silently terminate a confirmed external call without warning.

## Legacy-frame normalization

- Normalize sampled `18/25` headings to `18/26`, ordinary `14/24` body copy to `14/22`, `12/12` action copy to a valid component token, and the disclaimer's sampled `14/16` to the shared Disclaimer rules.
- Keep `11/14` only where the shared Tag component explicitly defines it. Do not use `11px` as general body copy.
- Use `PingFang SC Medium 500` for titles and `PingFang SC Regular 400` for body. Do not inherit missing weights from legacy nodes.
- Do not promote the sampled content-surface `12px` radius into a global token. Use the semantic `8px` card, `16px` prominent attached surface, or pill button radius.

## Review checklist

- Verify H5 versus immersive navigation, full-bleed media, contrast, and safe areas.
- Verify server time, timezone, countdown rollover, live start, replay, and ended transitions.
- Verify title, status Tag, categories, schedule, organizer, speakers, meeting number, and telephone mapping.
- Verify dial confirmation, external-call handoff, reservation eligibility, repeated taps, and return state.
- Verify report count, row geometry, thumbnail crop, metadata, and return behavior.
- Verify introduction wrapping, disclaimer completeness, bottom padding, and fixed-button clearance.
- Verify media loading/error/retry, offline, restricted, ended-without-replay, and no-report states.

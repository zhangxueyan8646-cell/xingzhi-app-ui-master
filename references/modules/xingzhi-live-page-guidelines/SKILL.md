---
name: xingzhi-live-page-guidelines
description: Apply the XingZhi App live-event landing-page specification when creating, revising, implementing, or reviewing 直播、云路演、直播前倒计时、正在直播、观看回放、活动详情、电话入会、预约外呼、相关研报及免责声明页面。Use whenever the user mentions 行知直播、直播落地页、云路演、直播预约、直播倒计时、电话入会 or asks to match the selected live-event pages.
---

# 行知直播落地页规范

Use this skill with `xingzhi-design-guidelines`. The base skill owns foundations and shared components; this skill owns live-event page structure, media states, meeting access, and persistent participation actions.

## Workflow

1. Identify the host as H5/web-view or immersive App live page.
2. Identify the event state: upcoming, live, ended with replay, ended without replay, loading/buffering, failed, or access restricted.
3. Read [references/live-page.md](references/live-page.md) completely.
4. Load the applicable base references from `../xingzhi-design-guidelines/references/`:
   - Always: `typography.md`, `colors.md`, `spacing.md`, `radius.md`, `navigation-bar.md`, `button.md`.
   - Event content: `tag.md`, `information-flow.md`, `disclaimer.md`.
   - Media states: `loading.md`, `empty-state.md`, `toast.md`.
   - Sharing: `share.md`, `popup.md`, `mask.md`.
5. Preserve event title, time, organizer, speakers, meeting number, telephone numbers, report links, introduction, and approved disclaimer copy from the PRD or service response.
6. Review state-to-copy consistency, join availability, dial behavior, countdown accuracy, video fallback, safe areas, and disclosure visibility.

## Non-negotiable rules

- Use `PingFang SC` explicitly on every Chinese text node. Headings use Medium `500`; body uses Regular `400`.
- Use current heading tokens `20/28`, `18/26`, `16/24`, `14/22` and body tokens `14/22`, `12/18`, `10/14`. Component-specific Tag tokens may override these.
- Use a `375px` mobile viewport, `16px` content gutters, and `343px` primary content width.
- Keep the live/video region full bleed. Never place essential event information only inside the video image.
- Match the primary CTA to the actual state. Do not label a replay-only action `立即参与`, and do not expose join/dial actions after they are invalid.
- Keep `立即参与`, `观看直播`, `观看回放`, `预约直播`, `拨号入会`, and `预约外呼` as distinct actions with distinct eligibility and outcomes.
- Treat phone numbers, meeting numbers, speakers, times, reports, and disclaimer copy as controlled data. Do not invent or silently reformat them.

## Conflict priority

Apply explicit user correction first, then current PRD/business state, this live-page skill, exact shared-component rules, global XingZhi foundations, and finally legacy sampled-frame styling. If a zone-specific skill controls the entry page, use it for the entry and this skill for the live-event detail after entry.

## Review checklist

- Confirm the correct H5 or immersive top treatment and that return/close/share actions retain their meanings.
- Confirm upcoming, live, replay, ended, buffering, failure, and restricted states cannot be confused.
- Confirm content order: media → event identity → schedule/people → meeting access → related reports → introduction → disclaimer.
- Confirm the fixed bottom CTA is `343 × 44px`, preserves the safe area, and never covers the disclaimer.
- Confirm phone and meeting details remain readable, copyable where approved, and protected from accidental dialing.
- Confirm the approved disclaimer is complete and reachable.

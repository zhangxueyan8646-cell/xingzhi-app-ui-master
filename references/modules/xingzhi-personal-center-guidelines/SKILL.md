---
name: xingzhi-personal-center-guidelines
description: Create, optimize, implement, or review XingZhi App personal-center experiences, including 个人中心、我的权益、我的服务、我的活动、消息通知、客户经理消息、我的联系人、我的客户、联系人统计、联系人筛选、内容推荐 and related profile or account-entry flows. Use whenever a task concerns 行知个人中心、我的页面、消息中心、联系人管理 or personal account/service navigation in XingZhi.
---

# 行知 App 个人中心规范

## Workflow

1. Load and apply `$xingzhi-design-guidelines` first for foundations and reusable components.
2. Read [personal-center.md](references/personal-center.md) whenever the task includes 个人中心、我的权益、消息通知、我的联系人、我的客户 or related states.
3. Identify whether the task is the personal-center root, a message list, or a contact-management page. Do not merge their navigation and content grids.
4. Treat names, organizations, counts, message previews, benefit copy, service entries and promotional content as business data, not fixed template copy.
5. Reuse current Avatar, Dot, Tag, Search, Tabs, Tab Bar, Navigation Bar, Card, Banner and Popover rules. Treat conflicting sampled values as legacy observations.
6. Preserve route, selected Tab, search query, filters, sort order and scroll position when returning from a child page.
7. Enforce role permissions and personal-information minimization before showing account, message, client or contact data.

## Core rules

- Use a `375px` mobile canvas and the documented `16px / 343px` content grid; allow full-width navigation and message rows where specified.
- Use `PingFang SC Medium 500` for titles and `PingFang SC Regular 400` for body text, declared on every text node.
- Keep the personal-center root vertically scrollable and reserve the complete fixed Tab Bar height so modules are never clipped beneath it.
- Keep badges independent from host selection and pressed states; changing a row background must not clear unread data.
- Distinguish navigation, filters and commands: Tabs switch peer content, pills filter a list, Popover changes sorting, and row actions execute contact-specific commands.
- Use supplied operational artwork and icon assets. Do not convert specimen-only fonts, gradients or off-canvas layers into global tokens.
- Mask or omit unnecessary personal data and keep privileged client actions conditional on the current user's role and relationship.

## Review checklist

- Verify the correct page subtype and stable information hierarchy.
- Verify `375px`, `16px / 343px`, module spacing, scroll behavior and bottom safe-area clearance.
- Verify PingFang family, `500/400` weights, current type scale and every text node's explicit font declaration.
- Verify profile, benefit, shortcut, service and activity modules on the personal-center root.
- Verify message Tabs, contextual Search, `72px` rows, avatar, preview, timestamp, unread count and pressed state.
- Verify contact Banner, Tabs, statistics, Search, filters, sorting, contact cards and per-contact actions.
- Verify role access, data masking, badge clearing, return-state restoration and accessibility semantics.
- Flag any sampled font, geometry or overlapping layer that conflicts with `$xingzhi-design-guidelines`.

---
name: xingzhi-asset-management-guidelines
description: Apply the XingZhi App asset-management specification when creating, revising, implementing, or reviewing 资管业务首页、ABS/REITs 产品入口、存续 ABS 产品列表与搜索、项目详情、产品分层、产品文件、查看权限申请及申请结果反馈。Use whenever the user mentions 行知资管业务、资管专区、ABS 产品、存续产品、项目详情、产品文件权限 or asks to match the selected asset-management landing pages.
---

# 行知资管业务规范

Use this skill together with `xingzhi-design-guidelines`. The base skill owns global foundations and shared components; this skill owns asset-management information architecture, product presentation, document access, and permission states.

## Workflow

1. Identify the requested page as asset-management home, product list/search, project detail, or document-permission state.
2. Read [references/asset-management.md](references/asset-management.md) completely.
3. Load only the relevant base references from `../xingzhi-design-guidelines/references/`:
   - Always: `typography.md`, `colors.md`, `spacing.md`, `radius.md`, `navigation-bar.md`.
   - Home: `business-layout.md`, `operations-banner.md`, `tabs.md`, `card.md`, `information-flow.md`, `tag.md`.
   - List/search: `search.md`, `card.md`, `tag.md`, `empty-state.md`.
   - Detail: `card.md`, `tag.md`, `collapse.md`, `disclaimer.md`, `button.md`.
   - Permission states: `modal.md`, `mask.md`, `input.md`, `result-feedback.md`.
4. Preserve the PRD's product data, state, permissions, disclosure copy, and actions. Do not invent returns, ratings, eligibility, approval, or compliance claims.
5. Build the page with real product states, including loading, empty, no permission, invalid applicant, submitted, failed, file available, and file unavailable when they are in scope.
6. Verify typography, card rhythm, access control, disclosure placement, search restoration, and result feedback before delivery.

## Non-negotiable rules

- Use `PingFang SC` explicitly on every text node. Headings are Medium `500`; body is Regular `400`.
- Use canonical heading tokens `20/28`, `18/26`, `16/24`, `14/22`; use body tokens `14/22`, `12/18`, `10/14`. Do not copy legacy `11px`, `12/17`, `14/20`, or heading `16/22` values from the sampled frames.
- Keep Tabs at the user-approved values: selected `16px/24px 500`; unselected `14px/22px 400`.
- Use a `375px` mobile viewport, `16px` page gutters, and `343px` primary content width. Card inner padding is `12px`; sibling cards are separated by `12px`.
- Treat product numbers as factual data, never as promotional promises. Keep units, dates, rating labels, hierarchy, data source, and update time unambiguous.
- Never expose protected product files before approval. Permission requests must explain why access is unavailable, what the user must provide, and what happens next.
- Keep approved disclaimer copy complete and reachable. Do not paraphrase regulated wording unless the PRD explicitly authorizes it.

## Conflict priority

Apply rules in this order: explicit user correction → current PRD/business requirement → this skill's asset-management rule → exact shared component reference → global XingZhi foundation → legacy sampled-frame styling. Preserve content and state from the selected frames while normalizing outdated visual tokens to the current XingZhi specification.

## Deliverable review

- Confirm the home page leads with business value and an actionable product path, not only an information feed.
- Confirm list and search use the same product-card schema and preserve the entered keyword on return.
- Confirm project details separate basic information, tranche metrics, product files, PC handoff, and disclaimer.
- Confirm locked files, applicant input, validation error, submitted, failed, approved, and downloadable states cannot be confused.
- Confirm masks use black `40%` for dialogs, dialogs use `270px` width and `16px` radius, and background content is non-interactive.
- Confirm content remains scrollable above the safe area and no fixed action obscures the disclaimer.

---
name: xingzhi-landing-page-guidelines
description: Create, optimize, implement, or review XingZhi App campaign and event landing pages, including 策划会、数字化活动、线下活动、扫码报名、活动详情、报名表单、登录拦截、隐私同意、重复报名检测、身份确认、电子票、参会二维码、活动议程、报名审核、承诺书签署、材料上传、CRM 客户管理、销售代客报名 and conversion flows. Use whenever a task concerns 行知落地页、活动落地页、数字化活动页面、策划会页面、参会信息、报名管理 or event-registration conversion in XingZhi.
---

# 行知 App 落地页规范

## Workflow

1. Load and apply `$xingzhi-design-guidelines` first for colors, typography, spacing, radius, masks, buttons, forms, inputs, checkboxes, Toast, Modal, Result Feedback, navigation and compliance.
2. Read [digital-event-registration.md](references/digital-event-registration.md) when the task includes 策划会、数字化活动、线下活动、扫码报名、参会信息、活动报名、报名审核、承诺书、上传、CRM 客户 or 代客报名 states.
3. Separate the stable landing-page shell from temporary flow states. Reuse one shell; do not redraw a new page for login, consent, duplicate-account or validation feedback.
4. Treat event title, date, address, organization, attendee identity and channel options as business content, not fixed template copy.
5. Preserve the conversion sequence: understand event → review/fill attendee information → consent to data use → submit → receive explicit outcome.
6. Apply the exact XingZhi component reference when a sampled landing page conflicts with the current design system. Record the sampled value as a legacy observation, not a new token.
7. Model registration, review, attendance, joint-investment compliance and commitment signing as independent state dimensions. Never infer one state from another.
8. For CRM and proxy-registration flows, verify role permissions, customer authorization, data masking and auditability before exposing actions or identity data.

## Core rules

- Use a `375px` mobile canvas and the documented `16px / 343px` content grid.
- Build the shell from hero information, overlapping content sheet, registration content, privacy/consent region and bottom primary action.
- Keep the hero concise: event title, date and location only; place long descriptions and registration fields in the content sheet.
- Use PingFang SC Medium 500 for titles and Regular 400 for body text, declared on every text node.
- Keep only one primary submission action. Disable it until mandatory information and consent requirements are satisfied.
- Use inline feedback for a field that must be corrected, Toast for brief page-level validation, Modal for login blocking, and Result Feedback for the final process outcome.
- Preserve entered information across login, account switching and recoverable validation states unless policy requires clearing it.
- Treat attendee QR codes and identity matches as protected credentials; mask sensitive identifiers and enforce role-based access.
- Verify signing outcomes with server state, request upload permissions only after a source is chosen, and preserve recoverable context across external flows.
- Distinguish customer self-service from sales proxy actions; never let a sales user silently accept customer consent or legal terms.
- Keep approved privacy, personal-information and risk copy intact; never shorten compliance text merely to fit.

## Review checklist

- Verify the selected event-page subtype and flow state.
- Verify the `375px` canvas, `16px` gutters, hero/content overlap and bottom safe-area clearance.
- Verify title/body font family and weight, image contrast, field hierarchy and one-primary-action rule.
- Verify required fields, selection controls, consent state, button availability and validation feedback.
- Verify login interception, duplicate-record handling, account switching, submission and return behavior.
- Verify identity matching, sensitive-data masking, electronic-ticket status, QR-code access and agenda actions.
- Verify registration review, commitment signing, upload-source selection, failure recovery and status independence.
- Verify CRM role access, conditional customer actions, proxy-registration authorization and audit records.
- Verify privacy purpose, collection scope, channel attribution and all approved compliance copy.
- Flag any specimen geometry that conflicts with `$xingzhi-design-guidelines`.

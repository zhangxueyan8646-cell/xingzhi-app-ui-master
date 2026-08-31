---
name: xingzhi-business-processing-guidelines
description: Apply the XingZhi App business-processing specification when creating, revising, implementing, or reviewing 业务办理入口、办理记录、机构研究服务申请、申请身份选择、信息完善、客户经理受理、模板下载、材料上传、身份核实、人脸识别授权、协议签署、提交审核及结果反馈。Use whenever the user mentions 行知业务办理、我的申请、研究服务机构客户申请、材料审核、模板下载、上传材料、人脸识别、签署协议 or asks to match the selected business-processing pages.
---

# 行知业务办理规范

Use this skill together with `xingzhi-design-guidelines`. The base skill owns foundations and shared components; this skill owns application orchestration, state transitions, identity/consent safeguards, material handoff, and resumption from messages or records.

## Workflow

1. Identify the business type and load its backend-defined steps; never reuse another business's step sequence.
2. Read [references/business-processing.md](references/business-processing.md) completely.
3. Load only the applicable base references from `../xingzhi-design-guidelines/references/`:
   - Always: `typography.md`, `colors.md`, `spacing.md`, `radius.md`, `navigation-bar.md`, `steps.md`, `button.md`.
   - Application forms: `form.md`, `input.md`, `radio.md`, `checkbox.md`, `card.md`.
   - Materials: `upload.md`, `loading.md`, `notice-bar.md`.
   - Identity and agreements: `popup.md`, `modal.md`, `mask.md`, `disclaimer.md`.
   - Completion: `result-feedback.md`, `toast.md`.
4. Model each state explicitly: draft, incomplete, invalid, submitted, accepted, supplementary-material required, reviewing, signing, polling, approved, rejected, failed, cancelled, and expired as applicable.
5. Preserve PRD fields, eligibility, material requirements, agreement versions, consent wording, approval status, and service contacts. Do not infer regulated requirements from screenshots.
6. Verify progress accuracy, validation, draft restoration, idempotent submission, sensitive-data handling, safe areas, and recovery paths.

## Non-negotiable rules

- Use `PingFang SC` explicitly on every text node. Headings use Medium `500`; body uses Regular `400`.
- Use canonical headings `20/28`, `18/26`, `16/24`, `14/22` and body `14/22`, `12/18`, `10/14`; exact Form/Input/component tokens may override only within that component.
- Use a `375px` mobile viewport, `16px` page gutters, `343px` content width, `12px` card padding, and `12px` between sibling cards in new pages.
- Never advance the Steps indicator before the server confirms the transition. Never let users jump over dependent identity, agreement, material, or approval steps.
- Never preselect privacy, personal-information, biometric, or agreement consent. A reading countdown never counts as consent; require an explicit user action.
- Never upload, submit, sign, or start face recognition without clear user intent. Prevent duplicate operations and preserve user-entered data on failure.
- Never expose full identity, biometric, agreement, or material data in logs, analytics, notifications, search indexes, or unprotected previews.

## Conflict priority

Apply explicit user corrections first, then the current PRD and backend workflow, this skill's process rules, exact shared-component references, global XingZhi foundations, and finally sampled-frame styling. The selected frames contain multiple business processes and historical versions; their step labels and positions are not interchangeable.

## Review checklist

- Confirm entry eligibility, business description, required materials, process summary, and records entry.
- Confirm every step and CTA reflects the server state, including asynchronous customer-manager review and signature polling.
- Confirm form errors are local, drafts survive interruption, and immutable organization data is clearly distinguished from editable fields.
- Confirm templates, required counts, uploaded files, signatures/seals, and submission confirmation are traceable and cannot be confused.
- Confirm biometric consent, agreement version, reading state, explicit checkbox, and signing result are auditable.
- Confirm success, failure, retry, pending, supplemental-material, and rejected states have accurate recovery paths.

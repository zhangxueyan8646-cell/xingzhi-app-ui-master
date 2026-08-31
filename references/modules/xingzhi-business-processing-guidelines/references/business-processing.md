# 业务办理落地页

## Contents

- [Source and page frame](#source-and-page-frame)
- [Flow families](#flow-families)
- [Entry and introduction](#entry-and-introduction)
- [Identity and package selection](#identity-and-package-selection)
- [Information form](#information-form)
- [Asynchronous acceptance](#asynchronous-acceptance)
- [Templates and materials](#templates-and-materials)
- [Identity verification](#identity-verification)
- [Agreement signing](#agreement-signing)
- [Submission and results](#submission-and-results)
- [Records and messages](#records-and-messages)
- [Privacy and compliance](#privacy-and-compliance)
- [Legacy normalization](#legacy-normalization)
- [Review checklist](#review-checklist)

## Source and page frame

Derived from 19 selected MasterGo frames in `行知app-规范`, including `业务办理页-入口`, `研究服务机构客户申请`, `选择申请身份`, `完善信息`, `模板下载`, `上传材料`, `确认身份`, `人脸识别服务授权协议`, `签署协议`, signing-status polling, submit success/failure, and the supplementary-material message. These frames define business states; current XingZhi foundations override historical visual values.

- Use a `375 × 812px` mobile reference with a `44px` status area and `44px` navigation bar.
- Entry title is `业务办理`; in-progress pages use `我的申请`. Use `办理记录` as the page-level action only on the entry page.
- Use `#F5F7FA` for the page/group background and white for primary rows/cards. Keep `16px` gutters and `343px` content width.
- Use a bottom `375 × 68px` action region, or `375 × 102px` with the `34px` Home Indicator area. Primary buttons are `343 × 44px` pills.
- Keep Save as a navigation-level text action when a draft can be stored. Explain save success/failure without advancing the process.

## Flow families

### Institution research-service application

Use this logical order unless the current PRD/backend explicitly changes it:

1. Select an eligible application identity.
2. Confirm application intent and complete organization/applicant information.
3. Submit the intent for customer-manager acceptance.
4. Receive acceptance or a request for supplementary information.
5. Download the correct material templates.
6. Complete required signatures/company seals offline or through an approved electronic-seal path.
7. Upload required materials and submit for review.
8. Show the resulting review/activation status.

The selected snapshots show different four-step labels because they capture different phases/versions. Build the step bar from the current workflow state, not from screenshot x-positions. Customer-manager acceptance may be represented as a passive review stage rather than an editable page.

### Identity-and-signature application

Use the selected four-step sequence:

1. `完善信息`
2. `确认身份`
3. `签署协议`
4. `提交`

Do not permit direct navigation to signing or submission until all preceding requirements are server-confirmed.

### Steps presentation

- Use the horizontal Steps component directly below navigation. The selected flow uses an approximately `65px` region; preserve the shared `64px` semantic component.
- Use `3px` connecting lines; completed/current paths are `#00D2F0`, future paths are `#CCF4FA`.
- Use `10/16` step labels. Current text is `#222222`; future text is `#999999`.
- Distinguish current, completed, waiting for external review, failed, and returned-for-changes states in both visuals and accessible status.

## Entry and introduction

- Present available businesses as full-width content rows/cards, each with business name, one concise applicability description, and a trailing arrow.
- Keep business names at `14/22 500`; descriptions at `12/18 #555555`. Allow descriptions to wrap without truncating the eligibility condition.
- Do not show an ineligible business as normally actionable. Explain login, account type, investor category, jurisdiction, or service prerequisites before entry.
- The business introduction page orders content as: `业务介绍` → service-detail link when supplied → `办理材料` → `办理流程` → primary `马上办理`.
- Use `343px` quiet cards with `8px` radius and `12px` padding. Preserve approved service-scope language; do not promise approval or access.

## Identity and package selection

- When multiple personal/organization identities exist, open a `270px` centered selection dialog with black `40%` mask.
- Title the dialog `请选择您要发起申请的身份`; show one mutually exclusive Radio per identity. Do not default to an identity when choosing the wrong legal entity has consequences.
- Keep cancel/confirm semantics explicit. Cancel restores the introduction page; confirm carries the exact identity ID into the application.
- Package selection uses a `375px` bottom Popup with `16px` exposed top corners, one Radio group, and a `343 × 44px` confirm button.
- A `荐` marker is an informational recommendation, not an automatic choice or suitability determination. Keep package terms and service-detail access available before confirmation.

## Information form

- Group fields into `机构信息`, `申请套餐`, and `申请人信息`. Use horizontal Form rows for compact label/value pairs.
- Organization name and unified social credit code may be read-only when supplied by the selected identity. Make read-only state explicit and do not style it like a placeholder.
- Validate the unified social credit code against the current business rule; the sampled flow expects 18 characters. Display `12/18 #F24949` directly below the field and preserve the entered value.
- Keep name, contact number, email, and customer-manager employee number as separate fields. Validate format locally where safe and revalidate on the server.
- The customer-manager number is optional only when the PRD says so. Keep its supporting explanation adjacent to the field.
- Personal-information consent uses a Checkbox plus approved purpose/recipient/retention text. Do not preselect it, bundle unrelated purposes, or enable the primary button before required consent.
- `确认无误，下一步` remains unavailable until required fields and consent are valid. Returning to fix an error must preserve valid fields.

## Asynchronous acceptance

- After application-intent submission, use a page-level result state: success icon, `申请意向已提交`, next-step explanation, and `完成`.
- A submitted intent is not final approval. Use precise copy such as waiting for the customer manager to accept.
- When supplementary materials are required, send an in-app notification with a specific title, concise reason, timestamp, and `查看详情` deep link.
- Opening the message returns to the correct application, step, and missing-material state. Do not create a new duplicate application.
- Preserve server status across app restart and show last-updated time when review may be delayed.

## Templates and materials

### Template download

- List every required document with its name, current state, and applicable instruction such as `需加盖公司公章`, `可使用电子公章`, or `可使用电子营业执照`.
- Use a dedicated `下载材料模板` operation. Downloads must use the template version tied to the current application and record version/date when supplied.
- `联系客户经理` is a separate help action. Do not make it the only way to learn material requirements.
- Mark a template complete only after the required document is downloaded/acknowledged according to the PRD. `已完成用印，下一步` does not verify the contents of a file.

### Upload

- Show the required section title and progress as completed/required count, such as `3/3`. Count only files that passed required validation; an upload-in-progress or failed file is not complete.
- Use `80 × 80px` document upload cards with `8px` radius, `24px` icon, and `10/14` helper copy when matching the small upload pattern.
- Support unselected, uploading, uploaded, interrupted/failed, replacing, and deleting states independently for each material.
- Display file type, complete filename, size, upload time/version when supplied, and required signature/seal instructions.
- Validate type, size, duplicate, corruption, malware/security status, and business-specific requirements before submission. Preserve successfully uploaded files if another file fails.
- Before `下一步：提交审核`, show a `270px` confirmation dialog reminding the user to verify signatures or seals. Use standard copy such as `请确认材料已签字或盖章`; do not reproduce source typos.
- Cancel closes the dialog without losing uploads. Submit is idempotent and disables repeated taps while pending.

## Identity verification

- Use a centered identity illustration, `身份核实` title at `20/28 500`, and `14/22 #555555` explanation.
- Explain why face recognition is needed before requesting permission. Keep the biometric-information checkbox and approved summary near the bottom action.
- Do not preselect biometric consent. `进入人脸识别` stays unavailable until the required agreement is read and explicitly accepted.
- If the user has not accepted the agreement, show a blocking `270px` dialog explaining that online processing cannot continue and provide an approved help path. Do not imply that contacting support equals consent.

### Face-recognition agreement

- Present the agreement in a `375px` bottom Popup over a full black `40%` mask. Use a `44px` title bar, `16px` top corners, a scrollable `343px` text region, agreement version/number, a consent Checkbox, and safe-area-aware action region.
- Agreement body uses `14/22`; controlled wording must remain complete. Do not shorten privacy, collection, storage, sharing, security, or liability clauses to fit the screen.
- A reading countdown such as `我已知悉并同意（3s）` may delay activation, but completion of the timer never selects the checkbox or records consent. Require a deliberate final tap and record version, timestamp, and user identity.
- Closing the Popup leaves consent uncommitted and returns to the identity page without starting the camera.
- Handle camera permission denied, face mismatch, timeout, cancellation, retry, success, and unsupported-device states separately.

## Agreement signing

- Show `请阅读以下协议并完成签署`, then one row per agreement with full name and `点击阅读`.
- The agreement checkbox states `我已阅读并同意签署以上协议`; do not enable `提交` until every required agreement is read/acknowledged and explicitly checked.
- Store agreement ID/version and signing result separately from the checkbox UI. A checkbox is intent, not proof that signing completed.
- While querying external signing status, use a blocking `270px` dialog or approved loading surface with a `32px` gray spinner and `正在查询签署状态…`. Prevent duplicate signing sessions.
- Poll with a bounded timeout. On success advance once; on pending keep the current step; on timeout/network failure offer retry; on rejected/expired signature provide the exact recovery path.

## Submission and results

- Before final submit, show a concise review/confirmation state when the operation has legal or material consequences.
- While submitting, use button loading or a scoped blocking loader and keep the request idempotent.
- Success uses a page-level Result feedback layout with a `48 × 48px` success icon, `16/24 500` title, `14/22 #555555` next-step copy, and `完成`.
- Distinguish `申请意向已提交`, `申请已提交审核`, `业务开通成功`, and `协议签署完成`. They are not interchangeable.
- Failure uses the failure icon, `提交失败，请重试`, and a specific `重试` action. Preserve completed inputs, identity results, agreements, and uploaded materials unless the server declares them invalid or expired.
- If rejection requires edits, return to the first affected step with the reviewer reason and keep unaffected completed steps intact.

## Records and messages

- `办理记录` and `我的申请` are the durable re-entry paths. Show business name, application identity, current state, last update, and available next action.
- Message cards may prompt supplementary materials but must not include sensitive personal/biometric content or unmasked identifiers.
- Deep links validate the current logged-in account and application ownership before showing details.
- Returning from messages, agreements, camera, file picker, or external signing restores the same application and current step.

## Privacy and compliance

- Collect only fields and files required by the current business. Explain purpose and scope before personal or biometric collection.
- Keep personal-information consent, biometric authorization, service agreement, and material submission as separate auditable actions.
- Mask sensitive identifiers outside the active user's secure form context. Never write identity numbers, phone numbers, agreement contents, biometric data, or uploaded documents into analytics or debug output.
- Respect agreement withdrawal/cancellation rules and explain effects without making legal conclusions.
- Preserve approved legal/service copy and template versions. Flag missing or contradictory compliance copy instead of inventing it.

## Legacy normalization

- Normalize sampled navigation `18/24` to `18/26`, identity title `20/30` to `20/28`, and ordinary `11/16` process labels to the Steps token `10/16`.
- Keep exact Input/Form line heights only inside those components; use global body `14/22`, `12/18`, and `10/14` elsewhere.
- Use `模板`, `等待`, `人脸识别`, and `签字或盖章` in new copy unless approved source wording requires otherwise. Flag source typos rather than reproducing them.
- Do not use sample company names, people, phone numbers, social-credit codes, manager numbers, or agreement numbers as defaults.
- New cards use `12px` inner padding and `12px` sibling gaps; retain tighter historical spacing only for explicit legacy reproduction.

## Review checklist

- Check business eligibility, intro/material/process accuracy, identity ownership, and package selection.
- Check workflow order, Steps state, draft save, back/close behavior, and asynchronous resumption.
- Check form groups, read-only values, required fields, local/server errors, consent, and disabled buttons.
- Check template versions, material requirements, upload state/count, signature/seal confirmation, and idempotent submit.
- Check biometric purpose, explicit authorization, agreement scrolling/countdown, camera outcomes, and audit record.
- Check agreement read/intent/signing separation, polling timeout, retry, expiry, and server-confirmed advancement.
- Check success/failure/rejection/supplemental-material states and preservation of prior work.
- Check sensitive-data minimization, masking, logging boundaries, message deep links, and safe-area clearance.

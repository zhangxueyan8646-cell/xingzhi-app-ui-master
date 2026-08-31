# 资管业务落地页

## Source and scope

Derived from the selected MasterGo frames in `行知app-规范`: `资管业务` (`110:61954`), product detail and permission states (`110:60642`, `110:62677`, `110:61515`, `110:63531`, `110:61033`, `110:63111`), `存续ABS产品` (`110:63981`), and its search states (`110:60397`, `110:60531`). These frames define structure and business states; current XingZhi foundation tokens override legacy measurements.

## Shared frame

- Use a `375px` mobile viewport. Apply a `44px` navigation bar below the system status area and preserve bottom safe-area space.
- Keep primary content inside symmetric `16px` gutters (`343px` content width). Full-bleed cyan headers are allowed only where the selected asset-detail pattern requires them.
- Use white cards on `#F5F7FA` grouped backgrounds. Default card radius is `8px`, inner padding is `12px`, and the vertical gap between sibling cards is `12px`.
- Use `#00D2F0` for primary actions and active emphasis, `#00A6FA` for informational links/tints, `#FEAF40` only for warm metric emphasis, and semantic colors for success/error.
- Show one clear primary action per decision point. Labels use explicit verbs such as `查看详情`, `申请查看`, `重新申请`, `复制PC链接`, and `下载`.

## 资管业务首页

### Information order

1. Navigation title `资管业务`.
2. Latest-update or key-message banner.
3. Peer business categories such as `ABS/REITs`, `WeFund`, fixed income, equity, and cross-border.
4. A concise business-value introduction and underlying-asset tags.
5. Featured product card and `更多项目` entry.
6. Business-system content or research recommendation.
7. `资管洞察` information flow.

### Layout and behavior

- Use a `343 × 112px` banner with `8px` radius. Keep one dominant message/action and avoid multiple equal calls to action.
- Category navigation is horizontally scrollable when it exceeds the width. Keep selected `16/24 500` and unselected `14/22 400`; restore the selected category after returning from a product.
- The business-introduction block may use a low-emphasis blue tint, a `16/24 500` module title, `14/22 400` explanatory copy, and compact asset tags.
- A product card includes product name, rating tags, core amounts or scale, and base-asset type. Values align in columns but remain associated with their labels when text wraps.
- `更多项目` is a visible list-level action, not a small decorative caption.
- `资管洞察` uses the XingZhi information-flow pattern: title and metadata on the left, optional `92 × 58px` thumbnail on the right, with a `12px` text-image gap.

## 存续 ABS 产品列表

- Navigation title is `存续ABS产品`; the right-side page action may hold share/open behavior when the PRD provides it.
- Place a `343 × 36px` pill search field below the navigation bar. Use a `16px` search icon, `12px` horizontal padding, and `14/22` placeholder/input copy.
- Product cards repeat one stable schema: product name; rating tags; three comparable columns such as amount, scale, and underlying-asset type; label text below each value.
- Product title uses `14/22 500`; values use `14/22 500` when emphasized; labels use `10/14 400` or `12/18 400` according to density. Use full units such as `亿元` and never detach the unit from its number.
- Use `12px` between cards. The entire card opens the detail page; do not add competing buttons to every metric.
- Support initial/loading, populated, empty, and error states. Loading keeps the list skeleton stable; an error offers a retry without erasing the current query.

## Search states

- Preserve the navigation title and convert the search field from placeholder to active input without shifting surrounding controls.
- While typing, show a clear affordance. Search suggestions highlight only the matching substring in cyan; the rest of the product name remains `#222222`.
- Selecting a suggestion opens its project detail. Returning restores the keyword and scroll position.
- When there is no match, show the approved empty illustration and `暂无匹配产品` centered below the search field. Do not show stale product cards behind the empty state.
- Empty state is not an error state; do not use red or a retry button unless the request itself failed.

## 项目详情

### Header

- Use a cyan detail header when matching this flow: navigation title `项目详情`, product name at `18/26 500`, then base-asset and rating tags.
- Long product names may wrap within the header; navigation actions remain fixed and tappable.

### Content order

1. `基本信息`
2. `产品分层`
3. `产品文件`
4. PC handoff action
5. Disclaimer

### Basic information

- Use a `16/24 500` section title and an `8px` title-to-card gap.
- Present label-value pairs in a low-emphasis grouped card. Labels use `14/22 #555555`; values use `14/22 #222222`.
- Keep business fields intact: total issue size, outstanding size, currency, exchange no-objection letter, underlying asset type, revolving purchase, and innovation tags when provided.
- Allow long values to wrap; never truncate legal identifiers or asset classifications without a full-view route.

### Product tranches

- Tranche chips switch between peer layers such as priority/subordinate classes. They do not replace the page-level category Tabs.
- Keep one selected tranche and update all metrics atomically when it changes.
- The summary card may show coupon rate, issue size, and rating in three columns, followed by a label-value table for remaining term, tranche type, period, repayment, day-count convention, interest type, start date, and expected maturity date.
- Do not infer missing values or calculate performance. Preserve decimal precision and units from the data source.

### Product files

- Group files by report type in collapsible rows, with the file count on the right. Opening one group must not silently close unrelated groups unless the PRD requires accordion behavior.
- An available file row shows file icon, full file name, size, date, and a dedicated download action. Keep download state distinct from opening the group.
- A protected group opens the permission dialog; it must never expose filenames, URLs, or download actions before approval.
- Use the cyan PC-handoff panel for content unavailable on mobile. `复制PC链接` copies the exact destination and gives lightweight success feedback.
- Place the approved disclaimer after the handoff panel. It remains readable and cannot be covered by fixed actions.

## File permission flow

### Locked state

- Keep the underlying detail page visible but non-interactive beneath a full-viewport black `40%` mask.
- Use a centered white dialog, `270px` wide, `16px` radius, and a lock icon. Title: `暂无查看权限` or the approved equivalent.
- Explain that access is unavailable and identify the required reviewer/contact role. Do not promise approval.
- Provide one applicant/contact input and the primary action `申请查看`. Preserve entered text when validation fails.

### Validation error

- Show the error directly below the input using `12/18 #F24949`; keep the dialog open and the primary action available.
- The error must state which role/name is invalid without exposing the full authorized-person list.

### Submitted, failed, and approved

- Submitted uses a success icon, `提交成功`, and the next step (`待审核通过后即可查看`). This is an application receipt, not access approval.
- Failed uses an error icon, `申请失败`, a concise reason, and the explicit action `重新申请`.
- Approved removes the lock and reveals only the files authorized for the current user/project. Do not reuse the submitted state as approval.
- If a request is pending, prevent duplicate submissions and show the current review status.

## Compliance and data integrity

- Product ratings, sizes, coupon rates, dates, asset types, report files, and approval status must come from the PRD or service response.
- Clearly distinguish `募集总规模`, `存续规模`, and tranche-level `募集规模`; do not collapse them into one metric.
- A rating tag is a data label, not a recommendation badge. Do not style it as guaranteed safety.
- Keep disclaimer wording, issuer/manager attribution, data date, and source when supplied. Do not create investment-suitability or performance claims from visual samples.
- Do not put protected documents into search indexing, analytics payloads, previews, or cached UI before authorization.

## Legacy-frame normalization

- The sampled frames contain `11px` tags, `12/17`, `14/20`, and `16/22` section labels. For new work, normalize these to the current complete tokens: `10/14`, `12/18`, `14/22`, and heading `16/24`.
- Use `PingFang SC Medium 500` for headings and `PingFang SC Regular 400` for body text. A missing `font-weight` in a sampled node is not permission to inherit an arbitrary weight.
- Use current primary cyan `#00D2F0`. Keep a legacy cyan header only when exact reproduction is explicitly requested.
- The selected product-list sample uses visually tight stacking. New work uses the confirmed `12px` card-to-card gap and `12px` card padding.

## Review checklist

- Check navigation, 16px gutters, 343px content width, card padding/rhythm, safe areas, and scroll reachability.
- Check the homepage order: message → categories → value → featured product → business content → insight flow.
- Check list/search card parity, keyword highlighting, clear behavior, empty state, and state restoration.
- Check detail sections, long values, tranche switching, dates/units, file counts, and collapsible behavior.
- Check locked, invalid, submitted, failed, pending, approved, downloadable, and unavailable-file states.
- Check black 40% mask, 270px dialog, 16px radius, inline validation, and semantic success/error colors.
- Check that protected data is not leaked and the disclaimer is complete, approved, and unobscured.

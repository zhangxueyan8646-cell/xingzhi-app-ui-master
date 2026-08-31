# Empty 空态

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-Empty 空态` (`6:2898`).

Use an empty state when expected content is absent, a query returns no results, the user has not supplied required information, or the system cannot provide content because of loading, network, permission, or error conditions. Diagnose the state before choosing the illustration and action.

## Scale and anatomy

| Context | Illustration | Label | Use |
|---|---:|---|---|
| Page-level | `160 × 160px` | Commonly `14px / 22px` in full-page application examples; the asset catalog captions use `12px / 18px` | Use in the main content region when the entire page or major section is empty. |
| Container-level | `120 × 120px` | `12px / 18px` | Use inside cards, panels, and smaller bounded regions. |
| Compact application example | `100 × 100px` | `12px / 18px` | Use only when the containing card or section cannot accommodate the standard page-level asset. |

Build the component from:

1. A semantic empty-state illustration
2. A concise state label or optional title and description
3. An optional recovery/action button

Center the group horizontally in its host region. Keep illustration and label adjacent with `0px` vertical gap where the source pairs them as one “缺省图” unit.

## Semantic illustrations

The page-level asset set includes these documented meanings:

- 当日暂无会议（日历）
- 无结果（筛选）
- 暂无邀请
- 暂无数据
- 暂无互动消息
- 暂无路演
- 未搜到您所在的机构/公司
- 暂无网络
- 无结果
- 已认证
- 认证中
- 无权限
- 未输入内容
- 网页版登录确认
- 加载中
- 加载异常
- 开发中，敬请期待

The container-level set includes `暂无数据` and `加载失败/异常`. Reuse the exact semantic asset when available; do not substitute a generic no-data illustration for offline, permission, loading, or error states.

## Copy hierarchy

### Simple state

- Use one centered label below the illustration.
- Use `#555555` for the label.
- Use `12px / 18px` for compact/container empty states.
- Use `14px / 22px` for the full-page application treatment shown in the source.

### Titled state

- Limit the title to one line.
- Use title `16px / 24px`, Medium `500`, `#222222`.
- Use description `14px / 22px`, Regular `400`, `#555555`.
- Use `8px` between title and description.
- Keep copy specific and actionable. State what is missing or what the user can do next; do not blame the user.

## Action button

Add a button only when the user can recover or continue, such as retrying after a load/network error.

- Reference size: `104 × 36px`.
- Use primary cyan `#00D2F0` and a full pill radius (`100px` in the source specimen).
- Use white label `14px / 20px`, Medium `500`.
- Use `16px` between the illustration/label unit and the button.
- Use a specific verb such as “重新加载”. Do not show retry for a true no-data state with no available recovery action.

## Host-context patterns

- **Default page state:** show the illustration and concise label centered in the available main content region.
- **With action:** add the recovery button beneath the label.
- **With title:** use illustration → title/description → action, with `8px` inside the copy block and `16px` before the action.
- **Card/panel:** use the container or compact scale; center within the actual empty content area, not the full screen.
- **Drawer/sheet:** center the empty state below the drawer title and close affordance. Use the drawer radius rules in [radius.md](radius.md).
- **Loading overlay/example:** distinguish loading from empty data and preserve the surrounding modal/sheet hierarchy; do not present loading as a final empty state.

## State behavior

- Replace skeleton/loading with a final empty state only after the request completes successfully with no content.
- Use loading-error or offline semantics for failed requests; preserve user input and offer retry when possible.
- Use no-results semantics for a search/filter result and offer clearing or changing filters when the product supports it.
- Use permission/authentication states only when access or verification is the actual cause.
- Keep surrounding navigation and context available unless the state belongs to a modal flow.
- Announce state changes to assistive technology, and expose the recovery action with a meaningful label.

## Source boundaries

- The catalog tiles (`160 × 178px` and `120 × 138px`) include illustration plus documentation caption; these outer tile measurements are not runtime component sizes.
- The large gray regions, specification borders, and sample list cards are presentation/context elements, not empty-state tokens.
- The source includes a `160 × 182px` illustration-plus-label group and larger `234/266px` composed groups. Treat those heights as content-derived examples, not fixed global heights.

## Review checklist

- Verify the semantic illustration matches the actual cause.
- Verify page/container/compact scale matches the host region.
- Verify simple or titled copy uses the documented sizes, colors, and `8px` internal spacing.
- Verify the button appears only for a real recovery action and uses the `104 × 36px` pill treatment with `16px` separation.
- Verify the state is centered in its content region, does not cover navigation, and remains legible at supported text sizes.
- Verify loading, empty, error, offline, permission, and no-results states are not conflated.

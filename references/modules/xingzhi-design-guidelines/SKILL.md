---
name: xingzhi-design-guidelines
description: Apply the XingZhi App design system when creating, revising, implementing, or reviewing mobile UI. Covers canonical color, typography, spacing, radius, components, navigation, overlays, forms, feedback and page-layout rules. Use whenever the user mentions 行知、行知 App、华泰行知、行知设计规范 or asks to match the XingZhi visual language.
---

# 行知 App 设计规范

## 使用流程

1. 识别页面、组件和业务域；多个行知专项可能匹配时，先读取 [domain-skill-routing.md](references/domain-skill-routing.md)。
2. 所有视觉任务读取 [colors.md](references/colors.md)、[typography.md](references/typography.md)、[spacing.md](references/spacing.md) 和 [radius.md](references/radius.md)。
3. 只读取页面实际使用的组件参考，不要一次加载全部文件。
4. 业务结构和状态由对应专项 Skill/PRD 定义；本 Skill 负责基础 Token、共享组件及视觉一致性。
5. MasterGo 生成或验收时检查真实文字节点，确认字体家族与 `font-weight` 实际保留。

## 权威基础规则

- 中文为 `PingFang SC`。标题 Medium `500`：`20/28`、`18/26`、`16/24`、`14/22`；正文 Regular `400`：`16/24`、`14/22`、`12/18`、`10/14`；最小字号 `10px`。
- 标准移动画布 `375px`，左右留白 `16px`，主内容宽 `343px`。Main 模块明确采用 `12px/351px` 变体时，不与标准网格混用。
- 新卡片默认内边距 `12px`；纵向同级卡片默认间距 `12px`；紧凑双列、三列或横向卡组使用 `8px`；卡片圆角 `8px`。
- 一级 Tabs：选中 `16/24 500`，未选中 `14/22 400`，容器高 `44px`，指示器 `14 × 3px`。
- 标签圆角 `3px`，卡片 `8px`，抽屉/弹窗 `16px`，按钮为全胶囊。
- 弹窗/抽屉遮罩为黑色 `40%`；引导和未开放状态为黑色 `75%`；需要模糊时另加 `10px` blur。
- 主色 `#00D2F0`；文字层级 `#222222 → #555555 → #999999 → #BBBBBB`；背景 `#F5F7FA`；边框 `#E6EBF0`。
- 金融涨跌色服从市场配置，但必须同时显示正负号、箭头或文字，不能只依赖颜色。

## 组件参考路由

- 图像与内容：[operations-banner.md](references/operations-banner.md)、[swipe-carousel.md](references/swipe-carousel.md)、[information-flow.md](references/information-flow.md)、[card.md](references/card.md)、[avatar.md](references/avatar.md)、[tag.md](references/tag.md)、[icons.md](references/icons.md)。
- 导航与布局：[navigation-bar.md](references/navigation-bar.md)、[tabs.md](references/tabs.md)、[tab-bar.md](references/tab-bar.md)、[main-module-layout.md](references/main-module-layout.md)、[main-login-layout.md](references/main-login-layout.md)、[topic-layout.md](references/topic-layout.md)、[project-layout.md](references/project-layout.md)、[business-layout.md](references/business-layout.md)。
- 表单与选择：[form.md](references/form.md)、[input.md](references/input.md)、[input-number.md](references/input-number.md)、[radio.md](references/radio.md)、[checkbox.md](references/checkbox.md)、[switch.md](references/switch.md)、[calendar.md](references/calendar.md)、[date-time-picker.md](references/date-time-picker.md)、[dropdown.md](references/dropdown.md)、[filter-view.md](references/filter-view.md)、[search.md](references/search.md)、[upload.md](references/upload.md)。
- 数据与流程：[table.md](references/table.md)、[steps.md](references/steps.md)、[collapse.md](references/collapse.md)、[loading.md](references/loading.md)、[empty-state.md](references/empty-state.md)、[dot-badge.md](references/dot-badge.md)。
- 浮层与反馈：[modal.md](references/modal.md)、[popup.md](references/popup.md)、[popover.md](references/popover.md)、[action-sheet.md](references/action-sheet.md)、[share.md](references/share.md)、[mask.md](references/mask.md)、[toast.md](references/toast.md)、[notice-bar.md](references/notice-bar.md)、[result-feedback.md](references/result-feedback.md)、[guide.md](references/guide.md)、[pendant.md](references/pendant.md)。
- 账号、合规与智能：[login.md](references/login.md)、[lightweight-login.md](references/lightweight-login.md)、[disclaimer.md](references/disclaimer.md)、[ai-layout.md](references/ai-layout.md)。
- 阴影：[shadows.md](references/shadows.md)。

## 冲突处理

统一优先级：用户当前明确要求 → 当前 PRD/监管/后端状态 → 专项 Skill 的业务结构 → 精确组件规范 → 本 Skill 基础 Token → 历史画板样式。

- 精确组件只在自身作用域覆盖基础 Token，例如验证码 `24/26`、InputNumber 数值 `16/18 500`、Table 专用字号。
- 历史画板的异常字号、错别字、演示数据、标注尺寸、像素取整和重复隐藏图层不能升级为规范。
- 同一页面跨域时允许组合专项 Skill，但必须按 [domain-skill-routing.md](references/domain-skill-routing.md) 明确各自负责的页面或流程段。
- 两条精确规则在同一作用域仍冲突时，不静默选择；创建时记录待决项，审核时保留现状并指出冲突。

## 验收

- 检查字体完整 Token、颜色语义、网格、卡片间距、圆角和安全区。
- 检查组件类型与交互语义一致，Tabs/Tab Bar、Toast/Notice、Modal/Popup 不混用。
- 检查加载、空态、失败、无权限和结果反馈彼此独立。
- 检查固定区域不遮挡正文、错误、免责声明或系统手势区域。

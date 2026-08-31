---
name: xingzhi-investment-wealth-guidelines
description: Apply the XingZhi investment-and-wealth specification when creating, revising, implementing, or reviewing 投资理财首页、私募管理人、管理人详情、私募创造营、活动介绍与规则、活动报名、参赛产品选择、产品数据授权、机构身份认证、交流申请、我的预约及提交结果反馈。Use whenever the user mentions 行知投资理财、私募基金、私募管理人、私募创造营、参赛产品、产品授权、机构认证、管理人交流 or asks to match the selected investment-and-wealth landing pages.
---

# 行知投资理财规范

## 目标

将投资理财首页、私募创造营报名和私募管理人交流组织为一致的行知移动端体验。调用本 Skill 时，同时使用 `$xingzhi-design-guidelines` 落实基础 token、组件和状态规范。

## 选择参考

- 创建或审核投资理财首页、私募创造营介绍、活动规则、策略分组和评分指标时，完整读取 [references/landing-and-camp.md](references/landing-and-camp.md)。
- 创建或审核活动报名、添加参赛产品、产品数据授权、机构身份认证及提交结果时，完整读取 [references/registration-and-authorization.md](references/registration-and-authorization.md)。
- 创建或审核私募管理人列表、管理人详情、交流申请和我的预约时，完整读取 [references/manager-and-exchange.md](references/manager-and-exchange.md)。
- 同一任务跨越多个子流程时，读取对应的全部参考；不要从一张画板推导未展示状态。

## 基础规范依赖

- 所有页面读取 `typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`。
- 首页与活动介绍读取 `business-layout.md`、`operations-banner.md`、`tabs.md`、`card.md`、`tag.md`、`disclaimer.md`。
- 报名与认证读取 `form.md`、`input.md`、`upload.md`、`checkbox.md`、`button.md`。
- 产品选择与授权读取 `search.md`、`popup.md`、`modal.md`、`mask.md`、`checkbox.md`。
- 交流申请读取 `form.md`、`input.md`、`radio.md`、`checkbox.md`、`disclaimer.md`、`button.md`。
- 成功、异常、空列表和加载失败读取 `result-feedback.md`、`empty-state.md`、`toast.md`。

## 工作流程

1. 先判断任务属于首页浏览、创造营活动、报名授权、管理人浏览还是交流预约。
2. 明确登录态、机构认证、产品资格、授权状态和交流申请权限；在入口处说明阻断原因及恢复路径。
3. 区分展示数据、用户输入、系统回填、可选择项和服务端状态；不得把画板示例值写死。
4. 长表单按管理人信息、参赛产品、协议与提交操作分组；提交失败时保留已填内容和已选产品。
5. 产品授权逐项确认授权对象、内容、频率、期限和产品范围；未明确同意不得默认授权。
6. 管理人交流先展示对象和交流方式，再收集议题、参会方式和联系人信息；认证信息异常时提供重认证入口。
7. 以服务端结果驱动报名、授权、认证和预约状态；成功、异常、失败不得共用文案或图标。

## 冲突与边界

优先级为：当前 PRD 与用户最新要求 → 本 Skill 的业务规则 → 行知具体组件规范 → 行知基础 token → 选中旧稿展示值。

- 中文逐文字节点显式使用 `PingFang SC`；标题 Medium `500`，正文 Regular `400`。
- 标题只使用 `20/28、18/26、16/24、14/22`；正文使用 `16/24、14/22、12/18、10/14`，最小字号 `10px`。
- 一级 Tab 保持选中 `16/24 500`、未选中 `14/22 400`。
- 新页面卡片内边距使用 `12px`，相邻卡片间距使用 `12px`；仅在还原既有组件专用几何时使用该组件明确值。
- 不复制旧稿中的 `14/20`、`12/17` 等过时行高；Input 等组件的专用行高只在其组件内部生效。
- 本 Skill 不覆盖 ABS/REITs、存续资产项目和文件权限；这些任务使用 `$xingzhi-asset-management-guidelines`。
- 本 Skill 不覆盖收益互换、交易申请和融券询价；这些任务使用 `$xingzhi-derivatives-guidelines`。
- 活动规则、产品数据、收益、日期、机构信息、风险提示和免责声明必须来自 PRD、接口或合规批准文本，不得推测或承诺收益。

## 验收重点

- 首页的理财入口、私募管理人、活动入口和内容资讯层级清楚，主操作不被信息流淹没。
- 创造营的活动简介、规则、策略分组、评分指标、报名状态和“我的报名”关系完整。
- 报名表单的必填、只读回填、产品添加、策略分组、协议勾选和提交状态一致。
- 授权弹窗逐项展示授权范围，并支持取消、关闭、继续和失败恢复。
- 管理人列表、详情和旗下产品数据来源明确，交流申请始终指向当前管理人。
- 交流议题多选、共同参会单选、联系人信息、重认证、免责声明和提交校验完整。
- 我的预约保留业务类型与状态，并能恢复到相应详情或申请上下文。
- 底部固定操作避让安全区，不遮挡协议、表单错误、免责声明或最后一张卡片。

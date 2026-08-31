---
name: xingzhi-derivatives-guidelines
description: Apply the XingZhi financial-innovation and derivatives specification when creating, revising, implementing, or reviewing 衍生品业务专区、跨境收益互换、大宗商品互换、港股及期货交易申请、多挂钩标的、TIF/CROSS 扩展参数、标的自选、分组管理、卖空询券、批量融券申请、融券申请记录、撤单及结果反馈。Use whenever the user mentions 行知金创、衍生品专区、收益互换、交易申请、多标的、TIF、CROSS、我的自选、添加自选、管理分组、卖空、询券、融券申请、券息率、DMA or asks to match the selected derivatives pages.
---

# 行知金创 / 衍生品规范

## 目标

将衍生品业务介绍、交易申请和融券询价申请组织为一致的行知移动端体验。调用本 Skill 时，同时使用 `$xingzhi-design-guidelines` 落实基础 token 与组件状态。

## 选择参考

- 创建或审核衍生品专区、收益互换入口时，完整读取 [references/derivatives-zone.md](references/derivatives-zone.md)。
- 创建或审核普通/HK 股票基金交易申请时，完整读取 [references/trading-application.md](references/trading-application.md)。
- 创建或审核添加自选、我的自选、标的搜索、移动分组、新建/重命名/管理分组时，完整读取 [references/watchlist-management.md](references/watchlist-management.md)。
- 创建或审核卖空询券、批量申请、融券记录、撤单及反馈时，完整读取 [references/securities-lending.md](references/securities-lending.md)。
- 同一任务跨越多个流程时，读取对应的全部参考，不从一张画板推导另一流程。

## 基础规范依赖

- 所有页面读取 `typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`。
- 专区读取 `business-layout.md`、`operations-banner.md`、`card.md`、`information-flow.md`、`tag.md`。
- 交易/申请读取 `form.md`、`input.md`、`input-number.md`、`radio.md`、`table.md`、`button.md`。
- 自选与分组读取 `search.md`、`tabs.md`、`popover.md`、`popup.md`、`checkbox.md`、`modal.md`。
- 异常与确认读取 `empty-state.md`、`modal.md`、`mask.md`、`toast.md`、`result-feedback.md`。

## 工作流程

1. 确认页面属于业务介绍、交易申请、自选管理、询券选择、申请编辑、申请记录还是结果反馈。
2. 明确账户、市场、标的、币种、数量、价格、券息率、DMA、锁定竞价等字段的数据来源与编辑权限。
3. 区分展示值、可选择值、可输入值和服务端计算值；不得只靠颜色表达。
4. 提交前校验必填、范围、精度、交易时间、账户权限和业务限制，并保留用户已输入内容。
5. 以服务端结果更新申请状态；失败、部分成功、撤单和重试必须提供明确恢复路径。
6. 对账户、证券代码、批次号和示例日期使用真实数据绑定，禁止复制画板演示值。

## 冲突处理

优先级为：当前 PRD 与用户最新要求 → 本 Skill 的业务规则 → 行知具体组件规范 → 行知基础 token → 选中旧稿展示值。

- 中文显式使用 `PingFang SC`；标题 Medium `500`，正文 Regular `400`。
- 标题只使用 `20/28、18/26、16/24、14/22`；正文使用 `16/24、14/22、12/18、10/14`，最小字号 `10px`。
- InputNumber 的数值 `16/18 500`、Table 和组件专用字号只在对应组件作用域内生效。
- 保留画板中的业务结构和状态关系；不复制 `14/20`、`12/17` 等旧行高或未经确认的字段错别字。
- 金融数值不得为适配布局而截断、四舍五入或改写单位；显示值与提交值必须一致。

## 验收重点

- 专区先展示关键业务入口，再展示产品说明、专家服务和投教内容。
- 交易申请的账户、标的、行情、方向、数量、价格和算法参数层级清晰。
- 自选标的的收藏状态、所属分组、搜索、移动、移除与分组管理同步。
- 询券表格的搜索、选择、批量申请、空态和加载失败语义完整。
- 融券申请的多笔编辑、删除、锁定竞价、券息率、数量、计数和提交结果同步。
- 申请记录的未受理、已拒绝、部分受理、已受理与撤单权限一致。
- 所有底部固定操作避让安全区，不遮挡风险提示、表单错误或表格内容。

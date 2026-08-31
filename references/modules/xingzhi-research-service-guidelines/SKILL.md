---
name: xingzhi-research-service-guidelines
description: Apply the XingZhi research-content service specification when creating, revising, implementing, or reviewing 研究服务首页、研报/个股/栏目/专题导航、个股列表与筛选、自选、个股详情、实时或五档行情、投资评级、目标价、公募持仓排名、研究员、研报与活动、月度金股、组合收益、选股策略、行业关注及空状态。Use whenever the user mentions 行知研究服务、个股研究、个股详情、研究员、月度金股、选股策略或行业关注。
---

# 行知研究服务规范

## 目标

将研究内容、证券行情和研究观点组织为可核验、可追溯的移动端体验。该规范约束研究服务内容页，不替代机构研究服务的申请与审核流程。

## 必须同时读取的基础规范

先读取 `xingzhi-design-guidelines` 的以下文件：

- `references/typography.md`、`colors.md`、`spacing.md`、`radius.md`
- `references/navigation-bar.md`、`tabs.md`、`card.md`
- 列表与筛选：`filter-view.md`、`search.md`、`tag.md`、`empty-state.md`
- 详情与内容：`information-flow.md`、`avatar.md`、`button.md`、`disclaimer.md`
- 浮层：`popup.md`、`mask.md`

## 页面路由

- 研究服务首页、个股列表和筛选：读取 [research-service-and-stock-list.md](references/research-service-and-stock-list.md)。
- 个股详情、行情、研究员、研报详情：读取 [stock-detail-and-content.md](references/stock-detail-and-content.md)。
- 月度金股、选股策略和行业关注：读取 [monthly-gold-picks-and-industry.md](references/monthly-gold-picks-and-industry.md)。

## 执行流程

1. 先识别页面类型：研究服务入口、个股列表、个股详情、研报正文、月度金股或行业关注。
2. 明确市场、证券代码、内容版本和数据时间，禁止把不同口径的数据拼接成同一状态。
3. 区分行情事实、研究评级、目标价、公募持仓排名和研究观点；分别标注日期或来源。
4. 补齐加载、正常、部分无数据、整体无数据、接口失败、无权限和不可关注等状态。
5. 保留主导航、筛选、滚动、自选和返回路径；浮层不得破坏页面上下文。
6. 最后校验免责声明、风险提示、时效性、数据口径和可访问性。

## 强制规则

- 字体使用苹方 `PingFang SC`。标题为 Medium 500：20/28、18/26、16/24、14/22；正文为 Regular 400：16/24、14/22、12/18、10/14；最小字号 10px。
- Tabs 保持选中 16/24、500，未选中 14/22、400。
- 新建卡片默认内边距 12px，卡片间距 12px；优先复用组件库实例。
- 行情涨跌色遵循当前市场约定，同时必须用正负号、方向或文字表达，不能只靠颜色。
- 评级、目标价、排名、收益及研究结论必须来自获准数据源，并标注适用日期；不得自行推断或补造。
- 示例中的历史价格、收益、研究员姓名、错别字和旧文案只用于识别结构，不得复制为真实数据。
- 不把研究内容写成保证收益，不主动增加交易、开户或购买入口。

## 边界与冲突处理

- 本 Skill 处理“研究内容服务”。机构研究服务申请、身份完善、材料上传和受理流程改用 `xingzhi-business-processing-guidelines`。
- 全局综合搜索结果改用 `xingzhi-search-results-guidelines`；超级 ETF 月报改用 `xingzhi-super-etf-monthly-guidelines`。
- 当业务专项规范与基础视觉规范冲突时，业务结构与字段以本 Skill 为准，字体、颜色、间距、圆角及基础组件以 `xingzhi-design-guidelines` 为准。
- PRD、监管或最新合规要求高于示例画板；如需偏离规范，记录偏离原因和影响范围。

## 交付检查

- 页面类型、市场、证券与日期均可识别。
- 行情、评级、观点和收益的层级与来源不混淆。
- 筛选、自选、月份、市场和行业切换的状态连续。
- 空状态能区分整体无数据与单市场无数据。
- 风险提示与免责声明可读，且不被吸底操作遮挡。

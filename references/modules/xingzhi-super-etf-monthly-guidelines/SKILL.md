---
name: xingzhi-super-etf-monthly-guidelines
description: Apply the XingZhi Super ETF monthly-report specification when creating, revising, implementing, or reviewing 超级ETF月报、专属策略表现、策略观点、收益率与回撤、资金洞察、融资余额、资金净流入、热门主题、主题ETF榜单、数据挖掘、融资余额增长、趋势突破、榜单展开、图表提示及月报免责声明。Use whenever the user mentions 行知超级ETF、超级ETF月报、ETF资金洞察、热门主题、ETF榜单、ETF数据挖掘 or asks to match the selected Super ETF report pages.
---

# 行知超级 ETF 月报规范

## 目标

将超级 ETF 月报的策略、资金、主题和榜单数据组织为一致、可核验的行知移动端阅读体验。调用本 Skill 时，同时使用 `$xingzhi-design-guidelines` 落实基础 token、组件和状态规范。

## 选择参考

- 创建或审核月报导航、月份选择、专属策略表现与策略说明弹窗时，完整读取 [references/report-shell-and-strategy.md](references/report-shell-and-strategy.md)。
- 创建或审核资金洞察、融资余额环图、分类明细、热门主题及主题说明时，完整读取 [references/fund-insight-and-topics.md](references/fund-insight-and-topics.md)。
- 创建或审核融资余额增长、趋势突破、榜单展开、数据异常和免责声明时，完整读取 [references/data-mining-and-compliance.md](references/data-mining-and-compliance.md)。
- 同一任务跨多个栏目时读取对应全部参考；不要从月报页面推导 ETF 交易、申购或产品详情流程。

## 基础规范依赖

- 所有页面读取 `typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`、`tabs.md`、`card.md`。
- 数据列表读取 `table.md`、`tag.md`；月份或指标切换读取 `dropdown.md` 或对应选择组件。
- 策略与主题说明读取 `modal.md`、`mask.md`；分享读取 `share.md`。
- 页面尾部读取 `disclaimer.md`；空数据、加载异常读取 `empty-state.md`、`loading.md`、`toast.md`。

## 工作流程

1. 确认页面属于专属策略表现、资金洞察、热门主题还是数据挖掘。
2. 先绑定报告月份、统计区间、数据截止日和数据源，再生成任何数值或观点。
3. 明确数值的字段语义、单位、精度、正负号、排序方向和空值规则；展示值不得替代原始计算值。
4. 保持图表、图例、汇总值和明细表使用同一数据快照；切换月份或指标时整体更新。
5. 将研究观点、事实数据和榜单规则分开呈现；不可把历史表现写成未来收益承诺。
6. 长榜单先展示约定条数，再通过“查看更多/收起”切换；不分页时仍保留当前滚动位置。
7. 所有弹窗、分享和免责声明使用批准文案，并能返回原栏目与原月份。

## 冲突与边界

优先级为：当前 PRD 与用户最新要求 → 本 Skill 的业务规则 → 行知具体组件规范 → 行知基础 token → 选中旧稿展示值。

- 中文逐文字节点显式使用 `PingFang SC`；标题 Medium `500`，正文 Regular `400`。
- 标题只使用 `20/28、18/26、16/24、14/22`；正文使用 `16/24、14/22、12/18、10/14`，最小字号 `10px`。
- 一级 Tab 保持选中 `16/24 500`、未选中 `14/22 400`。
- 新页面卡片内边距使用 `12px`，相邻卡片间距使用 `12px`；组件专用几何仅在该组件作用域内覆盖。
- 不复制旧稿的 `14/20`、`12/17` 等旧行高或已截断异常值；数据表专用字号仅作用于表内。
- 红绿涨跌遵循证券行情业务配置，并始终保留 `+/-`、箭头或文字；不得把涨跌色误当通用成功/错误色。
- 不四舍五入、截断、缩写或改变金融数据单位以迁就布局；若必须格式化，保留可查看完整值的交互。
- 本 Skill 只覆盖已选中的月报阅读体验，不覆盖 ETF 搜索、详情、自选、交易、申购赎回或持仓。

## 验收重点

- 月份、主栏目、二级指标和内容之间的状态同步且返回后可恢复。
- 策略观点、当月收益、历史累计和最大回撤的定义与区间清楚。
- 环图中心值、分段、图例和融资余额明细完全一致，极端值不会溢出或误导。
- 热门主题排名、主题说明、ETF名称、代码、规模和融资余额来源一致。
- 数据挖掘榜单的指标口径、排名、单位、展开数量和排序方向明确。
- 统计时点、数据来源、风险提示和免责声明完整，分享内容携带相同报告版本。

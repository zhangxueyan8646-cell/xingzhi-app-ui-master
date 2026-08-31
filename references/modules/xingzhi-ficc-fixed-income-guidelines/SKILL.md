---
name: xingzhi-ficc-fixed-income-guidelines
description: Apply the XingZhi FICC fixed-income specification when creating, revising, implementing, or reviewing 利率类收益互换、固定/浮动参考利率、固收交易表单、交易账户、账户资产与持仓、账户间资金划转、账户出金、结算账户、最大可出金额、出金确认与审核结果、出金记录与日期/状态筛选、机构信息修改、境内外主体审核、客户经理移交及机构搜索。Use whenever the user mentions 行知 FICC、FICC 固收、固收交易、利率互换、浮动参考利率、资金划转、账户出金、出金记录、交易账户或固收准入审核。
---

# 行知 FICC 固收规范

## 目标

将 FICC 利率交易、账户资产、资金划转和准入审核组织为可信、可核验的移动端体验。调用本 Skill 时，同时使用 `xingzhi-design-guidelines` 落实基础视觉与组件规范。

## 选择参考

- 利率类交易表单、浮动参考利率和基准切换：读取 [rates-and-order-entry.md](references/rates-and-order-entry.md)。
- 账户资产、持仓、资金划转、校验、确认与结果：读取 [account-and-fund-transfer.md](references/account-and-fund-transfer.md)。
- 账户出金、结算账户、确认转出、审核结果和出金记录：读取 [account-withdrawal-and-records.md](references/account-withdrawal-and-records.md)。
- 机构信息修改、审核、移交提示和机构搜索：读取 [institution-review-and-search.md](references/institution-review-and-search.md)。
- 同一任务跨越多个流程时，读取对应的全部参考，不能从单张画板补造完整流程。

## 基础规范依赖

- 所有页面：`typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`。
- 交易与划转：`form.md`、`input.md`、`input-number.md`、`table.md`、`button.md`。
- 选择与确认：`tabs.md`、`popup.md`、`modal.md`、`mask.md`。
- 结果与异常：`result-feedback.md`、`empty-state.md`。
- 机构查找：`search.md`。

## 工作流程

1. 识别页面属于利率交易、账户、资金划转、账户出金、出金记录、机构资料、审核还是搜索选择。
2. 确认客户、部门/产品、交易账户、币种、金额、利率基准和数据时间的来源及权限。
3. 区分只读值、选择值、输入值、服务端计算值和审批结论，不得用相同样式混淆。
4. 提交前校验账户类型、归属关系、余额、保障金额、金额范围、精度和业务开放状态。
5. 高风险动作执行“输入 → 服务端预校验 → 二次确认 → 提交 → 服务端结果”，防止重复提交。
6. 审核与移交必须保留原因、处理人/队列、状态和返回修改路径。
7. 记录列表按账户、发起日期和审批状态筛选，返回详情后保留筛选和滚动位置。

## 强制规则

- 中文字体为 `PingFang SC`。标题使用 Medium `500`：20/28、18/26、16/24、14/22；正文使用 Regular `400`：16/24、14/22、12/18、10/14；最小字号 10px。
- Tabs 保持选中 16/24、500，未选中 14/22、400。
- 新建卡片内边距 12px，卡片与卡片之间 12px；标准屏幕左右留白 16px。
- 金额、利率、期限、日期和账户编号不得为适配布局而截断、改写或静默四舍五入；显示值、确认值和提交值必须一致。
- 金额使用精确十进制计算；输入、单位提示、大小写金额和服务端值使用同一口径。
- 账户、机构、利率基准、样例价格、日期和审批文案均来自获准数据源，不复制画板示例数据。
- 交易或划转结果只能以后端最终状态为准；按钮进入提交中状态并防止重复点击。
- 出金并非即时到账；“提交成功”只表示进入审核，不能展示为“兑付完成”。

## 边界与冲突处理

优先级：当前 PRD 与用户最新要求 → 本 Skill 业务规则 → 行知具体组件规范 → 行知基础 token → 选中旧稿示例值。

- 利率类收益互换同时涉及合约生命周期时，使用本 Skill 定义利率、账户和划转字段，并使用 `xingzhi-derivatives-guidelines` 定义交易申请、订单与结果状态。
- 非 FICC 的跨境收益互换、大宗商品互换、询券和融券流程以 `xingzhi-derivatives-guidelines` 为主。
- 机构名称搜索属于表单选择器，不等同于行知全局内容搜索；只有综合内容检索才改用 `xingzhi-search-results-guidelines`。
- 画板中与 FICC 无关的任务、积分、币值或其他业务模块视为组合稿干扰，不纳入规范。

## 验收重点

- 利率基准的代码、名称、市场、币种、计息与重置规则可区分。
- 账户总览、持仓表格、划入/划出账户和余额口径明确。
- 四类划转限制分别给出准确原因与返回修改路径。
- 二次确认展示完整账户、金额、币种和方向；成功反馈可安全返回账户。
- 出金页展示脱敏结算账户和预计兑付日；记录页状态、发起时间、金额与兑付日期口径一致。
- 审核资料可追溯，境内/境外/无法识别三类结果与移交动作一致。
- 遮罩、弹窗、抽屉和底部操作避让安全区，并阻断背景交互。

---
name: xingzhi-programmatic-trading-guidelines
description: Apply the XingZhi programmatic-trading specification when creating, revising, implementing, or reviewing QTM/QMT 软件使用协议签署、经纪客户号确认、交易密码校验、程序化交易委托协议阅读、协议签署成功、电子签署待签署/已完成列表、文件搜索筛选、批量选择、查看、签署、发送邮箱及空状态。Use whenever the user mentions 行知程序化交易、QTM、QMT、程序化交易协议、经纪客户号、交易密码、电子签署 or asks to match the selected programmatic-trading signing pages.
---

# 行知程序化交易规范

## 目标

将程序化交易的软件协议签署和电子签署记录组织为安全、可审计的行知移动端流程。调用本 Skill 时，同时使用 `$xingzhi-design-guidelines` 落实基础 token 与组件，并复用 `$xingzhi-business-processing-guidelines` 的通用协议签署、幂等提交和结果反馈规则。

## 选择参考

- 创建或审核经纪客户号、交易密码输入与校验时，完整读取 [references/account-verification.md](references/account-verification.md)。
- 创建或审核程序化交易委托协议阅读、确认签署与签署结果时，完整读取 [references/agreement-signing.md](references/agreement-signing.md)。
- 创建或审核电子签署列表、搜索筛选、批量选择、待签署、已完成和空态时，完整读取 [references/e-signature-records.md](references/e-signature-records.md)。
- 同一任务跨多个阶段时读取对应全部参考；不要从本批画板推导策略参数、交易下单或算法配置。

## 基础规范依赖

- 所有页面读取 `typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`。
- 客户号确认读取 `input.md`、`form.md`、`button.md`、`toast.md`。
- 协议阅读与签署读取 `checkbox.md`、`button.md`、`modal.md`、`mask.md`、`loading.md`、`disclaimer.md`。
- 电子签署记录读取 `tabs.md`、`search.md`、`dropdown.md`、`card.md`、`checkbox.md`、`tag.md`、`empty-state.md`。
- 签署完成或异常读取 `result-feedback.md`、`toast.md`。

## 工作流程

1. 先确认当前任务属于客户号校验、协议阅读、签署提交、结果反馈或记录管理。
2. 绑定登录账户、经纪客户号、协议 ID/版本、签署对象和服务端状态；不得复制画板示例值。
3. 客户号与交易密码只用于安全校验，不得写入日志、分析事件、搜索索引或普通缓存。
4. 区分“已阅读”“已表达签署意愿”“签署请求已提交”和“服务端签署成功”；四者不得合并。
5. 提交采用幂等请求；重复点击、网络中断、签署处理中和状态轮询必须提供准确反馈。
6. 签署记录以服务端状态驱动；批量签署只提交用户明确选中的、仍可签署的记录。
7. 返回或重新进入时恢复正确记录、协议版本、Tab、搜索条件和滚动位置，不恢复明文交易密码。

## 冲突与边界

优先级为：当前 PRD 与用户最新要求 → 本 Skill 的业务规则 → `$xingzhi-business-processing-guidelines` 的通用签署规则 → 行知具体组件规范 → 行知基础 token → 选中旧稿展示值。

- 中文逐文字节点显式使用 `PingFang SC`；标题 Medium `500`，正文 Regular `400`。
- 标题只使用 `20/28、18/26、16/24、14/22`；正文使用 `16/24、14/22、12/18、10/14`，最小字号 `10px`。
- 一级 Tab 保持选中 `16/24 500`、未选中 `14/22 400`。
- 新页面卡片内边距使用 `12px`，相邻卡片间距使用 `12px`；组件专用几何仅在该组件作用域覆盖。
- 画板同时出现 `QTM` 与 `QMT`。产品正式名称必须由当前 PRD、协议标题和后台配置确认；不得凭经验自动改写。
- 协议正文、主体名称、法律法规、客户身份、协议版本和服务经理说明均属于受控内容，不得概括替换。
- 本 Skill 当前只覆盖协议签署闭环和电子签署记录，不覆盖算法策略、交易指令、风控参数、行情或订单管理。

## 验收重点

- 客户号、交易密码的空值、填写、显示/隐藏、错误和提交状态准确且安全。
- 协议标题、甲乙方、版本、正文、阅读位置和签署动作可追溯。
- 签署成功只在服务端确认后展示，并提供准确后续办理说明。
- 待签署、已完成、拒签、已签署等状态与可用操作一致。
- 搜索、业务类型、创建时间筛选和批量选择不会改变原始签署状态。
- 空列表、无搜索结果、加载失败和无权限使用不同反馈。
- 固定操作区避让 Home Indicator，不遮挡协议末尾、错误提示或最后一张记录卡。

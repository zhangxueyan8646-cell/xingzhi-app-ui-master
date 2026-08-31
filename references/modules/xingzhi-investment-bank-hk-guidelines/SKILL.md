---
name: xingzhi-investment-bank-hk-guidelines
description: Apply the XingZhi Hong Kong investment-banking specification when creating, revising, implementing, or reviewing 港股 IPO 簿记信息、发行规模、绿鞋、认购倍数、订单集中度、投资者结构、基石/锚定认购、投资者订单明细、智能排序、发行定价及配售明细。Use whenever the user mentions 行知投行港股、港股 IPO 簿记、基石投资者、锚定认购、簿记明细或配售明细。
---

# 行知投行港股规范

## 使用方式

1. 同时使用 `xingzhi-design-guidelines`；涉及图表、搜索、Tabs、Card、Table 时读取对应组件参考。
2. 创建或审核簿记总览、认购明细和配售明细时，读取 [bookbuilding-and-allocation.md](references/bookbuilding-and-allocation.md)。
3. 先绑定发行项目、版本、币种、价格区间和数据更新时间，再展示指标、图表或投资者数据。

## 强制规则

- 簿记、基石认购、锚定认购和配售是不同业务对象，不因卡片结构相似而合并字段。
- 金额、股数、价格、认购倍数、获配比例和发行规模使用精确金融数值；单位、币种和时间口径可见。
- 图表、汇总和明细必须来自同一数据快照；智能排序说明排序字段和方向。
- 投资者名称、订单、备注和投行名单按权限展示，导出、日志和截图遵循数据最小化。
- `HKD` 使用业务币种字典；源稿中的 `HDK`、异常千分位和示例名称不得复制。

## 边界

- 本 Skill 负责港股 IPO 一级市场簿记与配售，不负责二级市场港股交易、FICC、衍生品订单或普通投资产品。
- 投资者名称搜索属于簿记/配售列表内搜索，不调用全局综合搜索结果结构。
- 基础视觉冲突按：用户/PRD/监管 → 本 Skill 业务规则 → 精确组件 → 行知基础 Token → 历史画板处理。

## 验收

- 发行规模、绿鞋、价格、汇率和认购倍数的定义与币种一致。
- 集中度、投资者类型/地区分布和每日订单趋势有图例、单位、日期与更新时间。
- 认购与配售卡片字段、详情表、搜索、排序、结束状态和长文本展开可用。
- 不把历史示例数据、错别字或跨版本数值写成正式内容。

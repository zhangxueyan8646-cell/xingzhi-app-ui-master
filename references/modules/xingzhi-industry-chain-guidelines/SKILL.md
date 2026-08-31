---
name: xingzhi-industry-chain-guidelines
description: Apply the XingZhi industry-chain specification when creating, revising, implementing, or reviewing 产业链图谱首页、主题图谱、公司图谱、上中下游产品关系、主营构成、上下游/同业公司、关联产品选择及主题/公司搜索结果。Use whenever the user mentions 行知产业链、产业链图谱、主题图谱、公司图谱、上下游产品或关联公司。
---

# 行知产业链规范

## 使用方式

1. 同时使用 `xingzhi-design-guidelines`；涉及搜索结果框架时组合 `xingzhi-search-results-guidelines`。
2. 创建或审核首页、主题详情、公司详情时，读取 [industry-chain-graphs.md](references/industry-chain-graphs.md)。
3. 先绑定主题/公司 ID、证券市场、数据版本和更新时间，再生成图谱与行情数据。

## 强制规则

- 主题图谱按上游/中游/下游展示关系；公司图谱按上游产品/核心产品/下游产品及上游/同业/下游公司展示。
- 图谱节点必须可识别层级、关系、选中态和详情联动，不能只作为静态装饰。
- 公司名称、证券代码和市场共同校验；主题名称与简介必须属于同一主题版本。
- 最新价、总市值和涨跌幅注明市场与时间，并同时提供正负号/方向。
- 关联产品选择保留已选数量和上限，权限、重复和超限有明确反馈。
- 不复制源稿中的代码错配、主题简介错配、重复词、异常断行或示例行情。

## 边界

- 本 Skill 负责产业链图谱首页和详情，不负责“产业圈”的企业动态、活动与社区互动。
- 主题/公司搜索的通用搜索框、Tabs、关键词高亮和分页由 `xingzhi-search-results-guidelines` 负责；本 Skill 负责产业链结果字段和点击后的图谱详情。
- 个股研究评级、研报和研究员内容转 `xingzhi-research-service-guidelines`。

## 验收

- 首页主题/公司入口、涨幅排名和能力说明层级清楚。
- 搜索结果数量、分页、公司代码/价格和主题关联公司数准确。
- 主营构成注明报告期；产品/公司关系和“查看全部”返回上下文连续。
- 图谱、列表和行情来自同一数据快照，加载、空态、失败和无权限不混用。

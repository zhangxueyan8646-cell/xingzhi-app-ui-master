---
name: xingzhi-search-results-guidelines
description: Apply the XingZhi App global-search result specification when creating, revising, implementing, or reviewing 综合搜索、主题/产业链结果、公司/企业结果、研报、路演、专题、视频、资讯、管理人、产品、关键词高亮、分页及无结果页面。Use whenever the user mentions 行知搜索落地页、搜索结果页、综合搜索、主题搜索、公司搜索、产业链搜索 or asks to match the selected search-result screens.
---

# 行知搜索落地页规范

## 使用流程

1. 先加载 `$xingzhi-design-guidelines`，使用其 Search、Tabs、Information Flow、Empty、Loading、Icon 和字体规范。
2. 搜索入口来自首页时，同时加载 `$xingzhi-home-page-guidelines`，保持首页搜索头部和返回路径一致。
3. 读取 [references/search-results.md](references/search-results.md)，确定综合页、主题页、公司页和空结果状态。
4. 优先复用当前文件 `行知app-规范` 中已有的搜索框、一级 Tabs、产业链卡、企业行和信息流组件。
5. 生成后检查真实文字图层，确认 `PingFang SC`、标题 `500`、正文 `400` 和关键词局部高亮正确落地。

## 冲突优先级

1. 用户当前任务和 PRD 的明确业务要求。
2. 本 Skill 的搜索结果信息架构和数据语义。
3. `$xingzhi-design-guidelines` 的具体组件规范。
4. `$xingzhi-home-page-guidelines` 的入口与返回上下文。
5. 所选 MasterGo 历史画面的直接数值。

## 强制规则

- 将 5 个选中画面归为一个搜索结果体系：综合、主题、公司和当前 Tab 无结果状态。
- 顶部只保留一个搜索输入框；查询词、清除按钮、返回和提交操作保持稳定。
- 一级 Tabs 保持：选中 `16/24px 500`，未选中 `14/22px 400`，容器高 `44px`。
- 使用 `375px` 画布、`16px` 边距、`343px` 主内容宽和 `PingFang SC`。
- 关键词只高亮真实命中的文本片段；不得改写结果标题，也不得把整行都染成主色。
- 综合页每个结果模块最多展示代表性条目并提供“查看更多”；主题和公司完整列表使用明确分页或产品指定的加载方式。
- A 股行情涨跌色是市场数据语义，不得当作通用错误/成功色；数值、方向和颜色必须同步。
- 空结果、加载失败、网络异常和无权限使用不同反馈，不得统一显示为“未找到”。

## 验收

- 检查查询词、一级结果 Tab、主题/公司二级切换、结果数量和返回路径。
- 检查产业链、企业和混合内容模块的层级、截断、更多入口与点击目标。
- 检查关键词高亮、行情正负号、价格精度、分页、加载、空态和错误反馈。
- 将源稿旧行高、`9px` 普通文字和静态演示数据按本 Skill 纠正，不建立新 Token。

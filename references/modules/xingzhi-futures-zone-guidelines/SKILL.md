---
name: xingzhi-futures-zone-guidelines
description: Apply the XingZhi App futures-zone specification when creating, revising, implementing, or reviewing mobile UI for 期货专区、期货研报、商品期货分类、期货研究员、期货数据库、期货云路演、研报筛选及对应小程序或 App 首页入口。Use whenever the user mentions 行知期货专区、期货研报、期货数据库、期货研究员、商品期货、云路演 or asks to match the selected futures-zone pages.
---

# 行知期货专区规范

## 使用方式

1. 先加载 `$xingzhi-design-guidelines`，把它作为颜色、字体、间距、圆角、组件和状态的基础规范。
2. 再读取 [references/futures-zone.md](references/futures-zone.md)，确定期货专区的页面结构、业务模块、状态和例外。
3. 创建页面前确认目标是专区首页、研报列表、筛选状态，还是入口图标；不要把长画板截图误当成固定视口。
4. 优先复用当前文件 `行知app-规范` 中已有的 Navigation、Tabs、Avatar、Information Flow、Card、Tag、Button、Popup、Mask 和 Icon 组件。
5. 生成后读取真实文字图层，逐项检查 `PingFang SC`、标题 `500`、正文 `400` 是否实际保留。

## 冲突优先级

1. 用户在当前任务中明确指定的要求。
2. 本 Skill 的期货专区业务规则。
3. `$xingzhi-design-guidelines` 的具体组件规范。
4. 行知基础颜色、字体、间距和圆角规范。
5. 所选 MasterGo 画面的历史样式。

不得因为源画面存在旧字号、异常透明度或不一致头像尺寸而覆盖现行行知规范。

## 强制规则

- 中文字体使用 `PingFang SC`；标题为 Medium `500`，正文为 Regular `400`。
- 一级 Tabs 保持：选中 `16/24px 500`；未选中 `14/22px 400`；容器高 `44px`。
- 页面左右边距 `16px`，主内容宽 `343px`；标准 Banner 为 `343 × 112px`、圆角 `8px`。
- 研报标题使用 `14/22px 500`，元信息使用 `12/18px 400`；运行界面最小字号 `10/14px`。
- 研究员导航统一使用 `36px` 头像；没有研究员时收起整个研究员模块并让后续内容自然上移，不保留空白占位。
- 研报筛选是列表上的底部模态抽屉状态，不是独立页面；遮罩使用黑色 `40%`。
- 不得把选中的 `小程序-icon`、`app首页-icon` 两个入口素材误读为完整业务页面或重新绘制其品牌图形。

## 输出与验收

- 说明使用了哪些行知组件及其状态。
- 对未在源稿中定义的加载、空态、错误、无权限和数据边界，按基础 Skill 补齐，但不得虚构业务结果。
- 对疑似文案错误先标记待产品确认；不要静默纠正源稿业务词。
- 逐项检查页面架构、尺寸、字体、状态切换、筛选提交逻辑、滚动行为、权限提示和安全区。

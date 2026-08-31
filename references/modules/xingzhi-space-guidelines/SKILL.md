---
name: xingzhi-space-guidelines
description: Apply the XingZhi Space mobile specification when creating, revising, implementing, or reviewing 行知空间首页、空间预约、空间切换、空间动态、空间活动、全部活动列表、活动筛选、活动详情、活动议程、报名与签到二维码页面。Use whenever the user mentions 行知空间、空间专区、深圳空间、上海空间、南京空间、全部活动 or asks to match the selected XingZhi Space pages.
---

# 行知空间规范

## 使用流程

1. 先加载 `$xingzhi-design-guidelines`，使用其颜色、字体、间距、圆角和组件规则。
2. 页面包含活动详情、报名或签到凭证时，同时加载 `$xingzhi-landing-page-guidelines`。
3. 读取 [references/xingzhi-space.md](references/xingzhi-space.md)，确认页面类型、品牌化例外和状态模型。
4. 优先复用当前文件 `行知app-规范` 的 Navigation、Dropdown、Information Flow、Tag、Empty、Calendar、Button、Mask 和活动组件。
5. 生成后检查真实文字图层，确认 `PingFang SC`、标题 `500`、正文 `400` 已落地。

## 冲突优先级

1. 用户当前任务的明确要求。
2. 本 Skill 的行知空间业务结构与限定品牌例外。
3. `$xingzhi-landing-page-guidelines` 的活动报名、身份和凭证规则。
4. `$xingzhi-design-guidelines` 的具体组件和基础 Token。
5. 所选 MasterGo 旧画面的直接测量值。

## 强制规则

- 将选中内容归为三个页面：行知空间首页、全部活动列表、活动详情；其余画板均为状态或内容数量差异。
- 使用 `375px` 移动画布、`16px` 页面边距和 `343px` 主内容宽。
- 中文使用 `PingFang SC`；标题 Medium `500`，正文 Regular `400`。
- 运行文字回归行知现行字号：标题 `20/28`、`18/26`、`16/24`、`14/22`；正文 `14/22`、`12/18`、`10/14`。
- 深色实景背景、白色前景文字和黑色底部主按钮只属于行知空间品牌页面，不得扩散到其它行知模块。
- 活动列表的类型与地点是两个独立的单选筛选维度；展开菜单时使用黑色 `40%` 遮罩。
- 活动详情的报名、已报名、签到、已结束等状态独立建模；不得仅替换按钮文案而遗漏权限和反馈。
- 二维码属于受保护凭证，不得出现在日志、埋点、公开截图或分享预览中。

## 验收

- 核对页面类型、空间选择、活动状态、筛选状态和返回后的上下文保留。
- 核对品牌化深色区域与标准白色内容区的边界。
- 核对字号、字重、图片比例、列表截断、空态、加载、遮罩、安全区和底部固定操作。
- 对源稿中的旧行高、2px 圆角、异常字体或重复画板按本 Skill 规则纠正，不建立新 Token。

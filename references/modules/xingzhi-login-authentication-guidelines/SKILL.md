---
name: xingzhi-login-authentication-guidelines
description: Apply the XingZhi content-landing-page login and authentication specification when creating, revising, implementing, or reviewing external-link login, mobile-number login or registration, six-digit verification codes, content truncation, App diversion, domestic/overseas research-service access checks, and return-to-content behavior. Use whenever the user mentions 行知登录认证、站外登录、手机号验证码、内容访问拦截、阅读全文、境内境外研究服务权限 or asks to match the selected login-authentication landing pages.
---

# 行知登录认证规范

## 目标

为行知站内/站外内容落地页提供一致的登录认证、访问拦截和回跳规则。以当前 Skill 的业务流程规则为准，并调用 `$xingzhi-design-guidelines` 落实基础视觉与组件规范。

## 使用流程

1. 识别入口环境：App 内、站外浏览器或从分享链接进入。
2. 判断内容类型与访问策略：直播/回放、研报全文，以及境内/境外研究服务权限。
3. 保留公开内容预览；只在用户触发受限动作时进入 App 引流、权限提示或登录认证。
4. 登录时先收集手机号，再进入六位验证码页；成功后回到原内容和原触发位置。
5. 对登录失败、验证码错误/过期、倒计时、权限不匹配和取消流程提供可恢复路径。
6. 创建或验收前完整读取 [references/login-authentication.md](references/login-authentication.md)。

## 必须同时调用的基础规范

- 字体、颜色、间距、圆角、导航：读取 `$xingzhi-design-guidelines` 的 `typography.md`、`colors.md`、`spacing.md`、`radius.md`、`navigation-bar.md`。
- 登录与表单：读取 `login.md`、`lightweight-login.md`、`input.md`、`button.md`。
- 拦截与反馈：出现权限弹窗时读取 `modal.md`、`mask.md`；出现流程结果页时读取 `result-feedback.md`。
- 直播、研报或搜索等内容模块继续调用对应业务 Skill；本 Skill 只覆盖访问前后的认证衔接。

## 冲突处理

按以下顺序解决冲突：当前 PRD 与用户最新要求 → 本 Skill 的具体登录认证流程 → 行知具体组件规范 → 行知基础 token → 选中旧稿中的展示值。

- 旧稿中 `Alimama ShuHeiTi`、标题 `24px`、正文 `14/20px` 等值不得覆盖最新字体规范。
- 中文统一显式使用 `PingFang SC`；标题为 Medium `500`，正文为 Regular `400`。
- 标题仅使用 `20/28、18/26、16/24、14/22`；正文使用 `16/24、14/22、12/18、10/14`，最小字号 `10px`。
- 验证码字符 `24/26px` 是 `Input` 的专用组件例外，只作用于验证码字符。
- 画板里的真实业务结构、文案含义、状态关系和精确组件尺寸可以保留；规范展示字体、演示内容与偶发历史误差不可直接复制。

## 验收重点

- 确认公开内容不被无条件登录阻断，受限动作触发点明确。
- 确认手机号、验证码、倒计时、按钮可用态与错误反馈同步。
- 确认登录/取消/失败后均能回到合理位置，成功后恢复原内容上下文。
- 确认境内/境外服务权限提示与登录状态分开判断，不把“已登录”误当成“有权限”。
- 确认手机号脱敏、验证码不回显、不记录敏感信息，并防止重复提交。
- 确认所有真实文字节点都显式写入正确的字体家族与字重。

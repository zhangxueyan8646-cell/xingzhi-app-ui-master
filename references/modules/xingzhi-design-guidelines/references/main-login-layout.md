# Main 主模块（登录 / 轻量化登录）布局

## Layout choice

- Use an independent main-module login region when the business module requires its own authentication and contains many functions or substantial business content.
- Use lightweight login when users may browse open content before authentication and only restricted actions require login.
- Do not combine both patterns on the same screen. Choose according to access control and content priority.

## Independent login layout

- Use a `375px` mobile canvas with `16px` content gutters; primary content and login modules are normally `343–344px` wide.
- Keep the navigation and login region as distinct vertical zones. The navigation reference is `44px` high.
- Place the independent login region immediately below navigation and before business content so the current authentication state is visible without interrupting browsing.
- Use the Login component rules from `login.md`. The common compact card is `343 × 48px`; the descriptive card is `343 × 82px`.
- A promotional/login banner may use the `343px` content width and approximately `65px` height when a short value statement is required. Keep its action as a single `60 × 24px` login/detail capsule.
- Show account identity or a login value statement in the login region. Keep supplementary metrics and business details in separate modules.
- After the login region, arrange business modules in a consistent vertical stream. Use `343/344px` full-width modules or two `167.5px` columns where the content type supports paired cards.

## Login state and content order

- Before login, show a clear “登录” action and explain the value of authentication with concise copy such as viewing an overview or accessing a business account.
- Optional recommended content may appear below the login region to demonstrate product value; it must remain usable or clearly marked according to access rights.
- After login, replace the prompt with identifiable, masked account information and change the action to account detail or management.
- Refresh account-dependent modules after login or account switching. Do not retain unauthenticated placeholders alongside authenticated data.
- Preserve this order unless the scenario explicitly requires otherwise: status/navigation → login region → optional Banner/recommendation → primary business modules.

## Lightweight login layout

- Merge the login/account region into the `44px` navigation bar; do not add a separate login card below it.
- Keep the page title centered, navigation/back action on the left, and login/account action on the right.
- Before login, use one concise “登录” entrance. Continue to expose permitted content and trigger authentication only for restricted actions.
- After login, show an account name, masked funding/account number, and switch indicator on the right. Limit Chinese account names to four characters and mask numeric accounts, for example `**8888`.
- A search region or business module may follow directly below the merged navigation. Do not let the account block compress the page title or left navigation control.
- Complete or cancel authentication by returning to the originating page and restoring scroll/task context.

## Modules and recommendations

- Treat recommendation content as optional. It must support the login value proposition or the current business task rather than act as decoration.
- Use a full-width `343 × 192px` media card for prominent recommendations when appropriate; follow the Information Flow and Banner references for detailed content anatomy.
- Keep section titles `16px/22px`, medium (`500`), with optional “更多” using `12px` secondary text.
- Separate recommendation, search, data overview, expert/content cards, and business tools into recognizable modules with the documented spacing rhythm.

## Review checklist

- Confirm independent versus lightweight login matches the actual access model.
- Confirm the independent layout separates `44px` navigation, `343–344px` login region, and business content.
- Confirm the lightweight layout merges login/account state into navigation without adding a duplicate card.
- Confirm login-before and login-after states update action copy, styling, identity, and dependent data together.
- Confirm account fields are masked, account switching is synchronized, and no stale identity remains after expiry or failure.
- Confirm recommendation content is optional, relevant, and placed after the login region.
- Confirm login completion/cancel returns to the original page and preserves task context.

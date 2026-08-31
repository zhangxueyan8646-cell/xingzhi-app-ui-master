# Main 主模块布局

## Purpose

- Use Main modules on first-level pages to present the most important business information and act as the primary entrance to a key business.
- Give each first-level page one clear primary purpose. Do not make several modules compete as equal “main” entrances.
- Build the page from navigation plus a prioritized combination of information, recommendation, a function/金刚区, and information flow.

## Base canvas and frame

- Use a `375px` mobile reference canvas and preserve the system status/safe areas.
- Use `16px` page gutters for standard content, producing a `343px` content width. Some full page stacks use `12px` outer padding and a `351px` working width when the navigation/search treatment requires it; do not mix both gutter systems within one continuous module stack.
- Use a `44px` top navigation/search region. Keep primary title/search behavior consistent with the Navigation Bar and Search references.
- When a persistent bottom Tab Bar exists, reserve the documented `82px` region and ensure scrolling content is not obscured.
- Use `12px` as the common vertical rhythm between major blocks in the structural examples; follow `spacing.md` when component-specific spacing overrides it.

## Module hierarchy

- Navigation establishes page identity and contains only page-level actions.
- Information is the primary business/data summary and should occupy the strongest first-screen position when immediate comprehension is the task.
- Recommendation highlights the most valuable current content or activity. A full-width recommendation/Banner example uses `343 × 112px`; rich media recommendations may use `343 × 192px`.
- The 金刚区 provides direct entrances to frequent functions. Keep functions equal in visual weight unless one action is explicitly primary.
- Information Flow carries ongoing or repeatable content and follows the summary/recommendation region rather than displacing the page’s key task.
- Keep section headers clear: use `16px` medium-weight text for section titles and secondary `12px` actions such as more/filter.

## Supported page structures

- Information-led: navigation → information summary → recommendation → supporting information/content.
- Recommendation-led: navigation → recommendation → information/business modules.
- Function-led: navigation → recommendation or summary → 金刚区 → information flow.
- Content-led: navigation/search → topic/category controls → information flow, with Banner or recommendation inserted only when it materially supports discovery.
- Choose one structure from business priority and user intent; do not copy every available module into one page.

## Function area

- Keep the function area within the `343px` content grid.
- Use up to five evenly distributed entrances in one row in the reference layout. Maintain consistent icon, label, and tap-target anatomy.
- Keep labels concise and place them below the icon. Do not wrap labels into competing multi-line captions.
- When more functions are required, use a deliberate second row, horizontal overflow, or a “more” entrance according to task frequency; do not squeeze icon spacing.

## Recommendation and information flow

- Use Banner/Swipe rules for promotional recommendations and Information Flow rules for repeated article, report, video, expert, or event content.
- Keep recommendation visually distinct from information flow so users can distinguish promoted/current highlights from the ongoing feed.
- Use `8px` corner radius for the shown full-width media blocks and cards unless another component reference specifies otherwise.
- Separate major content sections with either the documented vertical rhythm or a quiet `#F5F7FA` divider band; avoid arbitrary separators.

## Scroll and fixed elements

- Keep navigation/search behavior stable while content scrolls. Sticky treatment is allowed only when it helps locate or filter the main content.
- Floating actions must not cover recommendation controls, information rows, or bottom navigation; follow Pendant rules for clearance and movement.
- Preserve the user’s scroll position when returning from a business entrance or content detail.

## Review checklist

- Confirm the page has one clear primary business purpose and entrance.
- Confirm navigation, information, recommendation, 金刚区, and information flow are ordered by user priority.
- Confirm `375px` canvas, consistent `16px/343px` or `12px/351px` grid, `44px` top region, bottom clearance, and major-module rhythm.
- Confirm recommendation and information flow use the correct component families and remain visually distinguishable.
- Confirm function entrances are evenly distributed, concise, and not compressed.
- Confirm fixed navigation and floating actions do not obscure content and return navigation preserves context.

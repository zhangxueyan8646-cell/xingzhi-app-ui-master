# Collapse 折叠面板

## Purpose and structure

- Use Collapse when information has multiple levels and each level may contain multiple secondary items.
- A first-level structure contains a selection/control area, information display, and an expand/collapse control.
- Information display commonly contains an icon, information name, number, and optional one-line description; place the icon before the information name.
- A second-level structure groups same-category information rows beneath the first-level row.

## Mobile geometry

- Mobile reference viewport: `375px` wide.
- Page content gutter: `16px`; Collapse content width: `343px`.
- Outer group spacing: `12px` between sections.
- First-level header row: `343 × 46px`; header content inset `12px` horizontally and `13px` from the top; inner content height `22px`.
- Header icon: `20 × 20px`; icon-to-label gap `8px`.
- Header label and action: `14px / 22px`; action and arrow gap `4px`; expand/collapse arrow: `14 × 14px`.
- Expanded content container: white, `343px` wide, bottom corners `8px`, clipped to the panel.
- Nested information block: `319px` wide, horizontal inset `12px` from the outer panel; background `#F5F7FA`, `8px` radius; inner horizontal padding `8px`.
- Information row: `20px` icon/checkbox, `8px` icon-to-text gap, vertical padding `12px`; text `14px / 20px`; divider `#E6EBF0`, `0.5px`.

## Behavior

- With one information row, omit the expand/collapse control.
- When multiple second-level items exist, keep the second-level structure collapsed by default; merge the content into one line and ellipsize the overflow.
- Tapping the expand control reveals same-category information rows, each with a fixed one-line height.
- If a group contains no more than two information cards, show both cards fully and omit the expand/collapse control.
- If a group contains more than two information cards, show two cards by default and provide an expand control to reveal the rest.
- Add an operation button only when an additional action is needed after viewing the information.
- Keep the expanded/collapsed state and arrow direction synchronized; do not change the information order between states.

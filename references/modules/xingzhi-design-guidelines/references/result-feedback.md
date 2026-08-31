# Result feedback 流程结果反馈

## Result-type list

- Showcase container: `1280 × 527px`, white, `8px` radius; content starts `40px` from the container’s left edge and `79px` from its top edge.
- Type section heading: `28px / 39px`; cyan leading bar `4 × 20px`; bar-to-title gap `36px`.
- List header row: `1200px` wide, `17px` high.
- Each result-type row: `1200 × 120px`, white, `1px` `#E6EBF0` border, `8px` radius; rows separated by `8px`.
- Row label: `16px / 24px`, medium; vertically centered at `48px` from the row top; left inset `20px` (the source uses `1.67%` of the 1200px row).
- Result illustration: placed around `36px` from the row top and aligned near the right side of the row.

## Page-level result screens

- Mobile reference viewport: `375 × 812px`.
- Top status area: `44px`; result navigation bar: `44px` immediately below it.
- Main content frame: `343px` wide, left/right inset `16px`, starts `104px` from the screen top.
- Card gaps: `8px`.
- Result card: white, `343px` wide, `8px` radius.
- Success icon: `48 × 48px`; icon-to-title gap `16px` in the transaction-result example.
- Result title: `16px / 24px`, medium; supporting copy: `14px / 22px`, `#555555`; timestamp: `12px / 17–18px`, `#999999`.
- Supporting-information panel inside the card: `319px` wide, left inset `12px`, `8px` radius, `#F5F7FA`.
- Bottom action region: `375 × 68px`, white; primary button `343 × 44px`, left inset `14px`, top inset `12px`, pill radius `100px`.
- Primary action label: `16px / 18px`, medium, white, centered.

## States

- Use three semantic result types: 完成 (success), 异常 (warning/abnormal), and 失败 (failure).
- Keep the result title and supporting copy centered in page-level result screens.
- Use the result-specific icon and semantic color; do not substitute a generic status glyph.
- Keep the bottom primary action visible without covering the Home Indicator/safe area.

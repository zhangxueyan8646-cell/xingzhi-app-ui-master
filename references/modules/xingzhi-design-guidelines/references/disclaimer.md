# Disclaimer 免责声明

Use Disclaimer to present required legal, regulatory, risk, source, or scope information near the end of relevant content. Treat the supplied copy as compliance-controlled content, not ordinary product copy.

## Component anatomy

- Use a `343px` mobile content width aligned to the standard `16px` page gutters on a `375px` screen.
- Center the title `免责声明` between two quiet horizontal gradient rules.
- Set the title in PingFang SC at `14px / 22px`.
- Set the body in PingFang SC at `12px / 18px`, left aligned across the full `343px` content width.
- Keep `8px` vertical space between the title group, body copy, and disclosure control.
- Use a centered `12 × 12px` chevron below the copy to indicate expand or collapse.

## Light-background variant

- Use title color `#555555`.
- Use body color `#999999`.
- Use quiet gradient rules based on `#E5E5E5` that fade toward transparency.
- Use the gray Disclaimer component on white and other light surfaces.

## Dark-background variant

- Use title color `rgba(255, 255, 255, 0.5)`.
- Use body color `rgba(255, 255, 255, 0.3)`.
- Use gradient rules based on `rgba(229, 229, 229, 0.3)` that fade toward transparency.
- Use the white Disclaimer component on the documented dark surface `#141B2A` and other sufficiently dark backgrounds.

## Collapse and expansion

- Use the compact state when the complete approved disclaimer fits the designated collapsed copy or when the product explicitly permits progressive disclosure. The documented compact component is `343 × 104px`.
- Use the expanded state for longer approved copy. The documented example grows to `343 × 140px`; actual height must follow the content and must not clip legal text.
- Point the chevron down when more content is available and up when the content is expanded.
- Preserve the user's reading position when expanding or collapsing.
- Make the entire disclosure control a clear touch target while keeping the visible chevron at `12 × 12px`.
- Never collapse text when law, policy, product risk, or the compliance owner requires immediate full visibility.

## Placement

- Place the Disclaimer after the primary content and before the bottom safe area or persistent navigation, using the normal page gutter.
- Keep it in the content reading order. Do not float it over content, hide it behind the home indicator, or detach it from the material it qualifies.
- Reuse the light or dark variant according to the host surface; do not mix the dark copy colors onto a light background.

## Compliance rules

- Do not invent, shorten, paraphrase, translate, merge, or remove disclaimer copy unless the user explicitly supplies approved replacement wording or an authorized compliance source.
- Do not treat the specimen's repeated placeholder copy as a universal legal disclaimer.
- Preserve required names, dates, jurisdiction, risk language, links, version identifiers, and source attribution exactly.
- If copy requirements conflict with available space, expand the layout rather than truncating or reducing text below the documented size.
- Flag missing approved copy, ambiguous jurisdiction, or a request to hide mandatory disclosure; do not make a legal determination from visual examples alone.

## Accessibility

- Expose the title as a heading or labelled disclosure region and connect the chevron control to the expandable content.
- Announce expanded and collapsed state programmatically.
- Keep the disclosure reachable by keyboard and assistive technologies; do not use color or chevron direction alone to convey state.

## Review checklist

- Verify light versus dark variant, width, page gutters, type styles, rules, and chevron.
- Verify compact and expanded states, content-driven height, reading position, and touch target.
- Verify placement near the qualified content and clearance from safe areas or navigation.
- Confirm all copy comes from an approved source and remains complete and unchanged.
- Verify reading order, labelled region, state announcement, contrast, localization, and dynamic text behavior.

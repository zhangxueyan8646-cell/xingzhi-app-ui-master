# AI 布局规范

## Design model

- Design AI experiences across three dimensions: scenario, user, and interaction.
- Match financial scenarios precisely: information acquisition, decision support, and roadshow interaction require different tools and output structures.
- Adapt information depth for ordinary customers, institutional customers, and enterprise executives.
- Build a professional human–AI collaboration loop with traceable data, explainable reasoning, human review, and error feedback.

## AI entry patterns

- For a primary module on a first-level page, pair a search field with a dedicated AI trigger button.
- For a submodule, allow one or two right-side actions and treat the AI trigger as one action in that operation area.
- In a dialog, present the AI trigger as an auxiliary consultation action rather than the primary confirmation action.
- In search scenarios, place the AI icon button at the right side of the search field.
- Keep entry meaning and visual treatment consistent across contexts; label AI assistance clearly.

## Initial guide

- On first entry into the AI page, compose the initial view from recommended questions, a convenience module, and the primary interaction area.
- Recommended questions should reflect likely user intent and may derive from prior questions or search behavior.
- Convenience modules provide direct entrances to common financial tools or tasks; keep them secondary to the conversation input.
- Do not show fabricated history. Use an explicit empty state when no prior interaction exists.

## Primary interaction area

- Compose the primary interaction area from the search/input field and auxiliary controls.
- Support text input and voice input when the product capability exists.
- Tapping the text field may reveal question history. Keep history distinguishable from current recommendations.
- Keep the input accessible while the conversation scrolls, without covering generated content or the bottom safe area.
- Distinguish primary operations from secondary actions such as share, feedback, follow, add to watchlist, or view more.

## Response presentation

- Present ordinary information in paragraphs. Use bold subheadings to separate sections and superscript references to open source material.
- Emphasize key textual facts with the documented underline treatment.
- Use visual key-information cards only for relatively precise system entities such as research reports, funds, stocks, and experts.
- Pair key-information cards with the primary actions required to continue the user flow.
- Keep recommended follow-up questions and cited sources visually separate from the answer body and action area.
- Maintain clear hierarchy through scale, weight, color, density, and whitespace; favor simple balanced structures and Bento grouping when it improves scanning.

## Financial AI trust and safety

- Label AI-generated reports or conclusions clearly.
- Make important conclusions explainable: expose the reasoning path, original data source, and relevant calculation/model context.
- Allow users to flag incorrect AI output and route that feedback into a visible correction or review process.
- Require human review for important reports and preserve revision traces when edits change AI-generated content.
- Separate facts, inference, confidence, and recommendations. Do not present estimates as confirmed facts.
- Tailor risk warnings to the financial scenario and avoid language that implies guaranteed outcomes.
- When expert verification exists, identify the reviewer and scope of verification without implying broader endorsement.

## Review checklist

- Confirm the AI entry pattern matches primary module, submodule, dialog, or search context.
- Confirm initial guidance contains recommendations, convenience entrances, and the primary interaction area without competing hierarchy.
- Confirm text/voice input, history, recommendations, sources, and action regions are distinct.
- Confirm ordinary text and key-information cards follow their permitted content types.
- Confirm generated content is labeled and important conclusions expose sources and reasoning.
- Confirm correction feedback, human review, revision traces, uncertainty, and risk language are handled.
- Confirm layout remains balanced, scannable, safe-area aware, and consistent with the XingZhi spacing and typography references.

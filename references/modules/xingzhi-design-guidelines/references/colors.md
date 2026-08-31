# Colors 颜色

Source: MasterGo document `行知app-规范`, node `XingZhi App - Design System-Colors 颜色` (`3:056`).

## Brand and accent colors

| Role | Source label | Value | Use |
|---|---|---:|---|
| Primary cyan | Bland Green | `#00D2F0` | Primary actions, active states, highlighted regions, design-system headers |
| Primary cyan tint | Bland Green 0.1 | `rgba(0, 201, 229, 0.1)` | Low-emphasis cyan surface or selected background |
| Blue accent | APP Blue | `#00A6FA` | Links, information accents, secondary blue actions |
| Blue tint | APP Blue 0.1 | `rgba(0, 166, 250, 0.1)` | Low-emphasis blue surface |
| Gold accent | APP Gold | `#D9AF6C` | Gold-tier or premium semantic accents |
| Orange accent | APP Orange | `#FEAF40` | Orange emphasis or warm attention state |
| Legacy header cyan | App Design System header | `#00C9E5` | Retain only when matching an existing legacy header |

Treat the source label “Bland Green” as the documented token name even though the rendered value is cyan.

## Semantic status colors

| Role | Value |
|---|---:|
| Success / correct | `#3B990F` |
| Warning | `#F2BA49` |
| Error | `#F24949` |

Do not use the warning color for errors or the success color for ordinary decoration.

## Text colors

| Role | Value | Guidance |
|---|---:|---|
| Primary label | `#222222` | Titles, primary body text, key values |
| Secondary label | `#555555` | Supporting content with clear readability |
| Tertiary label | `#999999` | Metadata, captions, de-emphasized text |
| Prompt / placeholder | `#BBBBBB` | Placeholder and weak prompt text |
| Non-editable / disabled | `#DDDDDD` | Disabled text or non-editable state |
| Section heading in spec | `#1F1F1F` | Use when matching specification-page headings |

## Surface and border colors

| Role | Value |
|---|---:|
| Pure white | `#FFFFFF` |
| Light gray background | `#F5F7FA` |
| Border / divider | `#E6EBF0` |

## Usage rules

- Prefer white for primary cards and `#F5F7FA` for page or grouped-section backgrounds.
- Use `#E6EBF0` for subtle one-pixel borders and dividers.
- Use the primary cyan for the most important action or selection, not for large decorative fields.
- Pair colored status indicators with text or icons; do not rely on color alone.
- Use the text hierarchy in descending order: `#222222` → `#555555` → `#999999` → `#BBBBBB`.


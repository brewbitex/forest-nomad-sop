# Forest Nomad SOP System

A touchscreen SOP browser for the Forest Nomad kitchen, built for a
**Galaxy Tab S10 FE in landscape** (1152 x 720 CSS px). Every page fits one
screen with no scrolling on that device; on smaller screens it falls back to
scrolling rather than clipping.

**Live site:** see the repository's GitHub Pages URL.

## What is here

| Section | Dishes | Groups |
|---|---|---|
| Cafe | 90 | 12 |
| Indian Kitchen | 42 | 10 |
| South Indian | 19 | 5 |
| OG Chats | 28 | 6 |

`index.html` is the home screen. Each kitchen page lists every dish as a
button grouped by category; each button opens that dish's SOP, with the
steps stacked vertically.

## Language

Every page carries a Hindi / English toggle. The choice is kept in
`localStorage` under `fn_sop_lang`, so it follows the user from page to page.
Hindi is written as kitchen Hinglish: Devanagari sentences with the English
kitchen terms left in English (`batch`, `simmer`, `airtight container`,
`Ticket 5 min`). Dish names stay in English in both languages.

## Colour

Only the five Tibetan prayer flag colours are used, one per dish group:

| | Deep | Edge | Tint | Text on deep |
|---|---|---|---|---|
| Blue | `#1F4FA6` | `#A9C4EA` | `#E4EDF9` | `#FFFFFF` |
| White | `#FFFFFF` | — | — | — |
| Red | `#C01B2E` | `#EDA6AF` | `#FBE5E8` | `#FFFFFF` |
| Green | `#137A3C` | `#9CD5B0` | `#E1F3E7` | `#FFFFFF` |
| Yellow | `#E8B007` | `#F0D78A` | `#FDF4D8` | `#1C1917` |

Flag yellow cannot carry white text at this size, so it takes `#1C1917`
instead; that is what the `--on` custom property is for.

## Brand marks

`fn-wordmark.svg` and `fn-mark.svg` are traced from the brand PDF, so they
scale cleanly and take their colour from `currentColor`. The five dots around
the mountain-M are fixed to the five flag colours. The wordmark is set on one
line (FOREST NOMAD in sequence, not stacked).

## Source

These pages are generated from a Claude Design canvas; the source of the SOP
text is `Forest_Nomad_Combined_Menu__Final.xlsx`. Edit the dish steps there
and regenerate rather than hand-editing the HTML.

## Known gap

**Brown Butter Iced Latte** has a blank SOP cell in the menu file. Its page
says so and lists what still needs confirming (the brown butter form, the
dose, and whether it is held hot or cold). Three further rows in the menu file
read `AWAITING DEFINITION` and are not published.

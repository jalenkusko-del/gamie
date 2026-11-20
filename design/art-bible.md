# Art Bible: VAINWARD

## Document Status
- **Version**: 1.0
- **Last Updated**: 2026-11-20
- **Owned By**: art-director
- **Status**: Draft. The palette and card background are approved. The other sections are still open.

## Visual Identity Summary
VAINWARD cards follow **Crimson Royale Minimalist**: restrained luxury, like a premium casino playing card with an unusual aged finish. Red, champagne gold and warm antique ivory make up the whole card identity, with decoration kept to a minimum. The game UI around the cards keeps the established Soft-Float style. Crimson Royale belongs to the cards.

## Reference Board
| Reference | Medium | What We're Taking |
| --------- | ------ | ----------------- |
| Exclusive casino playing cards | Physical cards | Restraint, a thin single-line border, premium feel |
| Aged paper / antique ivory stock | Material | Warm off-white surface with gentle weathering, not a ruined look |

Directions explored and rejected: traditional dark fantasy with ornate frames, Premium Hybrid, Spectral Glass, Occult Editorial, Living Portraits, Strange Relics, and heavy thornlike or vine embroidery.

## Color Palette

### Primary Palette (approved)
| Name | Hex | Token | Usage |
| ---- | --- | ----- | ----- |
| Royal Crimson | `#781B2B` | `crimson` | Card border line, card name, body text. Main ink colour. |
| Ruby Red | `#A52B3B` | `ruby` | Secondary text: tier label, stat labels. |
| Champagne Gold | `#D8B467` | `gold` | The two card stars and small accents. Decorative only, never text on ivory. |
| Aged Ivory | `#E8D1A5` | `aged` | Card surface, darker end of the gradient. |
| Pale Ivory | `#F0E3BD` | `pale` | Card surface, lighter end of the gradient. |

Machine-readable tokens: `assets/data/ui_palette.json`.

### Contrast (WCAG 2.x, measured)
| Foreground | Background | Ratio | Allowed use |
| ---------- | ---------- | ----- | ----------- |
| Royal Crimson | Aged Ivory | 7.08:1 | Any text |
| Royal Crimson | Pale Ivory | 8.25:1 | Any text |
| Ruby Red | Aged Ivory | 4.68:1 | Text at 12px and up (passes AA) |
| Ruby Red | Pale Ivory | 5.46:1 | Text at 12px and up |
| Champagne Gold | Aged / Pale Ivory | 1.32 / 1.54:1 | **Not for text.** Ornament only. |

Rule: card text on the ivory surface must use Royal Crimson or Ruby Red.

### Emotional Color Mapping
Not defined yet. The palette covers the card collection only. Battle, map and shop mood colours are still open.

## Card Art Standards

### Card background (approved)
- **Surface**: warm antique ivory, a soft gradient from Pale Ivory to Aged Ivory. It reads pale yellow-beige: warmer and darker than pure white.
- **Texture**: subtle stains, faint marbling and light weathering. It must never look damaged.
- **Border**: one thin Royal Crimson line set just inside the rounded edge (mockup: 1.5px, inset 10px, corner radius 12px on an 18px card radius).
- **Stars**: two small Champagne Gold stars, one centred at the top and one at the bottom.
- **Open centre**: no VAINWARD logo, large symbol or fixed decoration in the middle.
- **Embroidery**: almost none. No vines, flourishes or corner ornaments.

### Card front layout (not approved)
A proposed layout is in `prototypes/card-face-crimson-royale/`. It places the name, tier, ability text and stats inside the frame. It is for review only until it is approved.

### Open items
| Area | Status |
| ---- | ------ |
| Card-front information layout | Proposal only |
| Final card illustration style | Not decided |
| Tier-specific visual variations | Not finalized |
| Hybrid visual treatment | Not finalized |
| Red Artifact visual treatment | Not finalized |

## UI Art Standards
The UI around the cards uses the established Soft-Float style. Crimson Royale tokens may be used for accents that refer to cards, but the UI chrome is not restyled to Crimson Royale.

## Accessibility
- Never use colour alone to show state. Tier, Hybrid and Artifact status must also appear as text or an icon.
- Minimum card text size: 12px at the mockup scale (240×340 card).
- Gold on ivory is never used for text (see the contrast table).

# Design Kit — portable visual system

The NIOCCS **"Atmosphere · Open"** design system, ported and tokenized so a new
program (e.g. **ODH**) inherits the look and only swaps the palette.

## Files

| File | What it is | Touch it? |
|------|-----------|-----------|
| `tokens.css` | The single recolor/re-tune surface — palette, gradients, fonts, shape, type scale, density. | **Yes** — this is where you re-skin ODH. |
| `components.css` | The reusable, theme-agnostic component layer (app bar, buttons, KPI cards, the focal hero, tables, search, pagination…). Driven entirely by tokens, no hardcoded brand colors. | No — leave it; it inherits from tokens. |
| `style-guide.html` | Self-contained reference that renders every token + component + the design doctrine. The visual contract. | Read it / show it. |
| `CLAUDE.md.example` | Drop-in project instructions for the ODH repo. | Copy to the ODH repo **root** as `CLAUDE.md`. |

## Use it in a new project

1. Copy `tokens.css` + `components.css` into the new repo.
2. In each screen: `<link rel="stylesheet" href="tokens.css">` then `<link rel="stylesheet" href="components.css">` (order matters — tokens first).
3. Re-skin: edit the **BRAND / ACCENT / ACTION** block in `tokens.css` (seven values + the two gradients). Optionally retune fonts and the type scale. Everything inherits.
4. Build screens from the components shown in `style-guide.html`.

## The non-negotiable rules (see Doctrine in the style guide)

- Color only for **attention states** and the **primary CTA** — neutral otherwise.
- **Depth over flat**: panels sit on a plane with a resting lift; no dead-flat surfaces.
- **Pop via type, scale, contrast** — not color.
- **Signals never shimmer**: the action gradient is for "go" surfaces; alert/warn stay flat.
- **Numbers are the jewelry**; the table recedes beneath the focal mass.

## Preview

```sh
cd odh-design-kit
python3 -m http.server 8766
# open http://localhost:8766/style-guide.html
```

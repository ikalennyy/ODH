

# ODH

ODH reuses the visual system built for NIOCCS, recolored for ODH. The system lives in `./design-kit/`.

## Design kit — how to use it
- **`design-kit/tokens.css`** is the ONLY recolor / re-tune surface. To re-skin ODH, edit the BRAND / ACCENT / ACTION block (one teal hue drives the gradients + `--accent` + `--action`). Never hardcode brand colors anywhere else.
- **`design-kit/components.css`** is the component library (app bar, buttons, KPI cards, the active-file hero, tables, search, notice, pagination). Fully token-driven — leave it alone; it inherits from tokens. In each screen, link `tokens.css` first, then `components.css`.
- **`design-kit/style-guide.html`** is the rendered catalog + the doctrine. Open it to see every component and token in context.
- Build every screen from these components. If you need something the kit doesn't have, build it **from the existing tokens** so nothing drifts off-system.

## Doctrine (non-negotiable)
- **Color is rationed** — only for (1) attention states and (2) the primary CTA. Everything else neutral. Flat *color* is fine; flat *surfaces* are not.
- **Depth over flat** — every panel/card sits on a plane with a resting lift, tiering up on hover/selected. No dead-flat surfaces.
- **Pop via type, scale, contrast — not color.** Big display type (Sora), oversized tabular numbers, tracked-caps micro-labels.
- **Signals never shimmer** — the action gradient is for "go" surfaces only; `--alert` (red) and `--warn` (amber) stay flat.
- **Numbers are the jewelry; the table recedes** — flat, quiet, smaller, dark header, beneath the focal mass.

## Copy model
The engine auto-codes EVERY record; the human REVIEWS — never codes from scratch. Use "not yet reviewed" / "reviewed by you", never "coded". (Re-word for ODH's domain, but keep the model.)

## How to talk about UI here
Describe **intent** ("this needs attention", "this is the main action", "make this recede") — the kit's tokens/classes are the implementation, and the doctrine above is the default. Drop to **token names** (`shadow-pop`, `surface-sunk`, `--warn`) only to override a default or correct a tier.

## Working style
- Do only what's asked; flag extra polish as a suggestion rather than applying it unprompted.
- Verify visual changes by rendering in a browser before claiming done.
- Ask for a fresh explicit OK right before any `git push`.

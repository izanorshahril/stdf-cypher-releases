# Look and themes

Pick a theme at the bottom of the side bar, from the right-click menu, or on Settings, Look.
The half-circle button switches light and dark for every theme.

## Themes

| Theme | Look | Starts in |
|---|---|---|
| Workaholic | Navy, sky blue and yellow. The theme on first start. | light, blue accent |
| Struggling | Burgundy and magenta. | light, pink accent |
| CyberGeek (experimental) | Dot matrix, neon and glow; bars filled with dots and dotted lines. | dark, green accent |
| RetroNerd | Pastel pop, ink outlines and hard 8-bit shadows. | light |
| ProMaxUltra | Frosted glass, metal edges and gloss. | dark |
| NoirCyreel | Black, white and greys. | dark |
| GemilangAuAgPd (experimental) | Gold, silver and palladium, with metal edges. | dark |
| Industry (legacy) | Steel blue and charcoal. | dark |
| Chillax (legacy) | Neutral greys and blue. | light |

Each theme keeps its own light or dark mode and accent: change them while a theme is on, and the theme comes back that way.
**Reset this theme's colours** (right-click, Theme) puts back the mode and accent it starts in.
Legacy themes may be removed in a later version.
Switching experimental features off shows Workaholic until they come back on; your choice is kept.

## Look settings

Settings, Look changes any part of the theme.
Whatever you leave alone follows the theme, and every page changes at once.
**Reset the look to the theme's** goes back to the theme's own look, mode and accent.

### Type

The text and the headings (page titles, the banner and big numbers) each take one of:

- a Nerd font (the default, when one is installed on the PC);
- Cypher Sans, the system UI font, used when no Nerd font is installed;
- Cypher Dot, the app's own dot-matrix font, the headings of CyberGeek;
- Cascadia Mono.

### Accent

The theme's accent, a swatch or any colour.
A picked colour is darkened or lightened until it reads on the theme's background, and text on it is black or white, whichever reads better.

### Effects

- **Glow** around accents.
- **Glass**: translucent, blurred cards and panels.
- **Corner radius**.
- **Texture** on the background: dot grid, scan lines, squared paper or film grain.
- **Chart effect** on marks: neon glow, gloss, soft shadow or 8-bit shadow.

### Chart colours

The eight series colours as a set (theme, neon, pastel, colour-blind safe, accent shades, greys) or one by one, and the pass, fail, warning and limit colours.
Every chart follows, also charts already on screen.
Charts draw up to 64 layers (sites, bins, files), each in a colour of its own: the eight set here first, then 56 worked out from them, at an even lightness that stays readable on the theme's background.
A grey set (the Noir theme, the Greys colours) has fewer distinct greys than that, so some repeat.
Sites 1 to 64 keep their colour whatever a filter leaves: site 12 is always the twelfth colour.
More than 64 groups show the 63 largest and one "Other".

### Layer colours

Right-click a legend entry, or a point, bar or box of a layer, and open **Layer colour**:

- **Colour of** the layer: pick any colour; that layer keeps it in every chart of every page until it is set back (**back to its own colour**, or **Clear the colours set for layers**).
- **One colour for all but** the layer: every other layer of this page's charts turns grey, so one site stands out among 32 or 64.
  Then, on another layer, **Keep its colour too** to bring out several, **Colour of the others** to pick the shared colour instead of grey, and **Every layer in its own colour** to end it.

Layer colours are kept with the chart settings, so they survive a restart.

### Gradients

- The **magnitude** gradient: heat maps, count maps and table columns where rows are compared.
- The **better or worse** gradient: site maps of rates, correlation and rule cells.

Each is a preset or one to three colours of your own, and a stop can be clear.

### Shaded cells and rules

Cpk, yield % and bad parts or bin % each have a bad and a warning threshold, and optionally a good one.
A cell past a threshold pops in the fail or warning colour.

| Mode | Cells |
|---|---|
| Colourful | Rule cells along the better or worse gradient, magnitude columns along the magnitude gradient, and pops past thresholds. |
| Monotone | The same cells shaded in the accent only. |
| Rule colours only | Only cells past a threshold are coloured; the rest stay plain. |
| Off | No shading. |

Test Explorer's Cpk column, the Overview's fail pareto and bin tables, the Site Map's values, the Lot Summary's yields and fail-bin shares, and the Drift Report's defaults use these rules.

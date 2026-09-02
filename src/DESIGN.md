# Open Ethics Initiative — Design System

Extracted from [openethics.ai](https://openethics.ai/) on 2026-09-02 by reading the site's **actual active stylesheet**: the child theme `wp-content/themes/oeth/style.css`

## Logo

- **File:** `Open-Ethics-Logo.png` (https://openethics.ai/wp-content/uploads/2018/07/Open-Ethics-Logo.png), 1080×288px, transparent background.
- **Mark:** a solid circle in brand green with a bite/notch cut from the upper-left, forming a stylized lowercase "e" (an "open," incomplete circle) — reads as "open."
- **Wordmark:** solid **white**, to the right of the mark.
- **Important:** the background is transparent and the wordmark is white, so the logo is only legible on a **dark background** (the site places it on the near-black header bar `#1B1F23`). On white/light backgrounds only the green mark shows — plan for a dark-background lockup, or derive a dark-text variant for light layouts.

## Typography

Loaded via `@import` in the child theme:

```css
@import url('https://fonts.googleapis.com/css?family=Roboto+Mono|Roboto+Slab|Roboto:100,300,400,500,600,700,900&subset=cyrillic,cyrillic-ext');
@import url('https://fonts.googleapis.com/css?family=Exo+2:200,300,400,900&subset=cyrillic');
```

| Font | Role |
|---|---|
| **Roboto** | Base body font — `body, .hentry, .hentry p, article p` |
| **Exo 2** | Headings (h1–h6 inside articles), header title/subtitle, nav menu links, all buttons (`.btn`, `.button`), widget titles — the UI/display face |
| **Roboto Slab** | Blockquotes and the `.oe-georgia` pull-quote/lede paragraph style — serif-slab for emphasis text |
| **Roboto Mono** | Loaded for monospace/code contexts |

Both `Roboto` and `Roboto+Slab`/`Roboto+Mono` are pulled with the `cyrillic,cyrillic-ext` subset (the site serves Cyrillic-script content), and `Exo 2` with the `cyrillic` subset.

**Heading scale** (from `.hentry`/`article` rules):
- h1: `2.5em`, 1em line-height, green 5px bottom border (`#3E8914`)
- h2: `2em`, 56px top margin / 35px bottom margin
- h3: `1.6em`
- Body copy: `1.2em` at 160% line-height

**Recommended pairing for derivative work:** Roboto for body copy, Exo 2 for headings/labels/buttons, Roboto Slab for pull-quotes or callouts.

## Color Palette

### Core brand
| Role | Hex | Notes |
|---|---|---|
| **Brand green** | `#3E8914` | Logo mark, `.btn-primary`/`.btn-success`/`.btn-info`, text-selection highlight, h1 underline, roadmap "left" column |
| **Lighter green** ("second site color") | `#4B9C1C` | `.btn-link` |
| **Teal/blue** | `#05668D` | `.btn-secondary`, roadmap "right" column |
| **Near-black** | `#1B1F23` | Header bar, footer background — the logo's home surface |
| **Neutral gray** | `#636363` | `.btn-default` |
| **Body text** | `#454545` | Captions, blockquote text, roadmap element text |
| **Muted text** | `#999999` | Footer copy, blockquote citations |

### Semantic button colors
| Class | Hex |
|---|---|
| `.btn-primary` / `.btn-success` / `.btn-info` | `#3E8914` |
| `.btn-secondary` | `#05668D` |
| `.btn-warning` | `#F5B903` |
| `.btn-danger` | `#E34234` |
| `.btn-default` | `#636363` |
| `.btn-link` | `#4B9C1C` |

### POV Matrix scale — `.oe-povmatrix .pov-element.class-a` … `.class-g`
A **7-step sequential scale**, green → red, used to color-code the maturity/POV grid on the site. This is the scale most relevant to any risk/maturity scoring work (e.g. RSAIRF):

| Class | Hex | Position |
|---|---|---|
| `.class-a` | `#387A13` | 1 — best (dark green) |
| `.class-b` | `#79B752` | 2 (light green) |
| `.class-c` | `#C3D545` | 3 (yellow-green) |
| `.class-d` | `#FFF12C` | 4 — midpoint (yellow) |
| `.class-e` | `#F5B903` | 5 (amber/gold) |
| `.class-f` | `#D66F2C` | 6 (orange) |
| `.class-g` | `#CC232A` | 7 — worst (red) |

Text color pairs with each step for contrast: white text on `a`, `b`, `f`, `g`; dark text (`#454545`) on `c`, `d`, `e`.

Default (unclassed) `.pov-element` background is neutral gray `#7F7F7F` at 0.9 opacity, brightening to full opacity with a soft drop-shadow on hover.

## Visual Style

- **Buttons:** small radius (3–4px depending on size), `.btn-lg`/`.btn-sm`/`.btn-xs` size variants with matching radius/padding/font-size steps.
- **Links:** underlined by default with a **dotted** underline (700 weight), switching to a **solid** underline on hover — a distinctive, deliberate link treatment (not color-only).
- **Blockquotes:** light gray background (`#F8F8F8`), 5px radius, large decorative quote mark in brand green, Roboto Slab body text.
- **Roadmap component** (`.oe-roadmap`): two-column timeline, left items outlined/filled in brand green `#3E8914`, right items in teal `#05668D` — a clear two-color left/right complementary scheme, pill-shaped nodes (`border-radius: 2em`).
- **Layout:** generous vertical rhythm (`.oe-povmatrix`, `.oe-about`, `.oe-roadmap` all use `12em`/`10em` top/bottom margins) — sparse, breathing sections rather than dense stacking.

## Quick-reference CSS variables

```css
:root {
  --oe-green-brand:   #3E8914;  /* primary, logo, headings accent */
  --oe-green-light:   #4B9C1C;  /* secondary CTA */
  --oe-teal:          #05668D;  /* secondary brand color */
  --oe-dark:          #1B1F23;  /* header/footer surface */
  --oe-gray-default:  #636363;
  --oe-text-body:     #454545;
  --oe-text-muted:    #999999;

  /* POV / risk scale, green -> red */
  --oe-scale-1: #387A13;
  --oe-scale-2: #79B752;
  --oe-scale-3: #C3D545;
  --oe-scale-4: #FFF12C;
  --oe-scale-5: #F5B903;
  --oe-scale-6: #D66F2C;
  --oe-scale-7: #CC232A;

  --oe-font-body:    'Roboto', sans-serif;
  --oe-font-heading: 'Exo 2', sans-serif, Arial, serif;
  --oe-font-quote:   'Roboto Slab', serif;
  --oe-font-mono:    'Roboto Mono', monospace;
}
```

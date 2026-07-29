# stitch-studio

A FreeWebStore template for **tailor.alterations** by **@serge-ivo**.

Warm, craft-forward landing page for **alterations and repair shops** — tailors,
seamstresses, dressmakers, bridal fitters, leather and shoe restorers. Fills the
garment-services gap in the FWS library, which previously had fashion retail and
salons but nothing for a workshop that sells skilled labour rather than stock.

## Design

- **Palette** — warm ivory `#faf7f2` page, `stone-900` structure bands, brass
  `amber-300` accent. The ink-and-brass pairing reads as workshop rather than
  boutique, and the light-first base keeps it legible on a phone in the street.
- **Type** — system stack, `font-black` headings, `leading-7`/`leading-8` body.
  No web fonts, so the page paints with no external font request.
- **No JavaScript.** The mobile nav and the FAQ accordion are native `<details>`
  elements — nothing to break under a strict CSP, and both still work with JS
  disabled.
- **Accessibility** — skip link, labelled form controls, `aria-hidden` on
  decorative glyphs and star rows, visible focus styles, `<ol>` for the ordered
  process steps.
- **Every `<section>` carries its own background *and* text colour.** The
  platform keeps only the sections at deploy time and drops the template shell,
  so a section that inherits its colours renders unreadable on the platform
  body.

## Sections

`hero` (with a bench-work card and three trust stats) · `services` (6 cards) ·
`pricing` (3 grouped price lists) · `how` (3 steps) · `craft` (about + stats) ·
`reviews` · `faq` (5 items) · `contact` (details + enquiry form) · footer.

Each is a top-level `<section id="...">`, so the platform splits them into
independently editable sections at deploy time.

## Why a price list

Alterations customers shop on price and turnaround before anything else, and
almost never find either on a tailor's website. The `pricing` section is three
grouped "from $X" lists rather than plans — the platform AI swaps in the shop's
real numbers, and the guide-price disclaimer underneath keeps it honest.

## Slots

Universal set: `business.name`, `business.tagline`, `business.description`,
`about.body`, `contact.address`, `contact.phone`, `contact.email`,
`contact.hours`, `fws.byline`.

Category extras: `business.badge`, `business.headline`, `stats.turnaround`,
`stats.experience`, `stats.walkins`, `services.heading`, `services.intro`,
`pricing.heading`, `pricing.intro`, `how.heading`, `about.heading`,
`reviews.heading`, `reviews.summary`, `faq.heading`, `contact.heading`.

Repeating blocks are marked with `data-fws-slot-group`: `services.item`,
`pricing.group`, `reviews.item`, `faq.item`. See `slots.md`.

## Vibecoding this template

Open `index.html` in your editor of choice (Claude Code, Cursor, Windsurf, plain
VS Code with an AI sidebar) and iterate. Constraints:

- **HTML + Tailwind utility classes only.** No templating engines, no framework,
  no build step.
- **Slot markers (`data-fws-slot="..."`) mark customization points.**
- **Single-page output.** FWS produces one HTML file per business. Multi-page is
  a PWS feature, not FWS.

Regenerate `preview.png` (1280×720, ≤500KB) after visual changes:

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --hide-scrollbars --window-size=1280,720 \
  --screenshot=preview.png "file://$PWD/index.html"
```

## Publishing

```sh
npx @freewebstore/cli doctor     # local validation
npx @freewebstore/cli login      # one-time GitHub App install
npx @freewebstore/cli publish    # upload + create repo + queue for review
```

## License

MIT.

# Slot reference for category: tailor.alterations

The FreeWebStore platform AI rewrites your template per small business by
filling `data-fws-slot` attributes. The slots below are the *conventional*
set for **tailor.alterations** — using them gives the platform AI deterministic
anchors, so customization is predictable.

Templates *without* slot markers still work — the AI infers structure from
the HTML — but marked templates are more reliable and easier to QA.

## Universal slots (all categories)

| Slot | Element type | What goes there |
|------|--------------|-----------------|
| `business.name` | text | Legal or display name of the business |
| `business.tagline` | text | One-line pitch, shown in the hero |
| `about.body` | rich text | 2-4 sentence about-the-business paragraph |
| `contact.address` | text | Street address |
| `contact.phone` | text | Phone number, formatted |
| `contact.email` | text | Public email |
| `contact.hours` | text or list | Opening hours |
| `fws.byline` | reserved | DO NOT EDIT — the platform writes the designer credit here |

## Category-specific slots used by this template

| Slot | Element type | What goes there |
|------|--------------|-----------------|
| `business.description` | text | `<meta name="description">` content, for SEO |
| `business.badge` | text | Hero eyebrow — the three words a passer-by needs |
| `business.headline` | text | Hero H1. Shorter and blunter than the tagline |
| `stats.turnaround` | text | Typical time to get a garment back, e.g. "3–7 days" |
| `stats.experience` | text | Years in the trade, e.g. "20+ years" |
| `stats.walkins` | text | Walk-in policy, e.g. "Welcome" or "By appointment" |
| `services.heading` | text | Services section H2 |
| `services.intro` | text | One or two sentences under the services H2 |
| `pricing.heading` | text | Price-list section H2 |
| `pricing.intro` | text | One or two sentences under the pricing H2 |
| `how.heading` | text | Process section H2 |
| `about.heading` | text | Workshop/about section H2 |
| `reviews.heading` | text | Reviews section H2 |
| `reviews.summary` | text | Rating summary, e.g. "5.0 from 7 Google reviews" |
| `faq.heading` | text | FAQ section H2 |
| `contact.heading` | text | Contact section H2 |

## Repeating blocks

Marked with `data-fws-slot-group` rather than `data-fws-slot` — the platform
may add, drop or reorder these, and rewrites the text inside each one.

| Group | Count in this template | What it repeats |
|-------|------------------------|-----------------|
| `services.item` | 6 | A service card: icon glyph, `<h3>` name, description |
| `pricing.group` | 3 | A price list: `<h3>` heading + `<li>` job/price rows |
| `reviews.item` | 3 | A `<figure>`: star row, quote, attribution |
| `faq.item` | 5 | A `<details>`: question in `<summary>`, answer below |

Prices in `pricing.group` are guide figures. Replace them with the shop's real
numbers, or with "quoted" where the job is always priced in person.

For anything not listed here, see the per-category SLOT-SCHEMAS reference in
the platform docs.

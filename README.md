# creynia.github.io

Landing page for **Know the Odds**, a set of play-money web apps that teach casino games:

| Card | App | Game |
| --- | --- | --- |
| crappy | <https://creynia.com/crappy/> | Craps |
| baccaratton | <https://creynia.com/baccaratton/> | Baccarat (Punto Banco) |
| holdumb | <https://creynia.com/holdumb/> | Ultimate Texas Hold'em |
| spinner | <https://creynia.com/spinner/> | Roulette strategy lab |

The site lives at <https://creynia.com/> (`CNAME`; `creynia.github.io` redirects there). It is plain static HTML with no build step. GitHub Pages serves it from the root of `main`, and each app repo's Pages site appears under `/<app>/` on the same domain. Card links are root-relative (`/crappy/`), so they follow the domain.

## Files

| Path | What it is for |
| --- | --- |
| `index.html` | The landing page. Its head has the canonical URL, Open Graph/Twitter tags and a JSON-LD `@graph` (`WebSite` `https://creynia.com/#website`, `Person` `https://creynia.com/#creynia`, and an `ItemList` of the four apps). The apps' own pages reuse those two `@id`s so search engines can join the graph. |
| `about/index.html` | The About page: who makes the apps, the education-only stance, the helpline, links to every app. |
| `404.html` | GitHub Pages shows it for unknown paths on the root site. `noindex`, links to the apps. |
| `robots.txt` | Allows all crawlers, names the search and AI crawlers explicitly, and lists this sitemap plus each app's `/<app>/sitemap.xml`. |
| `sitemap.xml` | Landing pages only (`/` and `/about/`). Each app publishes its own sitemap for its pages. |
| `llms.txt` | [llms.txt](https://llmstxt.org/) summary of the whole site for AI assistants, linking to each app's own `llms.txt` and `llms-full.txt`. |
| `a02c23620b24433ba3470d53547479ec.txt` | IndexNow key. The app repos' deploy workflows submit their sitemap URLs to IndexNow with this key; the file must stay at the site root with exactly the key as its content. |
| `assets/og/<app>.jpg` | 1200 × 630 link-preview images that each app's `og:image` points to (`https://creynia.com/assets/og/<app>.jpg`). Cropped from the card art with the game name overlaid. |
| `assets/og-image.jpg` | Link-preview image for the landing page itself. |
| `.nojekyll` | Serve files as-is, without Jekyll. |

When you add an app: add its card and `ItemList` entry in `index.html`, its section in `llms.txt`, its `Sitemap:` line in `robots.txt`, and an `assets/og/<app>.jpg`.

## Analytics

Every page ends with a tiny inline script that sends one cookieless page-view count to [GoatCounter](https://www.goatcounter.com/) (`https://creynia.goatcounter.com`, the site shared with all the apps), as an image request with the path, title, screen width and an external referrer. It does nothing off `https://creynia.com`, in automated browsers, or with Do Not Track or Global Privacy Control. `404.html` counts as `404/<path>` so broken links show up. Each app counts its own pages and events; see `docs/analytics.md` in each app repo.

## Card art

Every card ships with built-in SVG art. To replace one with a generated image, save it as `assets/<app>.webp` (for example `assets/crappy.webp`) and it appears automatically; if the file is missing, the SVG shows.

Image specs: 1600 × 1000 px (16:10), WebP, under 250 KB. Keep the subject in the middle 60% of the frame, since phones in landscape crop the top and bottom. The bottom 25% fades into the card, so keep it plain. No text, logos or real casino branding.

Prompts (shared style first, then one per image):

- **Shared style:** "Stylized semi-realistic 3D illustration, overhead three-quarter view of a casino table, soft studio lighting with a warm gold rim light, shallow depth of field, rich felt texture, elegant and calm, no people, no text, no logos, centered composition, plain dark felt across the bottom quarter, 16:10."
- **`assets/crappy.webp`:** "…two ivory dice mid-tumble showing four and three, casting soft shadows on deep emerald green craps felt (#0b3d2e), a curved gold pass-line stripe, a red and a blue clay chip blurred at the edges."
- **`assets/baccaratton.webp`:** "…two playing cards fanned face-up, a king of clubs and a nine of diamonds, on deep burgundy baccarat felt (#5c1a2b), a thin gold curved line, a small neat stack of gold-edged chips blurred in the background."
- **`assets/holdumb.webp`:** "…an ace of spades and king of hearts as hole cards in the foreground, five face-down community cards softly blurred behind them, on deep navy poker felt (#0b2e4a), a short stack of gold chips to the right."
- **`assets/spinner.webp`:** "…a polished roulette wheel from above at a slight angle, alternating red and black pockets, a single green zero, a white ball resting in a pocket, warm walnut wood and brass, against a dark brown background (#2a1a0c)."
- **`assets/og-image.jpg`** (link preview, 1200 × 630): "Dark green-black background with a subtle gold vignette. Centered, a loose arrangement of two dice, two playing cards and a small roulette wheel. Generous empty space at the top for a title added later, no text, elegant and minimal."

The social preview image is optional: if `assets/og-image.jpg` is missing, links just show without a picture.

To remake the per-app previews in `assets/og/`, crop each `assets/<app>.webp` to 1200 × 630 (keep the card's `object-position` focus), darken the bottom third, set the game name (for example "Learn Craps") in Inter Display ExtraBold with "<app> · Know the Odds" below it, and save as JPEG under 200 KB.

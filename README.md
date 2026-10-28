# creynia.github.io

Landing page for **Know the Odds**, a set of play-money web apps that teach casino games:

| Card | App | Game |
| --- | --- | --- |
| crappy | <https://creynia.github.io/crappy/> | Craps |
| baccaratton | <https://creynia.github.io/baccaratton/> | Baccarat (Punto Banco) |
| holdumb | <https://creynia.github.io/holdumb/> | Ultimate Texas Hold'em |
| spinner | coming soon | Roulette |

It is a single static `index.html` with no build step. GitHub Pages serves it from the root of `main`.

## Card art

Every card ships with built-in SVG art. To replace one with a generated image, save it as `assets/<app>.webp` (for example `assets/crappy.webp`) and it appears automatically; if the file is missing, the SVG shows. To turn `spinner` into a link once it ships, change its `<div class="card soon">` to `<a class="card" href="https://creynia.github.io/spinner/">` and update the tag and call to action.

Image specs: 1600 × 1000 px (16:10), WebP, under 250 KB. Keep the subject in the middle 60% of the frame, since phones in landscape crop the top and bottom. The bottom 25% fades into the card, so keep it plain. No text, logos or real casino branding.

Prompts (shared style first, then one per image):

- **Shared style:** "Stylized semi-realistic 3D illustration, overhead three-quarter view of a casino table, soft studio lighting with a warm gold rim light, shallow depth of field, rich felt texture, elegant and calm, no people, no text, no logos, centered composition, plain dark felt across the bottom quarter, 16:10."
- **`assets/crappy.webp`:** "…two ivory dice mid-tumble showing four and three, casting soft shadows on deep emerald green craps felt (#0b3d2e), a curved gold pass-line stripe, a red and a blue clay chip blurred at the edges."
- **`assets/baccaratton.webp`:** "…two playing cards fanned face-up, a king of clubs and a nine of diamonds, on deep burgundy baccarat felt (#5c1a2b), a thin gold curved line, a small neat stack of gold-edged chips blurred in the background."
- **`assets/holdumb.webp`:** "…an ace of spades and king of hearts as hole cards in the foreground, five face-down community cards softly blurred behind them, on deep navy poker felt (#0b2e4a), a short stack of gold chips to the right."
- **`assets/spinner.webp`:** "…a polished roulette wheel from above at a slight angle, alternating red and black pockets, a single green zero, a white ball resting in a pocket, warm walnut wood and brass, against a dark brown background (#2a1a0c)."
- **`assets/og-image.png`** (link preview, 1200 × 630, PNG): "Dark green-black background with a subtle gold vignette. Centered, a loose arrangement of two dice, two playing cards and a small roulette wheel. Generous empty space at the top for a title added later, no text, elegant and minimal."

The social preview image is optional: if `assets/og-image.png` is missing, links just show without a picture.

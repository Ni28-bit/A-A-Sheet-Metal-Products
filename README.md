# A&A Sheet Metal Products — Website

Single-page website for A&A Sheet Metal Products, 111 Carneal St, Ludlow, KY 41016.
Plain HTML + CSS — no build step, no frameworks, nothing to install. Edit the files,
push, and the live site updates.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole site — all the text lives here |
| `css/style.css` | Colors, fonts, layout |
| `images/` | Put job photos and the logo here |

## Going live (GitHub Pages — free)

One-time setup, done on github.com by the repo owner:

1. Open the repo → **Settings** → **Pages** (left sidebar)
2. Under "Build and deployment", set **Source** to `Deploy from a branch`
3. Set branch to `main`, folder `/ (root)`, and click **Save**
4. In a minute or two the site is live at
   `https://ni28-bit.github.io/A-A-Sheet-Metal-Products/`

Every future `git push` updates the live site automatically (give it a minute).
A custom domain (like `aasheetmetal.com`) can be added later under the same
Settings → Pages screen after buying the domain from any registrar (~$10–15/yr).

## Adding job photos

1. Copy photos into the `images/` folder. Photos straight off a phone are big —
   they'll work, but the page loads faster if you resize them to ~1600px wide first
   (Preview on Mac: Tools → Adjust Size).
2. In `index.html`, find the `<!-- TO ADD REAL PHOTOS -->` comment in the gallery
   section. Replace a placeholder tile:

   ```html
   <!-- before -->
   <figure class="gallery-item"><div class="ph"><span>Ductwork Install</span></div></figure>

   <!-- after -->
   <figure class="gallery-item"><img src="images/duct-job-1.jpg" alt="Custom ductwork install" loading="lazy"></figure>
   ```

3. Commit and push. Add as many `<figure>` lines as you want — the grid grows on its own.

## Adding the real logo

Put the logo file in `images/` (e.g. `images/logo.png`), then in `index.html` replace
the `<span class="wordmark-badge">A&A</span>` in the header with:

```html
<img src="images/logo.png" alt="A&A Sheet Metal Products" style="height:42px">
```

## Activating the quote form (~5 minutes, free)

The quote form is wired for [Formspree](https://formspree.io) (free plan: 50
submissions/month). Until it's activated, the form falls back to opening the
visitor's email app — so nothing is broken, but real form delivery is better:

1. Sign up free at formspree.io using the shop Gmail
2. Click **New form**, name it "Quote requests"
3. Copy the endpoint URL it gives you — looks like `https://formspree.io/f/abcd1234`
4. In `index.html`, find `action="https://formspree.io/f/YOUR_FORM_ID"` and paste
   your real URL in its place
5. Push, then submit one test quote from the live site and confirm it lands in Gmail

## Working on the site (Mac)

```bash
git clone https://github.com/Ni28-bit/A-A-Sheet-Metal-Products.git
cd A-A-Sheet-Metal-Products
open index.html        # preview in browser
# ...edit, then:
git add -A
git commit -m "describe what changed"
git push
```

## Things to update over time

- Hours or phone number: search `index.html` — they each appear in 2–3 places
- The copyright year in the footer

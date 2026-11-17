# Jeffrey_website

Single-page website for Chop Fitness (personal training in Boulder and Louisville, Colorado).
It is a preview rebuild of chop-fitness.com that puts prices, locations, hours, trainers,
FAQ and contact on one page.

## Files

- `index.html`: the whole page (content, styles and script in one file)
- `assets/`: logo and photos
- `.nojekyll`: tells GitHub Pages to serve the files as they are

## Publish with GitHub Pages

1. In the repository on GitHub, open **Settings > Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Pick the branch that holds `index.html` and the `/ (root)` folder, then **Save**.
4. After a minute or two the page is live at `https://dmg159.github.io/Jeffrey_website/`.

## Turn on the booking form

The "Book your $25 assessment" form needs a form service to deliver requests to an inbox.

1. Whoever owns the inbox signs up at a form service such as Formspree and creates a form.
2. Copy the form address it gives you (it looks like `https://formspree.io/f/abcdwxyz`).
3. In `index.html`, find `var FORM_ENDPOINT = "";` and paste the address between the quotes.

Until that is done, the form opens the visitor's email app with their answers filled in.

## Things that still live on chop-fitness.com

Checkout ("Buy a plan"), the full member stories, and the privacy policy and terms
link to the current site. The Chop Method page and group programs are not linked.

## Before going live on the real domain

Remove the `<meta name="robots" content="noindex">` line near the top of `index.html`.
It keeps search engines from listing this preview next to the current site.

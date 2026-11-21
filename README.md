# Jeffrey_website

Single-page website for Chop Fitness (personal training in Boulder and Louisville, Colorado).
It is a preview rebuild of chop-fitness.com that puts prices, locations, hours, trainers,
FAQ and contact on one page.

## Files

- `index.html`: the whole page (content, styles and script in one file)
- `assets/`: logo, photos and the social preview image (`social.jpg`)
- `robots.txt` and `sitemap.xml`: for search engines, written for chop-fitness.com
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

## Turn on Google Analytics

1. Whoever owns the business Google account creates a GA4 property at analytics.google.com
   with a web data stream for `https://chop-fitness.com`.
2. Copy the measurement ID (it looks like `G-ABC123XYZ`).
3. In `index.html`, find `var GA_MEASUREMENT_ID = "";` and paste the ID between the quotes.

While the ID is empty there is no analytics and no cookie banner. Once it is set:

- Visitors see a cookie banner. Google Analytics only loads after they click **Accept**.
  **Decline** keeps it off and removes any Google Analytics cookies. The choice is remembered,
  and the **Cookie settings** link in the footer reopens the banner.
- The booking form sends these events:
  - `form_start`: the visitor starts filling in the form
  - `generate_lead`: the request was sent (only once the form service is set up)
  - `assessment_email_opened`: the form opened the visitor's email app instead
  - `form_error`: sending failed
- In GA4, mark `generate_lead` as a key event (Admin > Events) to count booking requests
  as conversions.

The privacy policy on chop-fitness.com should mention Google Analytics.

## Things that still live on chop-fitness.com

Checkout ("Buy a plan"), the full member stories, and the privacy policy and terms
link to the current site. The Chop Method page and group programs are not linked.
Moving this page onto chop-fitness.com replaces the current site, so those pages need
a new home first.

## Going live on chop-fitness.com

The canonical address, social preview tags, structured data, `robots.txt` and
`sitemap.xml` already use `https://chop-fitness.com/`. To launch:

1. Remove the `<meta name="robots" content="noindex">` line near the top of `index.html`.
   It keeps search engines from listing this preview next to the current site.
2. In **Settings > Pages > Custom domain**, enter `chop-fitness.com` and save, then tick
   **Enforce HTTPS** once it is offered.
3. At the domain registrar, point the DNS at GitHub Pages as GitHub's custom domain guide
   describes.
4. Submit `https://chop-fitness.com/sitemap.xml` in Google Search Console.

Until step 2, social previews of the github.io link show no image, because the image
address points at chop-fitness.com.

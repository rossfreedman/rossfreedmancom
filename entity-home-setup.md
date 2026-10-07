# Setting up your entity home page

Your entity home is the one page that says, in your own words, who you are. Google uses it to tie your Wikidata item and other profiles together, which helps a Knowledge Panel show up.

## 1. Pick where it lives
- Best option: a personal domain such as `rossfreedman.com`, with this page at the root (`https://rossfreedman.com/`).
- Also fine: an About page on a site you already control, like `https://yoursite.com/about/ross-freedman`.
- Choose one URL and keep it for good. Changing it later restarts the process.
- Any static host works (Netlify, Vercel, GitHub Pages, Squarespace or WordPress custom HTML, and so on). It's a single file with no dependencies.

## 2. Replace the placeholders in `entity-home.html`
1. Find `https://EXAMPLE-DOMAIN/` and replace every instance with the page's final URL. It appears in the canonical tag, the og:url and og:image tags, and the JSON-LD (url, image, and the `@id` values). Keep the trailing `/` consistent.
2. Upload a square headshot (at least 400×400 px) to `/images/ross-freedman-headshot.jpg`, or change the image path in both the `<img>` tag and the JSON-LD `image` field.
3. Optional: put a contact link in the footer where it says `REPLACE`.
4. If you edit the JSON-LD, make the same change in `person-schema.json` so the two match.

## 3. Point your profiles back to the page
This two-way linking is what convinces Google the profiles all describe the same person.
- **Wikidata (Q106428505):** add the page URL as **official website (P856)**. While you're there, add your other profile IDs if they're missing (LinkedIn, Crunchbase, X).
- **LinkedIn:** add it under Contact info → Website (type "Personal"), and/or as a Featured link.
- **Crunchbase:** add it as the website on your person profile.
- **367 Ventures bio and Rally team/about page:** link your name or a "Personal site" link to the URL.
- **X (@rfreedman):** put the URL in the website field of your profile.
- Keep the wording consistent everywhere: "Ross Freedman, American technology entrepreneur", with the same headshot if you can.

## 4. Verify in Google Search Console
1. Go to https://search.google.com/search-console and add a property. Use the **Domain** property if you own the domain (you'll verify with a DNS TXT record at your registrar). Use **URL prefix** if you only control part of a site (you'll verify with an HTML tag or file).
2. Submit a sitemap if your host creates one. Otherwise skip it; step 6 covers you.

## 5. Test the markup
- **Rich Results Test:** https://search.google.com/test/rich-results. Paste the live URL. It should find a valid **Profile page** item with no errors.
- **Schema.org Validator:** https://validator.schema.org. It should show ProfilePage and Person with no errors.
- Fix any errors and test again.

## 6. Request indexing
In Search Console, paste the page URL into **URL Inspection** and click **Request indexing**.

## 7. Then wait
Knowledge Panels aren't guaranteed and usually take weeks to months. Keep the page live and up to date, update it when something changes (new roles, awards, press), and add new press coverage to "Press & sources". Once a panel shows up, use its "Claim this knowledge panel" option to get verified.

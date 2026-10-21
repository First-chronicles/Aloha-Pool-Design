# Aloha Pool & Design: Website Build Notes

Built October 20, 2026 for Foundational Marketing Hub. A single-page static site with no framework and no build step. Upload the `website/` folder as-is to replace the current Mobirise site at alohapooldesign.com.

## Files

- `aloha-pool-design-website.zip` (5.5 MB): the `website/` folder, ready to upload. Upload the folder's contents to the web root so `index.html` sits at the top level. Rebuild the ZIP after any edit.

- `website/index.html`: the page, JSON-LD schema and meta tags
- `website/styles.css`: role-based design tokens at the top
- `website/script.js`: menu drawer, dropdowns, forms, lightbox and map. **`FORM_ENDPOINT` is on line 8.**
- `website/assets/img/`: 39 cropped and compressed images (photos plus the logo). They come from the client's Instagram build shots (captions cropped out) and the 12 finished-pool photos on the current site's gallery page.
- `website/assets/favicon.svg` and `apple-touch-icon.png`: a temporary wave mark, and the logo on black
- `website/assets/vendor/leaflet/`: Leaflet 1.9.4, CSS and JS hosted locally so the map works on strict-CSP hosts. It loads only when the map scrolls near the screen.
- `website/robots.txt` (AI crawlers allowed) and `sitemap.xml`
- `Assets/old-site/`: the 12 original gallery photos downloaded from alohapooldesign.com

## Facts used and their source

| Fact | Source |
|---|---|
| Name: Aloha Pool & Design. Legal name Aloha Pool & Design Inc | Current site; CSLB |
| Phone: (951) 453-9728 | Current site and CSLB (they match) |
| Email: info@alohapooldesign.com | Current site |
| License: C-53 #965927, active, bonded, expires 01/31/2027 | CSLB lookup, Oct 20, 2026 |
| Towns: Temecula, Murrieta, Winchester, Menifee, Sun City, Wildomar | Current site |
| "Lived and worked in the valley since 1990" | Current site |
| Owner-led, no salespeople, free estimates, turnkey | Current site |
| Concrete, landscaping, patio covers and design through Aloha Landscape | Current site |
| 12-step build process, shell watering 7 to 10 days, deck watering about a week, therapy-jet placement, four weeks of start-up visits | Current site's Course of Construction page |
| Financing pre-approval link (Lyon Financial) | Current site |
| Facebook: facebook.com/alohapooldesign | Current site |

## Placeholders to replace before launch

1. **Form backend.** Paste a Formspree or GHL URL into `FORM_ENDPOINT` in `script.js`, and replace `REPLACE_FORM_ID` in the two form `action` attributes in `index.html` (the no-JavaScript fallback). With the endpoint empty, the forms run in demo mode: the thank-you message says nothing was sent. Real success shows only on an OK response from the backend.
2. **HTTPS.** The current site is plain HTTP. The canonical, Open Graph tags and sitemap all assume `https://www.alohapooldesign.com/`, so the host needs an SSL certificate before launch.
3. **Instagram.** Not added. Add a social button and a `sameAs` entry once the handle is confirmed.
4. **Logo.** The logo is a JPG on a black field, so the header and footer badge are black to hide the edge. Swap in a transparent PNG or SVG when the client has one.

## Decisions made with defaults, so confirm with the client

- **Address is treated as private.** Two addresses conflict: the current site shows 41083 Sandalwood Cir #1, Murrieta, CA 92562, and the CSLB record shows 213 Marguerite Ave, Corona del Mar, CA 92625. The site shows "Temecula Valley, CA" only, the schema has region and country only, and the map plots town centers only. Once the client confirms a public, staffed address, add it to the contact section, the footer and the schema `address`, matching the Google Business Profile word for word. The CSLB record should be updated to match too.
- **Years in business.** Only "since 1990" is used. The old site's "over 18 years" line is out of date and was dropped.
- **Six services:** custom pools, spas and water features under the C-53 license; decking and concrete, landscaping and patio covers credited to Aloha Landscape. Remodels, resurfacing and repairs are left out until confirmed. Add Aloha Landscape's license number when we have it.
- **No "Hablamos Español" badge.** The top-bar slot is marked in an HTML comment.
- **Owner not named.** CSLB lists Mark Thomas Klingsporn as the qualifier. The About section says "the owner" until the client approves using his name.
- **No hours** anywhere, including the schema.
- **Before & After pairing.** The "During" and "After" photos (chevron-tile spa) match on fence, string lights, pergola, tile and coping, so they appear to be the same job. **Confirm with the client.** If they are different jobs, relabel or swap the pair.
- **Build stages** come from several different jobs, and the page says so.
- **Patio Covers card** uses the covered outdoor kitchen from the old site's gallery. Swap in a real Aloha Landscape patio-cover photo when available.
- **Copy avoids "our crew" and "our employees."** CSLB shows a workers' comp exemption (no employees on record).
- **Blog has 3 sample tips** drawn from the client's own process page. They expand in place. Replace them with real posts on their own pages before launch.
- **The "Ask About..." service buttons** pre-fill the contact form. Point them to dedicated service pages once those exist.
- **Schema type is `GeneralContractor`.** Schema.org has no pool-builder type. The license is in `hasCredential`.
- **Left out on purpose:** 5 Instagram photos with captions across the middle of the frame ("All set", "Prepped!", "Full!! Start up time") or a person in frame (acid wash), and the old site's hero image (infinity edge over the ocean), which may be stock.

## Verification done (October 20, 2026)

- 1 H1, a clean H2/H3 outline, and JSON-LD that parses (business, 6 Services, WebSite, FAQPage with 10 questions that match the visible FAQ)
- No horizontal overflow at 1366px or at 375px, no broken images, and no console errors
- Every content image has alt text and width/height. The hero is preloaded with `fetchpriority="high"`, and everything below it is lazy-loaded.
- All in-page anchors resolve
- Map: 6 markers, satellite and label tiles load, with Esri attribution
- The mobile drawer opens and closes, with dropdowns shown as indented items
- Form validation, the demo-mode thank-you and the service pre-select all work
- Lightbox opens and steps through all 9 photos

## Not verified

- Core Web Vitals. The hero image is 410 KB at 1920px (132 KB at 960px). Run PageSpeed Insights once the site is live on HTTPS.
- Google Rich Results Test. Run it on the live URL.

## Client actions

- Confirm the open items above (address, Spanish, Instagram, extra towns, remodel services, Aloha Landscape license, owner name, hours, the before/after pair).
- Claim and verify the Google Business Profile, complete every field and add real project photos. Keep the NAP identical to the site and the CSLB record.
- Add alohapooldesign.com to Search Console and submit the sitemap after launch.
- Ask for reviews steadily. Add review schema only once there are genuine reviews to show.
- List the business in local and trade directories with the same NAP.

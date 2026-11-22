# Royal Infra Scrap

This is a static HTML, CSS, and JavaScript website. The homepage and site assets are in the repository root. No Node server, build step, or separately hosted backend is needed.

## Deployment checklist

1. To use GitHub Pages, open **Settings → Pages**, choose **GitHub Actions** as the source, and save. The workflow copies the root `index.html` and required assets into a clean publishing folder and deploys them.
2. Configure the host to serve HTTPS for `royal-infra.in` and redirect the alternate hostname (such as `www.royal-infra.in`) to the chosen canonical hostname. The page currently declares `https://royal-infra.in/` as canonical.
3. Open the live site on desktop and mobile. Submit a test enquiry and verify it appears in the Google Sheet.
4. Verify ownership of `https://royal-infra.in/` in Google Search Console, then submit `https://royal-infra.in/sitemap.xml` in the Sitemaps report. Use URL Inspection to request indexing for the homepage.
5. Set up or claim the business's Google Business Profile and keep its name, phone, address, hours, and service area consistent with the website.

## Search visibility

The homepage includes a page title and description, canonical URL, search crawler directives, Open Graph/Twitter tags, LocalBusiness structured data, `robots.txt`, and a sitemap. Google decides whether and when to index the site and whether to show extra links under its result. Sitelinks are generated automatically; page owners cannot force them to appear. Clear section headings, descriptive navigation labels, and good internal links help Google understand the site structure.

## Enquiry form

The enquiry form sends JSON directly to the deployed Google Apps Script web app from `js/app.js`, using a plain-text request and `mode: 'no-cors'`. The Apps Script `doPost(e)` receives the JSON in `e.postData.contents`. Because the browser cannot read a cross-origin `no-cors` response, the form shows its thank-you state when the request is sent; it cannot confirm a Google-side error or show the Apps Script enquiry ID.

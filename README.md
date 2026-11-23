# Royal World Scraps

This is a static HTML, CSS, and JavaScript website. Its pages and site assets are in the repository root. No Node server or build step is needed.

## Preview on GitHub Pages

Open **Settings → Pages**, choose **GitHub Actions** as the source, and save. The workflow publishes the home page, services page, AC scrap catalog, sell scrap page, contact page, and the sitemap at:

https://hassaank78.github.io/royalinfra/

No custom domain is configured in the repository. The deployment workflow is triggered by pushes to `main`. The pages are linked through the shared navigation and listed in `sitemap.xml` for crawling.

## Enquiry form

The enquiry form sends JSON directly to the deployed Google Apps Script web app from `js/app.js`, using a plain-text request and `mode: 'no-cors'`. The Apps Script `doPost(e)` receives the JSON in `e.postData.contents`. Because the browser cannot read a cross-origin `no-cors` response, the form shows its thank-you state when the request is sent; it cannot confirm a Google-side error or show the Apps Script enquiry ID.

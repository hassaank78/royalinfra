# Royal World Scraps

This is a static HTML, CSS, and JavaScript website. Its pages and site assets are in the repository root. No Node server or build step is needed.

## Preview on GitHub Pages

Open **Settings → Pages**, choose **GitHub Actions** as the source, and save. The workflow publishes the home page, services page, AC scrap catalog, sell scrap page, contact page, and the sitemap at:

GitHub Pages preview: https://hassaank78.github.io/royalinfra/

The production domain is `https://royal-world.in/`. Add it under **Settings → Pages → Custom domain**, then configure the apex DNS records with your domain provider and enable HTTPS. The Actions workflow deploys on pushes to `main`; a `CNAME` file is not required for this workflow.

## Enquiry form

The enquiry form sends JSON directly to the deployed Google Apps Script web app from `js/app.js`, using a plain-text request and `mode: 'no-cors'`. The Apps Script `doPost(e)` receives the JSON in `e.postData.contents`. Because the browser cannot read a cross-origin `no-cors` response, the form shows its thank-you state when the request is sent; it cannot confirm a Google-side error or show the Apps Script enquiry ID.

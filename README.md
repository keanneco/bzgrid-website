# bzgrid.com

The website of **Bizniz Grid**, a product of **Keanne Software (Pty) Ltd**:
<https://bzgrid.com>.

It is plain HTML and CSS in `site/`. There is no build step. The site runs no
scripts, sets no cookies and loads nothing from another host: the fonts are
served from `site/assets/fonts` under the SIL Open Font License.

| Path | What it is |
| --- | --- |
| `site/index.html` | Home page: what Bizniz Grid does, bookings and WhatsApp, the company and its contact details |
| `site/privacy.html` | Privacy policy (POPIA). `#delete-your-information` is the data-deletion section |
| `site/404.html` | Not-found page |
| `site/assets/` | The stylesheet, wordmark, icons, link-preview image (`share.png`, 1200×630) and fonts |
| `site/robots.txt`, `site/sitemap.xml` | For search engines |
| `netlify.toml` | Netlify settings: publish `site/` as it is, and the security headers |

## Preview

Open `site/index.html` in a browser. `404.html` uses root-relative paths, so
it needs a web server, for example `npx serve site`.

## Deploying

Netlify publishes every push to `main`. A pull request gets a preview address
of its own before it's merged.

`bzgrid.com`'s DNS stays at Hostinger:

- **`@`:** an A record to Netlify's load balancer, `75.2.60.5`.
- **`www`:** a CNAME to the Netlify site's own `*.netlify.app` address.

Netlify redirects `www` to the bare domain and provides the HTTPS certificate.
The MX and TXT records belong to the domain's email, so leave them alone.

## Changing the site

Edit the files, commit and push to `main`. When Bizniz Grid changes what it
collects, or who processes it, update the privacy policy and its date in the
same push.

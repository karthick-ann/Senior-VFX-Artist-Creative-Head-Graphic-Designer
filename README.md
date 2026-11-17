# Karthick Annadurai — Résumé Website

A static, no-build résumé site for **Karthick Annadurai**, Senior VFX Artist, Graphic Designer and Creative Head. Includes AI-assisted web development and Be10x AI Tools certification. It works from a folder, on GitHub Pages, or on Hostinger.

## Files

```text
myresume/
├─ index.html          # the whole site: markup, CSS and JavaScript
├─ assets/
│  └─ profile.jpg      # portrait used in the hero
├─ .nojekyll           # tells GitHub Pages to serve files as-is
├─ .htaccess           # Apache caching, compression and security (Hostinger)
├─ robots.txt          # crawler rules
└─ README.md
```

`index.html` is self-contained apart from `assets/profile.jpg` and the Google Fonts stylesheet. There is no build step.

## Preview locally

Open `index.html` in a browser, or run a local server from this folder:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy to GitHub Pages

1. Create a repository and upload the **contents** of this folder to the repository root. Keep `assets/profile.jpg` inside `assets/`.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Wait for the Pages build, then open the published URL.

Do not upload a ZIP. GitHub Pages needs `index.html` at the repository root.

## Deploy to Hostinger

1. Open **hPanel → File Manager** for the domain.
2. Enter `public_html`.
3. Upload the contents of this folder, keeping `index.html` at the root of `public_html` and `profile.jpg` inside `assets/`.
4. Open the domain in a browser and confirm the portrait and fonts load.

`.htaccess` is already configured for compression, browser caching and basic security headers. If the host does not use Apache, the site still works; the `.htaccess` file is simply ignored.

## Customize

- **Content:** edit the semantic sections in `index.html` (`#craft`, `#toolkit`, `#career`, `#relocate`, `#contact`).
- **Colors and fonts:** edit the custom properties in `:root` near the top of the `<style>` block.
- **Portrait:** replace `assets/profile.jpg` with a square image, then update the `width` and `height` attributes on the `<img>` if the dimensions change.
- **Print / PDF:** the **Résumé PDF** button opens the browser print dialog. Print styles hide the navigation and portrait and condense the content for A4.
- **Email copy button:** works on HTTPS or `localhost`. On an insecure origin the button hides and the email link remains.

## Before going live

- Set the final domain in the canonical link if you add one, and change the relative `og:image` / `twitter:image` values to absolute URLs such as `https://example.com/assets/profile.jpg`.
- Add a canonical URL and a `sitemap.xml` after the domain is known.
- Uncomment the HTTPS redirect block in `.htaccess` only after an SSL certificate is active.
- Test the page at mobile width, with keyboard navigation, and with **Print → Save as PDF**.

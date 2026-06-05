# Orell — Landing Page

Static landing page for an **AI agent audit & compliance** startup. No build step, no dependencies — plain HTML/CSS/JS.

## Rebranding (company name / domain)

Edit the three values at the top of **`config.js`**:

```js
const BRAND = {
  companyName: "Orell",
  domain: "useorell.xyz",
  contactEmail: "hello@useorell.xyz"
};
```

Every occurrence of the company name, domain, and email in the page is injected from this file at load time. Nothing else needs to change.

## Deploy to GitHub Pages

1. Create a new GitHub repo and push this folder's contents to it:
   ```sh
   git init
   git add .
   git commit -m "Landing page"
   git remote add origin https://github.com/<user>/<repo>.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)`** → Save.
3. The site goes live at `https://<user>.github.io/<repo>/`.

For a custom domain, add it under **Settings → Pages → Custom domain** (GitHub creates a `CNAME` file) and point your DNS at GitHub Pages.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page structure & copy |
| `style.css` | All styling (CSS variables at top control the palette) |
| `config.js` | Brand config + injection script |

## Notes

- The email form shows a confirmation message client-side; wire it to Formspree, Buttondown, or your own endpoint to actually collect emails.
- Theme palette lives in the `:root` block of `style.css` (`--ink`, `--accent`, `--bg-hero`, `--bg-muted`).
- Logo is an inline SVG in `index.html` (nav + footer) — swap both `<svg class="logo-mark">` blocks to change it.

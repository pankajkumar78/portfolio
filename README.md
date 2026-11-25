# Pankaj Kumar — Portfolio

Static one-page portfolio (`index.html` + `style.css`). There's no build step, so GitHub Pages serves it directly.

## Preview locally

```bash
open index.html            # or: python3 -m http.server 8000  →  http://localhost:8000
```

## Publish free on GitHub Pages

1. Sign in to your **personal** GitHub account. Create a new **public** repo named exactly
   `pankajkumar78.github.io` and don't add a README to it.
2. From this folder, run:
   ```bash
   git add .
   git commit -m "Initial portfolio"
   git remote add origin https://github.com/pankajkumar78/pankajkumar78.github.io.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages → Build and deployment**. Choose *Deploy from a branch*, then `main` / `/ (root)`.
4. After about a minute the site is live at **https://pankajkumar78.github.io**.
5. Add the link to your LinkedIn: **Featured → Add link**, and **Contact info → Website**.

To use a custom domain (such as `pankajkumar.dev`), add it under Settings → Pages → Custom domain.

## Before going public

Search `index.html` for `VERIFY` and `TODO`:
- Confirm each metric marked `VERIFY`, and that your employer is fine with sharing it publicly.
- Fill in the automotive details: platform, partner and status.
- Add an `og:image` (1200×630) so the link looks good when shared on LinkedIn.

## Regenerate the resume PDF and share image

`resume.html` is the source for `resume.pdf`, and `og.html` is the source for `og-image.png`. After editing either one, run:

```bash
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
"$CHROME" --headless=new --no-pdf-header-footer --print-to-pdf="$PWD/resume.pdf" "file://$PWD/resume.html"
"$CHROME" --headless=new --hide-scrollbars --window-size=1200,630 --screenshot="$PWD/og-image.png" "file://$PWD/og.html"
```

The resume only includes figures that are already public (100M+, 7+, 15+). Add others once they're verified.

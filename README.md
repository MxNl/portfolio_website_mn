# Artist Portfolio — Quarto + GitHub Pages

A clean, minimal artist portfolio site built with [Quarto](https://quarto.org) and hosted on GitHub Pages.

## Adding new paintings

1. Drop your image file (`.jpg`, `.png`, `.webp`) into `images/paintings/`
2. Optionally add metadata to `paintings.yml`:
   ```yaml
   - file: my-new-painting.jpg
     title: "My New Painting"
     year: 2025
     medium: "Oil on linen"
   ```
3. `git add . && git commit -m "add painting" && git push`

The site rebuilds automatically via GitHub Actions within ~2 minutes.

---

## Local development

### Prerequisites
- [R](https://www.r-project.org/) (≥ 4.1)
- [Quarto](https://quarto.org/docs/get-started/)
- R package: `yaml` — install with `install.packages("yaml")`

### Run locally

```bash
quarto preview
```

This starts a live-preview server. Changes to `.qmd` files and CSS reload instantly. After adding new images, save any `.qmd` file to trigger a re-render of the gallery.

---

## GitHub Pages setup (first time only)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Under *Source*, choose **GitHub Actions**
4. Push to `main` — the workflow builds and deploys automatically

Your site will be live at `https://yourusername.github.io/your-repo-name/`

---

## Customise

| File | What to change |
|---|---|
| `_quarto.yml` | Site title, Instagram link, footer text |
| `styles.css` | Colors, fonts, column count, spacing |
| `about.qmd` | Bio text, contact links |
| `paintings.yml` | Image metadata |

### Change the number of gallery columns

In `styles.css`, edit the `:root` block:

```css
:root {
  --cols: 3; /* change to 2 or 4 */
}
```

Or override per breakpoint in the responsive section at the bottom of `styles.css`.

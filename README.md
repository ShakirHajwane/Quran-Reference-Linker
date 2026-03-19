# Quran Reference Linker

Single-file hover-to-play Quran reference linker for Islamic articles, blogs, and CMS-driven content.

## Live links

- Hosted script: `https://shakirhajwane.github.io/Quran-Reference-Linker/quran-ref-linker.min.js`
- Live docs: `https://shakirhajwane.github.io/Quran-Reference-Linker/`
- Live demo: `https://shakirhajwane.github.io/Quran-Reference-Linker/demo/`

## Use in your project

Add this once in your site layout or page `<head>`:

```html
<script
  defer
  src="https://shakirhajwane.github.io/Quran-Reference-Linker/quran-ref-linker.min.js"
></script>
```

Then write Quran references in normal article content such as:

- `[Quran 2:255]`
- `[Surah Baqarah 2:255]`
- `[2:255]`
- `Quran 36:58`
- `Surah Al-Baqarah 2:255`

The widget will scan eligible content, turn those references into interactive inline links, and show:

- the Arabic verse text
- an English translation
- a play/pause recitation button

## See the demo

Use the public GitHub Pages demo to sanity-check the hosted widget:

`https://shakirhajwane.github.io/Quran-Reference-Linker/demo/`

This demo is using the hosted GitHub Pages bundle, not a local dev build.

## Where it works well

- Islamic blogs and article archives
- WordPress, Ghost, Hugo, Jekyll, Next.js, static sites
- editorial CMS pages
- long-form essays with many Quran references

## Notes

- The widget scans `<p>`, `<li>`, `<span>`, and `<div>`.
- It ignores refs inside links, code blocks, form fields, and existing widget markup.
- It watches for late-added DOM content, so SPA or CMS-injected content still works.
- It works on HTML pages, not raw `.pdf` browser documents.

If your site uses a strict CSP, allow:

- `connect-src https://api.quran.com`
- `media-src https://verses.quran.com`
- `style-src 'unsafe-inline'`

## Local development

```bash
npm ci
npm test
npm run build
npm run demo
npm run build:pages
```

Local demo:

`http://127.0.0.1:4173/demo/`

## Updating the hosted Pages build

This repo currently deploys the checked-in `pages-dist/` snapshot to GitHub Pages. After changing the widget or docs, rebuild before pushing:

```bash
npm run build
npm run build:pages
git add pages-dist README.md docs .github/workflows
git commit -m "Update hosted widget"
git push
```

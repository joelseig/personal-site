# joelseignior.com

A small site for keeping notes and ideas.

## Structure

- `index.html` — front page
- `articles/` — long-form pieces
  - `flat-markdown.html` — Keep your reference knowledge in flat Markdown

## Deploy

Static. No build step. Vercel serves files as-is. Google Fonts are loaded at runtime.

## Adding a new article

1. In the GitHub web UI, open `articles/_template.html`, click the pencil icon to edit, and use the filename field at the top to rename it to your new slug, e.g. `articles/your-slug.html`. (GitHub will treat this as creating a new file rather than moving the template.)
2. In the editor, fill in the placeholders:
   - `{{TITLE}}` — the article title (appears in `<title>`, `<h1>`, and the meta block).
   - `{{SUBTITLE}}` — the one-sentence lede under the title.
   - `{{DATE_EYEBROW}}` — the short date above the title (e.g. `May 2026`).
   - `{{DATE_LONG}}` — the published date in the byline (e.g. `16 May 2026`).
   - `{{AUTHOR}}` — your name.
3. Replace the two example `<section>` blocks between `<!-- ARTICLE BODY START -->` and `<!-- ARTICLE BODY END -->` with your real prose.
   - Wrap each paragraph in `<p class="copy">…</p>`.
   - Wrap each section in `<section id="some-id">` with an `<h2 class="section__head">` heading.
   - The template includes a commented list of optional components (pull quotes, callouts, lists, code blocks, compare blocks, "move" cards) — copy/paste the markup for any you want to use.
4. Add a link to your new article on `index.html` under the "Writing." section. The pattern matches the existing entry for `flat-markdown.html`.
5. Commit. Vercel will redeploy automatically within a few seconds.

### Notes

- `articles/_template.html` is a template, not a published article. It is technically reachable at `/articles/_template.html` but nothing links to it. If you want to keep it strictly out of search engines, add a `Disallow: /articles/_template.html` line to `robots.txt`.
- All styling is in the `<style>` block at the top of each article file. Each article carries its own copy of the CSS — this is intentional for the static-site simplicity, and it keeps articles self-contained. To update the design across all articles in future, you would need to edit each article file (or switch to a templating system like Eleventy).

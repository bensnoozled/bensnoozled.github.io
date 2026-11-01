# nonzero

Personal site for writing, poetry, photography, paintings, and 3D art. Built with Jekyll, hosted on GitHub Pages at [banderl.net](https://banderl.net).

## Adding content

Each content type is a Jekyll "collection" — a folder of Markdown files. Adding a piece means adding one file; the index/gallery pages update automatically.

### Writing — `_writing/`

Create a new `.md` file (name doesn't matter, e.g. `_writing/my-essay.md`):

```yaml
---
title: My Essay Title
date: 2026-09-20
---

Body text goes here, written in Markdown.
```

### Poetry — `_poetry/`

Same front matter as writing (`title`, `date`). Dates aren't shown on poems; `date` only sets the order (newest first), so a rough one like `2022-01-01` is fine. Line breaks are kept as written, so type each line on its own line and leave a blank line between stanzas:

```markdown
---
title: My Poem
date: 2026-11-01
---

First line of the poem
second line of the poem

Next stanza begins here
```

### Photography / Paintings / 3D Art — `_photography/`, `_paintings/`, `_3d-art/`

1. Put the image file in the matching folder under `assets/images/` (e.g. `assets/images/photography/`).
2. Create a new `.md` file in the matching collection folder:

```yaml
---
title: Piece Title
date: 2026-09-20
image: /assets/images/photography/my-photo.jpg
alt: Short description of the image for accessibility
---

Optional caption/description text goes here. Leave the body empty if there's nothing to add.
```

The `image:` path is relative to the site root.

### Paintings: medium

Paintings can add `medium:` to the front matter (e.g. `medium: Acrylic on canvas`). It shows next to the date on the painting's page.

## Local preview (optional)

Requires Ruby 2.7+ (the system Ruby on this Mac is older, so install one via `rbenv` or Homebrew first):

```bash
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`. This step is optional — pushing to GitHub builds and deploys automatically.

## Deployment

Push to the `main` branch of `bensnoozled/bensnoozled.github.io` on GitHub. GitHub Pages builds the Jekyll site automatically — no CI config needed.

The `CNAME` file points the site at `banderl.net`. In the DNS settings for `banderl.net`, add:

- An `A` record (apex domain) pointing to GitHub Pages' IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- Or a `CNAME` record for a `www` subdomain pointing to `bensnoozled.github.io`

Then in the repo's GitHub Settings → Pages, set the custom domain to `banderl.net` and enable "Enforce HTTPS" once DNS propagates.

# nonzero

Personal site for writing, photography, paintings, and 3D art. Built with Jekyll, hosted on GitHub Pages at [banderl.net](https://banderl.net).

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

### Removing the example entries

Each collection ships with one placeholder entry (`example-*.md` / `hello-world.md`) using an SVG placeholder image. Delete these once real content is in.

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

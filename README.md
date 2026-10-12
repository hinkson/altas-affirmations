# Apps — the wellness studio website

A static "studio" website for the gentle/wellness apps. It can be hosted for free on
GitHub Pages, Cloudflare Pages, Netlify, or any static host.

Three apps have cards on `index.html`:

| App | Page slug | Status |
| --- | --- | --- |
| Alta's Affirmations | `alta` (privacy/support are unprefixed) | Live on the App Store |
| Not Beaten | `not-beaten` | Live on the App Store |
| Wait, Did I? | `wait-did-i` | Live on the App Store |

## Pages

- `index.html`: studio landing page (the apps grid)
- `alta.html`, `not-beaten.html`, `wait-did-i.html`: per-app product pages
- `privacy.html` / `support.html`: **Alta's** policy and support pages (unprefixed for
  historical reasons — they predate the site becoming a studio)
- `<slug>-privacy.html` / `<slug>-support.html`: the same pair for the other two apps

## Before Publishing

1. `publish-site.sh` aborts if the affirmation pack count in `alta.html`'s hero stat
   doesn't match the app **live on the App Store** (counted from that version's source in
   git, not from master, so an unreleased pack never blocks a publish). Tag each upload
   `alta-<version>-build-<n>` to make the match exact. Run `./publish-site.sh --check` first.
2. If using a custom domain, add a `CNAME` file with that domain.
3. Each product page's hero is a real screen from the app, at `assets/shots/<slug>-hero.jpg`.
   Those files are **not in this folder** (no images in the monorepo): `publish-site.sh`
   builds them from `~/Desktop/Studio Assets/<App>/Website/raw/hero.png` straight into the
   deploy repo, and aborts if one is missing. When an app's store frames are reshot, replace
   its `hero.png` in the same sitting. To preview locally, copy the built JPEGs into a
   scratch copy of `docs/assets/shots/`.

## Local Preview

From this project folder:

```sh
python3 -m http.server 8080 -d docs
```

Then open `http://localhost:8080`.

## Free Hosting Recommendation

For a separate free website, create a new public GitHub repository just for this site, copy the `docs` folder contents into it, and enable GitHub Pages. You can also publish from a `docs` folder if you keep it in a larger repo.

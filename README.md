# Alta's Affirmations Website

This is a static website for Alta's Affirmations. It can be hosted for free on GitHub Pages, Cloudflare Pages, Netlify, or any static host.

## Pages

- `index.html`: marketing landing page
- `support.html`: App Store support URL candidate
- `privacy.html`: App Store privacy policy URL candidate

## Before Publishing

1. Add the live App Store URL to the launch-status section in `index.html` after approval.
2. If using a custom domain, add a `CNAME` file with that domain.

## Local Preview

From this project folder:

```sh
python3 -m http.server 8080 -d docs
```

Then open `http://localhost:8080`.

## Free Hosting Recommendation

For a separate free website, create a new public GitHub repository just for this site, copy the `docs` folder contents into it, and enable GitHub Pages. You can also publish from a `docs` folder if you keep it in a larger repo.

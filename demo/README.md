# Client demos

Mock/preview sites hosted under your own domain so you never have to send a
client a `*.vercel.app` link.

## How it works

Anything in this folder is served at **`https://quecybersolutions.com/demo/<folder-name>`**.

```
demo/
  acme-dental/index.html   ->  quecybersolutions.com/demo/acme-dental
  rio-roasters/index.html  ->  quecybersolutions.com/demo/rio-roasters
```

## Add a new demo

1. Copy `_template/` to a new folder named with the client's slug
   (lowercase, dashes — e.g. `acme-dental`).
2. Paste the client's mock site into that folder's `index.html`.
   Extra files (images, CSS, JS) go in the **same folder**; reference them
   with relative paths like `./logo.png`.
3. Commit + push. It's live at `quecybersolutions.com/demo/<slug>` in ~30s.

That's it. Send the client the clean URL.

## Notes

- **Private by default.** Demos are never linked from the main site, carry a
  `noindex` meta tag, and `/demo/*` sends an `X-Robots-Tag: noindex` header
  (see `../vercel.json`) plus a `Disallow: /demo/` in `../robots.txt`. They
  won't show up in Google — but the URLs are still public to anyone who has
  the link (not password-protected). Use unguessable slugs for sensitive work,
  or ask about Vercel password protection if a client needs it locked down.
- **Preview badge.** Each template/example has a small "Preview by
  QueCyberSolutions" badge linking back to your site. Keep it for branding, or
  delete that `<a>` block for a clean handoff.
- `example/` is a working sample (Rio Grande Roasters) — safe to delete once
  you've seen the flow.

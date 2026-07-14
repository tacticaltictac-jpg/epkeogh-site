# E. P. Keogh Contractors Ltd — company website

Static marketing site for E. P. Keogh Contractors Ltd, a Swindon & Wiltshire
groundworks contractor and property developer established in 1995.

**Not yet live.** No deployment, domain, analytics or third-party services are
connected. Everything (including fonts) is self-hosted in this folder.

## Run it locally

No build step, no dependencies. Serve the folder with anything, e.g.:

```sh
python3 -m http.server 8080
# then open http://localhost:8080
```

Opening `index.html` directly in a browser also works.

## Structure

```
index.html          Home
groundworks.html    Services / groundworks capability
developments.html   Development showcase (photo-led)
about.html          Company history
contact.html        Contact (email only, by design)
css/main.css        The whole design system — tokens at the top
js/site.js          Mobile nav toggle (the only JavaScript)
assets/fonts/       Self-hosted variable fonts (Archivo Narrow, Source Sans 3)
assets/placeholders/  Temporary duotone SVGs standing in for photography
assets/img/         Favicon; drop the real logo files here
```

## Things waiting on real content

1. **Logos — done.** The supplied files live in `assets/img/`:
   `*-original.jpg` are byte-for-byte as provided. The `.png` copies are
   production cut-outs — margins trimmed and the white ground keyed to
   transparency; the mark and wordmark themselves are untouched.
   `logo-horizontal-header.png` is a downscaled rendition used in the page
   headers. The cut-outs' edges are anti-aliased against white, so use them
   on light surfaces only (the footer keeps the typographic wordmark for
   this reason). `logo-stacked.png` is kept ready for tight spaces.
2. **Photography** — every temporary image references
   `assets/placeholders/*.svg` and is marked with a `PHOTO SLOT` comment.
   Replace the `src` with real photos; layout expects roughly 4:3 for cards
   and wide/16:10 for bands and the featured project.
3. **Email address** — `enquiries@epkeoghcontractors.co.uk` is a placeholder.
   Search the project for `epkeoghcontractors` and replace everywhere (it
   appears on the contact page and in every footer).
4. **Copy marked `PLACEHOLDER COPY`** — capability scope, plant/fleet
   details, standards/accreditations and company history should be verified
   and refined with the company before going live.

## Design notes

- Palette: logo navy `#1B3A5C` (deep variant `#12283F`), warm structural
  greys, warm off-white `#F4F2EC`, near-black ink, and a muted bronze
  `#8C6D3F` accent used only for kickers, hairlines and hovers.
- Type: Archivo Narrow (display/headings), Source Sans 3 (body) — both
  self-hosted variable woff2 files, ~47 KB total.
- All design tokens live in `:root` at the top of `css/main.css`.

## Moving this to its own repository

This branch has an orphan history containing only this site (nothing from
any other project). To give it its own repo, create an empty repository and:

```sh
git push <new-repo-url> claude/ep-keogh-contractors-site-9zq2p0:main
```

Do **not** merge this branch into any other project's main branch.

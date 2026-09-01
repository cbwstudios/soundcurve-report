# soundcurve-report

Client-facing SoundCurve report, published with GitHub Pages.

**Everything in this repo is generated. Do not edit it here.**

The source of truth is `Foundation/Sitemap/soundcurve-report.html` in the SoundCurve Dropbox
workspace. Edit that master, then run:

```bash
cd Foundation/Sitemap
python3 build_static.py
```

That regenerates `deploy-github/`, which is what gets pushed here.

## What ships

| File | Purpose |
|---|---|
| `index.html` | The report — Site Map, Rankings and Updates tabs |
| `a2p-redline.html` | Text-messaging compliance review page, for client approval |
| `404.html` | Styled not-found page |
| `.nojekyll` | Stops Jekyll processing |

## What deliberately does not ship

- **The internal Log tab.** Stripped by the build. It carries internal candour and open
  decisions that are not client-facing. The build fails rather than publish if the strip misses.
- **`_headers`.** GitHub Pages cannot serve custom response headers, so the file would be
  silently inert. The `noindex` therefore rests on the meta tag alone here — a real reduction
  versus the Netlify target, accepted deliberately on 2026-09-01.
- **`robots.txt`.** A `Disallow` would stop crawlers reading the `noindex`, which is the
  opposite of the intent. Crawling is allowed; indexing is refused.

## Privacy

This repo is **public**. Anyone with the URL can read the report and browse its history.
The internal Log tab never ships, but treat everything here as publishable.

## Note for the build

`README.md`, `CNAME` and `.git` are preserved across rebuilds (see `PRESERVE` in
`build_static.py`). Everything else in this folder is wiped and regenerated each time.

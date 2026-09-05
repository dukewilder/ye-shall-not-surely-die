# ye-shall-not-surely-die

The landing page for *Ye Shall Not Surely Die: A Defence of the Accused* by
L. Calaris. One static page, no build step, no dependencies, no analytics.

## Files

| file | what it is |
|---|---|
| `index.html` | the whole site. The cover figure is embedded as a data URI, so this file works on its own if you open it locally |
| `og.png` | the social card, 1200 × 630. Must stay a real file at a real URL — a data URI cannot be an `og:image` |
| `404.html` | served by GitHub Pages for any unknown path |
| `CNAME` | the custom domain. **Edit this to whatever you register** |
| `.nojekyll` | stops GitHub running Jekyll over the repo. Empty on purpose |
| `robots.txt`, `sitemap.xml` | crawling. Both hard-code the domain — update if `CNAME` changes |
| `favicon.ico` | 16, 32 and 48px in one file, for the address bar and bookmarks |
| `favicon-16x16.png`, `-32x32`, `-48x48` | modern browsers prefer these to the .ico |
| `apple-touch-icon.png` | 180 × 180, iOS home screen. No transparency and no rounding: iOS applies its own mask |
| `icon-192.png`, `icon-512.png` | Android and PWA installs |
| `icon-maskable-512.png` | the same mark inset so it survives a circular crop |
| `safari-pinned-tab.svg` | Safari's pinned-tab mark, single colour, vector |
| `site.webmanifest` | names, colours and the icon list |
| `LICENSE` | CC0 1.0 |

## Deploying on GitHub Pages

1. Create a public repository and push these files to the root of `main`.
2. **Settings → Pages → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. **Settings → Pages → Custom domain**: enter your domain. GitHub reads `CNAME`
   but setting it here triggers the certificate.
4. At your registrar, point the domain at GitHub:
   - four `A` records for the apex — `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - one `CNAME` for `www` → `<your-username>.github.io`
5. Wait for the certificate, then tick **Enforce HTTPS**.

DNS takes anywhere from minutes to a day. The site works at
`<username>.github.io/<repo>` in the meantime.

## If the domain changes

Three files hard-code it: `CNAME`, `robots.txt`, `sitemap.xml`, plus the
`canonical` and Open Graph URLs near the top of `index.html`. A find-and-replace
on `ye-shall-not-surely-die.com` catches all of them.

## The links

Each button goes straight to its own edition:

| edition | ASIN | price |
|---|---|---|
| Paperback | `B0HHXWXS8B` | $8.99 |
| Hardcover | `B0HHXSPRFR` | $15.99 |
| Kindle | `B0HHXRJ9RS` | $0.99 |

The free edition points at `archive.org/details/ye-shall-not-surely-die`.

## The icons

All of them are generated from one geometric obelus rather than set in EB
Garamond, because the type's hairlines disappear below about 24px. At 16 and
32px the rectangles are snapped to whole pixels, so the mark stays crisp instead
of blurring to grey.

## Rebuilding the social card

`og.png` was generated rather than drawn. If the cover art changes, regenerate it
rather than editing by hand — it fits the type to the space automatically.

## Licence

CC0 1.0. No rights reserved.

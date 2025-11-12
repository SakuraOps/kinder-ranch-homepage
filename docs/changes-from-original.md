# Changes from the scraped source

Comparison target: `original-scrape/www.kinder-ranch.com` → working copy in `site/`.

## What changed
- Ran Prettier across all HTML entry points (`index.html`, `info.html`, `kontakt.html`, `impressum.html`, `ueber-mich.html`), which expanded everything onto readable lines, normalized indentation/attribute wrapping, and standardized void-tag endings.
- Ran Prettier on the bundled script at `assets/js/main.min.js` to normalize whitespace and quoting.

## What did *not* change
- No copy, markup structure, assets, or URLs were edited beyond the formatting pass; the files remain content-identical to the scrape aside from whitespace/line-break differences.
- No additional dependencies or build steps were introduced—`site/` is still a plain static export.

You can confirm by running `diff -qr original-scrape/www.kinder-ranch.com site`, which shows only the Prettier-touched files as differing.

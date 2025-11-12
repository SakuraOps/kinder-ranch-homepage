# Kinder-Ranch Homepage

A repository for Kinder-Ranch homepage by Stella.

## Repository layout

- `site/` – Prettier-formatted version of the static site that is ready for hosting. Entry points such as `index.html`, `info.html`, `kontakt.html`, etc. reference shared assets under `site/assets/` and images in `site/uploads/`.
- `original-scrape/` – Raw scrape of the production site (`www.kinder-ranch.com`) kept for reference/diffing. Use this to verify that content parity is preserved.
- `docs/` – Project documentation and migration notes (see below).

## Documentation

- `docs/changes-from-original.md` – Summary of differences between the scraped source and the cleaned `site/` export (currently just the Prettier formatting pass).
- `docs/wordpress-migration-plan.md` – Step-by-step manual for rebuilding the static site inside WordPress, covering hosting prep, page recreation, styling, SEO, launch, and maintenance tasks.

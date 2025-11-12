# WordPress Migration Plan

Target: migrate the static site in `site/` into a maintainable WordPress install (self-hosted or wordpress.com Business). Follow the steps in order and check off as you go.

## 1. Prep work
- **Choose hosting**: pick a WordPress-ready host (e.g., SiteGround, Raidboxes, WordPress.com Business, or any LEMP/LAMP box) that includes HTTPS and daily backups.
- **Set up a staging domain**: something like `staging.kinder-ranch.com` or a temporary host-provided URL so you can test before switching DNS.
- **Collect assets**: copy the entire `site/` folder locally; keep `assets/`, `uploads/`, and the HTML files handy to reference text and imagery during migration.

## 2. Install WordPress
- Use the host’s installer or run the famous 5-minute install on the staging domain.
- Create an administrator account and enable HTTPS immediately.
- Install a child theme or starter theme (e.g., GeneratePress, Astra) that gives you layout flexibility similar to the current site.

## 3. Configure global settings
- Settings → General: set Site Title, Tagline, preferred language (`Deutsch`), timezone (`Europe/Berlin`), and date/time formats.
- Settings → Reading: set homepage to “A static page” (create placeholder Home + Info pages now if prompted).
- Settings → Permalinks: choose “Post name”.
- Install essential plugins: a block-based page builder if needed (Gutenberg blocks may suffice), an SEO plugin (Yoast/RankMath), a form plugin (WPForms, Gravity Forms) if replacing the embedded Google Form, and a cookie consent plugin.

## 4. Build page structure
Create pages mirroring the static site:
1. **Startseite** (`/`)
2. **Info** (`/info`)
3. **Über mich** (`/ueber-mich`)
4. **Kontakt** (`/kontakt`)
5. **Impressum** (`/impressum`)
6. Optional extra pages or blog disabled.

Use the block editor (or chosen builder) to reproduce each layout:
- Copy text from the corresponding HTML file in `site/`.
- Upload images from `site/assets` or `site/uploads` into the WordPress Media Library, renaming descriptively.
- Recreate sliders/testimonials: either use a slider block/plugin or convert to stacked sections if you want simpler maintenance.
- Replace the embedded Google Form iframe on the contact page or configure the WordPress form plugin endpoint (update privacy text accordingly).

## 5. Theme styling
- Configure global fonts to Lora + Noto Sans via the customizer or a typography plugin; enqueue Google Fonts through the theme if necessary.
- Match color palette and spacing by inspecting `assets/css/style.css`. Use global styles/custom CSS to replicate key rules (header background, buttons, cards, etc.).
- Add favicon/site icon under Appearance → Customize → Site Identity.

## 6. Navigation & footer
- Menus: create “Hauptmenü” with the five main pages in the same order; assign to the header location.
- Footer: add copyright text, contact data, and any legal links; install a widget or block for the fence/visual separator if desired.
- Implement cookie consent via the plugin and ensure the banner text matches the prior implementation.

## 7. SEO & metadata
- With the SEO plugin, set default title/description templates and override per page to match the originals (copy from each HTML head).
- Add structured data: corporation info and business location via the plugin’s schema tools (no need to hand-code JSON-LD).
- Upload `robots.txt` and `humans.txt` equivalents using the SEO plugin or the host’s file manager if required.

## 8. Testing on staging
- Validate each page on desktop and mobile.
- Test navigation, slider behavior, and the contact form submission path.
- Run performance and accessibility checks (Lighthouse/Pagespeed). Optimize any large images before go-live.
- Confirm cookie banner, legal text, and privacy statements appear as required by German law (DSGVO).

## 9. Launch
- Backup the staging site.
- Point DNS `A`/`AAAA`/`CNAME` records from `kinder-ranch.com` to the new host. Keep TTL low beforehand for faster propagation.
- Once live, re-run SSL verification and force HTTPS.
- Submit updated sitemaps via the SEO plugin to Google Search Console and Bing Webmaster Tools.

## 10. Post-launch maintenance
- Enable automatic backups and updates (core, plugins, themes).
- Document how to edit each page using Gutenberg/your builder for the business owner.
- Schedule periodic content reviews and ensure the contact form emails reach the inbox (configure SMTP plugin like WP Mail SMTP if necessary).

Following the checklist above will migrate the static `site/` export into a functional WordPress presence with minimal surprises. Keep the old static site archived until the WordPress version is fully validated.

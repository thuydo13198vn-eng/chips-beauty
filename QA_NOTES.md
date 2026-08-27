# QA notes

- Local HTTP response for `/` returned 200 and served `index.html` (13,846 bytes).
- Local response for `assets/instagram-qr.jpg` returned 200 and served the asset.
- Browser rendered the landing page title `Chips Beauty | Beauty appointments for travelers` and displayed English-first hero, services, trust section, QR contact cards, FAQ and CTA links.
- The visible CTA `Check availability` opened `https://www.instagram.com/DO13198/` and Instagram redirected to its login wall. This confirms the website link target is correct; the profile content itself cannot be verified from the unauthenticated browser.
- No Google Business Profile/Maps work was performed in this task.

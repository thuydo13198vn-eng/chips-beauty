# QA notes

- Local HTTP response for `/` returned 200 and served `index.html` (13,846 bytes).
- Local response for `assets/instagram-qr.jpg` returned 200 and served the asset.
- Browser rendered the landing page title `Chips Beauty | Beauty appointments for travelers` and displayed English-first hero, services, trust section, QR contact cards, FAQ and CTA links.
- The visible CTA `Check availability` opened `https://www.instagram.com/DO13198/` and Instagram redirected to its login wall. This confirms the website link target is correct; the profile content itself cannot be verified from the unauthenticated browser.
- No Google Business Profile/Maps work was performed in this task.

- GitHub repository is public, branch `main` contains the full static site, but Pages API returned 403 `Resource not accessible by integration`; GitHub web settings remained logged out in the sandbox browser.
- Netlify Drop official page confirms public links are created by dropping a folder, ZIP or HTML file; free plan is available and custom domains are optional. This is the selected fallback because it does not require payment and can deploy the already-built static folder.

- Netlify Drop first rejected the ZIP path outside its allowed upload directory; the ZIP was copied into `/home/ubuntu/upload`.
- A second automated file-upload attempt could not locate the dynamic file-input element. The Netlify page is otherwise loaded and advertises free public links, but no deployment URL has been created yet.

- Netlify Drop exposes a dynamic file input in the page console, but the browser upload bridge could not locate it twice; no Netlify deployment URL was created.

- raw.githack required a one-click external-content confirmation, then rendered the Chips Beauty HTML. The public HTML and CTA text loaded, but the hero image did not display in the rendered page, so this is not accepted as the final hosting URL without further verification.

- Netlify Drop upload succeeded after making the dynamic file input visible; the page progressed through project upload, secure HTTPS certificate provisioning and global edge distribution.
- The deployment URL has not yet been displayed; continue waiting before reporting completion.

- Netlify Drop successfully created the temporary public URL: `https://deft-pasca-998987.netlify.app`.
- Netlify states the unclaimed site remains live for about one hour and then expires; the Claim flow opens Netlify sign-up/login. A persistent free deployment therefore requires an authenticated Netlify account.

- GitHub Pages workflow run `33095148009` uploaded the site artifact successfully, then failed at `actions/deploy-pages@v4` with HTTP 404: `Ensure GitHub Pages has been enabled`. This confirms the remaining GitHub step is a repository setting, not a website or workflow error.
- Netlify Drop produced `https://deft-pasca-998987.netlify.app`, but the site is temporary until claimed. Claim opens Netlify sign-up/login, which requires the user's authenticated browser session.

## Latest continuation check

- GitHub Pages API still returns 404 because Pages is not enabled; the GitHub Actions workflow uploads the artifact but fails creating the Pages deployment.
- The unclaimed Netlify URL now returns HTTP 401/password protection and is not accepted as a public production URL.
- The raw.githack fallback renders the HTML at `https://raw.githack.com/thuydo13198vn-eng/chips-beauty/main/index.html`; console verification confirmed all four image assets loaded with non-zero natural dimensions and all booking links point to `https://www.instagram.com/DO13198/`.
- A persistent, password-free Netlify deployment still requires claiming the site through Netlify sign-up/login.

## Existing Canva asset check

The existing Canva site `https://chipsbeauty.my.canva.site/` returns HTTP 200, but its browser page is JavaScript-rendered and visually blank in the sandbox. Source inspection found a verified public WhatsApp link `https://wa.me/84768402461` and embedded labels for Zalo, KakaoTalk and WeChat; their actual external URLs were not exposed, so no guessed links were added. The Canva site is kept as an existing fallback asset, not replaced or deleted.

## Stable public fallback check

HTML Preview renders the committed landing page without the raw.githack confirmation screen at `https://htmlpreview.github.io/?https://github.com/thuydo13198vn-eng/chips-beauty/blob/53bdb08/index.html`. Browser console verification found the correct page title, all four image assets loaded with non-zero dimensions, all Instagram booking CTAs point to `https://www.instagram.com/DO13198/`, and no internal anchors are broken. The service is a free GitHub-backed preview rather than a first-party custom hosting account, but it remains public as long as the repository and commit remain available.

## Mobile QA

Chromium headless at 390×844 with a 10-second virtual-time budget rendered the HTML Preview page cleanly. The responsive navigation collapsed correctly, the English hero copy fit the viewport, the primary Instagram booking CTA remained visible, and the contact-card image loaded. The first blank screenshot was a timing artifact; the waited render is the accepted mobile check.

## Final public check

The branch-main HTML Preview URL rendered the updated landing page with the WhatsApp CTA. Browser verification found six Instagram CTAs, four WhatsApp CTAs, four loaded image assets, no broken internal anchors, and a valid page title/description. Chromium mobile QA at 390×844 rendered the hero, English copy, Instagram booking CTA, WhatsApp CTA and contact-card image without overflow. The preview wrapper does not expose the JSON-LD script to the rendered DOM, so structured data is retained in the source but should become effective only on a first-party host such as GitHub Pages or claimed Netlify.

## Profile and listing audit

A public Facebook profile was found and verified as the existing business asset: **Chip’s Beauty House - Nail & Eyelash & Shampoo**, 4.2K followers, 1 following, category Beauty/cosmetic/personal care, address **68 Chính Hữu, Sơn Trà, Da Nang, Vietnam**, phone `+84 76 840 2461`, and 100% recommend from 8 reviews. This matches the Canva address and WhatsApp number, so it should be optimized/claimed rather than duplicated.

Tripadvisor search for `Chips Beauty Da Nang` did not show an exact Chips Beauty listing; results were other Da Nang spas/beauty businesses. No Tripadvisor listing should be created or claimed until the existing business owner confirms ownership through Tripadvisor.

## Additional channel research

Fresha’s official business page explicitly lists nails, spa/sauna and massage business types, says businesses can list on its beauty/wellness marketplace, reach clients and accept self-booking online 24/7. It is a strong candidate after the offer has confirmed price, duration and availability; marketplace new-client fees apply according to Fresha’s pricing/help pages.

Traveloka AXES is the official activity-partner route and Traveloka already carries Da Nang spa/beauty experiences in search results. The AXES page did not render in the browser sandbox, so no unverified partner terms were added. Klook remains a secondary marketplace candidate after offer data is complete.

## Verified offer and channel sync

The Canva source confirmed the real offer categories **Nails, Lashes, Relaxation, Shampoo**, the exact address **68 Chính Hữu, Đà Nẵng**, the WhatsApp link/number, and the source text for eyelash extensions and massage therapy. No public price or opening hours were found, so the landing page explicitly asks guests to confirm current price and available time rather than publishing invented values.

The public Facebook profile `https://www.facebook.com/p/Chips-Beauty-House-Nail-Eyelash-Shampoo-61581697785415/` was verified as the existing profile with matching address/phone, 4.2K followers and 8 recommendations. The website now links to this existing profile for trust. Tripadvisor search did not reveal an exact Chips Beauty listing, so no duplicate listing was created. Fresha was identified as the next best low-cost booking marketplace candidate after missing commercial fields are confirmed.

Final mobile QA at 390×844 after the offer sync rendered the English Da Nang copy, Check availability CTA, WhatsApp CTA and hero image without overflow.

## Continuous execution audit

The existing Facebook About view again confirmed the matching business name, 68 Chính Hữu, Sơn Trà, Da Nang, phone +84 76 840 2461, 100% recommend from 8 reviews, and no public opening hours. The public landing page on branch main again rendered the verified Da Nang offer, English copy, Instagram/WhatsApp/Facebook CTA and QR assets. No new commercial fields were discovered; no profile duplication or fabricated pricing was introduced.

## Revenue-focused content asset

Created `/home/ubuntu/chips_beauty_english_content_pack.md` with six non-spam English posts mapped to discovery, trust, conversion, traveler FAQ, location and service choice. Each post requires a real photo/video and avoids unverified pricing, opening hours, awards or guarantees.

The content pack is ready for reuse across Instagram, the existing Facebook profile and TikTok. Direct posting remains blocked only by owner-authenticated social sessions.

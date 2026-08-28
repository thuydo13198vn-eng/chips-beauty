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

## Latest public verification

The public HTML Preview page after commit `7abbf56` rendered successfully. Browser-side checks confirmed the English document, verified Da Nang address, the long-tail keywords `nail salon Da Nang`, `eyelash extensions Da Nang`, `beauty salon Son Tra`, and `English-speaking beauty salon Da Nang`, canonical URL, BeautySalon JSON-LD, 6 Instagram CTAs, 4 WhatsApp CTAs, 1 Facebook CTA, and 4/4 images loaded with natural dimensions. No new error was detected.

## Final public live-entrypoint QA

A stable `live.html` entrypoint was added because the HTML Preview layer intermittently cached `index.html` and delayed the remote hero image on mobile. The public URL `https://htmlpreview.github.io/?https://github.com/thuydo13198vn-eng/chips-beauty/blob/main/live.html` returned HTTP 200 and rendered the current premium page. Two headless renders at 390×844 and 1440×1000 completed; the inline hero card image was visible in the browser and the final mobile screenshot. DOM checks passed: correct title and English language, description, H1, sections `top/services/visit/faq`, 6 Instagram CTAs, 4 WhatsApp CTAs, 2 phone CTAs, 1 Facebook CTA, 7 images loaded with ALT text, no broken internal anchors and no horizontal overflow. The raw source on remote main is commit `b779e3f9dc07fc3d04b64263d0e57e89d53aef2a`; local branch is clean and synchronized.

## WhatsApp attribution update

The four WhatsApp CTAs now prefill a transparent message saying the guest found Chips Beauty via the website. This improves source attribution without tracking cookies or collecting sensitive data. Validator remains `ok`, and the updated wa.me URL redirects to the WhatsApp send endpoint with HTTP 200.

## New-channel safety audit

ServiceHub (`https://vnservicehub.com/`) was evaluated as a possible Vietnam English-language marketplace. Its homepage presents salons/spas, English booking, free business listing and booking claims, but these are first-party marketing claims and were not treated as verified demand. The official Terms URL (`https://vnservicehub.com/terms`) returned 404. Because a legal/terms page could not be verified, ServiceHub is **not recommended for Chips Beauty at this time** and no account, listing or business data was submitted.

## Phone fallback CTA

Added a verified `tel:+84768402461` call link under the WhatsApp card. This provides a direct booking fallback for travelers whose browser or messaging app cannot open WhatsApp. The HTML validator passed and the public page returned HTTP 200 after the update.

## Final mobile verification

The latest public page was rendered at 390×844 after the phone CTA update. The hero, English traveler message, Da Nang context, Instagram booking CTA, WhatsApp CTA and service image remain readable and within the viewport. No mobile overflow or visual regression was observed.

## Fresh traveler-intent benchmark

A current Reddit `r/DaNang` thread shows a traveler coming to Da Nang with family, staying in Hai Chau, actively asking for nail-art recommendations. The useful decision factors in the replies were proximity/area, English-speaking staff, cleanliness, detailed nail-art capability, speed and price. This supports content that targets traveler intent and hotel-area guidance, but does not justify copying competitor claims or posting unsolicited promotions.

The Vinpearl result indicated that English travel content about Da Nang nail salons includes price ranges and booking guidance, but the page did not render reliably in the browser sandbox. No unverified competitor price was added to Chips Beauty.

## Canva website audit

The current Canva site `https://chipsbeauty.my.canva.site/` returned HTTP 200 and exposed the real service categories **Nails, Lashes, Relaxation, Shampoo**, a `BOOK NOW` CTA and contact links labeled WhatsApp, Zalo, Call, KakaoTalk and WeChat. The page title is a generic Canva wedding-event template title, which is a branding/SEO weakness. The browser screenshot did not render reliably in the sandbox, so no visual claim was made from an unavailable screenshot; the current GitHub landing page remains the auditable source for redesign work.

## Premium visual benchmark

Image search references for premium nail/beauty websites consistently emphasized editorial typography, high-contrast hero imagery, generous whitespace, service-led navigation and a direct booking CTA. These references are design inspiration only; no third-party image was copied into Chips Beauty. The redesign should use the existing real Chips Beauty images/QR assets, with generated or stock imagery only clearly labeled as illustrative if ever needed.

## Photo rights/asset audit

The public Facebook Photos page exposed brand/service imagery, including a Chips Beauty contact-card image and service-related thumbnails. Individual photo URLs redirected to Facebook login in the sandbox, so the images were not downloaded or embedded without a reliable owner/rights path. The redesign will use only the four supplied local QR/contact assets unless a clearly authorized business photo is available; no third-party or customer photo will be represented as Chips Beauty imagery.

## Downloaded photo quality check

Two accessible Facebook thumbnails were checked locally. One is a 206×206 before/after foot-care graphic with text; the other is a 206×206 salon scene with a timestamp overlay. Both appear to be business-related but are too small/compressed for a premium hero or full gallery. They were not embedded in the redesign to avoid degraded visual quality; the supplied Chips Beauty card remains the primary hero asset.

## Premium redesign QA

The premium redesign was published on branch `main` and opened in the public HTML Preview. The browser render showed the new editorial hero, dark plum announcement bar, blue accent, premium card treatment, service ribbon and booking CTAs. Browser-side checks confirmed title `Chips Beauty — Da Nang beauty appointments for travelers`, `lang=en`, canonical URL, `services/visit/faq` sections, English/Da Nang/address/service text, 6 Instagram CTAs, 4 WhatsApp CTAs, 2 phone CTAs, 1 Facebook CTA and 7/7 images loaded with natural dimensions.

## Public URL regression QA

The latest public URL returned HTTP 200 with measured transfer time 0.038s and 1,269 bytes for the HTML preview response; all four raw GitHub image assets returned HTTP 200. Desktop screenshot at 1440×1000 and mobile screenshot at 390×844 were reviewed. The premium hero, announcement bar, navigation, typography, CTA buttons, local Da Nang context and card visual rendered without visible overflow or layout breakage. The validator passed with title, 6 Instagram CTAs, 4 WhatsApp CTAs, 1 Facebook link and 4 assets.

## Public QA fix pass

The public DOM showed that the HTML Preview wrapper did not preserve the source JSON-LD script in the rendered DOM, although the source HTML contains it. To make the fallback page more resilient, the source now also exposes lightweight Schema.org microdata on the body (`BeautySalon`, name, telephone, URL, address and service types). A preconnect to raw GitHub was added, the hero image keeps async decoding, and six below-the-fold QR images use lazy loading with async decoding. A final headless screenshot also caught an intermittent blank hero card while the interactive browser render showed the card correctly; the hero image was first changed to eager/high-priority synchronous decoding, then embedded as a data URI because the HTML Preview wrapper still intermittently delayed the remote hero asset on mobile first paint. Two local Chromium renders at both 390×844 and 1440×1000 now show the hero image consistently. Local semantic checks passed: English document, H1, two phone CTAs, six Instagram CTAs, four WhatsApp CTAs, one Facebook link, seven images with ALT text and six lazy-loaded QR images. Local HTTP returned 200.


## Canva old-site comparison audit

The old Canva website at `https://chipsbeauty.my.canva.site/` returned HTTP 200 and rendered the real offer categories Nails, Lashes, Relaxation and Shampoo, plus the verified address `68 Chính Hữu - Đà Nẵng`, phone `0768 402 461`, email `thuydo13198vn@gmail.com`, WhatsApp and Call links. Its visual language uses a warm pink/plum palette, large rounded image blocks and a clear `BOOK NOW` button. The page exposes 10 loaded images with natural dimensions, including four service/brand media assets and two video poster images.

The old site has useful source material but important weaknesses for the international conversion goal: generic Canva wedding-template title, `lang=vi-VN`, no meta description, mostly Vietnamese/translated copy, empty image ALT attributes, no visible Instagram/Facebook booking link, no actual Zalo/KakaoTalk/WeChat URLs (the links point to internal Canva page anchors), an unverified `Enjoy 10% OFF Today!` promotional claim, and no clear structured booking information. These findings are reference-only; no old-site claims were copied into the new site unless already verified elsewhere.


## Old-asset gallery upgrade

The old Canva site was audited and its public image assets were downloaded for quality review. Four high-resolution service/brand images were selected from the existing Chips Beauty site: salon interior, nail art, eyelash extensions and massage. Poster/video frames with visible text, overlays or weaker quality were not used. The selected images were optimized locally and added as a responsive gallery with descriptive ALT text, plus the salon interior was promoted to the hero visual. The navigation now includes Gallery, and OG/Twitter preview images plus BeautySalon JSON-LD image URLs point to the real service visuals.

Local Chromium QA at 390×844 and 1440×1000 showed the salon image in the hero, clean mobile stacking, a balanced desktop gallery layout, readable captions and no visible overflow. The old Canva source remains unchanged.


## Comparison decision and current upgrade

Comparison outcome: the current redesign is the preferred foundation for international discovery and booking because it has an English-first information architecture, traveler-focused copy, explicit service/location/FAQ sections, stronger CTA routing, descriptive ALT text, canonical/OG/Twitter metadata and structured data. The old Canva site contributes valuable real brand/service imagery and the verified public email, but its generic title, Vietnamese language tag, missing description/ALT/schema, internal placeholder links and unverified promotion make it unsuitable as the primary public experience.

The current version now uses the real salon interior image as the hero, adds a four-image gallery for salon, nails, lashes and massage, adds a Gallery navigation anchor, adds the verified email fallback, and synchronizes the same source to `index.html` and `live.html`. No unverified price, opening hours, review, promotion or social URL was added.

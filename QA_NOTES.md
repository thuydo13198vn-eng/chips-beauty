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

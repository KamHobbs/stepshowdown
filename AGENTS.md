# AGENTS.md — Standing rules for the Step Showdown website

Read this before doing anything. These rules apply to every task in this repository.

## Repository: KamHobbs/stepshowdown

- This is the public GitHub Pages site for `stepshowdown.app`. **The repository is public**: anything committed here can be read by anyone.
- The site is static: plain HTML, CSS and JavaScript. Don't add frameworks, build tools, package managers or generators unless the task asks for them.
- Never delete, rename or change these unless the task explicitly says to:
  - `CNAME` (must stay `stepshowdown.app`)
  - `.nojekyll` (keeps `.well-known` published)
  - `.well-known/apple-app-site-association` and `apple-app-site-association` (universal links)
- `404.html` (the invite fallback) must never interfere with the two `apple-app-site-association` files.

## Approved sources

The approved sources live in the app repository on this Mac:
`/Users/kamhobbs/Documents/GitHub/StepShowdown-App/`

**Read only.** Never create, change, move or delete anything in that folder, never run git commands in it, and never build it. Never copy app code, app files or app assets into this website unless a task names the exact file. All your work happens in this website repository only.

- `docs/StepShowdown-Canonical-Docs-v2-2026-08-01/Docs/` files 01–10. Ignore the `Archive` folder; it holds superseded versions and is never an approved source.
- `docs/StepShowdown-Architecture-Audit-2026-10-24.md`, especially step 15W. Kam's decisions recorded there are binding and override the canonical docs where they say so (for example: Fitbit is on the wearable list; the website uses brand logos; the 15W-1/15W-2 split).
- The website requirements are `04_Website_Spec.md`; exact wording is in `03_Copy_Deck.md`; credits are in `09_Credits_and_Licenses.md`.

Rules:
- Every word, label, colour and visual element must come from an approved source or from the task itself.
- Use approved text word for word. Never write new copy, legal text, claims or design that no source provides.
- If no approved source covers what the task needs, stop and ask in your reply. Kam makes the final decision.

## Brand logos (Kam's decision, 2026-11-04)

Kam decided the website uses wearable and Apple brand logos, overriding the Credits doc's "no third-party logos without separate permission" rule. When a task asks for a logo:
- Use only the brand's own official logo or badge file, from that brand's official press, brand or marketing page. Never redraw, recolour, stretch, crop or combine a logo, and never use a copy from a third-party site.
- Follow that brand's published usage rules (colours, clear space, minimum size, backgrounds, required wording such as a "Works with" badge's exact text).
- Record each logo's source URL, the guideline URL and the download date in `ASSETS.md` in this repository.
- Accompanying text must still be accurate: devices work by syncing steps to Apple Health. Don't use words like "partner", "official" or "endorsed by".
- Don't add disclaimers or "no affiliation" notices. The only exception is a trademark line a brand's own rules require; if one is required, report it and Kam decides where it goes.
- If a brand's rules forbid a use, or you can't find official files or rules, stop and report it. Don't substitute.

## Privacy and tracking

- No analytics, tracking pixels, fingerprinting, cookie banners, ad scripts or third-party embeds unless the task names the exact service.
- Never commit private information: private email addresses, receipts, license proofs, tester details, API keys, tokens or passwords.
- The only public contact address is `support@stepshowdown.app`.

## Quality (Website Spec §14)

Keyboard navigation, semantic headings and landmarks, visible focus states, useful alt text, readable contrast, `prefers-reduced-motion` respected for decorative effects, no autoplaying audio, works with browser zoom and on narrow screens, no essential text only inside images, light page weight.

## App Store link

There is exactly one place in the site that holds the App Store URL (`https://apps.apple.com/app/id6830061273`). Every button reads it from there. Never copy the URL into multiple files.

## Branching

- Work in a local clone. Create a new branch from the latest `main`, named exactly as the task specifies (`web-NN-short-name`).
- Commit only to that branch and push the branch to GitHub, so Claude can review it. Never commit to `main`. Never merge: Kam merges in GitHub Desktop, and merging into `main` publishes the live site.

## Verify before you reply

- Serve the site locally (for example `python3 -m http.server`) and load every page you touched, plus the invite paths `/invite/friend/<sample>` and `/invite/challenge/<sample>` through the 404 page.
- Check that both `apple-app-site-association` files are valid JSON and unchanged unless the task changed them.
- Check every link you added.
- Some behaviour only exists on GitHub Pages (custom 404 for unknown paths, the content type served for `apple-app-site-association`, HTTPS). Mark those checks **NEEDS LIVE CHECK**; never mark them PASS from a local server.
- Never say something works unless you checked it. Otherwise write "not verified."

## Your reply MUST include, in this order

1. Branch name and final commit hash, and confirmation that the branch is pushed.
2. Files changed, each with one line explaining why.
3. The exact commands you ran and the relevant output.
4. Each acceptance check marked PASS, FAIL, NEEDS DEVICE or NEEDS LIVE CHECK, with evidence.
5. Anything you skipped, assumed or are unsure about.

Your work will be reviewed by Claude, which can read this repository but cannot open the live site from a browser or test on a device.

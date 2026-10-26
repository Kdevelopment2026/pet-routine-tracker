# SEO changes (branch `seo-update`)

Goal: help the site show up in Google for searches such as "pet care app",
"pet feeding reminder app", "dog and cat feeding reminders" and
"pet routine tracker", without changing the design or the voice.

## What changed

### index.html
- Title: `Pet Routine Tracker: Pet Care & Feeding Reminders for iPhone` (60 characters).
- Meta description (148 characters): "Free iPhone app for everyday pet care:
  feeding, walks, litter, grooming and reminders for every pet. No account,
  no ads, and it works fully offline."
- Open Graph: site name, locale, title, description, URL, and `og:image`
  (`assets/og-image.png`, 1200x630) with width, height and alt text.
- Twitter card (`summary_large_image`) with the same title, description and image.
- Kept the canonical URL and the `apple-itunes-app` smart banner.
- JSON-LD:
  - `MobileApplication`: operatingSystem iOS, applicationCategory
    LifestyleApplication, offer price 0 GBP, App Store download URL,
    publisher KF Media. No rating or review data.
  - `WebSite`: site name, which helps Google show "Pet Routine Tracker" as
    the site name in results.
  - `FAQPage`: the same six questions and answers as the visible FAQ.
- Visible copy:
  - An App Store button under the hero (the existing button at the bottom stays).
  - H2s: "A calm pet care app for the whole household", "Dog and cat
    feeding reminders, on your schedule", "Your data stays on your iPhone"
    (unchanged) and "Common questions about Pet Routine Tracker".
  - Short factual paragraphs on unlimited pets and avatars, the built-in
    routine types and custom routines, skipping with a note, editing later,
    History filters, and iOS 15+ and accessibility support.
  - Six FAQ cards, in the same card style as the support page:
    free feeding tracker, offline, several pets, medicine reminders (as a
    custom routine; no medical advice), sharing between family phones (not
    yet; one iPhone only), privacy.
  - Footer navigation: Home, Support, Privacy, App Store.

### support.html
- Title `Support & Help | Pet Routine Tracker for iPhone` and a more
  specific description.
- Open Graph image, site name, locale, and a Twitter card. Canonical and
  smart banner kept.
- Footer navigation: Home, Support (current page), Privacy, App Store.
  Body copy unchanged.

### privacy.html
- Title `Privacy Policy | Pet Routine Tracker for iPhone` and a more
  specific meta description. Still indexable (no `noindex`).
- Open Graph image, site name, locale, and a Twitter card. Canonical and
  smart banner kept.
- Footer navigation: Home, Support, Privacy (current page), App Store.
- The policy text and the "Last updated" date are unchanged.

### style.css
- One small rule (`.links.hero`) to space the new hero App Store button.

### New files
- `assets/og-image.png`: 1200x630 RGB share image: the headline and paw
  mark beside the App Store Today screenshot.
- `sitemap.xml`: the three pages.
- `robots.txt`: allows everything and points to the sitemap. Crawlers only
  read robots.txt at the domain root (`https://kdevelopment2026.github.io/robots.txt`),
  so this file is for reference only on a project site. It becomes active
  if the site ever moves to its own domain.

## Next steps for you

1. **Review and merge.** Check the branch locally (`open index.html`), then
   `git checkout main && git merge seo-update && git push`. GitHub Pages
   redeploys within a minute or two. Copy the same files into
   `Pet Routine Tracker/docs/` if you keep that copy in sync.
2. **Check the live page.** Paste the home page URL into
   - Google Rich Results Test: https://search.google.com/test/rich-results
   - Schema validator: https://validator.schema.org/
   - A share preview tool (for example https://www.opengraph.xyz/) to see the OG image.
3. **Google Search Console** (https://search.google.com/search-console):
   - Add a **URL-prefix** property for `https://kdevelopment2026.github.io/pet-routine-tracker/`.
     A Domain property isn't possible because you don't own `github.io`.
   - Verify it with the **HTML tag** method: add the
     `<meta name="google-site-verification" ...>` tag Google gives you to
     the `<head>` of index.html and push. (Or upload the HTML verification file to the repo root.)
   - Under Sitemaps, submit `sitemap.xml`. **This step is required**,
     because Google won't find the sitemap through robots.txt on a project site.
   - Use URL Inspection, then "Request indexing", for the home page.
4. **Bing Webmaster Tools** (https://www.bing.com/webmasters): sign in,
   choose "Import from Google Search Console" (fastest), or add the site
   and verify with Bing's meta tag. Then submit the same sitemap. Bing
   also feeds DuckDuckGo and Yahoo.
5. **Links help most.** Link to the site from the App Store listing (the
   Marketing URL and Support URL fields), and from any social profiles or
   posts. A new site on `github.io` with no links can take weeks to rank.

## Notes
- Google currently shows FAQ rich results only for well-known government
  and health sites, so the FAQ won't appear as an expandable snippet. It
  is still useful: the questions match real searches, and the structured
  data stays valid.
- Google shows software-app rich results only when there is rating or
  review data. None was added, on purpose, because nothing may be invented.
  The `MobileApplication` markup still describes the app correctly.

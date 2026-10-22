# 06 Motion, speed and accessibility

Three topics that decide whether a page works for everyone, and whether people wait for it. Think phone first in each. Source format: (Source, page title, date, URL). Where a page shows no date the entry says "read 18 Oct 2026".

## When does motion help?

Rule of thumb: use motion to confirm an action or to show where something went. If it only decorates, leave it out.

Reason: movement is a strong signal to the eye. Used for feedback it answers "did that work?" (a button that presses down, a menu that slides open from where you tapped, an item that flies into a basket). Used for decoration it competes with the words for attention and slows people who want to read.

Evidence: Nielsen Norman Group's guidance treats animation as something that should serve the task, and says animations are more often too long than too short (Nielsen Norman Group, Executing UX Animations: Duration and Motion Characteristics, 9 Feb 2020, https://www.nngroup.com/articles/animation-duration/). That article is guidance from NN/g's practitioners, not a controlled study. No study was found that proves decorative motion lowers conversion, so do not claim it. The argument against it is about attention, load time and the people it harms, which come next.

On a phone: motion costs battery and can stutter on cheap devices. Fewer, smaller movements work best. Never animate the main headline in a way that delays reading it.

Common mistake: text that fades or slides in as you scroll, so that a visitor scrolling quickly sees blank space. Another is a spinning or bouncing element next to the main button.

## How long should an animation last?

Rule of thumb: about 100 milliseconds for small feedback, 200 to 300 for a panel or modal, and never over 500.

Evidence from NN/g (9 Feb 2020, same URL as above): simple feedback such as a toggle or checkbox, around 100 ms. Substantial screen changes such as a modal, 200 to 300 ms. Large movements across a large screen, up to 400 ms, which they describe as very slow, so use it rarely. The general range is 100 to 500 ms, typically 100 to 400. Over 500 ms feels like a drag. Things entering can take slightly longer than things leaving (they give 300 ms to appear and 200 to 250 to disappear). The article gives no separate figure for phones, so any phone number is a guess. Our guess, flagged as one: stay at the short end on a phone, because the screen is small and the distances are short.

Common mistake: a one second fade on a menu. People tap, wait, and tap again.

## Reduced motion

Rule of thumb: every animation you add must switch off or calm down when the visitor has asked for less motion.

Reason: some people get dizzy or sick from scaling, panning and parallax. MDN says scaling or panning large objects can trigger discomfort for people with vestibular motion disorders (MDN, prefers-reduced-motion, modified 10 Jun 2026, https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion). The setting is in the phone or computer itself (on iOS under Settings, Accessibility, Motion; on Android 9 and up, Remove animations). The CSS feature `prefers-reduced-motion` has been widely available in browsers since January 2020 (same page).

How: wrap the movement in a check, or add a rule such as `@media (prefers-reduced-motion: reduce) { ... }` that removes or replaces it. MDN's own example replaces a scaling pulse with a gentle fade, which keeps some feedback. Replace, do not only delete. A short fade is usually fine. Parallax, big zooms and spinning are what to remove.

Common mistake: forgetting it entirely. Test by turning the setting on in your phone and loading the page.

## Autoplay video and carousels

Rule of thumb: do not auto-advance a carousel, and do not autoplay anything with sound. A background video must be muted, short, pausable and not the only way to get the message.

Evidence on carousels, graded honestly. Nielsen Norman Group says people often scroll straight past large carousel images and often miss content in later frames, and that animated ads draw looks only 27% of the time in their eyetracking research. The article gives no sample sizes, click rates or dates for the studies behind this, so it is an expert view backed by unreported data (Nielsen Norman Group, Designing Effective Carousels, published 14 Sep 2013, reviewed 7 Aug 2026, https://www.nngroup.com/articles/designing-effective-carousels/). Their advice: avoid auto-forwarding unless people can read each frame (they suggest about 3 words per second as a timing guide), do not auto-forward on mobile, use five frames or fewer, show where you are, and consider a single static hero image instead. If sources disagree, it is on whether carousels ever work. The same article admits some carousels get fixations and clicks. Our reading: one strong message beats a rotating set, and on a phone it is clearer still.

Evidence on autoplay video: No good controlled study was found showing that autoplay video raises or lowers sign-ups. Say that plainly if asked. What was found is a rule. WCAG 2.2 success criterion 2.2.2 (Level A) says moving, blinking or scrolling content that starts automatically, lasts more than five seconds and sits beside other content needs a way to pause, stop or hide it (W3C WAI, Understanding SC 2.2.2 Pause, Stop, Hide, updated 10 Aug 2026, https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html). A looping background video breaks that rule unless it has a visible pause button.

On a phone: video eats data and slows the page, and phones often block autoplay with sound anyway. A still image for phones, with the video only on wide screens, is a good compromise.

Common mistake: a full-screen background video with the headline over it. It is slow, hard to read, and fails the pause rule.

## Page speed and the three numbers

Rule of thumb: aim for the three Core Web Vitals to pass for real visitors: LCP 2.5 seconds or less, INP 200 ms or less, CLS 0.1 or less.

Evidence: these are Google's published "good" thresholds, measured at the 75th percentile of real page loads, with phones and desktops measured separately. A page passes when it meets all three at that level (web.dev, Web Vitals, last updated 31 Oct 2024, https://web.dev/articles/vitals).

What each means:

LCP, Largest Contentful Paint, is how long until the biggest thing in the first view (usually the main picture or headline) is on screen. Good is 2.5 s or less.

INP, Interaction to Next Paint, is how long the page takes to react after a tap, click or key press. Good is 200 ms or less, needs improvement is up to 500, poor is over 500. It does not count scrolling, hovering or zooming (web.dev, Interaction to Next Paint, updated 2 Sep 2025, https://web.dev/articles/inp).

CLS, Cumulative Layout Shift, is how much the page jumps while loading. Good is 0.1 or less, poor is over 0.25 (web.dev, Cumulative Layout Shift, updated 12 Apr 2023, https://web.dev/articles/cls).

Note the date on the main web.dev page. Thresholds can change, so check the live page before quoting them as current.

Grade: these are the vendor's own targets, not a law, and the link between speed and business results comes from many company case studies that were not reviewed here. Do not quote "every second costs X% of sales" without a source.

On a phone: the thresholds apply to phones too, and phones are where they fail, because the chip is slower and the network worse. Test the phone result first.

## What slows a marketing site

Rule of thumb: the usual causes are big images, too many fonts, too much script, and video. Fix them in that order.

Images. The picture at the top of the page is usually the LCP. web.dev lists what delays it: the image added late by JavaScript or set as a CSS background so the browser finds it late, lazy loading it by mistake, and not giving it priority. It says never to lazy-load the LCP image, and that `fetchpriority="high"` on the likely LCP image can help, but only on one or two (web.dev, Optimize Largest Contentful Paint, updated 31 Mar 2025, https://web.dev/articles/optimize-lcp). Lazy loading belongs on images below the first view only (web.dev, Browser-level image lazy loading, updated 13 Aug 2024, https://web.dev/articles/browser-level-image-lazy-loading). In Next.js, the Image component serves right-sized files in modern formats, reserves space and lazy loads by default (Next.js docs, Image Optimization, last updated 1 Apr 2026, https://nextjs.org/docs/app/getting-started/images). Use it, and tell it to load the top image straight away with `loading="eager"` or `fetchPriority="high"`. The older `priority` setting is deprecated since Next.js 16: the Image reference says "In most cases, you should use `loading="eager"` or `fetchPriority="high"` instead of `preload`" (Next.js docs, Image component, updated 28 Sep 2026, https://nextjs.org/docs/app/api-reference/components/image). Upload sensible sizes: a photo straight off a camera is many megabytes.

Fonts. Each font file is a request, and a late font makes text jump. web.dev says fonts are a cause of layout shift and advises a fallback font, matching metrics, and preloading the important font (web.dev, Optimize Cumulative Layout Shift, updated 7 Feb 2025, https://web.dev/articles/optimize-cls). Next.js's `next/font` self-hosts fonts and loads them with no layout shift (Next.js docs, Font Optimization, last updated 27 May 2026, https://nextjs.org/docs/app/getting-started/fonts). Use one family, two weights at most.

Scripts. The browser can only do one job at a time, and any task over 50 ms is a long task during which it cannot respond to a tap. That hurts INP (web.dev, Optimize long tasks, updated 19 Dec 2024, https://web.dev/articles/optimize-long-tasks). Chat widgets, tag managers, heatmaps, pop-up tools and ad pixels add scripts. No single study was found that ranks them, but the mechanism is documented: more script means more main-thread work. Add one at a time and test. Third-party widgets that resize themselves also shift the layout (web.dev, Cumulative Layout Shift, 12 Apr 2023).

Video. A video file is far larger than an image. Use a poster picture, do not autoplay on phones, and host it somewhere built for it instead of putting a big file in the site folder.

Layout jumps (CLS). Always set width and height on images and video, or reserve space with CSS aspect ratio. Reserve space for any ad or embed. Late content should load lower on the page, as content injected near the top causes larger shifts (web.dev, Optimize Cumulative Layout Shift, 7 Feb 2025).

Common mistake: adding five tracking tools in week one, then wondering why the page is slow.

## How to test speed for free

Rule of thumb: run PageSpeed Insights on the live link, read the phone result first, and fix the biggest item it names.

How: go to pagespeed.web.dev, paste the address, click Analyze. It needs no install. PageSpeed Insights shows two kinds of data. Field data is from real Chrome users over the previous 28 days, at the 75th percentile, and falls back to the whole site if your page has too little traffic, or shows nothing. Lab data comes from Lighthouse, which loads the page in a controlled test, with the phone setting simulating a mid-tier Moto G4 on a mobile network (Google for Developers, About PageSpeed Insights, updated 21 Oct 2024, https://developers.google.com/speed/docs/insights/v5/about).

Lighthouse also runs inside Chrome: open developer tools, find the Lighthouse tab, click Analyze page load, wait 30 to 60 seconds. It scores Performance, Accessibility, Best Practices and SEO (Chrome for Developers, Lighthouse overview, updated 2 Jun 2025, https://developer.chrome.com/docs/lighthouse/overview).

Two cautions. A brand new site has no field data, so you only get the lab result, which is a guide. And a Lighthouse accessibility score of 100 does not mean the page is accessible. Automated tools catch only some problems. No source in this round says what share they catch, so do not quote one.

Common mistake: testing the preview link once, on fast wifi, on a laptop.

## Accessibility basics a marketer must get right

Rule of thumb: five checks cover most of what a marketer controls. Contrast, picture descriptions, headings in order, link words, and keyboard use. Captions come with video.

Standard to aim for: WCAG 2.2 at Level AA. WCAG 2.2 became a W3C Recommendation on 5 Oct 2023, adding nine criteria, and the old 4.1.1 Parsing was removed (W3C WAI, What's New in WCAG 2.2, read 18 Oct 2026, https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/). Levels run A, AA, AAA. A is the base, AA is the usual target (and what laws usually ask for), AAA is stricter and not expected everywhere. New at AA in 2.2: focus not obscured, dragging alternatives, target size minimum 24 pixels, and accessible login.

Contrast. Normal text needs 4.5 to 1 against its background, and large text (18 point, or 14 point bold) needs 3 to 1. Disabled controls, decoration and logos are exempt (W3C WAI, Understanding SC 1.4.3 Contrast (Minimum), updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html). Pale grey text on white and white text on a photo are the usual failures. On a phone in sunlight, low contrast is worse. Check with a contrast checker, and use 4.5 as a floor.

Alt text. Write what the picture adds. W3C's decision tree: decorative or repeated images get an empty `alt=""`; informative images get a brief description of their meaning; an image that is a link or button says where it goes or what it does; an image of text carries that text (W3C WAI, An alt Decision Tree, updated 13 May 2024, https://www.w3.org/WAI/tutorials/images/decision-tree/). "Image of team" is not useful. Do not stuff keywords.

Headings in order. One H1, then H2s for sections, H3s under them. W3C says skipping ranks (an H2 straight to an H4) can confuse and should be avoided where possible (W3C WAI, Headings, updated 4 May 2017, https://www.w3.org/WAI/tutorials/page-structure/headings/). Pick the heading level for structure, then style it with CSS. Screen reader users jump by headings.

Link text. The purpose of each link should be clear from its words, or from the sentence around it. "Click here" and a row of "Read more" links fail the spirit of this. Put any needed context before the link, and use the same words for links to the same place (W3C WAI, Understanding SC 2.4.4 Link Purpose (In Context), updated 18 May 2026, https://www.w3.org/WAI/WCAG22/Understanding/link-purpose-in-context.html). This also helps search and helps anyone skimming.

Keyboard and focus. Everything clickable must work with the Tab and Enter keys, and you must be able to see where you are. WCAG 2.4.7 (AA) requires a visible keyboard focus indicator (W3C WAI, Understanding SC 2.4.7 Focus Visible, updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html). The classic mistake is a style rule that removes the outline and puts nothing in its place. Tab through your page once. Also check that a sticky bar does not hide the focused item (see file 05, and success criterion 2.4.11).

Captions. Prerecorded video with sound needs captions (WCAG 1.2.2, Level A) (W3C WAI, Understanding SC 1.2.2 Captions (Prerecorded), updated 10 Aug 2026, https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html). On a phone, many watch muted, so captions help everyone.

Tap size and motion: see file 05 for target size (24 pixels at AA, 44 at AAA) and above for pause controls.

Common mistake: treating accessibility as a final polish. Contrast, heading order and link text cost nothing if done while writing.

## The European Accessibility Act

Rule of thumb: if you sell products or certain services to consumers in the EU, assume your website or app has to meet accessibility rules, and check with a lawyer on exemptions. Claude cannot give legal advice.

Evidence: the European Accessibility Act is Directive (EU) 2019/882, dated 17 April 2019. Article 31(2) sets the date: "They shall apply those measures from 28 June 2025". Article 32 holds the transitional measures, which run some existing service contracts to 28 June 2030. Its scope includes e-commerce services. Article 4(5) exempts microenterprises that provide services: "Microenterprises providing services shall be exempt from complying with the accessibility requirements referred to in paragraph 3". A microenterprise is defined in Article 3(23) as fewer than 10 people with annual turnover or balance sheet "not exceeding EUR 2 million". Microenterprises that deal in products get lighter duties, not an exemption (recital 71) (Directive (EU) 2019/882, Official Journal, 17 Apr 2019, https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32019L0882). The European Commission's page lists covered areas, among them e-commerce, banking services, e-books, and passenger transport (European Commission, European Accessibility Act, no date shown, read 18 Oct 2026, https://commission.europa.eu/strategy-and-policy/policies/justice-and-fundamental-rights/disability/union-equality-strategy-rights-persons-disabilities-2021-2030/european-accessibility-act_en). It does not itself state the 28 June 2025 date.

Fine amounts quoted by compliance vendors are unverified. Each EU country enforces in its own way, so penalties differ.

What it means for a marketer's own site: a pure information site for a business that does not sell to consumers is mostly outside the Act, though good practice still pays. A shop, booking tool or sign-up with payment, aimed at EU consumers, is in scope unless the microenterprise exemption holds. Building to WCAG 2.2 AA covers the practical ground either way.

Common mistake: assuming "we are a small agency" or "we are outside the EU" settles it.

## What Claude should do with this

When critiquing or building a page, check in this order: does the first image load fast (loaded eagerly, right size)? Are widths and heights set? Is motion short and reduced-motion safe? Contrast 4.5 to 1 on text? Headings in order, links that say where they go, alt text written by the rules, focus visible, captions on video? Then send the owner to PageSpeed Insights on the phone setting. State plainly which claims are guideline and which are measured.

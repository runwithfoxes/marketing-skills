# 05 Mobile

Read this before giving any answer about a page. Whatever the question is, think about the phone first. How a design looks on a 390 pixel wide screen decides whether most visitors stay.

Source format used below: (Source, page title, date, URL). Where a page shows no date the entry says "read 18 Oct 2026".

## How many people are on a phone?

Rule of thumb: assume most visitors are on a phone, and check your own analytics to see how many.

Reason and evidence: StatCounter, which counts page views across a large network of sites, put worldwide traffic in September 2026 at 58.99% mobile, 39.26% desktop and 1.76% tablet (StatCounter Global Stats, Desktop vs Mobile vs Tablet Market Share Worldwide, September 2026, https://gs.statcounter.com/platform-market-share/desktop-mobile-tablet). That is a worldwide, all-sites figure. A Europe or Ireland figure could not be read. Business sites that sell to other businesses often see far more desktop traffic in working hours, so the real split for a given marketer's site can differ a lot. The grade here is a large measured sample, but of the whole web, not of your audience.

On a phone: the phone is the main case for most sites. When Claude critiques a page, it should say what happens on the phone first, and mention desktop second.

Common mistake: designing on a big monitor, then checking the phone at the end. Fixes that late usually mean cutting things the page was built around.

## Which do you design first?

Rule of thumb: design the phone layout first, then widen it.

Reason: a single column forces you to decide what matters. MDN teaches this order. Start with a simple single column layout for narrow screens, then add columns at wider breakpoints when there is room (MDN, Responsive web design, modified 4 Sep 2026, https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design). In code, that means the base styles are the phone styles, and media queries add things for larger screens.

One setting must be in the page head, or none of this works. MDN says to always include the viewport tag, `<meta name="viewport" content="width=device-width" />`. Without it a phone pretends to be about 980 pixels wide and shows a shrunken desktop page (same MDN page). In Next.js the app router adds this for you, but Claude should still check the built page.

Common mistake: setting a layout in fixed pixel widths. Use flexible units and let the grid shrink.

Wireframes: draw the phone wireframe first, as a single narrow column, and then show how the desktop version spreads out. The wireframe file in this pack covers how.

## How does a desktop layout stack into one column?

Rule of thumb: the order on the phone is the order of importance. Whatever you would tell a visitor first, in the order you would say it, goes first.

How to do it, step by step:

1. Write the sections in order of what a stranger needs: what this is, who it is for, the proof, the next step. Do this before you think about columns.
2. Side by side columns become one above the other. By default the left column goes on top. If the right column holds the headline and the left holds a picture, put the headline first. Do not let a picture push the headline off the first screen.
3. A row of three or four feature cards becomes a single stack. Cut cards that say nothing, because a stack of eight cards is eight screens of scrolling. Three to five is plenty. Where a list is long and the items are similar, collapse them (an accordion with the question or title showing).
4. A wide table cannot fit. Turn each row into a small card, or let the table scroll sideways with a visible cue. Better, cut columns to the two or three that matter.
5. Logo walls shrink to two rows, or a single sliding row. Long testimonials get trimmed to the sentence that proves something, with the name below.
6. Large decorative images and background videos are the first things to drop or shrink. A picture that adds nothing on a phone should not be there.
7. Sidebars either drop below the main content or go. Sidebars on a phone mean the thing they hold was not that important.

Evidence grade: this is practice and convention. MDN states the single column starting point, but the order and the cutting rules are design judgement, so say so if asked.

On a phone, check that the first screen still shows the headline, one line of explanation and the main button without scrolling. Whether people scroll or not, they should know what the page is for before they do.

Common mistake: stacking everything on the phone as it was on desktop. The page becomes six times longer and the main button sits at the bottom.

## Where do thumbs reach?

Rule of thumb: put the main action where a thumb can easily reach it, and keep rarely used things out of the corners hardest to reach. Do not treat this as a precise map.

Evidence: the best known observational research is by Steven Hoober, published on 18 Feb 2013. He and a few researchers watched people use phones in public places, such as streets, airports, bus stops, cafes, trains and buses, over two months ending 8 Jan 2013. There were 1,333 observations, of which 780 involved touching the screen. Among those touching: 49% held the phone in one hand, 36% cradled it (one hand holds, the other taps) and 15% used two hands. Cradlers used a thumb 72% of the time and a finger 28%. One handed users used the right thumb 67% of the time and the left 33% (UXmatters, How Do Users Really Hold Mobile Devices?, 18 Feb 2013, https://www.uxmatters.com/mt/archives/2013/02/how-do-users-really-hold-mobile-devices.php).

The limits are real, and Hoober states them. Grip changes, sometimes every few seconds. It was public places only, so people at home on a sofa are missing. No demographics were recorded. Hoober says "I don't consider this the ultimate study", and he did not try to identify devices. This was 2013 and phones have grown a great deal since, so the percentages are not a law, and the study cannot say which part of today's bigger screens is easy to reach. Smashing Magazine's popular thumb zone article repeats the 49% figure and draws easy, medium and hard areas on a map, but it gives no sample size (Smashing Magazine, The Thumb Zone: Designing for Mobile Users, September 2016, https://www.smashingmagazine.com/2016/09/the-thumb-zone-designing-for-mobile-users/). Treat any thumb zone picture as a rough guide.

What the evidence supports: a lot of people use one hand, and a thumb is the main finger, so the top of a tall phone is the hardest part to reach. It does not prove that a bottom bar beats a top bar. If you add a bottom bar, do it because the actions are used often, not because of the diagram.

Common mistake: quoting "75% of people use their thumb" as a Hoober finding. It is not from that study.

## How big must a tap target be?

Rule of thumb: make every button and link you want tapped at least 44 by 44 pixels, and use 48 for the main ones. 24 pixels is the WCAG AA minimum, the level most laws and contracts point to. It is a floor, not a goal.

Evidence, with each source's own unit:

WCAG 2.2, success criterion 2.5.8, Level AA: the target is at least 24 by 24 CSS pixels, with exceptions. Small targets pass if a 24 pixel circle centred on each does not touch another target or another small target's circle. Links inside a sentence are exempt, and so is any control that has an equivalent that is big enough (W3C WAI, Understanding SC 2.5.8 Target Size (Minimum), updated 11 May 2026, https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html).

WCAG 2.2, success criterion 2.5.5, Level AAA: at least 44 by 44 CSS pixels (W3C WAI, Understanding SC 2.5.5 Target Size (Enhanced), updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html).

Apple: controls at least 44 by 44 points (Apple Developer, UI Design Dos and Don'ts, no date shown, copyright 2026, https://developer.apple.com/design/tips/). Apple's full Human Interface Guidelines page could not be read, as it did not load, so this comes from Apple's tips page.

Google's Android accessibility help: at least 48 by 48 dp, about 9 mm on any screen, with a recommended range of 7 to 10 mm (Google Accessibility Help, Touch target size, no date shown, https://support.google.com/accessibility/android/answer/7101858). Material Design's own pages did not load. Google's help page points to them.

On the web, one CSS pixel is close to one point or one dp, so 44 to 48 is the working range. The three numbers do disagree, and the answer is to take the larger when the space allows: 48 for main buttons and menu items, 44 as the least for anything else, and never below 24.

The target can be bigger than what you see. A small icon with padding around it can be a 48 pixel target. In CSS, use padding on the link or button, not a bigger icon.

Common mistake: small text links in footers and tight rows of icons. Another is a tiny close "x" on a banner.

## How much space between targets?

Rule of thumb: leave at least 8 pixels between neighbouring tap targets.

Evidence: Google's Android help says to separate targets by 8 dp or more so touch areas do not overlap (same Google Accessibility Help page). WCAG's spacing exception for small targets gives the WCAG AA minimum (the 24 pixel circle must not touch another target or another small target's circle), which is a different test.

On a phone, a stack of links in a menu or footer needs both height and gaps. If someone taps the wrong one, they are annoyed, then they leave.

Common mistake: three buttons in a row on a narrow screen with 4 pixels between them. Stack them, or give each full width.

## Sticky headers and bottom bars

Rule of thumb: keep any fixed bar thin, and keep the number of fixed things on screen at one or two.

Reason: on a phone the screen is short. A sticky header 64 pixels high plus a cookie banner plus a bottom bar can leave a third of the window for the page. This is judgement, not a measured number, so say so.

Evidence that matters for a marketer: WCAG 2.2 success criterion 2.4.11 (Level AA) says a keyboard focused item must not be entirely hidden by author created content. A sticky header or footer that fully covers a focused item fails. Partly covering is allowed. Using CSS scroll padding, so content scrolls clear of the bar, is one of the fixes (W3C WAI, Understanding SC 2.4.11 Focus Not Obscured (Minimum), updated 15 Jun 2026, https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html). The same goes for a cookie banner.

A sticky call to action bar at the bottom can be right on a long page, as the button is always there. Use it when the page asks for one thing. Do not stack it with another bar.

Common mistake: a header that hides on scroll down and shows on scroll up, which jumps around and adds work for the page. Keep it simple.

## Menus on phones

Rule of thumb: with four or fewer top level links, show them. With more, a hamburger button is a fair trade on a phone, and it is a worse trade on desktop.

Evidence: Nielsen Norman Group tested 179 people on 6 live sites, on desktop and smartphone, two tasks each. Hidden navigation behind a menu button was used less on desktop (27% against 48% for visible and 50% for a mix). On mobile, 57% used hidden navigation and 86% used the mixed kind. Visible only navigation was not tested on mobile. Content was found over 20% less often with hidden navigation. Tasks were 39% slower on desktop with hidden navigation and 15% slower on mobile than with the mixed kind. NN/g's advice: on mobile, four or fewer links should be visible; more than four, hiding some is reasonable (Nielsen Norman Group, Hamburger Menus and Hidden Navigation Hurt UX Metrics, 26 Jun 2016, https://www.nngroup.com/articles/hamburger-menus/). The study is ten years old, but it is a proper comparison with a stated sample. Habits have moved on, so the direction is reliable and the exact percentages are not.

Practical design: put the one or two most important actions (say Contact or Book a call) outside the menu as a visible button, and put the rest inside. Label the menu button with the word Menu as well as the icon. Make it a 48 pixel target. Open the menu as a full-width panel, with big links, and let the visitor close it with a clear button.

Common mistake: hiding the main call to action inside the menu.

## Text size on phones

Rule of thumb: body text at 16 pixels or larger, and form fields at 16 pixels or larger.

Evidence is mixed in quality. Apple's tips page says text should be at least 11 points so it is legible without zooming (Apple Developer, UI Design Dos and Don'ts, no date shown, https://developer.apple.com/design/tips/). That is a floor for fine print, not for reading. For body copy, 16 pixels is the browser default and the usual starting point, but no controlled study was found that fixes one number, so call 16 a convention.

One point for forms: iOS Safari zooms the page in when someone taps a field whose text is under 16 pixels, and does not zoom at 16 or above. It comes from a developer's blog and several other developer write-ups, with no Apple or WebKit statement, so grade it as widely reported by developers, not confirmed by the vendor (Rick Strahl's blog, Preventing iOS Textbox Auto-Zooming and ViewPort Sizing, 17 Apr 2023, https://weblog.west-wind.com/posts/2023/Apr/17/Preventing-iOS-Textbox-Auto-Zooming-and-ViewPort-Sizing). The fix is to set input text to 16 pixels. Some developer write-ups, Strahl's among them, offer `maximum-scale=1` as an iOS stopgap. Don't use it or `user-scalable=no`: blocking zoom takes it away from people who need it, and WCAG requires that text can be resized to 200% (W3C WAI, Understanding SC 1.4.4 Resize Text, https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html).

The type size and line length rules are in file 01. For phones, leave about a 16 pixel gutter at each side and let paragraphs run the full width.

Common mistake: small grey text for captions or prices. If it matters, make it 16 pixels and dark.

## Images on phones

Rule of thumb: send phones a small file, and give every image a reserved space.

Reason and evidence: MDN warns that one large image scaled down for small devices wastes bandwidth, and says to use `srcset` and `sizes` or the `picture` element (MDN, Responsive web design, modified 4 Sep 2026, same URL as above). In Next.js, the Image component does this: it serves correctly sized images for each device in modern formats, prevents layout shift, and lazy loads (Next.js docs, Image Optimization, last updated 1 Apr 2026, https://nextjs.org/docs/app/getting-started/images). Use it for every picture.

Two rules. Do not lazy load the picture at the top of the page: web.dev says lazy loading is only for images outside the first view (web.dev, Browser-level image lazy loading, 13 Aug 2024, https://web.dev/articles/browser-level-image-lazy-loading). And set the width and height so nothing jumps. File 06 has the numbers.

A photo needs crop thinking on a phone. A wide hero with the subject at the right edge may lose the subject on a tall narrow screen. Use `object-fit: cover` with a focal point, or use a different crop for phones. Pictures with words baked in become unreadable when shrunk, so put words in real text.

Common mistake: a large wide banner image as the first thing on a phone, with the headline inside the image.

## Testing on a real phone and in the browser

Rule of thumb: check in browser device mode while you build, and on a real phone before you publish.

Reason: device mode in a desktop browser (the phone icon in the developer tools) resizes the page and fakes touch, which catches layout problems fast. It does not show real speed, real thumbs, glare, or how the on-screen keyboard covers a form. Lighthouse and PageSpeed Insights simulate a mid-tier phone on a mobile network, which is slower than a recent phone on wifi (Google for Developers, About PageSpeed Insights, updated 21 Oct 2024, https://developers.google.com/speed/docs/insights/v5/about).

A short phone check, in this order:

1. Open the live link on your own phone, on mobile data, not wifi.
2. Is the headline and the main button on the first screen?
3. Scroll the whole page with one thumb. Can you tap every button without a miss?
4. Turn the phone sideways once. Does it hold together?
5. Open a form. Does the keyboard hide the field you are typing in? Does the page zoom?
6. Open the menu and close it.
7. Pinch to zoom. If zoom is blocked, the page is wrong.

Borrow a second phone, ideally an older Android, if you can. A cheap phone shows problems a new one hides.

Common mistake: saying a page "works on mobile" because it looked fine when the browser window was narrowed.

## What Claude should do with this

On every layout answer, state what the phone version does in one line. Show the phone wireframe first. Check these five things on any page you critique: viewport tag present, main button visible on the first screen, tap targets 44 pixels or more with 8 pixels between, body text and form fields at 16 pixels or more, and pictures sized for phones.

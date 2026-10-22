# Navigation and page order

How to use this note: each section is a decision. It gives the rule, the reason, the evidence with its source, what changes on a phone, and the usual mistake. Where the evidence is thin the note says so, and where the advice is judgement from the sources rather than a tested finding it is labelled "judgement". Wireframes are plain text so you can show them before building.

Source format: (publisher, page title, date, URL). Saved extracts are in sources/ux/.

## 1. What must the first screen answer?

Rule: in the first screen a stranger should be able to tell three things: who this is for, what it is, and what to do next. Nothing else needs to be there.

Reason: people arrive without your context. NN/g's homepage guidance says to treat the homepage as an elevator pitch: company name and logo top left, a short tagline that states the offering, the value in words the visitor uses (not jargon), and clear next steps with descriptive labels (Nielsen Norman Group, homepage design principles article, 15 Mar 2024, https://www.nngroup.com/articles/homepage-design-principles/). Jakob Nielsen's older list says the same thing more bluntly: open with a one-sentence tagline that says what the company does, and give clear starting points for the one to four main tasks visitors come to do (Nielsen Norman Group, Top Ten Guidelines for Homepage Usability, 11 May 2002, https://www.nngroup.com/articles/top-ten-guidelines-for-homepage-usability/). That is a 2002 expert guideline, not a study with numbers, but it has held up and nobody has found evidence against it.

A practical test (judgement): cover everything except the first screen and ask someone who has never heard of you to say, in their own words, what you sell and to whom. If they cannot, the headline is doing too little.

On a phone: the first screen is smaller, so the headline, one supporting sentence and one button have to carry it. A picture can go under them. If the picture pushes the button off the first screen on a typical phone, move the button up or shrink the picture.

Common mistake: a clever headline that names a feeling instead of the thing ("Make it happen"). The visitor has to work out what you do, and many will not.

Wireframe, first screen (desktop and phone share the same order):

```
[logo]                        [Services] [Work] [About] [Contact]   <- phone: logo + menu button
-------------------------------------------------------------------
  Headline: what you do, for whom, in plain words
  One sentence: the result they get
  [ Primary button: Book a call ]   Secondary link: See our work
  (picture or proof to the side, below on a phone)
-------------------------------------------------------------------
```

## 2. The fold: does it matter?

Rule: put the headline, the one-sentence promise and the main button in the first screen. Do not cram everything there. People do scroll, but they give most of their time to the top.

Evidence: NN/g's eyetracking analysis, 130,000+ eye fixations from 120 participants on 1920 by 1080 screens, found that 57% of viewing time was above the fold (it was 80% in a 2010 study on smaller monitors), 74% fell in the first two screenfuls, and 81% in the first three (Nielsen Norman Group, Scrolling and Attention, 15 Apr 2018, https://www.nngroup.com/articles/scrolling-and-attention/). Read it as: people scroll, but attention falls steeply below the first screen and then spreads thinly. The same article advises putting priority content and the main call to action in the first screen, and using cut-off content as a cue so people know there is more below.

So the popular line "the fold is dead" is half right. The fold is not a wall, and it is also not unimportant. 57% is a lot of attention for one screen. Note the study was on desktop sized screens and mixed page types (news, ecommerce, blogs, FAQs and encyclopedic pages; search results are reported separately), not service homepages, so call it good guidance rather than a law for your page.

On a phone: the fold is closer, so the top of the page matters even more. A trap NN/g calls a false floor is a page that looks finished at the bottom of the first screen, for example a full-width hero with a big gap under it. Let the next section peek in.

Common mistake: a hero that takes a full tall screen with only a headline in it and a button hidden under the bottom edge.

## 3. Page order for a service or product homepage

Rule: order the page the way a sceptical visitor asks questions. What is this, is it for me, can I believe it, how does it work, what does it cost or what happens next, and then a clear way to act.

Judgement, and where it comes from: No tested "best order" for homepages was found. What exists is guidance on what a homepage must contain (the NN/g homepage pieces above), research on what makes people trust a company, and the plain logic that each section answers the next doubt. NN/g's trust study (a small qualitative study run at their Singapore conference, not a large sample) found people want to see real customers and the service in action, find contact details easily. One participant objected that a firm did not state its rate; that is a single remark, not a finding that hiding prices lowers trust (Nielsen Norman Group, Trustworthiness in Web Design, 8 May 2016, https://www.nngroup.com/articles/trustworthy-design/).

Suggested order for a service business:

```
1. Header: logo, 4-6 plain nav items, one button (Contact / Book a call)
2. First screen: what you do, for whom, primary button
3. Proof strip: a few specific results or a named client quote (short)
4. What you do: 3-4 services, each one sentence and a link to its page
5. How it works: 3-4 steps, ending in what happens after they get in touch
6. Proof in depth: one or two short case examples with real numbers
7. Who you are: a face, a name, a sentence of credibility
8. Closing call to action: same button, same words as the top
9. Footer: contact details, legal links, secondary links
```

Product homepage: same bones, but step 4 becomes the product shown working (a real screenshot, not an abstract picture), step 5 becomes pricing or the first steps to start, and the button is "Start" or "Try", whatever really happens.

Landing page (one campaign, one audience): shorter and with a single goal. Headline and promise, the button, three or four reasons or proof points, how it works, one piece of proof, the button again. Take the main navigation off or cut it to a logo, so there is nowhere to wander (judgement; the sources give no tested number for this).

On a phone: the same order, one column. Keep each section short enough that a thumb scroll shows its point. Repeat the button every two or three sections, because the top button is out of sight after a short scroll.

Common mistake: starting with the company's history, or putting the "about us" first. Visitors do not know yet whether they care.

## 4. One page, one job

Rule: every page has one thing it wants the visitor to do next. Pick it before you design the page.

Reason: a page with five equal asks gives the visitor five decisions. GOV.UK's guidance on buttons says to avoid several main buttons on one page because it makes it harder to know what to do next, and to simplify the page or split it up when you have many actions (GOV.UK Design System, Button, read 18 Oct 2026, https://design-system.service.gov.uk/components/button/). That is a government design team's guidance from its own testing, not a controlled experiment, but it matches how NN/g describes the homepage: a few clear starting points.

Common mistake: a homepage that tries to also be the pricing page, the blog index and the about page. Link to those pages; do not stack them.

On a phone: one job matters even more, because only one thing fits on screen at a time.

## 5. The path from first visit to contact

Rule: plan the shortest honest path, and make sure each step states what it leads to.

A path for a services business (judgement): homepage, then a service page, then proof (a case or two), then contact. Every page on that path carries the contact button. A visitor who arrives straight at a service page from search should not need the homepage to understand it, so each page repeats who it is for.

Evidence on the shape of the path is thin. The "three click rule" is the popular claim here, and it is false as stated: NN/g reports it has not been supported by data in any published study, cites a 2003 study by Joshua Porter that found drop off did not rise after three clicks and satisfaction did not fall, and notes the rule came from a 2001 book with no data behind it (Nielsen Norman Group, The 3-Click Rule for Navigation Is False, 11 Aug 2019, https://www.nngroup.com/articles/3-click-rule/). What matters is that each click is clearly the right one, which brings in information scent.

## 6. Information scent: naming links so people know where they lead

Rule: a link or menu item should tell the visitor what they will find, in the words they would use.

Reason: NN/g defines information scent as the visitor's estimate of what a link will deliver, based on the label, nearby text and what they already know. Its advice: describe the destination accurately and briefly, avoid vague labels such as "More" or "Learn more", avoid jargon and invented brand terms, do not lean on surrounding text because it can be hidden on small screens, and make sure the label matches the page (Nielsen Norman Group, Information Scent, 2 Feb 2020, https://www.nngroup.com/articles/information-scent/).

For menus the same point: use clear, specific, familiar wording, avoid invented terms and abstract categories, and put the key word first (Nielsen Norman Group, Menu Design: Checklist, 7 Jun 2024, https://www.nngroup.com/articles/menu-design/).

Plain words, in practice (judgement from those rules): "Services" or the actual service name, not "Solutions". "Pricing" not "Investment". "Contact" not "Let's talk" or "Get in touch with the team". "Work" or "Case studies" not "Stories". If you would not say the word to a friend in a pub, do not use it as a menu label.

On a phone: link text still has to make sense without the sentence around it, and "Read more" repeated five times in a row tells nobody anything.

## 7. How many items in the main menu?

Rule: as few as cover the real jobs, usually four to six, with the contact button set apart. 

Evidence, and what is folk: there is no tested magic number. The idea that menus must have seven items or fewer comes from memory research ("seven plus or minus two") that is about how many things people hold in mind at once, not about menus. NN/g's menu article gives no item count (it only says not to nest more than two tiers) and its 3-click article calls "no more than 7 main navigation categories" another unsupported rule of thumb (Nielsen Norman Group, The 3-Click Rule for Navigation Is False, 11 Aug 2019, https://www.nngroup.com/articles/3-click-rule/). A secondhand blog quote suggests NN/g has called the 7 limit a misconception, but it was not found on NN/g's own pages, so do not rely on it.

So the advice of four to six is judgement. The reason is practical: a small business site has a handful of real destinations, and each extra item dilutes the others and shrinks the room for the button. If the sources allow one hard line it is this: group before you cut. NN/g's mega menu article suggests clustering related options under short, distinct headings, no forms in the menu, and a plain fallback page that lists all options (Nielsen Norman Group, Mega Menus Work Well for Site Navigation, 26 Mar 2017, https://www.nngroup.com/articles/mega-menus-work-well/). A small site does not need a mega menu at all.

Other menu rules from the NN/g checklist: open submenus on click rather than hover, since hover does not exist on touch screens and fires by accident; show where the user is now; keep link text contrasting; avoid more than two tiers of cascading menus.

Wireframe, desktop header:

```
[logo]      Services   Work   About   Contact us   [ Book a call ]
```

Common mistake: eleven items, a dropdown under each, and the logo shrunk to fit.

## 8. Hamburger menus

Rule: on desktop, do not hide the main menu. On a phone, a menu behind a button is acceptable, but if you have four or fewer top-level links, show them.

Evidence: NN/g tested 179 participants on six live sites, on phones and desktops, with navigation hidden, visible or a mix. On desktop, hidden navigation was used in 27% of cases against 48% for visible and 50% for the mix. Content discoverability dropped by more than 20% with hidden navigation on both devices. Desktop tasks took at least 39% longer with hidden navigation, mobile tasks 15% longer than the mix. Their advice: avoid hidden navigation on desktop; on mobile, show all links if there are four or fewer, otherwise hide some and add in-page links or other support (Nielsen Norman Group, Hamburger Menus and Hidden Navigation Hurt UX Metrics, 26 Jun 2016, https://www.nngroup.com/articles/hamburger-menus/). This was done in 2016, and people are more used to the icon now, so the gap may be smaller today, but no newer study that overturns it was found.

NN/g's earlier mobile article says tab bars and top bars suit about five or fewer options, and hamburger menus suit content-heavy sites where people browse, as long as you support navigation in other ways (Nielsen Norman Group, Mobile Navigation Patterns, 15 Nov 2015, https://www.nngroup.com/articles/mobile-navigation-patterns/). The examples there are dated, the principle is not.

On a phone, a good compromise (judgement): keep the logo, put the main call to action button visible in the header or just under it, and put the rest behind the menu button. Label the button "Menu" with the icon, not the icon alone (labelled icons are easier to recognise; the 2016 study is about hidden menus, not icon labels, so this part is judgement). Keep the menu button at least 24 by 24 CSS pixels, which is the WCAG 2.2 minimum for targets (W3C WAI, Understanding SC 2.5.8 Target Size (Minimum), read 18 Oct 2026, https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html); aim bigger, since NN/g suggests at least 1 cm by 1 cm for touch targets in headers (Nielsen Norman Group, Sticky Headers, 4 Apr 2021, https://www.nngroup.com/articles/sticky-headers/).

Common mistake: a hamburger icon on a wide desktop screen with lots of space beside it.

## 9. Sticky headers

Rule: use one only if it is small, solid and still. NN/g says a persistent header helps when it is unobtrusive, high contrast and barely animated, and suggests one that comes back when the user scrolls up (slide in about 300 to 400 ms) as a good middle route (Nielsen Norman Group, Sticky Headers, 4 Apr 2021, https://www.nngroup.com/articles/sticky-headers/). On a phone, every pixel of header is a pixel less of content, so keep it thin.

## 10. The footer

Rule: the footer is the place people go for the dull but important things, so make it plain and complete.

Evidence: NN/g's article on footers lists utility links (contact, privacy, terms) as something every site needs, plus patterns that depend on size: repeating the main navigation on long pages, secondary tasks such as jobs, a sitemap on larger sites, and trust items such as awards for lesser-known brands. It says to keep to about two levels, use conventional labels ("Contact Us" rather than "Resources"), and not to hide or collapse the footer (Nielsen Norman Group, Footers 101: Design Patterns and When to Use Each, 24 Feb 2019, https://www.nngroup.com/articles/footers/).

For a small service site (judgement): your name and what you do in a line, contact details (email, phone if you take calls, town or country), the main menu again, privacy and terms links, and a repeat of the main button. On a phone, stack in one column and keep tap targets spaced out.

Common mistake: a footer full of links to every page, or social icons and nothing else.

## 11. Breadcrumbs

Rule: use them if your site has more than two levels (for example Services, then a service, then a sub-service). A five-page site does not need them.

Evidence: NN/g's 11 guidelines (published 23 Dec 2018, last reviewed 1 Sep 2026) say the current page in the trail should not be a link, that a Home link should appear in either the trail or the main navigation, and give a separate rule for mobile (Nielsen Norman Group, Breadcrumbs: 11 Design Guidelines, https://www.nngroup.com/articles/breadcrumbs/). Only a summary of the full list was captured, so check the article if you build a deep site.

On a phone: breadcrumbs shrink to a single "back to parent" link in many designs. That is a design choice, not something with evidence behind it.

## 12. Search

Rule: add search only when the site has enough pages that people might need it. For under 20 pages it adds clutter without help. If you add it, make it a box, not a link.

Evidence: Nielsen's 2001 guidance on search says homepage search should be a type-in box rather than a link, at the top of the page, and available everywhere. On his own site, changing a link into a box raised search use by 91%. In an ecommerce study 51% found what they wanted on the first query, 32% on the second and 18% on the third, and almost half of those whose first search failed gave up (Nielsen Norman Group, Search: Visible and Simple, 12 May 2001, https://www.nngroup.com/articles/search-visible-and-simple/). That article is 25 years old and from the early web, so the exact numbers are historic, but the finding that people give up fast after a failed search has kept turning up. Nielsen's 2002 homepage list puts a search box on the homepage as a baseline for sites of any size, but that predates how people use Google to search inside sites (Nielsen Norman Group, Top Ten Guidelines for Homepage Usability, 11 May 2002, https://www.nngroup.com/articles/top-ten-guidelines-for-homepage-usability/). Where sources and today's small sites differ, the call here is "only if it will be used".

On a phone, search sits behind an icon in the header. Make sure the keyboard that opens is the search one: `type="search"` or `inputmode="search"` (MDN, inputmode, last modified 17 Apr 2026, https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/inputmode).

## 13. Progressive disclosure: how much to show at once

Rule: show what most people need first and put the rest one click away, but keep it to two levels. NN/g: three or more levels of hidden detail often leaves people lost (Nielsen Norman Group, Progressive Disclosure, 3 Dec 2006, https://www.nngroup.com/articles/progressive-disclosure/). Good for an FAQ or a long list of service detail; bad for the main reason to hire you, which should be visible.

## What to do when someone asks Claude to design a navigation

1. Ask or state what the one job of the site is and who the visitor is.
2. List the real destinations, name them in plain words, cut to the fewest.
3. Show the header and first screen wireframe on desktop and phone before any code.
4. Check that the contact button appears in the header, after the first section, and at the end.
5. Flag anything that is judgement rather than evidence, such as item counts and page order, so the owner can overrule it.

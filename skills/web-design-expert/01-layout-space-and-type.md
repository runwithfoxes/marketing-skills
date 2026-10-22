# Layout, space and type

How to use this file: when someone asks "how big should the text be?" or "why does this page feel messy?", answer with the rule, give the reason, and say what it means on a phone. Every number below has its source. Where a popular claim is weak, it says so. Raw extracts of each source are in sources/design/.

A note on grades. "Study" means someone measured people. "Guideline" means a design body or expert recommends it and we have no measurement behind it. "Standard" means it is written into WCAG, the web accessibility rules.

## What gets seen first? How people actually read a page

Rule: people scan, they do not read, and a page should be built so that scanning finds the right thing. Put the point of each section in its heading, put the main words first in each line, and break text into clearly separated chunks.

Reason and evidence. Nielsen Norman Group (NN/g) has run eyetracking studies for years and describes four ways people move over text, from least to most effective: the F-pattern, the spotted pattern, the layer-cake pattern and the commitment pattern (NN/g, "Text Scanning Patterns: Eyetracking Evidence", Kara Pernice, 25 Aug 2019, https://www.nngroup.com/articles/text-scanning-patterns-eyetracking/). In the F-pattern the eye runs along the top, then a shorter way along lower down, then down the left edge. NN/g says it "resembles the shape of the letter F, but it is rarely a perfect F" and that it shows up as the default "when there are no strong cues to attract the eyes towards meaningful information" (NN/g, "F-Shaped Pattern of Reading on the Web: Misunderstood, But Still Relevant (Even on Mobile)", Pernice, 12 Nov 2017, reviewed 19 Aug 2026, https://www.nngroup.com/articles/f-shaped-pattern-reading-web-content/).

Caveats you should pass on, because the F-pattern is often quoted as a law. It is a description of what happens with plain, unformatted text, and NN/g itself calls it bad for users, since people skip content on the right. It is not a recipe to design to. The heatmaps behind it are from groups of roughly 45 to 47 people on specific pages, and the mobile examples are single-person replays, not a measured group (same F-pattern article). Treat it as a warning about walls of text.

The layer-cake is the pattern NN/g says to design for: people fixate on headings and subheadings and dip into the body under the heading they want. NN/g calls it "by far the most effective way to scan pages" (NN/g, "The Layer-Cake Pattern of Scanning Content on the Web", Pernice, 4 Aug 2019, https://www.nngroup.com/articles/layer-cake-pattern-scanning/). That article is a review of observations, with one heatmap from 9 participants, so call it strong practitioner evidence, not a controlled trial. Its advice is plain: make subheadings look the same each time, use spacing so body text clearly belongs to its subheading, write subheadings that describe all and only the section, and put the most informative words first.

On the fold. A common claim is that "the fold doesn't matter". NN/g measured it. In a 2018 eyetracking analysis of 120 users and more than 130,000 fixations, about 57% of viewing time was above the fold, and about 74% was within the first two screenfuls, against about 80% above the fold in an earlier 2010 study (NN/g, "Scrolling and Attention", Therese Fessenden, 15 Apr 2018, https://www.nngroup.com/articles/scrolling-and-attention/). So people do scroll, but the top of the page still gets the most attention. Put the point of the page there.

On a phone: the same thing holds, narrower. Text reflows, so a line that was the start of a row on desktop is now mid-paragraph. Headings do more work on a phone than anywhere else. Check every section by reading only the headings. If they do not tell the story, rewrite them.

Common mistake: a heading that is a label ("Our approach") rather than the point ("We fix the checkout before we touch the ads"). Labels give the scanner nothing.

## Grids and columns

Rule: use a simple column grid, one column on a phone, two or three on a laptop, and let everything line up to it. Do not invent a grid.

Reason: a grid is how items end up aligned and evenly spaced without someone measuring each one. In CSS you make one in a few lines: display grid, a column list, a gap. Repeat(), the fr unit, gap and minmax() do the work (MDN, "Basic concepts of grid layout", last modified 27 Aug 2026, https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout). A row of cards that fills as many columns as fit, each at least a set width, is the usual answer and needs no breakpoints.

Numbers for the switch points. Tailwind, the CSS tool most Next.js projects use, switches at 640px (sm), 768px (md), 1024px (lg), 1280px (xl) and 1536px (2xl), all as "this width and up" (Tailwind CSS docs, "Responsive design", read 18 Oct 2026, https://tailwindcss.com/docs/responsive-design). These are defaults of one tool, not a standard. GOV.UK's type scale switches at 640px (GOV.UK Design System, "Type scale", read 18 Oct 2026, https://design-system.service.gov.uk/styles/type-scale/). Two sources agreeing on about 640px suggests the phone-to-bigger break is well chosen.

Mobile first means you write the phone layout first and add changes for wider screens. In Tailwind, a plain class applies everywhere and "md:" means "from 768px up"; a common mistake is writing "sm:" and thinking it means small screens (Tailwind docs, same page).

Common mistake: three or four columns of cards squeezed onto a phone. On a phone it is one column, always, with the same order of importance as the desktop reading order.

## White space and grouping

Rule: put things that belong together close, and things that do not further apart. Space does the grouping, so you need fewer boxes and lines.

Reason: the proximity principle. Items near each other are seen as related (NN/g, "Proximity Principle in Visual Design", Aurora Harley, 2 Aug 2020, https://www.nngroup.com/articles/gestalt-proximity/). NN/g's practical points: keep a form label near its own field, keep a heading closer to its own text than to the section above, and check groupings at every screen size because stacked columns on a phone can separate things that belong together.

A rule of thumb for spacing: the gap above a heading should be clearly bigger than the gap between the heading and the text under it, roughly double. That is our rule of thumb, not a sourced figure. The principle behind it is sourced above.

Evidence on "white space improves comprehension". You will often see "white space raises comprehension by 20%". The figure traces to a 2004 study by D.Y.M. Lin, cited second-hand on blogs, and some blogs wrongly credit NN/g. The original was not found or read, so treat the 20% as unconfirmed and do not repeat it. The principle is still sound; the number is not safe.

The opposite risk is real and measured. NN/g reports that large gaps and full-width lines can look like the end of the page, called a "false floor". In one test of a site with a full-screen hero, six of eight users did not realise they could scroll (NN/g, "The Illusion of Completeness: What It Is and How to Avoid It", Kim Flaherty, 17 Jan 2016, https://www.nngroup.com/articles/illusion-of-completeness/). That is a small usability test on one site, so a warning, not a law. The fix is to let the next section's top edge show at the bottom of the first screen.

On a phone: white space costs scrolling. Use a smaller step between sections on a phone than on desktop, but never let two unrelated things touch.

Common mistake: adding a card border or a divider line to every block. If spacing already separates them, the lines add noise.

## One most important thing per screen (visual hierarchy)

Rule: on every screen, the eye should land on one thing first, then a second, then a third. Decide the order before you style anything.

Reason: NN/g defines visual hierarchy as arranging elements so the eye reaches them in order of importance, using contrast, scale and grouping (NN/g, "Visual Hierarchy in UX: Definition", Kelley Gordon, 17 Jan 2021, https://www.nngroup.com/articles/visual-hierarchy-ux-definition/). This is a guideline from an expert, with no measurement behind the specific limits. They suggest at most three sizes, with the most important element the biggest and no more than two large elements. The article's squint test is useful and free: blur your eyes at the page and see what stands out. If the biggest thing is not the most important thing, change it.

The phrase "one most important thing" is our summary of that advice, and it is a fair one. A page where five things shout leaves the scanner with no entry point.

On a phone: only one or two things fit on the first screen, so the choice is forced. Heading, one line of support, one button.

Common mistake: a big photo that wins the squint test when it should be the headline. NN/g notes a strongly coloured image can dominate even if it illustrates a secondary point (same article).

## Alignment

Rule: pick one left edge for text and keep to it. Left-align body text and headings for left-to-right languages. Centre only short things: a heading of one or two lines, a button label, a short tagline.

Reason: with a straight left edge the eye finds the start of each line without searching. Centred lines have ragged starts. The confirmed sources are mixed here. WCAG says nothing about centred text; it restricts only fully justified text, as a mechanism users can ask for (W3C, "Understanding SC 1.4.8: Visual Presentation", updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/visual-presentation.html). The "centred paragraphs are hard to read" view comes from design blogs, not studies, and No NN/g or academic measurement was found. Present it as a widely held expert view. It matches how scanning works (the F-pattern evidence above is about the left edge).

On a phone: centred looks fine for a few lines in a narrow column, which is why mobile hero text is often centred. Anything over about three lines goes left.

Common mistake: centring a whole page including paragraphs and lists. Also mixing centred and left-aligned blocks on the same page.

## How many fonts

Rule: one typeface family is enough. Two at most. Use size and weight to make a hierarchy before adding a font.

Reason: every font file adds download weight, so each extra family slows the page. web.dev says each web font file can slow page loads and that variable fonts can cut the file count when you want many weights (web.dev, "Typography", updated 9 Dec 2021, https://web.dev/learn/design/typography). The "no more than three typefaces" rule is a common design-blog guideline (SitePoint and a learning site both say it), with no measurement behind it. Two is the safer limit.

Is there a best font? NN/g covers a study by Shaun Wallace (Adobe) and colleagues with 352 people reading 300 to 500 word passages in 16 fonts, five each. On average, a person's fastest font was about 35% faster than their slowest (314 against 232 words a minute), but no font was best for everybody, and people's favourite fonts were not their fastest. Nielsen's own conclusion is that the study gives no actionable font guidelines for websites (NN/g, "Best Font for Online Reading: No Single Answer", Jakob Nielsen, 24 Apr 2022, https://www.nngroup.com/articles/best-font-for-online-reading/). So pick a clean, widely used face and spend your effort on size, spacing and contrast, where the evidence is stronger. Avoid thin weights for small text and avoid condensed faces for body text: a lab study reported by NN/g found condensed text took about 11% longer to read (NN/g, "Typography for Glanceable Reading: Bigger Is Better", Page Laubheimer, 26 Nov 2017, https://www.nngroup.com/articles/glanceable-fonts/). That study measured quick word recognition, not long reading, so use it as a caution.

Pairing, if you must: one family for headings, one for body, clearly different in style (a serif with a sans-serif is the common combination). That advice comes from design blogs and a web typography article, so it is expert opinion. Keep the roles fixed: the heading face is only ever for headings.

Loading cost. An unsubsetted font with every style can be "a multi-megabyte download" (web.dev, "Optimize WebFont loading and rendering", Ilya Grigorik, updated 16 Aug 2019, https://web.dev/articles/optimize-webfont-loading). The article gives no exact byte figures, so do not quote one. What it recommends is concrete: use WOFF2, load only the Latin subset you need, preload the main font, and set font-display so text shows while the font loads (otherwise you get the "blank text problem"). In Next.js the built-in font loader does the subsetting and self-hosting for you; say so and move on.

On a phone: the cost is bigger on slow connections, which is the point of fewer files.

Common mistake: loading four weights of two families "in case".

## How big should body text be?

Rule: 16px is the floor on a phone and desktop. Many sites use 17 to 19px. Never go below 16px for text people must read.

Evidence. GOV.UK's design system sets body text at 19px on both large and small screens, and its smallest style at 16px (GOV.UK, "Type scale", read 18 Oct 2026). In December 2022 the team announced it was removing the 14px step and stopping sizes shrinking on small screens, because service teams reported that smaller text on small screens harms visually impaired users. They cite the British Dyslexia Association's advice not to go below about 12pt, which is roughly 16px, and tell teams to avoid sizes under 16px (GOV.UK Design in government blog, "Making the GOV.UK Frontend typography scale more accessible", 12 Dec 2022, https://designnotes.blog.gov.uk/2022/12/12/making-the-gov-uk-frontend-typography-scale-more-accessible). That is a guideline from a government design team, built on user feedback and WCAG; it is not a controlled study. WCAG itself sets no minimum text size, only that text must resize (same blog).

The popular "16px minimum" claim traces to a 2011 Smashing Magazine opinion piece, which was seen in search results but not opened. It is where the number first spread, so call it an opinion, and rest the claim on the GOV.UK evidence.

Apple's tips page says text should be at least 11 points (Apple Developer, UI Design Dos and Don'ts, no date shown, read 18 Oct 2026, https://developer.apple.com/design/tips/; see 05). That is a floor for fine print, not a size for reading. Apple's 17pt default body size could not be confirmed, because its full guidelines page did not load, so do not cite Apple for it.

What NN/g says. The visual hierarchy article gives 14 to 16px for body on the web as an example (NN/g, Visual hierarchy, 17 Jan 2021). That is an illustration, and it sits below GOV.UK's later floor. No NN/g article on body font size was found, so no number is attributed to NN/g beyond that example.

Why bigger helps: in the quick-reading lab study NN/g reports, larger lowercase text read about as fast as smaller all-caps (Laubheimer 2017, above). Separately, NN/g says the advantage of dark text on a light background grows as text gets smaller (NN/g, "Dark Mode vs. Light Mode: Which Is Better?", Raluca Budiu, 2 Feb 2020, https://www.nngroup.com/articles/dark-mode/).

Our call: body 17 to 18px with 1.5 line height on both phone and desktop, captions never under 14px and only for things that do not matter if missed. Set sizes in rem, not px, so user settings still work, and never size type in vw alone because it blocks resizing (web.dev Typography, above).

Common mistake: grey 14px text for "secondary" information that is actually what the customer needs, such as delivery terms or prices.

## How long should a line be?

Rule: 50 to 75 characters per line including spaces. In CSS, set the text column to a max-width of about 65ch to 70ch.

Evidence. Baymard Institute gives 50 to 60 characters as optimal, citing Emil Ruder, and says up to 75 is acceptable. It also says that in their usability testing long lines put users off: lines of 100 characters or more tired people, and some left the page at the sight of long blocks. Lines that are too short also hurt (Baymard, "Readability: The Optimal Line Length", Edward Scott, 10 May 2022, https://baymard.com/blog/line-length-readability). web.dev gives 45 to 75, with 66 ideal, citing Robert Bringhurst, and says to set the limit in ch or rem rather than px (web.dev Typography, 9 Dec 2021). WCAG sets 80 characters as the AAA limit (W3C, SC 1.4.8, updated 6 Sep 2026). The sources agree on about 45 to 80 with a centre near 66. The 66 figure is a typographer's rule, not a measured optimum, so hold it loosely.

On a phone: portrait width rarely gives a line problem, since a 390px screen at 17px fits about 40 characters. The problem is phones held sideways and tablets, so keep the max-width rule. The tablet point is our own judgement and was not found in the Baymard article.

Common mistake: letting a paragraph run the full width of a 1440px laptop screen. Fix it by limiting the text column, not by shrinking the font.

## Line height

Rule: 1.5 for body text, tighter for big headings (1.1 to 1.25).

Evidence. WCAG's text spacing criterion (AA) requires that nothing breaks when a user sets line height to 1.5 times the font size, paragraph spacing to 2 times, letter spacing to 0.12 and word spacing to 0.16. These are a test baseline, not a ceiling (W3C, "Understanding SC 1.4.12: Text Spacing", updated 1 Oct 2025, https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html). That means your layout must survive 1.5, so you may as well start there. web.dev adds: use a unitless value so it scales with the size, and shorter lines can take larger line heights while long lines need smaller (web.dev Typography). GOV.UK's body is 19px on 25px, which is 1.3, with its design built to a 5px rhythm (GOV.UK Type scale). So sources differ: 1.3 at GOV.UK, 1.5 as the WCAG baseline. For a marketer's site with a 65ch line, 1.5 is the safer call.

Headings: GOV.UK's large heading is 36 on 40 (about 1.1). Large type needs less leading. That is the pattern across their scale.

Common mistake: the default line-height of 1.2 on body text, which looks cramped.

## Heading scale

Rule: pick a small set of sizes and reuse them. Three to five steps: one page title, one section heading, one sub-heading, body, small. Do not invent a new size for each block.

Evidence. GOV.UK's scale has fixed steps (16, 19, 24, 36, 48 on large screens) and tells designers to align any new style to a scale point. The scale also has 27 and 80, for exceptional use only (GOV.UK Type scale). On small screens the large headings shrink: 48 drops to 32, 36 to 27, 24 to 21, while body stays at 19. That is a useful pattern to copy: big headings shrink on phones, body does not. NN/g's visual hierarchy article suggests no more than three sizes in a view and gives examples of 18 to 22px for subheadings and up to 32px for headers (NN/g Visual hierarchy, 17 Jan 2021). web.dev suggests clamp() to scale type smoothly between a minimum and a maximum (web.dev Typography).

A sensible set for a marketing site on desktop: title 44 to 48px, section heading 32 to 36px, sub-heading 22 to 24px, body 17 to 18px, small 14 to 16px. On a phone: title about 32px, section about 26px, sub-heading 21px, body 17 to 18px. This is our reading of the GOV.UK scale, so call it a recommendation, not a standard.

Common mistake: a hero headline at 80px on desktop that wraps to six lines on a phone. Test the longest real headline at 360px wide.

## All caps and long text

Rule: all caps only for a one-to-three word label (a tag, a small section marker). Never for a sentence.

Evidence. A lab study (Ben Sawyer, MIT AgeLab, 2017) found uppercase was recognised faster than lowercase at a glance, with lowercase taking about 26% longer, yet larger lowercase text matched smaller uppercase. NN/g's reading of it: "We generally don't recommend using all-caps text for longer passages" (NN/g, "Typography for Glanceable Reading: Bigger Is Better", 26 Nov 2017). The study tested quick word-or-not decisions in one typeface, not paragraphs, so it is thin evidence either way. The advice against caps for long text is a widely held guideline. Other sources dispute the claim that caps is simply "harder to read"; where sources differ, short caps labels are fine and long caps text is risky.

Common mistake: a caps headline across two lines with wide letter spacing.

## Quick checks before you call a page done

Squint at it and name the three things that stand out. Read only the headings. Look at it at 360px wide. Check a line is under about 75 characters. Check body text is 16px or more. If any fail, fix them before polishing.

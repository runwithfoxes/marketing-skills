# Colour, contrast and pictures

How to use this file: when someone asks "what colours should I use?", "can I put white text on this photo?" or "should I use stock photos?", give the rule, the reason, the source, and what it does on a phone. Raw extracts are in sources/design/. Grades: "standard" is WCAG (the written web accessibility rules), "study" means people were measured, "guideline" means an expert or design team recommends it with no measurement behind it.

## How many colours?

Rule: one neutral for text and background, one brand colour for the main action, and at most one or two supporting colours. If you can name five colours on the page, it has too many.

Reason: colour is a signal, and a signal only works if it is rare. NN/g's visual hierarchy article suggests about two primary and two secondary colours for a simple design and no more than three contrast treatments in a complex one. It also says hierarchy comes from differences in value (how light or dark) and saturation against the surroundings, not from hue alone, and suggests keeping warm, bright colours like red for warnings and errors (NN/g, "Visual Hierarchy in UX: Definition", Kelley Gordon, 17 Jan 2021, https://www.nngroup.com/articles/visual-hierarchy-ux-definition/). That is a guideline from NN/g, with no study numbers behind it.

You may hear "60-30-10" as a rule for colour balance. No research source for it was found. It is a rule of thumb from interior design and design blogs, so use it as a rough picture of the idea (mostly neutral, a bit of brand, a little accent), not as a law.

A quick way to apply it: take a screenshot, make it greyscale. The page should still show what to read first and what to click. If it does not, colour was doing the work that size and weight should do.

On a phone: bright colour is the main tool for pulling the eye on a small screen, and the screen is small, so one accent colour for one action beats three.

Common mistake: giving every section its own colour so the page looks lively. The reader then cannot tell which colour means "click".

## One colour for the main action

Rule: pick one colour that is used for the primary button and nothing else decorative. Secondary actions are outlined or plain text links.

Reason: the eye goes first to what is different. If the primary button colour is also used for headings, icons and badges, the button stops being different. This follows from the hierarchy guidance above (contrast and scale make something first); it is a guideline, not a measured finding about buttons. Button text on that colour has to pass contrast too (next section). Many bright oranges and light blues fail with white text. Check before you commit.

On a phone: the main button is often full width and sits where the thumb is. Give it room and the one strong colour. Tap size and placement are covered in the mobile file.

Common mistake: two buttons of equal weight side by side ("Book a call" and "Learn more" both solid). The reader has to choose, and the one you want is no longer obvious.

## Contrast: the numbers that decide what passes

Rule: text needs a contrast ratio of at least 4.5 to 1 against its background. Large text needs 3 to 1. The edges of controls and meaningful icons need 3 to 1.

Reason and evidence. These are the WCAG 2.2 Level AA rules. Contrast ratio is a number from 1:1 (no difference) to 21:1 (black on white), and tools such as browser dev tools calculate it for you.

Text (SC 1.4.3). Normal text and images of text: 4.5:1. Large-scale text: 3:1. "Large" means at least 18 point, which is 24px, if not bold, or at least 14 point, about 18.5px, if bold. Ratios are not rounded: 4.499:1 fails. Thin or unusual fonts may need more than the ratio says. Placeholder text and text that appears on hover or focus must pass as well. Logos and purely decorative or inactive text are exempt (W3C, "Understanding SC 1.4.3: Contrast (Minimum)", updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html). A trap worth saying out loud: body text at 16 or 17px is not large, so it needs 4.5:1. It is common to assume it qualifies for 3:1 and it does not.

UI parts (SC 1.4.11). Controls and the states they show, and graphics you need to understand the content, need 3:1 against neighbouring colours. The W3C examples: a text input with a #767676 border on white passes; a checkbox with a #9D9D9D border on white is 2.7:1 and fails. Focus indicators always need enough contrast. Disabled controls are exempt, and a button border need not hit 3:1 if its text already makes it clear it is a button (W3C, "Understanding SC 1.4.11: Non-text Contrast", updated 6 Sep 2026, https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html).

How firm is it? WCAG AA is a written standard and the rules in many countries' accessibility law point to it, so treat 4.5:1 as the minimum to pass, not a taste. It is a minimum. A pale grey that scrapes 4.5:1 is still tiring to read, so for body text aim above it. #767676 on white is commonly given as the lightest grey that still passes 4.5:1 (our own calculation, about 4.5 to 1, not a W3C statement), so anything paler fails for body text. Use darker for body text: a dark grey like #333 or #1f2937 is easy to pass.

On a phone: people use phones outdoors in sun, which lowers the effective contrast of the screen. That is why passing the minimum is the floor and not the target. (This is common reasoning; no study measuring it was found, so present it as reasoning.)

Common mistake: pale grey text on white for captions, or white text on a light brand colour in the button. Check every text and background pair, including the footer and the placeholder text in form fields.

## Grey on grey and text on photos

Rule: never place text straight on a busy photo. Put a dark (or light) layer between them, or put the text on a solid block beside the photo.

Reason and evidence. WCAG's failure technique F83 says text over a background image must contrast with the darkest or lightest area of the image. The quick check: for light text, compare it against the lightest area of the image under it; for dark text, the darkest area (W3C, "F83: Failure of Success Criterion 1.4.3 and 1.4.6 due to using background images that do not provide sufficient contrast", updated 9 Mar 2026, https://www.w3.org/WAI/WCAG22/Techniques/failures/F83). So the test is against the worst spot, not the average.

The common fix is a dark gradient or a semi-transparent layer over the image under the text. A practitioner guide that cited F83 gave 60% black as an example, which is one person's value, not a standard. Use enough that the lightest pixel under the text still passes against white text, and test with real images, because the editor will swap the photo later.

Also: put headline text as real text, not baked into the picture. WCAG treats text as an image as something to avoid where real text works, and real text scales and can be read aloud (W3C 1.4.3 Understanding page).

Grey on grey (a light grey label on a light grey panel) fails for the same reason: it is two close values. Contrast depends on lightness difference, not on how different the hues look.

On a phone: a photo is cropped differently on a narrow screen, so the part under the text changes. Check the text over the phone crop, not just the desktop one.

Common mistake: white headline over a sky or a bright window, which looks fine on the designer's photo and fails on the next one.

## Dark mode basics

Rule: make light mode the default. Offer dark mode if you can, and follow the visitor's device setting.

Evidence. NN/g did not run its own studies. It reviewed the research and found that for people with normal vision, dark text on a light background usually performs better, and the advantage grows as text gets smaller. People did not rate the two as different in readability even though they performed differently. Some people with low vision, such as those with cataracts, did better with light text on dark. NN/g's advice: do not default to dark mode for a general audience, let users switch, and use the operating system setting (NN/g, "Dark Mode vs. Light Mode: Which Is Better?", Raluca Budiu, 2 Feb 2020, https://www.nngroup.com/articles/dark-mode/). Caveats: some of the older studies used screens that flickered more in light mode, which could have biased the results against light mode, and one finding linking light mode to eye changes came from seven people. Say the evidence is a literature review of small and old studies.

If you build dark mode: do not simply invert. Use a very dark grey rather than pure black, off-white rather than pure white for text, and recheck every pair against 4.5:1 and 3:1. Take care with small text in dark mode (NN/g, same article). The "dark grey not pure black" tip is common design practice, not a sourced finding.

In Next.js with Tailwind, the browser's preference is available with the prefers-color-scheme media query. For a marketer's first site, our recommendation is to ship light mode only and do it well. Dark mode doubles the colour checking.

Common mistake: a dark theme chosen because it looks premium, then low-contrast grey text on near-black.

## Colour blindness and not using colour alone

Rule: never let colour be the only way to tell something. Add a word, an icon, an underline or a shape.

Evidence. WCAG SC 1.4.1 (Level A, the most basic level) says colour must not be the only visual cue for conveying information, indicating an action, prompting a response or telling elements apart. A lightness difference of 3:1 counts as an extra cue. Named failures include links that look like normal text except for colour, and required or error fields marked only by colour. The W3C example: required fields with red labels plus an icon (W3C, "Understanding SC 1.4.1: Use of Color", updated 16 Sep 2025, https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html).

Red-green is the most common type of colour vision deficiency; blue-yellow is less common and complete colour blindness is rare (National Eye Institute, "Types of Color Vision Deficiency", updated 7 Aug 2023, https://www.nei.nih.gov/learn-about-eye-health/eye-conditions-and-diseases/color-blindness/types-color-vision-deficiency). A prevalence figure could not be confirmed from the NEI or NHS pages, so do not quote a "1 in 12 men" number.

What to do: links in body text get an underline. Form errors get a message in words next to the field. Chart lines get labels, not only a colour key. Status (paid, failed) uses a word as well as a green or red dot.

On a phone: bright sun makes weak colour differences vanish for everyone, so this helps all users.

Common mistake: a red "x" for an error beside a green tick for success, with no text. Another: a link as a slightly different blue with no underline.

## Real photos or stock?

Rule: use photos that show something true and useful: the product, the place, the people who do the work. Use as few as you can. Avoid generic stock pictures of smiling people.

Evidence. NN/g's eyetracking work reported in 2010 found that people skip decorative images and look hard at photos with information. Real photos of staff were scrutinised and generic stock photos of models ignored (a university application page photo was described as "pure filler"). On one team page, one tested user spent 10% more time on staff portraits than on the bios, though the bios took up 316% more space. On a retailer's category page, photos got 18% of viewing time and text 82%. Product photos on product pages drew attention and clicks to enlarge, and NN/g advises making the enlarged view at least twice the size (NN/g, "Photos as Web Content", Jakob Nielsen, 31 Oct 2010, reviewed 13 Aug 2026, https://www.nngroup.com/articles/photos-as-web-content/). Grade: eyetracking studies by a respected research firm, but from 2010, with small samples that the article does not state, and on a handful of pages. The direction (people ignore filler and look at information) matches later NN/g work, but no recent replication was found, so do not claim current numbers.

A fair counterpoint: not every decorative image is harmful. The finding is that the picture is not looked at, not that it damages the page. The cost is load time and the room it takes from content (next section).

What this means for AI-made or illustrated pictures: the same test applies. Does it tell the reader something? A picture of the product screen or the finished result passes. A glowing abstract shape does not.

On a phone: a photo takes a whole screen of height. If it is filler, it pushes the point below the first screen. Put the headline first and keep the picture shorter on phones.

Common mistake: a full-screen hero photo of people at a laptop, with the headline in a thin strip.

## Image sizes and formats

Rule: save photos as WebP or AVIF with a JPEG fallback, never larger than needed, with width and height set so the page does not jump. Logos and icons are SVG.

Evidence. web.dev says AVIF and WebP generally compress better than older formats and should be used where possible with a JPEG or PNG fallback; JPEG suits photos; PNG is lossless but much bigger; SVG suits logos, icons and simple shapes but not photos; use video instead of GIF for animation (web.dev, "Choose the right image format", updated 13 Aug 2024, https://web.dev/articles/choose-the-right-image-format). The page gives no percentage savings, so do not invent one. Next.js's own docs say AVIF takes about 50% longer to encode but compresses about 20% smaller than WebP, and still recommend WebP for most cases (Next.js docs, "Image Component", lastUpdated 28 Sep 2026, https://nextjs.org/docs/app/api-reference/components/image).

Why it matters: images are often the largest thing on the page and the biggest picture is usually what Google's Largest Contentful Paint measures. web.dev rates LCP of 2.5 seconds or less as good, 2.5 to 4.0 as needing improvement, over 4.0 as poor, at the 75th percentile of visits and separately for phones and desktops (web.dev, "Largest Contentful Paint (LCP)", updated 4 Sep 2025, https://web.dev/articles/lcp). Layout jumping is measured by Cumulative Layout Shift, where 0.1 or less is good and over 0.25 poor; images with unknown dimensions are a common cause (web.dev, "Cumulative Layout Shift (CLS)", updated 12 Apr 2023, https://web.dev/articles/cls). Set width and height on every image so the browser reserves space (Next.js docs, same page).

Sizing: do not send a 3000px photo to a 390px phone. The browser can choose between several sizes if you give them with srcset and sizes (web.dev, "Responsive images", updated 1 Feb 2023, https://web.dev/learn/images/responsive-images). A practical size: hero images no wider than about 1600 to 2000px on the source, and card images far smaller. Those pixel numbers are our rule of thumb, not a sourced standard.

next/image, mentioned once: in Next.js the Image component does the format choice, resizing and lazy loading for you, and the first big image above the fold should be marked to load early. Use it for every photo instead of a plain img tag. Details are in the Next.js file.

On a phone: the data matters most here, since the connection may be slow or capped.

Common mistake: dropping a 6MB photo straight from a camera or an AI image tool into the site.

## Alt text basics

Rule: every image has an alt attribute. If the picture carries meaning, describe the meaning in a short sentence. If it is decoration, leave alt empty (alt="") so screen readers skip it.

Evidence. The W3C decision tree: an image of text gets the same text as its alt unless the text is nearby; an image inside a link or button gets alt that says where it goes or what it does, not what it looks like; a simple photo that adds meaning gets a brief description of that meaning; a chart or complex image gets a short alt and the full data elsewhere on the page; purely decorative or redundant images get empty alt (W3C WAI, "An alt Decision Tree", updated 13 May 2024, https://www.w3.org/WAI/tutorials/images/decision-tree/).

Good alt says what a reader needs, in context: "Two builders fitting a roof on a new extension", not "image123.jpg" and not "photo of builders, roofing, building company, best roofers". Do not stuff it with search words. That last point is common expert advice, not a tested result.

Next.js requires an alt prop on the Image component (Next.js docs, Image Component).

On a phone: alt text shows if the image fails to load on a weak connection.

Common mistake: alt text on a logo link that says "logo" when it should say where the link goes ("Home").

## Icons with labels

Rule: put a visible text label next to every icon, except the tiny handful everybody knows (search, home, close, basket) and even those are better with words when space allows.

Evidence. NN/g: most icons have no standard meaning, so they are ambiguous; only a few (home, print, search) are widely recognised; even a standard icon is often safer with a text label; labels should always be visible because hover-only labels cost effort and do not work on touch. In one site's test, no participant clicked a clock icon used for history (sample size not given). The article's 5-second rule: if choosing an icon takes more than five seconds, it will probably fail (NN/g, "Icon Usability", Aurora Harley, 27 Jul 2014, https://www.nngroup.com/articles/icon-usability/). This is an expert article with small anecdotal tests. It is old but matches common practice. Blogs also give figures for icon prediction accuracy (88% with a label, 60% without), cited second-hand from UserTesting and not traceable to the source, so they are left out. A blog counterpoint says icon-only items can be found faster once learned, which is plausible for frequent users of one app but not for visitors to a new site.

On a phone: icons are more noticeable on small screens because the page is less busy, and the hamburger menu icon is one of the few that has become familiar. Even so, adding the word "Menu" is safe.

Common mistake: a row of unlabelled icons in a feature grid that the reader has to guess at. Also icons that look different from set to set. Use one icon set at one stroke weight.

## Quick checks before you call a page done

Greyscale screenshot: is the order still clear? Contrast: every text and background pair at 4.5:1, big text and control edges at 3:1. Photos: would the reader miss it if removed? Every image has alt, width, height, and is not larger than needed. Every icon has a word. No meaning carried by colour alone.

# Making a wireframe: draw the shape and agree it before you build

This note tells Claude what to do when the user asks for a page. The first move is never code. The first move is to draw the page as a plain layout, agree the order of it with the user, and only then build. Everything below is how to do that well.

A word on evidence. The sources for wireframing are mostly short guidance pieces and practitioner views, not experiments. Where a claim is a guideline or one expert's view, it is marked as that. Where something is our own working rule, it says so.

## What is a wireframe, and what is it not?

A wireframe is a drawing of a page that shows what goes where, in what order, and what each part says. It has no colour, no brand, no real pictures and no polish. Think of it as the floor plan of a house, drawn before anyone picks the wallpaper.

Nielsen Norman Group defines the fidelity of a prototype by "how closely it matches the look-and-feel of the final system". Low-fidelity ones may be black-and-white sketches or schematic layouts, may lack realistic spacing and visuals, and may not be clickable (Nielsen Norman Group, "UX Prototypes: Low Fidelity vs. High Fidelity", 18 Dec 2016, https://www.nngroup.com/articles/ux-prototype-hi-lo-fidelity/). That article is about prototypes tested with users, and a page wireframe is the simplest kind.

A wireframe says nothing about colours, fonts or pictures, and it makes no promise about how the page will look. If the user starts commenting on colours or fonts, say "that comes after, right now we are only agreeing the order and the words". Greyscale is what keeps the conversation on the right thing. The same NN/g article gives one reason that applies directly, though it is written about testing with users: with a rough prototype, users "feel less obliged to be successful", so they are freer to say what is not working (same article, 18 Dec 2016).

## Why agree the order before building?

Changing a box in a drawing takes seconds. Changing a section that has been coded, styled and made to work on a phone takes much longer, and the user is more reluctant to ask for it because it already looks finished. That is a judgement, not a measured result, but the GOV.UK Service Manual says the same in its own terms: prototypes let teams explore design ideas faster and with less risk than changing production code (GOV.UK Service Manual, "Making prototypes", published 18 Oct 2016, https://www.gov.uk/service-manual/design/making-prototypes). NN/g makes the matching point about cost: ripping up a prototype is easy, "especially if it's just a piece of paper" (NN/g, 18 Dec 2016, link above).

The GOV.UK page also says sketches suit exploring and discussing basic ideas with colleagues, while more realistic coded prototypes suit user research (GOV.UK, 18 Oct 2016, link above). For a marketer building a first site, the sketch level is the right one. We are not testing with users yet. We are making sure the order of the page is right before it costs anything.

There is a second reason that is specific to working with Claude. If the user says "make me a homepage" and Claude builds one, the user reacts to dozens of small decisions at once: the words, the layout, the colours, the pictures. Their feedback becomes vague ("it's not quite right"). If instead they agree ten lines of order first, the later feedback is about looks only, and Claude knows the structure is settled.

Common mistake: skipping this because the user is in a hurry. A wireframe takes a few minutes in the chat. Rebuilding a page takes much longer.

## The steps

Do these in order. Ask the user for what Claude does not know. Never invent facts about the business (prices, locations, qualifications, awards); where a fact is missing, put a visible blank such as [price] in the wireframe and ask.

Step 1: the page's one job. Ask what the single thing is that a visitor should do after reading the page. For a homepage of a small service business it is usually one action: book, call, request a quote. If the user names three, ask which one matters most this quarter and make that the main action. The others become quieter links. This is our working rule, in line with the call-to-action advice in note 04.

Step 2: who arrives, and from where. Ask who the visitor is and what they were doing a minute before: searching "physio near me" on a phone, following a link from a friend, typing the name from a card. This changes the order. Someone who searched a problem needs to see that you treat it before anything else. Someone who was recommended needs to see proof and the team sooner. Also ask roughly how many of the visitors will be on a phone; if the user does not know, assume most (note 05 gives the evidence on mobile).

Step 3: the sections, in order. For each section write three things: a name, what it must say in one sentence, and the one action or next step it leads to. Keep the list short. A homepage of a small business rarely needs more than seven or eight sections. If a section cannot be given a one-sentence job, cut it.

Step 4: the real words. Write the headline and the first line of each section for real, using what the user has told you. This is the content-first part, and it is covered in the next section.

Step 5: desktop and phone together. Draw both. The phone version is mostly a question of how the desktop sections stack into one column, what moves, what is shortened and what is cut. Spell that out for every section. Do not treat the phone as something to sort out after building.

Step 6: show it, and ask for changes. Two ways to show it are described below.

## Real words or placeholder text?

Use real words wherever you can, and a clear blank where you cannot. Avoid Latin filler.

The evidence here is a mix of views, and they agree more than they disagree. NN/g's Page Laubheimer says placeholder text such as Lorem Ipsum is quick and useful early on, but causes problems later if the real content has different characteristics from the filler. The video says placeholders "can ultimately create problems if the real content has different characteristics" (NN/g, "A Downside of Fake Copy in UI Prototypes", video page, 24 Mar 2017, https://www.nngroup.com/videos/fake-copy/). NN/g's Anna Kaley presents "content frames" as a tool so that teams are not waiting until the end of the design process to bring in real content (NN/g, "Using Content Frames in the Design Process", video page, 22 Jun 2018, https://www.nngroup.com/videos/content-frames/). Only the summaries of those two videos could be read, not the videos themselves, so the detail behind them is not confirmed here.

An opinion piece worth knowing about, seen only as a search result and not read in full, says a design built on filler can break when real copy arrives. It is a blog view and is not relied on.

What this means in practice for Claude: a headline written as real words ("Back pain and sports injuries treated in Millbrook") shows at once whether it fits on one line, whether it says anything, and whether the section below it has anything left to say. A headline of "Lorem ipsum dolor sit amet" shows none of that. And the user can judge real words. They cannot judge Latin.

One caution, from the other side of the argument. Early in a project, polished copy can pull attention to wording and away from structure. So keep wireframe words short and plain: a headline, one line of support, the button label. Full paragraphs come when the user has agreed the order. For pictures, never use a stock-photo placeholder. Use a grey box with a label saying what the picture should show, such as [photo: the team at work].

Common mistake: pasting in long made-up paragraphs to "fill it out". It adds length without information and hides the sections that are thin.

## Show it in the chat: a plain text layout

This is the fastest way and the right first step. Use a monospace block with boxes. One box per section, numbered, with the job and the words inside. Put the desktop first and then the phone, with a line on what changes.

Here is a worked example for an invented physiotherapy clinic. We made up Harbour Physio and every detail about it for this example. If a real clinic shares the name, this is not about it.

Its order differs a little from the suggested order in 03, which puts a short proof strip straight after the first screen. Neither order is tested; both are judgement. Choose by what the visitor doubts first. If they need to know you treat their problem, put what you do first, as here. If they need to know you're any good, put the proof first, as in 03.

Never invent facts for a real business. Prices, how they charge, offers ("free first call"), what a call or visit involves and how long it takes, how they work, the country's rules they follow, qualifications, registration numbers, results and quotes all come from the user. Example wording elsewhere in this pack is an example, never a fact about the user. Until the user gives them, leave a marked blank like [fee for a first appointment] and ask for it.

```
DESKTOP (wide)

+--------------------------------------------------------------+
| 1 HEADER   [logo]        Treatments  Prices  Team  Contact   |
+--------------------------------------------------------------+
| 2 HERO                                                       |
|  Back pain, sports injuries and stiff joints   [photo:       |
|  treated in Millbrook                           physio with  |
|  Chartered physios. First visit within         a patient]   |
|  [days], [minutes], [price].                                 |
|  [ BOOK YOUR FIRST APPOINTMENT ]  <- the one action          |
+--------------------------------------------------------------+
| 3 WHAT WE TREAT                                              |
|  [Back and neck] [Sports injuries] [Joints and mobility]     |
|   one line each, each a link to its page                     |
+--------------------------------------------------------------+
| 4 YOUR FIRST VISIT                                           |
|  1 We listen  ->  2 We examine  ->  3 You leave with a plan  |
+--------------------------------------------------------------+
| 5 ONE PATIENT, NAMED     "[real quote]"  [name, town]        |
+--------------------------------------------------------------+
| 6 THE LEAD PHYSIO   [photo]  two lines on who she is         |
+--------------------------------------------------------------+
| 7 THREE QUESTIONS   referral? insurance? parking?            |
+--------------------------------------------------------------+
| 8 FINAL ACTION   [ BOOK YOUR FIRST APPOINTMENT ]  or call    |
+--------------------------------------------------------------+
| 9 FOOTER   address, hours, map, privacy, registration        |
+--------------------------------------------------------------+

PHONE (one column, 390 wide)
 1 Header: logo and one Menu button; phone number one tap away
 2 Hero: headline, support line, full-width button, picture
   below (shorter)
 3 Treatments: three cards stacked, one line each
 4 First visit: three steps stacked as a short list
 5 Patient quote: unchanged
 6 Physio: photo above the two lines
 7 Questions: each opens when tapped
 8 Final action: full-width button, number to tap
 9 Footer: stacked
Cut on the phone: nothing is removed, but the support line in
section 2 is trimmed to one sentence and section 4 loses its
arrows.
```

Notice what the example does. Each box has a job. Section 2 says what is offered, for whom and where, and carries the single action. The action appears twice, at the top and at the end, so someone who scrolled does not have to scroll back. The phone version is a statement of how things stack, not a second design. The page order follows the question a worried visitor asks: can you help with my problem, what will happen, can I trust you, how do I book. That order is our judgement for a service business; note 03 covers the evidence on page order.

After the text layout, ask the user the review questions below. Most of the changes happen at this stage.

## Show it in the browser: a greyscale HTML file

When the user wants to see it at real width, or the page has many sections, make a single HTML file they open in the browser. There is a working example in this pack, wireframe-template.html. Copy its structure rather than starting from nothing.

Rules for the file:

1. One file, no external anything. No linked stylesheets, no web fonts, no images, no scripts from elsewhere. It must open by double-clicking.
2. Greyscale only. Greys for boxes, black for text and for the one action. No brand colours, even if the user has them. This is deliberate and Claude should say why if asked: colour pulls the conversation towards looks.
3. One font, a plain system sans-serif. No font choices at this stage.
4. Each section is a labelled box with a number tag in the corner and its one-line job in small grey text above the words. The numbers match the list agreed in the chat.
5. Real headings and short real text, as in the section above. Blanks in square brackets where facts are missing.
6. Pictures are grey boxes with a label of what they should show: [photo: the team at work], [logo], [chart: monthly savings]. Never an actual image.
7. The call to action is the only dark filled block, and it is tagged "CALL TO ACTION" so the user can see at once where the page asks for something. If there are two actions, the second is an outlined box.
8. Show two frames side by side: a desktop frame around 960px wide and a phone frame exactly 390px wide, both with the same content. 390px is a common phone width today; the exact figure is a convention, not a rule, and the point is to show a narrow single-column version. The page may need to scroll sideways to show both on a small laptop, and that is fine for a wireframe.
9. The phone frame must show the real stacking, not a shrunk desktop. Columns become one column, a row of links becomes a Menu button, a wide button becomes full width. This follows the standard responsive pattern: a single column on a phone, more columns as the screen widens (web.dev, "Responsive web design basics", last updated 12 Feb 2019, https://web.dev/articles/responsive-web-design-basics).
10. Small dotted notes under a section may say what changes on the phone. They are for the review, and they come out when the page is built.
11. No clicks, no hover effects, no animation. If it moves, it is not a wireframe.
12. Keep it short. The template is about 150 lines. If the file grows past a few hundred lines, the wireframe has become a design.

One thing to say to the user when you hand over the file: the phone frame is a drawing of the layout at phone width, not a test on a real phone. It is a good guide to the order and the stacking. It does not replace opening the finished page on an actual phone.

## How to review a wireframe with the user

Ask a few direct questions and wait for answers. Do not ask "what do you think?", which gets "looks good". Useful ones:

1. If a visitor read only the top of the page, would they know what you do, for whom, and where? Point at the headline.
2. Is there one action, and is it the one that matters most? Is it the same action everywhere it appears?
3. Read the section names in order, top to bottom. Is that the order the visitor's questions come in? What is the first thing they would want to know that we have put third?
4. Which section would you cut if the page had to be a third shorter? (If the user cannot name one, a section may be there out of habit.)
5. Is anything here something you cannot honestly back up with a fact, a number or a named person? Replace it with a blank for now.
6. On the phone version, what is the first thing someone sees without scrolling? Is it the right thing?
7. Is there something you expected to see that is missing, such as prices, opening hours or contact details?
8. Are any of the blanks things only you know? List them and who fills each.

Then change the wireframe and show it again. Two rounds is typical. Stop when the user can say in one sentence what each section is for and has no more changes to the order or the words. Write the agreed order down as a numbered list in the chat so it stays in the conversation, and in a short comment at the top of the page file once building starts.

Common mistake: letting the review drift to colours and logos. Say "later" and bring it back to order and words.

## From wireframe to the built page

Once the order is agreed, building is mostly following the list. Our working practice, not a sourced rule:

1. Build a section at a time in the agreed order, using the agreed words. The grey boxes become components, one per section, so a section can be changed without touching the rest.
2. Start with the phone layout and widen from there. This matches the mobile-first approach in web.dev: design for the smallest screen first, add wider layouts with min-width media queries, and choose the breakpoints where the content needs them, not for particular devices (web.dev, last updated 12 Feb 2019, link above). It also matches the wireframe: the phone version is the base and the desktop version is the same content spread out.
3. Put in the page's meta viewport tag with width=device-width and initial-scale=1, and do not block zoom (web.dev, last updated 12 Feb 2019, link above). Note 05 has more.
4. Replace grey boxes with real pictures only when the user has them. Until then keep the labelled box or use a plain tinted block rather than a stock photo.
5. Add colour, type and brand last, using the choices in notes 01 and 02. At that point the user reacts to looks, and the structure does not move.
6. Check the finished page against the wireframe: same order, same single action, same words unless the user changed them. If something had to change while building, say so and why.
7. Look at it on a phone width before showing the user, then critique it with note 10.

Keep the wireframe. When the user later says "add a section", draw it in the wireframe first, in the place it would go, and agree it before editing the page. That keeps the habit going.

One thing from the GOV.UK Service Manual is worth carrying over: prototype code is not live code, and the manual says not to copy prototype code straight into a live service (GOV.UK Service Manual, "Making prototypes", 18 Oct 2016, link above). The wireframe HTML in this pack is a drawing. Do not build the real page by editing it. Build the page properly in the site framework, using the wireframe as the plan.

## Not confirmed

A UK government department is reported to argue that traditional wireframes can give stakeholders a false sense of a finished product, as part of a content-first approach. That report came from a search snippet and the page itself could not be read (blocked), so it is not used as a claim here. It is a fair reason to keep wireframes greyscale and obviously unfinished, which the rules above already do.

Sources saved in sources/wireframing/.

# Critiquing a page

Written 18 Oct 2026. This file is how Claude looks at a page and tells you what is wrong with it. The numbers it judges against (text sizes, contrast, tap targets, speed) live in the other files, so this file points to them instead of repeating them.

## What a critique is for

A critique is a fast, cheap check by someone who knows the rules, before real people see the page. It finds the problems an expert can spot from the page itself. It can't tell you what your customers will do, and it isn't a replacement for watching a few of them use the page (see the end of this file).

The method comes from what Nielsen Norman Group calls a heuristic evaluation: you go through a page and note everything that breaks a known rule of good design. Their guide says each reviewer goes through twice, once to learn the page and once to note what breaks a rule, and that "ideally, three to five people should independently evaluate the same interface" because one person, however expert, misses things (Nielsen Norman Group, How to Conduct a Heuristic Evaluation, Kate Moran and Kelley Gordon, 25 Jun 2023, https://www.nngroup.com/articles/how-to-conduct-a-heuristic-evaluation/). So treat Claude's critique as one reviewer. A colleague's read is a second.

## How Claude does it

1. Ask what the page is for and who it is for, if the user hasn't said. A page can't be judged without its one job (03).
2. Look at the page on a phone first, then on a laptop. More than half of web visits worldwide now come from phones (05), so for most sites the phone view is the real page. If Claude can open the page, it should look at both widths. If it only has a screenshot of one, it says which view it hasn't seen.
3. Read the words before judging the looks (07). Then go through the checks below in order.
4. Report the problems in order of how much they cost the page, worst first, each with the fix. Plain words: "The headline says what every competitor says", "The body text is too small to read on a phone", "There are three buttons in the first screen and none of them is the main one."
5. Say what works too, in a line, so the user knows what to keep.
6. Never guess at things it can't see. If the question is speed, give the free tests (06). If it's whether people buy, say a critique can't tell you that.

## The checks, in order

These run from the things that cost the most to the things that cost the least.

1. Does the first screen say what this is, who it's for and what to do next? If a stranger can't tell in a glance, nothing below matters much (03).
2. Could a competitor put their logo on this headline and every section? If so, the page is generic however good it looks. Name the sentence and say what a specific version would say (07).
3. Is there one main action, and is it the strongest thing on the screen? Is the button text a verb that says what happens (04)?
4. Can you read it? Body text size and line length (01), contrast against the background, including text on photos (02), on a phone as well as a laptop.
5. Does the eye know where to go? One most important thing per screen, clear headings, related things grouped by space (01).
6. Does it work with a thumb? Tap targets big enough and far enough apart, the main action within reach, nothing that needs hovering, nothing that scrolls sideways (05).
7. Is it in an order that answers the visitor's questions as they come up: what is it, is it for me, can I trust it, what does it cost or involve, what do I do now (03)?
8. Is there proof, and is it specific? Named people, real numbers, real pictures (02, 07).
9. Forms: only the fields you need, labels above fields, clear errors (04).
10. Accessibility and speed basics: alt text, headings in order, link text that makes sense alone, nothing that only works with a mouse, nothing that moves for no reason, page weight and load (06).
11. Looks everyone is using. If the file website-cliches.md is in the folder beside this pack, read it and point out any of those looks the page uses. The point is not whether a look is good or bad. These looks are easy to do, so they have become commonplace, and a page built from them starts to look like everyone else's. Don't judge them and don't tell the user to keep them. Name each one the page uses, say it is one of the common looks, and ask what would make that part of the page theirs instead. If the file isn't there, skip this step.

## Ten rules to check a page against

Jakob Nielsen's ten usability heuristics, first published in 1994 and last reviewed by Nielsen Norman Group on 30 Jan 2024, are what NN/g calls "broad rules of thumb", developed by Nielsen with Rolf Molich in 1990. Some fit a marketing page better than others. In our words, with the ones that matter most for a marketing site first:

Speak the visitor's language. Use their words, not your company's or your industry's ("Match between the system and the real world": "The design should speak the users' language").
Keep it consistent. The same thing should look and be called the same everywhere, and follow what people expect from other websites ("Consistency and standards").
Cut what isn't needed. Nielsen's wording is that "interfaces should not contain information that is irrelevant or rarely needed", because every extra thing competes with what matters ("Aesthetic and minimalist design").
Show, don't make them remember. Options and information should be visible where they're needed ("Recognition rather than recall").
Prevent mistakes, then explain them plainly. Error messages in plain words that say what went wrong and how to fix it ("Error prevention" and "Help users recognize, diagnose, and recover from errors").
Show what's happening. After a click or a form send, the visitor should see that it worked ("Visibility of system status").
Give a way back. Let people undo, go back or close things easily ("User control and freedom").
The other two, flexibility and efficiency of use (shortcuts for experts) and help and documentation, matter less on a marketing page. The two error rules above are the file's folding of heuristics 5 and 9 into one.

(Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, Jakob Nielsen, 24 Apr 1994, reviewed 30 Jan 2024, https://www.nngroup.com/articles/ten-usability-heuristics/)

## How to write up the critique

Keep it short and ranked. For each problem: what's wrong, where it is, why it matters, and the fix, in one or two sentences. For example:

"1. The headline, 'Solutions for a changing world', could belong to any firm. Visitors won't know what you do. Say what you do and for whom: 'Payroll for Irish restaurants with 10 to 50 staff'.
2. On a phone the body text is about 13px and grey on white. It's hard to read. Make it at least 16px and darker (01, 02, 05).
3. The first screen has three buttons the same size. Make 'Book a call' the one solid button and turn the others into plain links."

The example headline above is made up.

Then one line on what works and should stay, and one line on what Claude couldn't check.

## What a critique can't tell you

Claude can't tell whether real visitors understand the page, trust it or act on it. Only watching people can. The cheapest version is to sit five people from your target group in front of the page, give them a task ("find out what this costs and book a first appointment") and watch without helping. Nielsen's model is that five such users find about 85% of the problems, but only if they're "comparable users who will be using the site in fairly similar ways". His advice is several small rounds rather than one big one, testing again after each fix, because fixes don't always work (Nielsen Norman Group, Why You Only Need to Test with 5 Users, Jakob Nielsen, 18 Mar 2000, https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/). The 85% comes from a model in Nielsen and Landauer's 1993 paper, so treat it as a rule of thumb, not a guarantee.

Analytics tell you what people did, not why. A critique tells you what an expert thinks is wrong. Watching five people tells you why. You need all three over time, and the critique is the one you can do today.

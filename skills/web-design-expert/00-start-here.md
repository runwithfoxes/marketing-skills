# Start here: a web design and UX knowledge pack

Written 18 Oct 2026, and every fact in it carries its own date. Made by Run with Foxes for module 3 of AI Fluency for Ambitious Marketers.

## What is this folder?

It's what a good web designer and UX specialist knows, written down as files your Claude can read and work from. Unzip it into the folder you're building your website in, open that folder in Claude Code, and Claude becomes your designer. It will plan pages with you, draw the shape of a page before building it, make design decisions and tell you why, and critique your pages in plain words.

It covers four things. Design is how the page looks. UX is how people find their way round it: what they see first, what they do next, how the menu and the forms work. Next.js is what the site is built in. Vercel is how it goes live. Underneath all four is what the page says, because a beautiful site that says what every competitor says is still generic.

## What's in it?

SKILL.md turns the folder into a Claude skill, so Claude uses it whenever you're working on your site.
00-start-here.md is this file.
01-layout-space-and-type.md covers grids, space, visual hierarchy, fonts, text sizes, line length and how people scan a page.
02-colour-contrast-and-pictures.md covers colour, contrast you can read, text on photos, real pictures against stock, image formats and alt text.
03-navigation-and-page-order.md covers what the first screen must answer, the fold, menus, page order and the path from first visit to contact.
04-forms-and-calls-to-action.md covers buttons, button words, forms, labels, errors and trust near the button.
05-mobile.md covers designing for the phone first: how a page stacks, thumb reach, tap target sizes, phone menus and testing on a real phone.
06-motion-speed-and-accessibility.md covers when movement helps, page speed and how to test it for free, and the accessibility basics, including the European Accessibility Act.
07-what-to-say-positioning-and-messaging.md covers writing the page before designing it, positioning, the sea of sameness, headlines, proof and the About page.
08-nextjs-and-vercel.md covers Next.js and Vercel for someone who has never coded: pages, components, running it on your computer, going live, and what it costs.
09-making-a-wireframe.md covers how to agree the shape of a page before building it.
wireframe-template.html is a worked example of a wireframe for a made-up physio clinic, desktop and phone side by side. Open it in your browser.
10-critiquing-a-page.md covers how Claude reviews a page and writes up what's wrong, worst first. If you also put website-cliches.md from the course page in the folder, it uses that too.
learn-a-subject.md is the instructions to make a pack like this for any other subject.

## How was it made?

We sent Claude agents to read the best public sources on web design and usability, then had them write these notes, and checked them. They read about 140 pages. Forty-seven were from Nielsen Norman Group, the usability research firm whose studies most of this field leans on. The rest came from the W3C's accessibility guidelines (WCAG 2.2), Google's web.dev and Chrome guidance on speed, the UK government's GOV.UK Design System, the Baymard Institute's usability research, MDN's web documentation, and the Next.js and Vercel documentation and pricing pages.

## What should I keep in mind?

Most of web design is good practice, not proven science. Where a rule comes from a study, the notes say who ran it and how many people took part. Where it's a guideline or someone's opinion, they say that too. Some well-known "facts" (the three-click rule, "nobody scrolls", seven items in a menu) don't hold up, and the notes say so.

Some of the best studies are old. Nielsen Norman Group's study on how people read web copy is from 1997, its picture study from 2010 and its menu study from 2016, and phones have changed since. The notes give the year beside each one.

Accessibility isn't optional. The contrast, text size, tap target and alt text rules in these notes are the floor, and in the EU the European Accessibility Act has applied since 28 June 2025, including to online shops, with an exemption for the smallest businesses. 06 says who it applies to. Check your own case with someone qualified.

Vercel's free Hobby plan is for personal, non-commercial use only. A website for your business needs the paid Pro plan, $20 a month on 18 Oct 2026 (08).

Prices, versions and guidelines change. Every fact is dated. If a date or a price matters, ask Claude to open the link and check the live page.

## How do I use it with Claude?

Put the folder inside your website folder and open that folder in Claude Code. Then ask it things like "Wireframe a homepage for my business", "What should go first on this page?", "How big should my buttons be on a phone?" or "Critique this page". It should make a call and tell you why, show you the shape of a page before building it, and say what happens on a phone every time. Ask it which file and link an answer comes from. Then ask it something it can't know, like whether your site is fast enough, without giving it your site. A good answer is "I can't tell without your site, here's how to test it."

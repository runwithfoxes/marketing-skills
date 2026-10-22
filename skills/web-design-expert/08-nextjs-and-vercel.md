# 08. Next.js and Vercel, for a marketer who builds with Claude Code

Read 18 Oct 2026. Each price, limit and version below is quoted with its link and the page's date. The Vercel docs pages were read in full that day; the pricing page came through as a summary, and its figures match the docs. Prices and limits change, so when you act on one, ask Claude to open the page again. Raw extracts are in sources/nextjs-vercel/.

## What the pieces are

Next.js is the toolkit your site is built with. The Next.js docs call it "a React framework for building full-stack web applications" (Next.js Docs, 18 Oct 2026, https://nextjs.org/docs). Vercel makes it and also runs the hosting service where you put the site live (the Next.js code is in Vercel's own repository, https://github.com/vercel/next.js, read 18 Oct 2026).

The current major version is Next.js 16. The latest release is 16.4, published 6 Oct 2026. Version 16 itself came out 21 Oct 2025 (Next.js blog index, read 18 Oct 2026, https://nextjs.org/blog). The 16.4 post says: "As of today, all new apps created with `create-next-app` will have Cache Components enabled by default" (Next.js 16.4, 6 Oct 2026, https://nextjs.org/blog/next-16-4). Cache Components is a new way of deciding which parts of a page are saved and reused and which are worked out fresh for each visitor. You don't need to master it to build a marketing site, but Claude should write code that works with it on, because it is on in every new app. Ask Claude to build a normal site and to keep `next` up to date with `npx next upgrade` (Installation docs, lastUpdated 2 Oct 2026, https://nextjs.org/docs/app/getting-started/installation).

React is the layer under Next.js. It lets you build a page from reusable pieces. React's own tutorial says a component is "a piece of the UI" that "can be as small as a button, or as large as an entire page" (React, Quick Start, read 18 Oct 2026, https://react.dev/learn). A pricing card is one component. You use it three times and edit it once.

Tailwind CSS is how the look gets written. Instead of a separate style file, small single-purpose labels sit on each element: one for padding, one for text size, one for colour. Tailwind says you style "by combining many single-purpose presentational classes (utility classes) directly in your markup" (Tailwind docs, v4.3, read 18 Oct 2026, https://tailwindcss.com/docs/styling-with-utility-classes). It is mobile first: a label like `sm:grid-cols-3` only applies from 40rem (640px at default size) upward, and the plain label applies on every screen. So the phone layout is the base you write first.

## The words you will hear

A page is one screen of your site, such as the homepage or the About page. A route is the address that leads to it, such as `/` or `/pricing`. A layout is the shared frame around pages (the header and footer), written once. A component is a reusable piece, such as a button or a testimonial.

Next.js uses folders as addresses. The docs say "the routes in your application are determined by how you structure your files" (Installation docs, 2 Oct 2026). Inside the `app` folder, `app/page.tsx` is the homepage at `/`, and `app/pricing/page.tsx` is the page at `/pricing`. The file `app/layout.tsx` is the root layout and is required. A folder only becomes a public address once it holds a `page` file (Project structure docs, lastUpdated 21 Jul 2026, https://nextjs.org/docs/app/getting-started/project-structure). The `public` folder holds pictures and other files served as they are.

Tell Claude in these words and it will use the right folder: "Add an About page at /about" or "Put the header and footer in the layout so every page gets them."

## The free parts people use, and their licences

All checked 18 Oct 2026 against the project's own licence file.

Tailwind CSS: MIT licence, copyright Tailwind Labs (https://raw.githubusercontent.com/tailwindlabs/tailwindcss/main/LICENSE). shadcn/ui, a set of ready-made buttons, forms and menus that are copied into your project as files you own: MIT licence (https://raw.githubusercontent.com/shadcn-ui/ui/main/LICENSE.md). Radix Primitives, the accessible building blocks under many of those menus and dialogs: MIT licence, copyright WorkOS (https://raw.githubusercontent.com/radix-ui/primitives/main/LICENSE). Lucide icons: "Released under the ISC License", with a few icons derived from the Feather project under MIT (https://lucide.dev/license). MIT and ISC both allow commercial use if you keep the licence notice; the usual way is to leave the licence files in `node_modules` alone.

Google Fonts: the font collection says "Most of the fonts in the collection use the SIL Open Font License, v1.1", some use Apache 2, and the Ubuntu fonts use their own licence (google/fonts repository, read 18 Oct 2026, https://github.com/google/fonts). The Google Fonts FAQ page could not be read, so the claim that every Google Font is free for commercial use is not confirmed here. Check the licence of the font you pick.

`next/font` loads a Google Font from your own site. The docs say "no requests are sent to Google by the browser when the user visits your site" (Font Optimization, lastUpdated 27 May 2026, https://nextjs.org/docs/app/getting-started/fonts). That helps speed and privacy.

`next/image` is Next.js's picture tag. It serves sizes that fit the device, uses modern formats like WebP, stops the page jumping while pictures load, and loads pictures only when they near the screen (Image Optimization, lastUpdated 1 Apr 2026, https://nextjs.org/docs/app/getting-started/images). The mobile gain is real: a phone does not download a desktop-sized photo. Always ask Claude to use it for photos instead of a plain picture tag, and to write real alt text.

## Where to learn

The official docs are at https://nextjs.org/docs. They assume you know some HTML, CSS, JavaScript and React, so with Claude Code you will read them rather than study them. The free course is Learn Next.js, which builds a full dashboard app step by step and teaches the App Router (https://nextjs.org/learn, read 18 Oct 2026). Nobody in this course needs to finish it. Ask Claude to explain any page of it in plain words.

## Running it on your own computer

You need Node.js version 20.9 or newer (Installation docs, 2 Oct 2026). The docs give the start-up as `npx create-next-app@latest my-app --yes`, then `cd my-app`, then `npm run dev`, then open http://localhost:3000. The default setup includes TypeScript, Tailwind CSS, ESLint, the App Router, Turbopack (the tool that builds the site while you work), the `@/*` import alias and an AGENTS.md file with instructions for AI coding tools (Installation docs, 2 Oct 2026). Localhost means "this computer": nobody else can see that page. Changes you save show up in the browser within a second or so.

Ask Claude: "Check I have Node 20.9 or newer, create the project, start the dev server, and tell me when it is running." Keep the dev server open in one terminal and talk to Claude in another.

Look at it on a phone width straight away. In the browser, open developer tools and switch on the device toolbar, or ask Claude to take screenshots at 390px and 1280px wide. Note 390px is a common phone width, not an official standard.

## What "deploying" means

Deploying means copying your site from your computer onto a computer on the internet that anyone can reach. Two steps happen. A build turns your files into the fast final version (`npm run build`). Hosting then serves that version at an address.

## Git and GitHub in one paragraph

Git keeps a history of your project, so you can go back to any earlier save. GitHub's docs describe Git as "the most popular distributed version control system" and GitHub as the place that hosts Git repositories and adds review and teamwork on top (GitHub Docs, About Git, read 18 Oct 2026, https://docs.github.com/en/get-started/using-git/about-git). A repo is one project folder with its history. A commit is one saved step with a note. A branch is a side copy to try something without touching the main version. Ask Claude: "Make a Git repo, make a first commit, create a private GitHub repo and push it."

## Vercel: from GitHub repo to live site

Vercel connects to your GitHub repo and deploys on its own. Its GitHub page says it "will deploy every push by default", including pushes and pull requests on branches (Deploying GitHub Projects with Vercel, last updated 17 Sep 2026, https://vercel.com/docs/git/vercel-for-github). The steps, which you do in the browser: sign in to Vercel with GitHub, choose Add New Project, pick the repo, accept the detected Next.js settings and press Deploy. The first deployment of a new project is always a production one (Environments, last updated 17 Sep 2026, https://vercel.com/docs/deployments/environments).

Preview versus production. Production is the live site on your real address. A push to your production branch (commonly `main`) updates it. A preview is a private test copy: Vercel makes one when you push any other branch or open a pull request, with its own web address, and posts the link on the pull request (Environments, 17 Sep 2026). The habit that keeps you safe: ask Claude to work on a branch, look at the preview on your phone, and only then merge to `main`. If a bad change goes live, reverting the commit makes the previous production version available again "instantly" (Vercel for GitHub, 17 Sep 2026).

Custom domains. Every deployment gets a `vercel.app` address. For your own name, go to the project's Settings, then Domains, then Add Domain. A bare domain like `example.com` needs an A record at the place you bought it, and a `www` subdomain needs a CNAME record (Adding a Custom Domain, last updated 16 Sep 2026, https://vercel.com/docs/domains/working-with-domains/add-a-domain). The page warns that DNS changes can take time to spread. Add both the bare and the `www` version and set one to redirect to the other. Careful with nameservers: changing them moves all your DNS, including email records, so copy the existing ones first (same page).

Environment variables. These are settings and keys kept outside your code, such as an email-service key. Vercel describes them as "key-value pairs configured outside your source code" that are encrypted at rest, and changes "only apply to new deployments", so redeploy after editing (Environment variables, last updated 17 Sep 2026, https://vercel.com/docs/environment-variables). In Next.js, a variable is private to the server unless its name starts with `NEXT_PUBLIC_`, which puts the value into the code sent to every visitor (Environment Variables guide, lastUpdated 25 Aug 2026, https://nextjs.org/docs/app/guides/environment-variables). Never give a secret that prefix.

## Vercel plans and prices

Read live on https://vercel.com/pricing on 18 Oct 2026, and checked against Vercel's plan docs.

Hobby is $0 a month with one developer seat. Pro is $20 a month. Extra developer seats on Pro are $20 per month each, and viewer seats (read-only people who can see deployments and comment on previews) are free (Pro Plan, last updated 15 Sep 2026, https://vercel.com/docs/plans/pro-plan). The $20 Pro fee includes one deploying seat and $20 of monthly usage credit, which expires unused at month end. Enterprise is custom. Prices exclude tax.

Hobby is for personal, non-commercial use. This is the exact wording from Vercel's Fair Use Guidelines (last updated 14 Sep 2026, read 18 Oct 2026, https://vercel.com/docs/limits/fair-use-guidelines): "Hobby teams are restricted to non-commercial personal use only. All commercial usage of the platform requires either a Pro or Enterprise plan." Commercial use is defined as any deployment "used for the purpose of financial gain of anyone involved in any part of the production of the project, including a paid employee or consultant writing the code." The listed examples include taking payment from visitors, advertising a product or service for sale, being paid to create, update or host the site, affiliate links as the main purpose, and ads. Donations are not commercial. The Terms of Service (last updated 1 Jun 2026, https://vercel.com/legal/terms) say: "You shall only use the Services under a Hobby plan for your personal or non-commercial use."

What this means for you: a site "advertising the sale of a product or service", which is what a business website does, or one you build as a paid consultant for a client, is commercial under that definition, so it needs Pro. A learning site or a course exercise is fine on Hobby. A personal portfolio may be fine, but if it helps you win paid work it may count as financial gain, so ask Vercel support. This is our reading of Vercel's wording, not legal advice.

Hobby allowances (Hobby Plan docs, last updated 14 Sep 2026, https://vercel.com/docs/plans/hobby): 100 GB of data transfer a month, 1 million CDN requests, 1 million function invocations, 100 deployments a day, 50 domains per project. Image Optimization on Hobby: 5,000 transformations a month (Fair Use Guidelines, 14 Sep 2026). The Pro page figure for CDN requests (10 million) did not match the Pro docs (1 million in the included tier), so no Pro request figure is given.

What happens when you go over. On Hobby you cannot pay for more. The pricing page says Hobby users "cannot purchase additional usage", and the Hobby docs say you may "have to wait until 30 days have passed before you can use the feature again" (Hobby Plan, 14 Sep 2026). On Pro, use over the credit is billed as you go. The pricing page calls it "pay as you go, uncapped", but new teams get a default spend alert at $200 per billing cycle that you can change, and you can choose to pause projects at the limit (Pro Plan docs, 15 Sep 2026; pricing page, 18 Oct 2026). Set that budget on day one. A project can also be paused for a budget cap, a usage limit, a policy breach or a platform incident (Vercel Knowledge Base, last updated 2 Oct 2026, https://vercel.com/kb/guide/why-is-my-account-deployment-blocked).

## Vercel Analytics and Speed Insights

Web Analytics counts visitors and page views. It "only stores anonymized data and does not use cookies" (Vercel Web Analytics, last updated 11 Aug 2026, https://vercel.com/docs/analytics). Hobby includes 50,000 events a month with one month of history. Pro includes none and charges $0.03 per 1,000 events, with 12 months of history (Pricing for Web Analytics, last updated 25 Aug 2026, https://vercel.com/docs/analytics/limits-and-pricing). Over the limit on Hobby, there is a three day grace period, then collection stops; wait 7 days or upgrade. A Plus add-on is $10 a month per team.

Speed Insights measures how fast the site feels to real visitors, and the paid tier covers the Core Web Vitals (FCP, LCP, INP, CLS, TTFB). The free tier gives one overall score and 10,000 events over a rolling 30 days shared across the team. At that limit it pauses collection for at least 14 days, "Your sites keep running", with no overage charge (Speed Insights limits and pricing, last updated 23 Sep 2026, https://vercel.com/docs/speed-insights/limits-and-pricing). Plus is $10 per project per month on Pro plus $0.65 per 10,000 events.

Ask Claude: "Add Vercel Web Analytics and Speed Insights to the layout." Mention both are optional. Many marketers use Google Analytics or another tool instead; that is a choice for you, and Next.js works with either.

## Alternatives, in one line

Netlify describes itself as an "All-in-one platform to build, deploy, manage, and extend modern web apps" (https://docs.netlify.com/, read 18 Oct 2026). Cloudflare Pages is for "full-stack applications that are instantly deployed to the Cloudflare global network", and its docs now say "Start new projects with Workers" (https://developers.cloudflare.com/pages/, read 18 Oct 2026). This pack assumes Vercel because Vercel makes Next.js.

## What a beginner breaks, and what to ask

Committing a secret. Next.js's own warning is that you "almost never want to commit" `.env` files, and the starter template already lists them in `.gitignore` (Environment Variables guide, 25 Aug 2026). If a key reaches GitHub, even in a private repo, treat it as leaked: make a new key at the service and delete the old one. Ask Claude: "Check nothing secret is in the repo or its history before the first push." Deleting the file later does not remove it from history.

Huge images. A 6 MB camera photo on a phone is slow and eats allowance. Ask Claude: "Resize every image to the largest size it is shown at, save as WebP or JPEG, and use next/image." On Hobby, Image Optimization has a monthly cap of 5,000 transformations, so oversized photo galleries can use it up.

Forgetting the mobile view. Most marketers build and check on a laptop. Because Tailwind starts from the phone layout, a page that looks wrong on mobile usually means a desktop style was written without a small-screen base. Ask Claude: "Screenshot every page at 390px and 1280px wide, list anything cut off, too small to read, or hard to tap." Check the preview URL on a real phone before merging.

Working straight on `main`. Anything pushed there goes live. Ask for a branch and a preview each time.

Skipping the build. The linter no longer runs during `next build` in Next.js 16 (Installation docs, 2 Oct 2026). Ask Claude to run `npm run build` and the lint command before every push, and to tell you in one line whether they passed.

Using Hobby for a commercial site. See the fair use quote above. If the site sells or advertises your business, budget the $20 a month.

## What to ask Claude Code at each step

1. Set up: "Check Node is 20.9 or newer, create a Next.js app with Tailwind in this folder, start the dev server."
2. Build: "Read the pack files. Show me a wireframe first. Then build the homepage as components, mobile layout first."
3. Check: "Open it at 390px and 1280px wide and critique it using the pack."
4. Save: "Commit with a clear message and push to a new branch."
5. Preview: "Open a pull request and give me the preview link."
6. Go live: "Merge to main once I approve."
7. Domain and keys: "Tell me exactly which DNS records and environment variables I need, and where to click."
8. Watch: "Add Web Analytics and Speed Insights, then tell me what the first week of data says."

## What could not be confirmed

The Google Fonts FAQ page returned no licence text, so general commercial use of every Google Font is not confirmed beyond the repo wording. The Pro-plan CDN request figure differs between two Vercel pages. The Vercel pricing page was read through a summarising fetch tool, so the exact on-page wording of a few lines may differ slightly; the Vercel docs pages were returned in full and carry the quotes above.

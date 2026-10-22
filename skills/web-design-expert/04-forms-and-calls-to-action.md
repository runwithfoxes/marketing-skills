# Forms and calls to action

How to use this note: each section is a decision, with the rule, the reason, the evidence and its source, what changes on a phone, and the usual mistake. "Judgement" marks advice that comes from reading the sources together, not from a tested finding. Saved extracts are in sources/ux/. Source format: (publisher, page title, date, URL).

## 1. One main call to action per section

Rule: each section of a page gets one main button. The whole page can repeat the same main button, but two different main asks side by side split the visitor's attention.

Reason and evidence: GOV.UK's button guidance says to use one default (main) button for the main call to action on a page, to avoid several because it makes it harder to know what to do next, and to use secondary buttons for the rest. If you have many calls to action, simplify the page or split it (GOV.UK Design System, Button, read 18 Oct 2026, https://design-system.service.gov.uk/components/button/). This is a design team's rule from its own testing, not a controlled experiment, but nothing in these sources argues against it.

What a secondary action looks like: a text link or an outline button, quieter than the main one. On the first screen, for example, "Book a call" as the solid button and "See our work" as a link.

On a phone: sections are stacked, so each section's button sits alone, and a full-width button is easier to hit with a thumb (judgement).

Common mistake: three equal buttons in a row, all the same colour ("Learn more", "Get a quote", "Download the guide").

## 2. Button wording

Rule: two to four words, start with a verb, and say what will happen. "Book a 20 minute call", "Get a quote", "Send message". Not "Submit", "Click here" or "Go".

Evidence: NN/g's guidance on button copy says labels should be short (about two to four words), lead with a verb, and say what will happen; it also warns against "OK" in confirmations and says buttons trigger commands while links navigate (Nielsen Norman Group, UI Copy: Buttons and Links, 3 Mar 2019, https://www.nngroup.com/articles/ui-copy/). GOV.UK uses sentence case and describes the action: "Start now", "Sign in", "Continue", "Save and continue" (GOV.UK Design System, Button, read 18 Oct 2026, https://design-system.service.gov.uk/components/button/). NN/g's homepage guidance asks for descriptive labels in place of "Click Here" (Nielsen Norman Group, homepage design principles, 15 Mar 2024, https://www.nngroup.com/articles/homepage-design-principles/).

A word on first person labels ("Get my free quote" against "Get your free quote"). You will see claims that one beats the other by large percentages. Those come from single-site A/B tests posted by vendors, and no source held up, so it should not be made a rule. Pick the one that sounds natural.

What the button promises must be what happens. If it says "Book a call" and goes to a general contact form, that is a broken promise (this is the information scent point from file 03).

On a phone: short labels fit on one line. A label that wraps onto two lines inside a button looks like a mistake.

Common mistake: "Submit" on a contact form. It says nothing about what you get.

## 3. What a button should look like

Rule: the main button is the most obvious solid shape on the screen, with strong contrast against its background and its text. A secondary button is outlined or plain text. Nothing else on the page should look like a button.

Evidence: NN/g says clickable things should keep a clear button shape (a rectangle, ideally with softly rounded corners), have clear borders and consistent styling, and that non-clickable things should not look like buttons. It also reports an early study where clicks rose 416% after a switch from flat to 3D buttons, and says the effect is smaller now but still real (Nielsen Norman Group, Beyond Blue Links: Make Clickable Elements Evident, 8 Mar 2015, https://www.nngroup.com/articles/clickable-elements/). That number is from a 1995 Sun Microsystems test, about 30 years old, so don't quote it as a target. The conclusion that matters: do not let a flat style make buttons ambiguous.

Contrast numbers (WCAG): text on the button needs a contrast ratio of at least 4.5 to 1 for normal text, and the button's edge or fill against the page needs 3 to 1 if the shape is the only way to see it. These are standard WCAG values (W3C WAI, WCAG 2.2 Understanding SC 1.4.3 Contrast (Minimum) and 1.4.11 Non-text Contrast, https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html, quoted from memory and not re-read in this pass). File 02 covers them in detail.

Touch size: WCAG 2.2 says targets need to be at least 24 by 24 CSS pixels (W3C WAI, Understanding SC 2.5.8 Target Size (Minimum), read 18 Oct 2026, https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html). That is the WCAG AA minimum, the level most laws and contracts point to. NN/g suggests at least 1 cm by 1 cm for touch targets (Nielsen Norman Group, Sticky Headers, 4 Apr 2021, https://www.nngroup.com/articles/sticky-headers/). On a phone, make main buttons about 48 pixels high (judgement, a common platform size) and put space between neighbouring buttons.

Common mistake: a button whose colour is the same as the headline or the links, so it does not stand out.

## 4. How long should a form be?

Rule: ask for the fewest things that let you do the next step. For a first contact form that is usually name, email, and a message, and sometimes one choice (what they are interested in).

Evidence, graded:
- Strong on principle: NN/g says to keep forms short, remove fields whose answers can be got elsewhere or later, and gives an example where a form went from six fields to two (Nielsen Norman Group, Website Form Usability: Top 10 Recommendations, 1 May 2016, https://www.nngroup.com/articles/web-form-design/). Baymard's research on shop checkouts found the average checkout in 2024 had 11.3 form fields, that most sites need only about 8, and that 17% of users abandon because of checkout complexity (Baymard Institute, Checkout Flow Average Form Fields, 26 Jun 2024, https://baymard.com/blog/checkout-flow-average-form-fields). That is checkout, not enquiry forms, so treat the numbers as a pointer, not a target for you.
- Mixed on size of effect: vendor and practitioner tests report that fewer fields usually means more people finish, but their figures disagree with each other, none is peer reviewed, and at least one published test found that cutting fields lowered conversions. So the direction is clear and the size is not.
- Against going too far (judgement): fewer fields can mean more poor quality enquiries. If you sell a high value service and get plenty of time wasters, one qualifying question, such as budget range or timing, can be worth the drop.

What to cut first, drawn from Baymard (checkout, 2024): separate first and last name boxes (89% of benchmarked sites had them; 42% of testers typed their full name into the first name box at least once, so use one "Full name" field); a second address line shown by default (75% of sites; 30% of testers paused at it); optional fields like company name, which can sit behind a link (Baymard Institute, Checkout Flow Average Form Fields, 26 Jun 2024, https://baymard.com/blog/checkout-flow-average-form-fields). web.dev agrees about a single name field with autocomplete set to "name" (web.dev, Payment and address form best practices, last updated 9 Dec 2020, https://web.dev/articles/payment-and-address-form-best-practices).

GOV.UK adds a principle worth copying: know why you ask each question and ask only what you need, and ask once (GOV.UK Design System, Question pages, read 18 Oct 2026, https://design-system.service.gov.uk/patterns/question-pages/).

On a phone: typing is the worst part. NN/g says soft-keyboard typing is the biggest pain point on mobile and to keep typed input to a minimum (Nielsen Norman Group, Mobile UX, 19 Apr 2015, https://www.nngroup.com/articles/mobile-ux/). One column, one field per row (NN/g, web form design, 1 May 2016, same URL as above).

Common mistake: asking for phone, company, job title, budget and "how did you hear about us" on a first enquiry.

## 5. Labels above fields, not placeholders

Rule: every field has a visible label above it. Never use the grey text inside the box as the label.

Reason and evidence: NN/g lists seven problems with placeholders as labels: the hint disappears when you start typing, so people forget what the field was; they cannot check their entries before sending; errors are hard to fix; keyboard users tab past it; filled fields get less attention; people mistake it for a pre-filled value; and it has to be deleted by hand (Nielsen Norman Group, Placeholders in Form Fields Are Harmful, 11 May 2014, reviewed 10 Sep 2018, https://www.nngroup.com/articles/form-design-placeholders/). The page does not show the underlying data, so this is NN/g's research conclusion rather than a published study that can be checked.

GOV.UK says the same: every input needs a visible label, placed above the input, short, in sentence case and with no colon, and a placeholder should not replace the label or carry hints (GOV.UK Design System, Text input, read 18 Oct 2026, https://design-system.service.gov.uk/components/text-input/). WCAG 3.3.2 (Level A) requires labels or instructions on any input (W3C WAI, Understanding SC 3.3.2 Labels or Instructions, read 18 Oct 2026, https://www.w3.org/WAI/WCAG22/Understanding/labels-or-instructions.html). web.dev says to link each label to its input with matching `for` and `id` (web.dev, Payment and address form best practices, 9 Dec 2020, https://web.dev/articles/payment-and-address-form-best-practices).

Hint text, if needed, goes between the label and the field, in one short sentence without links (GOV.UK, Text input).

On a phone: labels above also keep the field full width and stop the label sitting off screen to the side.

Common mistake: floating labels that shrink and move on focus. They are a placeholder in disguise and can be hard to read; There is no research on them in these sources, so that is judgement.

## 6. Required and optional fields

Rule: mark which fields are required, and keep optional fields to one or two at most.

Sources disagree on how. NN/g says to mark all required fields, with an asterisk or the word "required", because notes such as "all fields are required" are often skipped (Nielsen Norman Group, Required Fields, 16 Jun 2019, https://www.nngroup.com/articles/required-fields/). GOV.UK says the opposite: add "(optional)" to optional labels and never use asterisks for mandatory fields (GOV.UK Design System, Question pages, read 18 Oct 2026, https://design-system.service.gov.uk/patterns/question-pages/). Both are expert guidance from testing.

Our call for a short contact form (judgement): if every field except one is required, label the one "(optional)" in words. It is clear, needs no legend, and screen readers read the word. If most fields are optional, mark the required ones. NN/g also recommends limiting optional fields to one or two (Nielsen Norman Group, Website Form Usability, 1 May 2016, https://www.nngroup.com/articles/web-form-design/).

## 7. Validation and error messages

Rule: tell people what went wrong, next to the field, in plain words, and keep what they typed.

When to check: sources differ.
- GOV.UK says not to validate when someone leaves a field, and to wait until they press the button, because checking early causes problems for slow typists; it also says to show an error summary at the top and move focus to it, and to put a message by each field with an error (GOV.UK Design System, Validation, read 18 Oct 2026, https://design-system.service.gov.uk/patterns/validation/).
- Baymard, in testing on live shop sites, found 31% of benchmarked sites had no inline validation and recommends checking when the user leaves a field (or when the input reaches its expected length, such as a postcode), clearing the error the moment it is fixed, and showing a tick for correct entries (Baymard Institute, Usability Testing of Inline Form Validation, 9 Jan 2024, https://baymard.com/blog/inline-form-validation). The page does not state the sample size.
- web.dev also advises validating as people type, and always on the server (web.dev, Payment and address form best practices, 9 Dec 2020, https://web.dev/articles/payment-and-address-form-best-practices).

Our call (judgement): for a short contact form, validate when the person leaves a field and again on send, never while they are mid-typing, and always check on the server. That sits between the two views.

How to word errors (GOV.UK Design System, Error message, read 18 Oct 2026, https://design-system.service.gov.uk/components/error-message/): say what happened and how to fix it; avoid "please", "sorry", "invalid", "you forgot" and "oops"; reuse the field's label words; avoid the generic "This field is required". Example in their own guidance: label "How many hours do you work a week?", error "Enter how many hours you work a week". For an email, GOV.UK's email address pattern gives "Enter an email address in the correct format, like name@example.com" (GOV.UK Design System, Email addresses, read 18 Oct 2026, https://design-system.service.gov.uk/patterns/email-addresses/).

Show it: red text after the label, a border on the field, an icon or text so colour is not the only signal. WCAG 3.3.1 (Level A) requires the error be identified and described in text, not by colour or icon alone (W3C WAI, Understanding SC 3.3.1 Error Identification, read 18 Oct 2026, https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html). Do not clear the form. GOV.UK says to keep answers so users can see and edit what went wrong.

Also ignore harmless characters: spaces, hyphens or brackets in a phone number are not errors (GOV.UK, Validation).

On a phone: put the message directly under the field and scroll to the first error, otherwise the person taps send and nothing visible happens.

Common mistake: a red banner at the top that says "Please fix the errors below" with nothing marked below the fold.

## 8. Mobile keyboards, input types and autocomplete

Rule: set the right `type`, `inputmode` and `autocomplete` on every field. It costs nothing and removes typing.

- Email: `type="email"` brings up the keyboard with @; phone: `type="tel"` brings the number pad (web.dev, Payment and address form best practices, 9 Dec 2020, https://web.dev/articles/payment-and-address-form-best-practices). MDN lists the `inputmode` values: numeric, decimal, tel, search, email, url, text, none. It gives a keyboard hint only and does not check the input (MDN, inputmode, last modified 17 Apr 2026, https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/inputmode).
- Avoid `type="number"` for things that are not quantities, such as phone, card or postcode numbers. GOV.UK says it risks accidental changes when scrolling and gives no feedback on non-numeric entry, and suggests a text input with `inputmode="numeric"` (GOV.UK Design System, Text input, read 18 Oct 2026, https://design-system.service.gov.uk/components/text-input/).
- Autocomplete: use the standard values (`name`, `email`, `tel`, `organization`, `postal-code`, `one-time-code`) so the browser fills fields for the person (MDN Web Docs, HTML attribute: autocomplete, read 18 Oct 2026, https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/autocomplete). GOV.UK points out WCAG 2.2 1.3.5 makes this a requirement for production forms where a fitting purpose exists.
- Turn off spellcheck for names and emails: `spellcheck="false"` (GOV.UK, Text input).
- `enterkeyhint` labels the return key ("next", "send") on Android and iOS (web.dev, 9 Dec 2020).
- Disable the send button after a tap to stop double sends, but not while the form is incomplete (web.dev, 9 Dec 2020). Do the same check on the server.
- Font size in fields: keep text at 16px or larger, or iOS Safari zooms in on focus. That is widely known among developers but it was not found in an official Apple or MDN page during this research, so check before relying on it.

Common mistake: a plain text field for email, so phones show the letters keyboard without @.

## 9. Contact form or booking link?

Rule: offer both when you can, and make the choice obvious. A booking link suits people who know they want a conversation, and a form suits people with a question or who are not ready to book.

Evidence: there is no good comparison study in these sources of booking links against contact forms for enquiry conversion, only vendor claims, so this is judgement. The related findings are about trust and friction. In NN/g's trust study, one participant objected that a firm did not state its rate, and the article says contact details should be easy to find (Nielsen Norman Group, Trustworthiness in Web Design, 8 May 2016, https://www.nngroup.com/articles/trustworthy-design/). That is one remark in a small qualitative study, not a finding about prices. So: show an email address in the footer and header alongside the form, and say what happens next ("We reply within one working day").

For a booking link: embed or link a calendar page with a clear promise ("20 minutes, no preparation"), and say what time zone and length. On a phone, check the embedded calendar fits the screen without sideways scrolling.

Common mistake: a "Contact" page with only a form and no sign of who will read it or when they will answer.

## 10. Trust near the button

Rule: put a little real proof close to the button, and keep it specific. Do not stack badges.

What the evidence says, graded:
- Testimonials: in NN/g's small trust study, users trusted independent reviews more than quotes on the company's own site, and every participant said they would read reviews before hiring. They found on-site quotes and case studies useful but suspected only positive ones were shown. NN/g's advice is to link to third-party review sites and show real customers and the service in action (Nielsen Norman Group, Trustworthiness in Web Design, 8 May 2016, https://www.nngroup.com/articles/trustworthy-design/). The study was qualitative and small. A claim going round that named testimonials lift trust by about 20% is attributed to NN/g by blogs, but it could not be found on NN/g's site, so it is not used here.
- Logos: NN/g's trust article does not discuss logo strips. Its footer article says awards and testimonials help lesser-known brands (Nielsen Norman Group, Footers 101, 24 Feb 2019, https://www.nngroup.com/articles/footers/). There is no tested evidence in these sources that a row of client logos raises enquiries. Use only logos of clients who have agreed, and treat it as unproven.
- Security badges: Baymard ran seven surveys between 2013 and 2023 and found that trust seals (which verify the business) ranked above plain encryption seals, and that a homemade fake seal beat most established encryption ones. This tells you the badge's look matters more than any check behind it, which is a reason to be careful about badges. It was about card payment, and Baymard says its results are about perception (Baymard Institute, Perceived Security of Payment Form, published 5 Oct 2016 with results to 2023, https://baymard.com/blog/perceived-security-of-payment-form). Baymard says Symantec, the parent of the Norton seal, is a Baymard client. For a contact form with no payment, badges are unnecessary.
- Privacy line: no study measuring it was found. The reasonable practice (judgement) is one short sentence under the button saying what you will do with their details, for example "We use your email only to reply to you." GOV.UK's hint text rule fits: one short sentence, no links inside hints (GOV.UK Design System, Text input, read 18 Oct 2026, https://design-system.service.gov.uk/components/text-input/). Put the link to your privacy policy in the footer or as plain text after the sentence.

Layout near the button: one short quote with a name, a job and a place, a response promise, and nothing that competes with the button.

On a phone: the proof line goes directly above or below the button so it appears in the same screen. If it is further away, it will be off screen when the person decides.

Common mistake: stock photo avatars with invented names. People spot them, and they undermine the real proof next to them.

## 11. A short checklist for Claude when asked to build or review a form

1. One goal for the form; one main button; label that says what happens.
2. Fields: name (one box), email, message, at most one extra. Everything else needs a reason.
3. Visible labels above, no placeholder-as-label, optional marked in words.
4. Correct `type`, `inputmode`, `autocomplete` on each field; test on a phone.
5. Errors next to the field in plain words, input kept, server check as well.
6. A line under the button on what happens next and how the details are used.
7. Show the wireframe first; list what is evidence and what is judgement.

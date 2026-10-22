---
name: segmentation-audit
description: Audits an existing segmentation study to find out how different the segments really are, using Wiemer Snijders' seven-stage method - similarity to base, correlation, scatter against base, brand size, usage frequency, the genuine discriminators, and purchase triggers. Use when someone has segmentation research or survey data by segment and asks whether the segments are real, how different they are, whether to target them separately, or wants their segmentation stress-tested.
---

# Segmentation audit

Segmentation studies usually make segments look more different than they are. Measured properly, most segments are 89 to 99% the same on how they see a brand, and the few real differences are specific to the category. This audit finds those few. Its most useful answer is often that there are one or two real dimensions, not six segments, and that saves a budget being split six ways.

The method is Wiemer Snijders' (The Commercial Works), shown on National Lottery data. Read `snijders-method.md` first: the data format, the benchmarks and the house style for the output pages.

## The seven stages, in order

Run them in order. Each one says what it needs and what comes next. Reuse the data from earlier stages in the same conversation rather than asking again.

1. `01-similarity.md`: how similar each segment is to the base, in percent.
2. `02-correlation.md`: whether the segments rank the attributes in the same order.
3. `03-scatter.md`: each segment's scores plotted against the base, the 45-degree line.
4. `04-penetration.md`: strip out brand size effects. Needs scores for several brands plus their penetration.
5. `05-usage.md`: test whether the differences are really usage frequency in disguise.
6. `06-discriminators.md`: pull stages 1 to 5 together and name the genuine discriminators, or say there are none.
7. `07-triggers.md`: purchase triggers and occasions by segment, where the exceptions are often the useful part.

If the user has only some of the data, run the stages it allows and say which ones it does not. Never invent a figure to fill a stage.

For a simpler first question, whether one proposed group in a customer file is a segment at all, use the `segmentation-check` skill instead.

---

Part of the marketing skills Paul Dervan gives away alongside his free course, AI Fluency for Ambitious Marketers, at Run with Foxes: https://runwithfoxes.com/course

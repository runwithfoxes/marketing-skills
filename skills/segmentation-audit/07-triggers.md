# stage 7 (`07-triggers.md`) -- Purchase Trigger Analysis (Stage 7 of 7)

You analyse purchase triggers and occasions by segment to find where segmentation actually earns its keep. Brand perceptions are usually uniform across segments (stages 1-6 prove this). But purchase triggers -- what prompts someone to buy in a specific moment -- can vary meaningfully. This is where segmentation adds genuine value.

The Snijders finding: at the National Lottery, even triggers showed 83-92% similarity across segments. But the exceptions were actionable: Risk Takers over-indexed on "saw the Jackpot amounts on a sign" (37% vs 28% base), and Buzzers on "saw someone else buying" (27% vs 20% base). These trigger differences inform physical availability and media strategy, not creative messaging.

Read `snijders-method.md` for the full methodology.

## What you need

Purchase trigger or occasion data by segment:

```
Trigger,Base,Segment1,Segment2,Segment3,...
"Saw it in-store",28,22,37,30,...
"Friend recommended",15,23,12,14,...
"Saw an ad",18,20,16,19,...
"Needed it for a project",12,8,15,13,...
```

If the client doesn't have trigger data, say:

> "Your brand tracker may not include purchase trigger questions. If not, this is a gap worth adding. Triggers tell you WHERE and WHEN to show up, which is more actionable than brand image data. Ask your research agency to add: 'What prompted your most recent purchase/use of [category]?'"

## The calculation

### Similarity analysis (same as stage 1, applied to triggers)

For each segment:
1. Calculate absolute deviation from base on each trigger
2. Average absolute deviation = mean of all trigger differences
3. Similarity % = 100 - average absolute deviation

### Over-indexing analysis

For each trigger in each segment:
1. Index = (Segment score / Base score) * 100
2. Flag triggers where index > 120 (meaningful over-index) or < 80 (meaningful under-index)
3. These are the actionable differences

### Trigger clustering

Group triggers by type:
- **Social triggers:** saw someone else, friend recommended, heard people talking
- **Visual/in-store triggers:** saw display, saw signage, noticed at point of sale
- **Media triggers:** saw an ad, saw online, received an email
- **Situational triggers:** needed it for occasion, had spare money, felt like treating myself
- **Price/promotion triggers:** saw a deal, loyalty reward, price drop

Check if segments over-index on trigger clusters rather than individual triggers. A segment that over-indexes on all social triggers is genuinely different from one that over-indexes on all visual triggers.

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. Trigger similarity table

Same format as stage 1, but for triggers:

| Segment | Similarity to base | Verdict |
|---------|-------------------|---------|
| Risk Takers | 83% | Some meaningful differences |
| Buzzers | 87% | Minor differences |
| Habituals | 92% | Effectively identical |

### 2. Over-indexing heatmap

A matrix with triggers as rows, segments as columns. Cells colour-coded:
- Green: index 120+ (over-index)
- Red: index below 80 (under-index)
- Grey: 80-120 (within normal)

Values shown as index numbers (e.g. 132, 78, 105).

### 3. The actionable triggers

For each trigger that shows meaningful segment variation:

> **"Saw jackpot sign in-store"**: Risk Takers over-index at 132 (37% vs 28% base). This is a physical availability insight, not a creative insight. Risk Takers respond to visible price/prize signals at point of sale. Implication: ensure jackpot signage is prominent and updated frequently.

### 4. Trigger clusters by segment

If segments over-index on trigger clusters:

> "Buzzers respond to social triggers (saw someone else buying, heard people talking). Risk Takers respond to visual/in-store triggers (signage, displays). This distinction is useful for media and distribution strategy, not for brand messaging."

### 5. The Snijders framing

> "Even on purchase triggers, where we expect the most meaningful segment differences, similarity is [X]%. But the exceptions are more actionable than brand image differences. Brand perceptions tell you what people think. Triggers tell you where and when to show up. The latter drives media and distribution strategy; the former rarely survives scrutiny."

### 6. Overall pipeline verdict

Since this is the final stage, provide a summary of the full audit:

> **Full Snijders Audit Summary**
> - Brand perception similarity: [X]% average (from stage 1)
> - Segment correlation: [X]% average (from stage 2)
> - Penetration-adjusted genuine differences: [X] out of [N] (from stage 4)
> - Usage-driven attributes: [X] out of [N] (from stage 5)
> - Genuine discriminators: [X] (from stage 6)
> - Trigger differences: [X] actionable triggers (from stage 7)
>
> **Verdict:** [One sentence -- either "Your segmentation is not supported by the evidence" or "Your segmentation has [X] genuine dimensions, primarily on [triggers/discriminator]"]

If earlier stages weren't run, only summarise what's available and note the gaps.

## Save

Ask before saving. Default: `segmentation/07-triggers.html` in the current folder.

## Gotchas

1. **Triggers are more actionable than perceptions.** Even if brand perceptions are uniform (stages 1-5), trigger differences can justify different distribution, media, or POS strategies. This is the positive finding -- segmentation isn't useless, it just works differently than people think.
2. **Trigger data is often not in the tracker.** Many brand trackers measure perceptions but not purchase triggers. Flag this as a gap and recommend adding trigger questions to the next wave.
3. **Beware small base sizes.** Triggers are often multi-response questions with low base rates per trigger. A 37% vs 28% difference sounds large but may not be significant if the segment has 80 respondents. Flag base sizes if available.
4. **Triggers inform WHERE to show up, not WHAT to say.** A segment that over-indexes on in-store triggers needs better physical availability, not a different ad campaign. Keep the interpretation practical.

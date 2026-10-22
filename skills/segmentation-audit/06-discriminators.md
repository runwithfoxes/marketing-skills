# stage 6 (`06-discriminators.md`) -- Isolate Genuine Discriminators (Stage 6 of 7)

You synthesise findings from stages 1-5 to answer the question: after stripping out similarities, penetration effects, and usage frequency, what actually discriminates between these segments? The answer is usually 1-2 attributes. Sometimes zero.

This is the diagnostic climax of the Snijders audit. Everything before this was building the evidence. This skill delivers the verdict.

Read `snijders-method.md` for the full methodology.

## What you need

Findings from earlier stages in this conversation or saved HTML files from previous runs. The skill synthesises, it doesn't recalculate. If earlier stages haven't been run, say:

> "This stage synthesises the findings from the earlier analyses. Run stage 1 (`01-similarity.md`) first, then as many of stages 2-5 as you have data for. I'll pull them together."

If the user has partial results (e.g. stages 1-3 but not 4-5), work with what's available and note the gaps.

## The synthesis

### Step 1: Collect candidate discriminators

From each completed stage, gather the potential signals:
- **Stage 1 (Similarity):** attributes with largest absolute deviations per segment
- **Stage 2 (Correlation):** the lowest-correlation segment pair and which attributes drive the divergence
- **Stage 3 (Scatter):** dots furthest from the 45-degree diagonal
- **Stage 4 (Penetration):** residuals exceeding 8 points
- **Stage 5 (Usage):** attributes with non-monotonic or reverse-monotonic patterns

### Step 2: Cross-reference

A genuine discriminator must survive multiple tests:
- It should appear as an outlier in similarity AND scatter AND (if available) penetration residuals
- It should NOT show monotonic decline in the usage test (if available) -- otherwise it's a usage artifact
- It should be conceptually coherent: the attribute makes sense as a category-specific discriminator, not a generic quality judgement

### Step 3: Classify

For each candidate:
- **Genuine discriminator:** survives all available tests. Category-specific. Actionable.
- **Usage artifact:** appears different across segments but is explained by usage frequency. Not actionable for targeting.
- **Noise:** appears in one test but not others. Sample size or measurement artifact.

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. The verdict (2-3 sentences, bold)

> "Across [N] attributes and [N] segments, [X] genuine discriminators survive all tests: [list them]. Everything else is similarity, size, or usage frequency. Your segmentation has [X] actionable dimension[s], not [N]."

### 2. Discriminator cards

For each genuine discriminator, a card showing:
- **The attribute:** what it is
- **The pattern:** which segments score differently and in what direction
- **Why it's genuine:** which tests it survived (similarity outlier, non-monotonic in usage, residual > 8)
- **Why it matters:** what this means for the category (this is category-specific and requires interpretation)
- **What to do with it:** one actionable recommendation

### 3. The eliminated candidates

A table of attributes that looked like discriminators but weren't:

| Attribute | Why it looked different | Why it's not genuine |
|-----------|----------------------|---------------------|
| "Fun brand" | 15-point spread across segments | Monotonic decline with usage -- just frequency |
| "Premium quality" | Buzzer segment scores 12 points above base | Buzzers are heaviest users; user-effect |

### 4. The similarity summary

Restate the overall finding: "[X]% of all attribute-segment combinations are within [Y] points of the base. The segments perceive the brand almost identically."

### 5. Strategic implications

Frame around what the client should do differently:
- If 0 discriminators: "Your segments are not meaningfully different on brand perception. Targeting different messages to different segments is not supported by the data. Consider reaching all category buyers with consistent creative."
- If 1-2 discriminators: "You have [X] genuine dimension[s] of difference. Build your segmentation strategy around [this/these], not around the full segment scheme. Everything else can be served with the same message."
- If 3+ discriminators: "Unusual. You have genuine multi-dimensional segmentation. Verify with the usage test (stage 5) to ensure these aren't category-usage artifacts."

### 6. What to do next

> "Run stage 7 (`07-triggers.md`) to check whether purchase occasions and triggers vary by segment. Triggers often show more genuine variation than brand perceptions."

## Save

Ask before saving. Default: `segmentation/06-discriminators.html` in the current folder.

## Gotchas

1. **Don't manufacture discriminators.** If nothing survives the tests, the answer is zero. That's the most valuable finding you can deliver -- it saves the client from building a targeting strategy on sand.
2. **Category-specific interpretation required.** A discriminator in lottery ("Greedy brand") means something different from a discriminator in banking ("Hidden fees") or tech ("For business vs personal"). The skill identifies WHAT discriminates; Paul interprets WHY it matters.
3. **The client may resist.** They paid for a segmentation study that told them they have 6 distinct segments. You're telling them they have 1-2 genuine dimensions at most. Frame it as freeing, not diminishing: "You don't need 6 campaigns. You need 1 campaign that addresses [the discriminator]."

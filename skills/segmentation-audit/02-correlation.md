# stage 2 (`02-correlation.md`) -- Segment Correlation Matrix (Stage 2 of 7)

You build a Pearson correlation matrix across all segment pairs to show whether segments rank brand attributes in the same order. High correlations (0.86+) mean the segments see the brand essentially the same way -- they just differ in intensity.

Read `snijders-method.md` for the full methodology.

## What you need

Same data as stage 1 (`01-similarity.md`): brand attribute scores by segment. If the user already ran stage 1 in this conversation, reuse the same data. If not, ask for it.

## The calculation

For each pair of segments (S1, S2):
1. Take the vector of attribute scores: V1 = [S1_A1, S1_A2, ...], V2 = [S2_A1, S2_A2, ...]
2. Calculate Pearson correlation coefficient r
3. Present as percentage (r * 100) to match Snijders format

Also calculate:
- Average correlation across all pairs
- Minimum and maximum pair correlation
- Which pair has the lowest correlation (the most "different" segments)

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. Correlation matrix (heatmap)

A segment x segment matrix with correlation values. Colour-code cells:
- 95-100%: deep green -- identical ordering
- 86-94%: light green -- very similar ordering
- 70-85%: amber -- some divergence
- Below 70%: red -- genuinely different (rare)

### 2. Key statistics

- **Average correlation:** [X]% (Snijders found 91% average across NL's 8 segments)
- **Lowest pair:** [Segment A] vs [Segment B] at [X]% -- these are your most "different" segments
- **Highest pair:** [Segment A] vs [Segment B] at [X]% -- these segments are indistinguishable

### 3. Interpretation

One paragraph:

> "When two segments correlate at [X]%, it means they rank brand attributes in almost exactly the same order. They may score slightly higher or lower overall (that's an intensity difference, usually driven by usage frequency), but their priorities, perceptions, and associations are the same. You are not looking at two different audiences -- you are looking at the same audience at different levels of engagement."

### 4. The Snijders comparison

> "For comparison, the National Lottery's 8 segments -- designed to capture genuinely different motivational profiles -- correlated at 0.71-0.99 (average 0.91). Even the most divergent pair (Buzzers vs Disengaged) correlated at 0.71. Your segments correlate at [range], averaging [X]%."

### 5. What to do next

> "To see this visually, run stage 3 (`03-scatter.md`). To check whether these similarities survive once you strip out brand size effects, run stage 4 (`04-penetration.md`)."

## Save

Ask before saving. Default: `segmentation/02-correlation.html` in the current folder.

## Gotchas

1. **High correlation does not mean identical scores.** Two segments can correlate at 0.98 while one scores 20 points higher on everything. Correlation measures ordering, not level. The level difference is usually a usage-frequency effect (stage 5 tests this).
2. **Low correlation in one pair demands investigation.** If most pairs are 0.90+ but one pair is 0.72, check which attributes drive the divergence. It may be one outlier attribute pulling the correlation down.
3. **Small number of attributes inflates variance.** With fewer than 10 attributes, correlations can swing widely on a single data point. Flag this if the dataset has fewer than 10 attributes.

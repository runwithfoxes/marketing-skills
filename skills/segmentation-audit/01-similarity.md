# stage 1 (`01-similarity.md`) -- Segment Similarity Analysis (Stage 1 of 7)

You calculate percentage similarity between each segment and the base across all brand attributes. This is the opening move in the Snijders segmentation audit: before looking at differences, establish the baseline of similarity.

Read `snijders-method.md` for the full methodology, data format, and benchmarks.

## What you need

A table of brand image/attribute scores by segment. Columns = segments (plus a Base/Total column). Rows = attributes. Values = percentages.

Accept CSV file drop, Excel file drop, or pasted table. Parse according to the rules in `snijders-method.md`.

If no data is provided, ask:

> Drop your brand tracker data as a CSV -- columns for each segment, rows for each attribute, values as percentages. Include a Base or Total column.

If no Base column exists, calculate base as the mean across all segments.

## The calculation

For each segment S:
1. For each attribute A: calculate the absolute difference |Score_S_A - Score_Base_A|
2. Average absolute deviation = mean of all absolute differences for that segment
3. **Similarity % = 100 - average absolute deviation**

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. Similarity scores table

| Segment | Similarity to base | Verdict |
|---------|-------------------|---------|
| Segment A | 96% | Effectively identical |
| Segment B | 93% | Effectively identical |
| Segment C | 89% | Minor differences only |

**Verdict thresholds** (from Snijders benchmarks):
- 95%+ = "Effectively identical to base"
- 89-94% = "Minor differences only"
- 80-88% = "Some meaningful differences -- investigate"
- Below 80% = "Genuine segment differentiation -- rare, check for outlier attributes"

### 2. Similarity bar chart

Horizontal bar chart, one bar per segment, scale 0-100%. Draw a reference line at 89% (the lowest similarity Snijders found even in his most divergent NL segment). Cream background, clean styling.

### 3. The differences that exist

For each segment, list the top 3 attributes with the largest absolute deviations from base. Show the segment score, base score, and difference. This surfaces where to look, not a conclusion -- those come in later stages.

### 4. Headline verdict

One paragraph. Frame around the Snijders finding:

> "Across [N] attributes and [N] segments, the average similarity to base is [X]%. For comparison, Snijders found 89-99% similarity across the National Lottery's 8 segments, and Ehrenberg found brand user profiles differ by only 2-3 percentage points across 42 product categories. Your segments [are/are not] meaningfully different on brand perceptions."

### 5. What to do next

Point to the next stage:

> "Similarity scores tell you how different the segments are overall. To see whether they rank attributes in the same order, run stage 2 (`02-correlation.md`). To see this visually, run stage 3 (`03-scatter.md`)."

## Save

Ask before saving. Default: `segmentation/01-similarity.html` in the current folder.

## Gotchas

1. **One outlier attribute can drag similarity down.** If one segment scores 89% similarity but all others are 95%+, check which attributes are driving the deviation. Flag them explicitly -- they may be genuine discriminators or they may be noise.
2. **Don't over-interpret small differences.** A 94% similarity score does not mean "6% different in a meaningful way." It means the average deviation across all attributes is 6 percentage points. Most individual attributes will be within 2-3 points.
3. **Base column matters.** If no base is provided and you calculate it as the mean, say so in the output. The base should ideally be the total sample, not the mean of segments (which can differ if segments are unequal sizes).

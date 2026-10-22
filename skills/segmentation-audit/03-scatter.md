# stage 3 (`03-scatter.md`) -- 45-Degree Scatter Plots (Stage 3 of 7)

You build scatter plots showing each segment's attribute scores vs the base. If points cluster on the 45-degree diagonal, there is no segmentation in brand perception. This is the visual proof -- the chart that makes the point land in a client meeting.

Read `snijders-method.md` for the full methodology.

## What you need

Same data as stages 1-2. Reuse if already in conversation.

## The chart

For each segment, create a scatter plot:
- **X-axis:** Base score per attribute (0-100%)
- **Y-axis:** Segment score per attribute (0-100%)
- **Each dot:** one brand attribute, labelled on hover
- **Reference line:** 45-degree diagonal from (0,0) to (100,100) -- represents perfect similarity
- **R-squared value:** displayed on the chart

Build using Chart.js in the HTML output. Interactive: hover over dots to see attribute names and scores.

### Layout

If 4 or fewer segments: 2x2 grid of charts on one page.
If 5-8 segments: 2-column layout, scrollable.
If 9+: paginated.

Each chart should be ~400x400px with clear axis labels.

### Styling

- Dots: solid circles, 8px radius, orange (#F47521) with 80% opacity
- Diagonal line: dashed, grey (#999)
- Background: cream (#FAFAF8)
- Outlier dots (residual > 8 points from diagonal): highlighted in red with label visible by default

## The coin-flip validation (optional but powerful)

If the user asks for it, or if the data has enough respondents:

> "Want me to add the coin-flip comparison? I'll randomly split the base into two halves and show the same scatter plot -- it will look identical to the segment plots, proving the observed differences are within normal sampling variation."

To simulate this without raw respondent data: generate two random halves of the base scores by adding gaussian noise (SD = 2-3 points, matching typical sampling error for brand tracker data) and plot them against each other. Label it "Random split (simulated)" with a note explaining the method.

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. Scatter plot grid

One chart per segment, all on the same page with the same axis scales.

### 2. Outlier table

List any attributes where a segment deviates more than 8 points from the base:

| Segment | Attribute | Segment score | Base score | Deviation |
|---------|-----------|--------------|------------|-----------|
| Risk Takers | "Saw jackpot sign" | 37% | 28% | +9 |

If no outliers exceed 8 points, say so explicitly: "No attributes deviate more than 8 points from base in any segment."

### 3. Visual verdict

One line per segment under its chart:
> "12 attributes, all within 5 points of the diagonal. R² = 0.94. This segment sees the brand the same way the total market does."

### 4. What to do next

> "The scatter shows brand perception is uniform across segments. To check whether this holds when you strip out brand size effects, run stage 4 (`04-penetration.md`). To test whether the segment differences are really usage frequency in disguise, run stage 5 (`05-usage.md`)."

## Save

Ask before saving. Default: `segmentation/03-scatter.html` in the current folder.

## Gotchas

1. **Label the outliers.** Any dot more than 8 points from the diagonal should be labelled by default, not just on hover. These are the potential discriminators.
2. **Same scale on all charts.** All scatter plots must use the same 0-100 axis range so they're visually comparable.
3. **Don't over-produce.** If there are 15 segments, ask the user which ones to chart. Plotting all 15 creates visual noise.

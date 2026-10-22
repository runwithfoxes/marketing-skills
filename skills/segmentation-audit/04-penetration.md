# stage 4 (`04-penetration.md`) -- Penetration Adjustment (Stage 4 of 7)

You strip out brand size effects to show whether "brand differences" are genuine or just reflections of penetration. Bigger brands score higher on everything because more people have used them and familiarity inflates all scores. This skill removes that effect and shows what's left.

The Snijders demonstration: 75 data points (5 brands x 15 attributes) collapsed to effectively 1 data point once penetration was removed. Only one brand-attribute combination (Brand 3 on "Stylish Design", residual of -8) showed a genuine signal.

Read `snijders-method.md` for the full methodology.

## What you need

Different data from stages 1-3. This needs **multi-brand data**:

```
Brand,Penetration,Attr1,Attr2,Attr3,...
"Brand A",48,52,45,68,...
"Brand B",23,31,28,42,...
"Brand C",12,18,15,29,...
```

Columns: brand name, penetration %, then one column per brand image attribute (% agreeing).
Rows: one per brand in the category.

If the user doesn't have multi-brand data (only their own brand), this skill can't run. Say so:

> "This stage needs attribute scores for multiple brands in the same category, plus penetration figures for each. It shows that what looks like brand differentiation is really just size. If you only have your client's data, skip to stage 5 (`05-usage.md`)."

## The calculation

For each attribute:
1. Plot each brand's score (Y-axis) against its penetration (X-axis)
2. Fit a simple linear regression: Expected_score = a + b * Penetration
3. For each brand: Residual = Actual_score - Expected_score
4. Residuals near zero = penetration explains the score entirely
5. Large residuals (>8 points) = genuine brand-specific signal

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. Raw scatter plots

For 2-3 key attributes, show the scatter plot with regression line:
- X-axis: Brand penetration (%)
- Y-axis: Attribute score (%)
- Each dot = one brand, labelled
- Regression line drawn through the data
- R-squared displayed

### 2. The residual waterfall

A bar chart centred on zero. One bar per brand-attribute combination (so 5 brands x 15 attributes = 75 bars). Bars sorted by magnitude. Most bars should cluster near zero. Outliers (>8 points) highlighted in red with labels.

This is the "75 data points to 1" visual. The chart should make the point viscerally: almost everything is noise.

### 3. Outlier table

| Brand | Attribute | Actual | Expected (from penetration) | Residual |
|-------|-----------|--------|----------------------------|----------|
| Brand C | Stylish Design | 18% | 26% | -8 |

If no residuals exceed 8 points: "No brand-attribute combinations show genuine differentiation beyond what penetration predicts."

### 4. Perceptual map (if 4+ brands)

2D scatter of brands positioned by their residual profiles. Use the two principal components from the residual data as axes (or the two attributes with largest residual variance if PCA is too complex to explain). The map should show most brands clustering together, with outliers pulled away on their genuine differentiator.

### 5. Headline verdict

> "Across [N] brands and [N] attributes ([N x N] data points), [X] show residuals greater than 8 percentage points. Penetration explains [Y]% of the variance in brand image scores. The 'brand differences' your tracker reports are largely size differences."

### 6. What to do next

> "Now we know brand perceptions are driven by size, not positioning. To check whether your segment differences are really usage frequency in disguise, run stage 5 (`05-usage.md`)."

## Save

Ask before saving. Default: `segmentation/04-penetration.html` in the current folder.

## Gotchas

1. **Minimum 4 brands needed.** With fewer than 4 data points, regression is meaningless. Say so and skip.
2. **Penetration must be measured consistently.** Past-year penetration, past-month penetration, and "ever bought" will give different results. Ask which measure is being used.
3. **The residual threshold of 8 is empirical, not absolute.** Snijders used it because it matched the largest genuine signal in his data. For categories with very high or very low base rates, the threshold may need adjusting. Flag this if the overall attribute scores are very high (>80%) or very low (<15%).

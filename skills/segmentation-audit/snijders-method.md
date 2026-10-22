# Snijders Segmentation Audit Methodology

Shared reference for all 7 segmentation audit skills. Based on Wiemer Snijders (The Commercial Works) methodology, demonstrated on National Lottery data (105-slide presentation).

## The core argument

Segmentation research routinely overstates differences between segments and understates similarities. When you measure similarities properly, most segments are 89-99% identical on brand perceptions. The genuine discriminators are few and category-specific. Usage frequency, not segment membership, drives most "attitudinal differences."

## Data input format

All skills accept data as:
- **CSV file drop** (preferred): columns = segments, rows = attributes, values = % agreeing
- **Excel file drop**: same structure, first sheet used
- **Pasted table**: markdown or tab-separated, parsed the same way

### Required data structure

**Minimum viable input** (skills 1-3):
```
Attribute,Base,Segment1,Segment2,Segment3,...
"Supports good causes",74,83,76,71,...
"Fun brand",45,52,44,43,...
"Trustworthy",68,72,69,65,...
```

**For penetration adjustment** (skill 4):
```
Brand,Penetration,Attr1,Attr2,Attr3,...
"Brand A",48,52,45,68,...
"Brand B",23,31,28,42,...
```

**For usage-drives-attitudes** (skill 5):
```
Attribute,Heavy,Medium,Light,Non-user
"Supports good causes",83,76,71,45,...
```

**For purchase triggers** (skill 7):
```
Trigger,Base,Segment1,Segment2,Segment3,...
"Saw jackpot sign in-store",28,22,37,30,...
```

## Parsing rules

1. First column is always the attribute/trigger/brand label
2. First row is always headers (segment names or frequency bands)
3. Values are percentages (0-100). Strip % signs if present
4. "Base", "Total", "All", or "Overall" column = the comparison benchmark
5. If no base column, calculate base as mean across all segments
6. Handle both comma-separated and tab-separated input
7. Ignore empty rows and columns

## Calculation reference

### Percentage similarity (skills 1, 7)
For each segment S:
1. For each attribute A: difference = |Score_S_A - Score_Base_A|
2. Average absolute deviation = mean of all differences
3. Similarity % = 100 - average absolute deviation

### Pearson correlation (skill 2)
For each pair of segments (S1, S2):
1. Take vectors of attribute scores: V1 = [S1_A1, S1_A2, ...], V2 = [S2_A1, S2_A2, ...]
2. Calculate Pearson r between V1 and V2
3. Present as percentage (r * 100) to match Snijders format

### Residual analysis (skill 4)
For each attribute across multiple brands:
1. Plot attribute score (Y) against brand penetration (X)
2. Fit linear regression line
3. Residual = actual score - predicted score from regression
4. Residuals near zero = penetration explains the score
5. Large residuals = genuine brand-specific signal

### Monotonicity test (skill 5)
For each attribute across usage frequency bands:
1. Check if scores decline monotonically from heavy to non-user
2. If yes: usage drives this attitude, not genuine segment difference
3. If no (score rises for lighter users, or is flat): potential genuine signal

### Over-indexing (skill 7)
For each trigger in each segment:
1. Index = (Segment score / Base score) * 100
2. Values > 120 = meaningful over-index
3. Values < 80 = meaningful under-index
4. Values 80-120 = within normal variation

## Output conventions

Every stage outputs a light-mode HTML page. Use the user's own brand if they have one; otherwise this house style:
- Cream background (#FAFAF8), clean typography
- Light mode only, no dark backgrounds
- Charts rendered in HTML/CSS/JS (Chart.js or inline SVG)
- Each output stands alone as a client deliverable
- Save path: ask before saving. Default: a `segmentation/` folder in the current folder.

## Snijders benchmarks

These are empirical norms from the Snijders presentation, not arbitrary thresholds:
- **Similarity 89%+**: effectively no segmentation in brand perception (NL range: 89-99%)
- **Correlation 0.86+**: segments rank attributes in same order (NL range: 0.71-0.99, avg 0.91)
- **Residuals within +/-8 points**: noise, not signal
- **MAD 1.7 average**: across 32 categories, brand buyer profiles differ by <2 points on average
- No hard cutoffs. The argument is inductive: even segments designed to be different produce these numbers

## The pipeline

| Stage | Skill | What it proves |
|-------|-------|---------------|
| 1 | stage 1 (`01-similarity.md`) | Segments are 89-99% identical on brand perceptions |
| 2 | stage 2 (`02-correlation.md`) | Segments rank attributes in the same order |
| 3 | stage 3 (`03-scatter.md`) | Visual proof - points on the 45-degree diagonal |
| 4 | stage 4 (`04-penetration.md`) | "Brand differences" are really size differences |
| 5 | stage 5 (`05-usage.md`) | "Segment differences" are really usage frequency differences |
| 6 | stage 6 (`06-discriminators.md`) | The 1-2 genuine signals, category-specific |
| 7 | stage 7 (`07-triggers.md`) | Where segmentation actually earns its keep |

Skills 1-3 use the same input data (attribute scores by segment). Skill 4 needs multi-brand penetration data. Skill 5 needs usage frequency bands. Skill 6 synthesises findings from 1-5. Skill 7 needs purchase trigger/occasion data.

## Academic sources

- Ehrenberg & Kennedy (2001): 32-category MAD table, brand segmentation analysis
- Romaniuk, Bogomolova & Dall'Olmo Riley (2012): usage drives attitudes framework
- Romaniuk & Sharp (2000): usage drives attitudes evidence
- Colombo, Ehrenberg & Sabavala (2000): automotive repeat purchase / double jeopardy
- Ehrenberg, Uncles & Goodhardt (2004): FMCG purchase frequency / penetration
- Sharp & Sharp (1997), Sharp, Kennedy & Danenberg (2017): how brands grow model
- Binet & Field (2017): SOV/SOM equilibrium
- Kantar Worldpanel (2016): shopper base distribution

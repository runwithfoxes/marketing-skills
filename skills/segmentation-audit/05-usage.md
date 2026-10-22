# stage 5 (`05-usage.md`) -- Usage Drives Attitudes Test (Stage 5 of 7)

You test whether the differences between segments are genuine attitudinal differences or just reflections of how often each segment uses the product. Heavier users rate brands higher on everything. If your "segment differences" are really just usage frequency wearing a different hat, your segmentation is not telling you anything actionable.

The Snijders finding: at the National Lottery, weekly players scored brand attributes at an average of 49, non-players at 25. All attributes declined monotonically with usage frequency except one ("Greedy brand", which reversed). The segment "differences" were usage differences.

Read `snijders-method.md` for the full methodology.

## What you need

Brand attribute scores broken by usage frequency, not by segment:

```
Attribute,Heavy,Medium,Light,Non-user
"Supports good causes",83,76,71,45
"Fun brand",62,48,35,18
"Greedy brand",36,42,48,52
```

If the client doesn't have this breakdown, the skill can't run. Ask:

> "Can you cut your brand image data by purchase/usage frequency instead of by segment? I need the same attributes scored by heavy, medium, light, and non-users."

If they have both segment AND usage frequency data, that's ideal -- you can run the three-effect analysis.

## The calculation

### Monotonicity test

For each attribute:
1. List scores from heaviest to lightest usage band
2. Check if scores decline monotonically (each step lower than the previous)
3. **Monotonic decline = usage drives this attitude.** The perception is a byproduct of using the product, not a genuine brand meaning.
4. **Non-monotonic = potential genuine signal.** An attribute that rises for lighter users, or stays flat, may represent something real about the brand that exists independently of usage.
5. **Reverse monotonic = diagnostic gold.** An attribute that increases as usage decreases (like "Greedy brand" at the NL) is a genuine discriminator -- lighter users/non-users actively hold this perception.

### Three-effect decomposition (if data available)

When you have both segment data and usage frequency data:
1. **User-effect:** difference between current users' average score and non-users' average score across all attributes. This is the dominant driver.
2. **Brand-effect:** residual differences between brands after controlling for user-effect. Small.
3. **Category-effect:** baseline attribute levels driven by category norms. Constant across brands.

## Output

Generate an HTML page (house style in snijders-method.md) with:

### 1. The monotonicity table

| Attribute | Heavy | Medium | Light | Non-user | Pattern | Signal? |
|-----------|-------|--------|-------|----------|---------|---------|
| Supports good causes | 83 | 76 | 71 | 45 | Monotonic decline | Usage-driven |
| Fun brand | 62 | 48 | 35 | 18 | Monotonic decline | Usage-driven |
| Greedy brand | 36 | 42 | 48 | 52 | Reverse monotonic | GENUINE SIGNAL |
| Trustworthy | 55 | 53 | 50 | 48 | Flat | Possible signal |

Colour-code the Signal column: green for usage-driven, red for genuine signal, amber for flat/unclear.

### 2. The slope chart

For each attribute, draw a line from Heavy to Non-user. Most lines should slope downward (usage-driven). Lines that slope upward or stay flat are the signals. Visually, the chart should show a waterfall of parallel declining lines with 1-2 exceptions standing out.

### 3. User-effect magnitude

> "The average difference between heavy users and non-users across all attributes is [X] percentage points. This is the user-effect -- the dominant driver of brand perception scores. Your segments contain different mixes of heavy, medium, light, and non-users, which is why they score differently. The segment labels are describing usage frequency, not attitudes."

### 4. The genuine signals

List any attributes that break the monotonic pattern:

> "Out of [N] attributes, [X] show monotonic decline (usage-driven) and [Y] show genuine signal. The genuine signals are: [list with scores]. These are the only perceptions that exist independently of how often someone uses the product."

### 5. What to do next

> "Now we know which perceptions are usage-driven and which are genuine. Run stage 6 (`06-discriminators.md`) to synthesise all findings and identify the true discriminators. Run stage 7 (`07-triggers.md`) to check whether purchase occasions vary by segment."

## Save

Ask before saving. Default: `segmentation/05-usage.html` in the current folder.

## Gotchas

1. **"Heavy" and "light" must be defined consistently.** Ask what the frequency bands are. Some trackers define "heavy" as weekly, others as top quartile. This matters.
2. **Small base sizes in extreme bands.** Very heavy and very light users may have small sample sizes, making their scores volatile. Flag if any frequency band has fewer than 50 respondents.
3. **Category matters.** In high-involvement categories (cars, insurance), the user-effect may be smaller because even non-users have strong opinions. In low-involvement (FMCG, lottery), the user-effect will be dominant. Set expectations accordingly.

# Chart Selection and Visual Design Guide

Use the chart that matches the analytical task and variable types.

| Question | Recommended chart | Watch out for |
|---|---|---|
| How does a metric change over time? | Line, step, area (sparingly) | Time order, missing periods |
| Which categories are largest? | Sorted bar / horizontal bar | Long labels, truncated axis |
| What is the distribution? | Histogram, KDE, ECDF | Bins, bandwidth, sample size |
| Are there extreme values? | Box, violin, strip, swarm | Outlier definition and sample size |
| Are two numeric variables related? | Scatter, hexbin, 2D density | Overplotting, confounding |
| How do groups differ? | Box, violin, point + interval | Unequal group sizes |
| What is the composition? | Stacked bar, 100% stacked bar, treemap | Hard-to-compare segments |
| How does a process convert? | Funnel | Stage definitions and denominators |
| How do values vary across two dimensions? | Heatmap | Color scale and ordering |
| How do values vary by geography? | Choropleth, symbol map | Projection, geographic aggregation |
| What is the hierarchy? | Treemap, sunburst, icicle | Too many nested categories |
| How does a metric flow/change? | Waterfall, Sankey | Clear definitions and scale |
| How do values compare against a target? | Bullet chart, dot plot, reference line | Consistent scale |
| How do many variables relate? | Pair plot, correlation heatmap | Correlation is not causation |
| How does a distribution accumulate? | ECDF | Tie handling and sample size |

## Additional chart families to learn

- **Comparison:** grouped bar, dot plot, lollipop, slope chart, dumbbell chart.
- **Time series:** line, step, area, stacked area, candlestick (financial OHLC), calendar heatmap.
- **Distribution:** histogram, KDE, ECDF, box, violin, strip, swarm, rug, ridgeline.
- **Relationship:** scatter, bubble, hexbin, 2D histogram, contour, regression/residual plot.
- **Composition:** stacked bar, 100% stacked bar, pie/donut (few categories only), treemap, sunburst, waterfall, Sankey.
- **Flow/process:** funnel, Sankey, chord diagram, network graph.
- **Matrix:** heatmap, clustered heatmap, correlogram.
- **Geospatial:** point map, bubble map, choropleth, hex map, flow map.
- **Specialized:** radar (carefully), parallel coordinates, ternary, polar, error bars, forest plot, survival curve.

## Design checklist

- State the question in the title or subtitle.
- Label axes with units and define metrics.
- Use a zero baseline for ordinary bar charts unless a justified alternative is clearly marked.
- Use color consistently and accessibly; do not rely on color alone.
- Avoid 3D effects when they obscure comparisons.
- Show sample size and uncertainty when relevant.
- Avoid unnecessary chart junk and excessive gridlines.
- Include data source, date range and caveats.

# Chart Config

Source: `src/config/chartConfigs.ts`

## CHART_COLORS

- `primary: string[]`
- `secondary: string[]`
- `gradients: { blue: [start,end]; green: [start,end]; purple: [start,end]; orange: [start,end] }`
- `treemap: string[]`

## getBaseChartConfig(): Partial<Highcharts.Options>

- Transparent background, theme-aware tooltips/legend.

## getAxisConfig()

- Theme-aware grid/label styles.

## getLineChartConfig()

- Datetime x-axis, numeric y-axis with locale formatting.

## getColumnChartConfig()

- Category x-axis, rounded columns.

## getPieChartConfig()

- Selectable slices with data labels.

## getTreemapChartConfig()

- Treemap defaults with dark tooltip.
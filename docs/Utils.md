# Utilities

## lib/utils.ts

### cn(...inputs: ClassValue[]): string

Tailwind class merge utility using clsx + tailwind-merge.

```ts
import { cn } from '@/lib/utils'
<div className={cn('p-2', isActive && 'bg-blue-500')} />
```

## utils/csvParser.ts

- `parseCSVFile(file: File): Promise<{ data: CursorDataRow[]; error?: string }>` — parses CSV, strips quotes, filters to active users.
- `validateCSVHeaders(headers: string[]): boolean`

## utils/dataAggregation.ts

- `type AggregationPeriod = 'day'|'week'|'month'`
- `aggregateDataByPeriod(data, period): CursorDataRow[]` — aggregates metrics, injects synthetic rows with `Email = "{N} active users"` and period start dates.
- `formatPeriodLabel(date: string, period: AggregationPeriod): string`

## utils/metricsCalculator.ts

`calculateMetrics(data, baseFilteredData, { linesPerMinute, pricePerHour, cursorPricePerUser })`

Returns human-formatted totals:
- `totalAcceptedLines`, `activeUsers`, `acceptanceRate`, `estimatedHoursSaved`, `estimatedMoneySaved`, `roi`

## utils/chartHelpers.ts

- `createDateTooltipFormatter(seriesName, valueFormatter?)`
- `createCategoryTooltipFormatter(seriesName, valueFormatter?)`
- `createPercentageFormatter()`
- `transformToTimeSeriesData([{ date, value }])`
- `transformToCategoryData([{ category, value }])`

## utils/exportUtils.ts

- `exportToImage(): Promise<void>` — renders `[data-export="dashboard-main"]` to PNG via html2canvas and downloads it.

Example

```ts
await exportToImage()
```
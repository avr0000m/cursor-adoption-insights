# Charts

All charts accept `data: CursorDataRow[]`. Time-based charts also accept `aggregationPeriod: 'day'|'week'|'month'`.

Common helpers

- Base config from `getBaseChartConfig`, `getLineChartConfig`, `getColumnChartConfig`, `getPieChartConfig`, `getTreemapChartConfig`.
- Tooltip helpers: `createDateTooltipFormatter`, `createCategoryTooltipFormatter`.

## CumulativeChart

Props: `{ baseFilteredData: CursorDataRow[]; aggregationPeriod }`

- Cumulative accepted vs suggested lines over selected period.

```tsx
<CumulativeChart baseFilteredData={baseFilteredData} aggregationPeriod={filters.aggregationPeriod} />
```

## AcceptanceRateChart

Props: `{ data; aggregationPeriod }`

- Daily/weekly/monthly acceptance rate (% accepted/suggested).

```tsx
<AcceptanceRateChart data={filteredData} aggregationPeriod={filters.aggregationPeriod} />
```

## AverageAskRequestsChart, AverageTabsAcceptedChart

Props: `{ data; aggregationPeriod }`

- Averages per user-day.

```tsx
<AverageAskRequestsChart data={filteredData} aggregationPeriod={filters.aggregationPeriod} />
<AverageTabsAcceptedChart data={filteredData} aggregationPeriod={filters.aggregationPeriod} />
```

## ChatRequestTypesChart

Props: `{ data; aggregationPeriod }`

- Stacked columns for Agent, Cmd+K, Ask, Edit, Bugbot.

```tsx
<ChatRequestTypesChart data={filteredData} aggregationPeriod={filters.aggregationPeriod} />
```

## ModelUsageChart

Props: `{ data }`

- Pie chart of `Most Used Model` frequency.

```tsx
<ModelUsageChart data={filteredData} />
```

## DayOfWeekChart

Props: `{ data }`

- Column chart of accepted lines by weekday. Auto-rotates labels on mobile.

```tsx
<DayOfWeekChart data={filteredData} />
```

## ClientVersionChart

Props: `{ data; aggregationPeriod }`

- Stacked columns of client versions across periods.

```tsx
<ClientVersionChart data={filteredData} aggregationPeriod={filters.aggregationPeriod} />
```

## ProgrammingLanguageTreemap

Props: `{ data }`

- Treemap built from `Most Used Apply Extension`.

```tsx
<ProgrammingLanguageTreemap data={filteredData} />
```

## TabExtensionWordCloud

Props: `{ data }`

- Lightweight positioned word cloud from `Most Used Tab Extension`.

```tsx
<TabExtensionWordCloud data={filteredData} />
```

## ApplyExtensionWordCloud / EnhancedWordCloud

- `ApplyExtensionWordCloud({ data })` computes word counts from `Most Used Apply Extension` and renders `EnhancedWordCloud`.
- `EnhancedWordCloud({ data, title, helpText, colors })` responsive spiral layout with collision detection.

```tsx
<ApplyExtensionWordCloud data={filteredData} />
```
## Common Components

### ChartContainer

Props: `{ title: string; helpText: string; children: ReactNode; className?: string }`

```tsx
import { ChartContainer } from '@/components/common/ChartContainer'

<ChartContainer title="My Chart" helpText="What this chart shows">
  {/* chart component */}
</ChartContainer>
```

### BaseHighchart

Props: `{ options: Partial<Highcharts.Options>; className?: string }`

```tsx
import { BaseHighchart } from '@/components/common/BaseHighchart'

<BaseHighchart options={{ series: [{ type: 'line', data: [[Date.now(), 1]] }] }} />
```

### MetricCard

Props: `{ title: string; value: string; gradient: string; tooltip: React.ReactNode }`

```tsx
<MetricCard title="Accepted Lines" value="12,345" gradient="from-blue-500 to-blue-600" tooltip="Total accepted lines" />
```

### PrivacyFooter

Simple footer with privacy text.

```tsx
<PrivacyFooter />
```

### LinkedInFollowButton

Icon button linking to a profile.

```tsx
<LinkedInFollowButton />
```

## Dashboard Shell Components

### DashboardHeader

Props: `{ showReloadButton?: boolean; onReloadCSV?: () => void; showExportButton?: boolean; showSettingsButton?: boolean }`

- Integrates export via `exportToImage()` and opens settings drawer.

```tsx
<DashboardHeader 
  showReloadButton={true}
  onReloadCSV={() => {/* reload */}}
  showExportButton
  showSettingsButton
/>
```

### DashboardSettings

Props: `{ open: boolean; onOpenChange(next: boolean): void }`

- Edits global settings; mirrors `SettingsContext` values.

```tsx
<DashboardSettings open={open} onOpenChange={setOpen} />
```

### DashboardFilters

Props: `{ data: CursorDataRow[]; onFiltersChange(filters) }`

- Bundles `DateRangePicker`, `AggregationPeriodSelector`, `UserSelector`, and `FilterActions`.

```tsx
<DashboardFilters data={data} onFiltersChange={updateFilters} />
```

### DashboardMetrics

Props: `{ data, originalData, baseFilteredData }`

- Computes KPI cards with `calculateMetrics` and context settings.

```tsx
<DashboardMetrics data={filtered} originalData={original} baseFilteredData={baseFiltered} />
```

### DashboardCharts

Props: `{ data, originalData, baseFilteredData, aggregationPeriod, selectedUsers? }`

- Renders rows of charts based on `settings.chartVisibility`.

```tsx
<DashboardCharts data={filtered} originalData={original} baseFilteredData={baseFiltered} aggregationPeriod={filters.aggregationPeriod} selectedUsers={filters.selectedUsers} />
```

### ExampleShowcase / ExportButton / FileUpload

- `ExampleShowcase`: marketing showcase card with image and CTA.
- `ExportButton`: downloads dashboard as image using html2canvas.
- `FileUpload({ onFileUpload, isLoading })`: drag-and-drop CSV uploader using react-dropzone.

```tsx
<FileUpload onFileUpload={handleFileUpload} isLoading={isLoading} />
```
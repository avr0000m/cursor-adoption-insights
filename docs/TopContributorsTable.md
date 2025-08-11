# Adoption Champions Table (TopContributorsTable)

Entry point: `src/components/dashboard/charts/TopContributorsTable/index.ts`

## Component

`TopContributorsTable({ data, isFiltered? })`

- `data: CursorDataRow[]`
- `isFiltered?: boolean` — when true, hides the Show All/Top 10 toggle.

```tsx
import { TopContributorsTable } from '@/components/dashboard/charts/TopContributorsTable'

<TopContributorsTable data={filteredData} isFiltered={selectedUsers.length > 0} />
```

## Types

- `PerformanceSegment = 'Champion'|'Producer'|'Explorer'|'Starter'`
- `ContributorWithSegment` includes totals, acceptanceRate, userROI, segment.
- `SortableColumn` and `columnLabels` for headers.

## Data Processing

`useContributorData(data, linesPerMinute, pricePerHour, cursorPricePerUser)`

- Aggregates per-user stats and computes `acceptanceRate`, `userROI`, and `segment`.

## Sorting

- `useTableSorting()` returns `{ sortConfig, handleSort }`.
- `useSortedContributors(contributors, sortConfig)` returns sorted list.
- `getAriaSort(col, sortConfig)` for accessibility.

## Segments

- `getPerformanceSegment(acceptanceRate, chatTotalApplies, userROI)`
- `getSegmentIcon(segment)`, `getSegmentBadgeStyle(segment)`, `getSegmentCalculationExplanation(...)`, `getSegmentDescription(segment)`

## Subcomponents

- `SortableTableHead({ column, label, sortConfig, onSort })`
- `ContributorRow({ contributor })`
- `PerformanceSegmentBadge({ segment, contributor })` — highlights related columns on hover and shows calculation tooltip.
- `TableHoverProvider`/`useTableHover()` provides hover/highlight state.
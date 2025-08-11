## useDashboardData

Aggregates file upload and filtering logic for the dashboard.

Returns

- `originalData: CursorDataRow[]`
- `filteredData: CursorDataRow[]` (aggregated by selected period)
- `baseFilteredData: CursorDataRow[]` (filtered by date/user but not re-aggregated)
- `isLoading: boolean`
- `handleFileUpload(file: File)`
- `updateFilters(filters)`
- `filters` (dateRange, selectedUsers, aggregationPeriod)
- `handleReloadCSV()` clears dataset and filters

Example

```tsx
const {
  originalData,
  filteredData,
  baseFilteredData,
  isLoading,
  handleFileUpload,
  updateFilters,
  handleReloadCSV,
  filters,
} = useDashboardData()
```

## useDataFiltering(originalData)

- Manages `filters` and computes `filteredData` and `baseFilteredData`.
- `updateFilters(newFilters)` and `resetFilters()`.

```ts
const { filteredData, baseFilteredData, filters, updateFilters, resetFilters } = useDataFiltering(data)
```

## useFileUpload

- `data`, `isLoading`, `handleFileUpload(file)`, `resetData()`.
- Uses CSV parser and toast notifications.

```ts
const { data, isLoading, handleFileUpload } = useFileUpload()
```

## useIsMobile

- Returns boolean indicating viewport < 768px.

```ts
const isMobile = useIsMobile()
```

## useToast / toast

- `useToast()` returns `{ toasts, toast, dismiss }` stateful API.
- `toast({ title, description, action, variant })` shows a toast. Render `<Toaster />` once at root (from `src/components/ui/toaster`).

```tsx
import { useToast } from '@/hooks/use-toast'

function SaveButton() {
  const { toast } = useToast()
  return (
    <button onClick={() => toast({ title: 'Saved', description: 'Changes persisted' })}>
      Save
    </button>
  )
}
```
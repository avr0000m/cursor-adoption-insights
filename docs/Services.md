# Services

## analytics

Anonymous analytics wrapper for `window.gtag` (if present).

- `trackFileUpload(fileSize?: number)`
- `trackExport(exportType: 'image'|'pdf' = 'image')`
- `trackFilterUsage(filterType: string)`
- `trackCsvReload()`
- `trackSettingsOpen()`

Usage

```ts
import { analytics } from '@/services/analytics'

analytics.trackFilterUsage('dateRange')
```
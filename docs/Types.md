# Types

## CursorDataRow

Defined in `src/pages/Index.tsx` for CSV rows.

Required headers (see `validateCSVHeaders`):

- Date, User ID, Email, Is Active,
- Chat Suggested Lines Added/Deleted,
- Chat Accepted Lines Added/Deleted,
- Chat Total Applies/Accepts/Rejects,
- Chat Tabs Shown, Tabs Accepted,
- Edit Requests, Ask Requests, Agent Requests, Cmd+K Usages,
- Subscription Included Reqs, API Key Reqs, Usage Based Reqs, Bugbot Usages,
- Most Used Model, Most Used Apply Extension, Most Used Tab Extension, Client Version

Example row

```ts
const row: CursorDataRow = {
  Date: '2024-05-01',
  'User ID': 'u-1',
  Email: 'dev@acme.com',
  'Is Active': 'true',
  'Chat Suggested Lines Added': '100',
  'Chat Suggested Lines Deleted': '0',
  'Chat Accepted Lines Added': '40',
  'Chat Accepted Lines Deleted': '0',
  'Chat Total Applies': '0',
  'Chat Total Accepts': '0',
  'Chat Total Rejects': '0',
  'Chat Tabs Shown': '0',
  'Tabs Accepted': '5',
  'Edit Requests': '2',
  'Ask Requests': '7',
  'Agent Requests': '1',
  'Cmd+K Usages': '3',
  'Subscription Included Reqs': '0',
  'API Key Reqs': '0',
  'Usage Based Reqs': '0',
  'Bugbot Usages': '0',
  'Most Used Model': 'gpt-4',
  'Most Used Apply Extension': 'ts',
  'Most Used Tab Extension': 'tsx',
  'Client Version': '0.38.2'
}
```

## TopContributors types

See `src/components/dashboard/charts/TopContributorsTable/types.ts` for `PerformanceSegment`, `ContributorWithSegment`, `SortableColumn`, `columnLabels`.
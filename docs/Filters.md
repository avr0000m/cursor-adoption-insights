# Filters

## DateRangePicker

Props: `{ data: CursorDataRow[]; value: DateRange | undefined; onChange(value) }`

- Computes min/max dates from data and constrains selection.

```tsx
<DateRangePicker data={data} value={dateRange} onChange={setDateRange} />
```

## AggregationPeriodSelector

Props: `{ value: AggregationPeriod; onChange(value) }`

```tsx
<AggregationPeriodSelector value={aggregationPeriod} onChange={setAggregationPeriod} />
```

## UserSelector

Props: `{ users: string[]; selectedUsers: string[]; onChange(next: string[]) }`

- Popover with multi-select checkboxes. Includes Select All / Clear All.

```tsx
<UserSelector users={uniqueUsers} selectedUsers={selected} onChange={setSelected} />
```

## FilterActions

Props: `{ onApply(): void; onClear(): void }`

```tsx
<FilterActions onApply={handleApply} onClear={handleClear} />
```
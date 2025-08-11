## Settings Context

- Provider: `SettingsProvider`
- Hook: `useSettings()` returns
  - `settings`: `{ linesPerMinute: number; theme: 'light'|'dark'; pricePerHour: number; cursorPricePerUser: number; chartVisibility: { cumulativeChart; acceptanceRateChart; modelUsageChart; chatRequestTypesChart; averageAskRequestsChart; averageTabsAcceptedChart; tabExtensionWordCloud; programmingLanguageTreemap; dayOfWeekChart; clientVersionChart; topContributorsTable } }`
  - `setSettings(next: Settings)`
  - `updateSetting<K extends keyof Settings>(key: K, value: Settings[K])`
  - `toggleChartVisibility(key: keyof ChartVisibility)`
  - `showAllCharts()` / `hideAllCharts()`
  - `resetDefaults()`

Example

```tsx
import { SettingsProvider, useSettings } from '@/contexts/SettingsContext'

function ChartToggle() {
  const { settings, toggleChartVisibility } = useSettings()
  return (
    <button onClick={() => toggleChartVisibility('cumulativeChart')}>
      {settings.chartVisibility.cumulativeChart ? 'Hide' : 'Show'} Cumulative
    </button>
  )
}

export function AppRoot() {
  return (
    <SettingsProvider>
      <ChartToggle />
    </SettingsProvider>
  )
}
```

## Theme Provider

- Provider: `ThemeProvider`
- Hook: `useTheme()` returns `{ theme: 'light'|'dark'; setTheme(theme) }`
- Integrates with settings: internally reads and updates `settings.theme`.

Example

```tsx
import { ThemeProvider, useTheme } from '@/components/ThemeProvider'
import { SettingsProvider } from '@/contexts/SettingsContext'

function ThemeToggleButton() {
  const { theme, setTheme } = useTheme()
  return (
    <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
      Toggle Theme
    </button>
  )
}

export function AppRoot({ children }: { children: React.ReactNode }) {
  return (
    <SettingsProvider>
      <ThemeProvider>
        <ThemeToggleButton />
        {children}
      </ThemeProvider>
    </SettingsProvider>
  )
}
```

## ThemeToggle component

- `ThemeToggle`: Small icon button that toggles theme using `useTheme()`.

Usage

```tsx
import { ThemeToggle } from '@/components/ThemeToggle'

<ThemeToggle />
```
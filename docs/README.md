# Project Documentation

This documentation covers all public APIs, functions, hooks, context providers, components, utilities, configuration, and services in this repository, with examples and usage guidance.

- Components
  - See `docs/Components.md` (layout and common components)
  - See `docs/Charts.md` (all dashboard charts)
  - See `docs/Filters.md` (dashboard filter controls)
  - See `docs/TopContributorsTable.md` (adoption champions table)
  - See `docs/UI.md` (UI primitives from `src/components/ui`)
- Hooks: `docs/Hooks.md`
- Context: `docs/Context.md`
- Utilities: `docs/Utils.md`
- Configuration: `docs/Config.md`
- Services: `docs/Services.md`
- Types: `docs/Types.md`

Quick start

- The main page is `src/pages/Index.tsx`. It demonstrates end-to-end usage of settings, filters, data hooks, charts, and metrics.
- For theming, wrap your app with `SettingsProvider` and `ThemeProvider`. Use `ThemeToggle` to switch themes.
- For notifications, use `useToast` and render a `Toaster` component once at the root.
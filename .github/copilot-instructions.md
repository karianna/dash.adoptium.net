# Copilot Instructions for Adoptium Dashboard

## Project Overview
- This is a React-based dashboard for Adoptium download statistics, using TypeScript, Vite, Parcel, and Ant Design (antd).
- The main entry point is `index.html` and the app is bootstrapped from `src/index.js` or `src/index.tsx` (if present).
- Major UI components are under `src/Components/` and `src/Graph/`.
- Data fetching and API logic is in `src/api.tsx`.
- The project uses Highcharts for data visualization, with custom chart components in `src/Graph/`.

## Build & Test Workflows
- Install dependencies: `npm install`
- Start local dev server: `npm start` (Parcel, runs at http://localhost:3000)
- Build static files: `npm run build` (outputs to `dist`)
- Run tests: `npm test` (Vitest)
- Coverage: `npm run coverage`
- Test setup and mocks are in `vitest-setup.ts`.

## Patterns & Conventions
- Use functional React components and hooks.
- UI layout and navigation are managed via Ant Design (`antd`) and custom components in `src/Components/NavigationMenu/`.
- All charts (bar, line, pie, etc.) are implemented as separate components in `src/Graph/` and use Highcharts.
- Test files are colocated in `__tests__` directories next to the code they test.
- Use TypeScript for all new code; legacy JS files remain for compatibility.
- Use ESM imports/exports throughout (see `package.json` with `type: module`).
- Custom SVG handling is configured in `vitest.config.ts`.

## Integration & External Dependencies
- Relies on `highcharts` and `highcharts-react-official` for chart rendering.
- Uses `express` for any server-side logic (see `server.tsx`).
- Ant Design (`antd`) and `@ant-design/icons` for UI.
- Parcel is used for local dev, Vite for test/build tooling.

## Examples
- See `src/Graph/BarChart.tsx` for a typical chart component.
- See `src/Components/NavigationMenu/index.tsx` for navigation patterns.
- See `src/api.tsx` for data fetching logic.
- See `src/Graph/__tests__/BarChart.test.tsx` for test structure and patterns.

## Notes
- When updating dependencies, check for breaking changes in Vite, Parcel, antd, and Highcharts.
- Use ESM syntax everywhere; avoid CommonJS.
- For new features, prefer co-locating tests in `__tests__` folders next to the code.
- If you add new chart types, follow the structure in `src/Graph/` and update navigation as needed.

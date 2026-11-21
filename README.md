# PikNirnay (पीक निर्णय)

An interactive, frontend-only crop advisory demonstration for Maharashtra. It shows how a farmer could compare crop suitability, estimated costs and returns, loss risk, sowing windows, and the reasons behind a recommendation.

> **Important:** All crop, market, weather, and dashboard figures are illustrative demonstration data. They are not verified agricultural advice or live information. Confirm decisions with a local agriculture officer.

## Run locally

Requirements: Node.js 20 or later.

```bash
npm install
npm run dev
```

Create a production build with `npm run build`; preview it with `npm run preview`. Vite outputs to `dist/`. `vercel.json` includes SPA fallback rewrites so nested routes work on refresh.

## Routes

- Public: `/`, `/how-it-works`, `/language`, `/welcome`, `/demo-access`
- Farmer: `/farmer/dashboard`, `/farmer/farm-profile`, `/farmer/advisory/setup`, `/farmer/advisory/results`, `/farmer/advisory/compare`, `/farmer/advisory/why/:cropId`, `/farmer/sowing-calendar`, `/farmer/mandi`, `/farmer/weather`, `/farmer/expert`, `/farmer/history`, `/farmer/settings`
- Expert: `/expert/dashboard`, `/expert/cases`, `/expert/cases/:caseId`, `/expert/crop-rules`
- Admin: `/admin/dashboard`, `/admin/crops`, `/admin/data-sources`, `/admin/data-freshness`, `/admin/users`, `/admin/expert-cases`, `/admin/models`, `/admin/audit-logs`

Expert routes share the interactive sample case desk. Admin routes provide the sample overview, tables, and detail views.

## Data and persistence

The configurable crop catalogue lives in `src/data/crops.ts`; interface translations live in `src/i18n/translations.ts`. User language, farm profile, advisory choices, and expert cases persist in browser `localStorage`. The demonstration does not use a server, account system, OTP, live weather, live mandi prices, or a trained prediction model.

## Deploy to Vercel

Import this repository into Vercel or run the Vercel CLI from the project folder after signing in. Use the Vite defaults: build command `npm run build`, output directory `dist`. No environment variables are required. Publish the source to GitHub first if deploying through Vercel's Git integration.

## Known limits and next work

- The pilot district is intentionally not selected. Location examples are configurable.
- Crop return, cost, risk, suitability, weather and market examples have not been reviewed or validated by agronomists.
- Language switching is persisted and Marathi/Hindi/English labels are provided for core navigation and key actions; much explanatory content remains in English in this prototype.
- Voice prompts, real expert responses, data integrations, authentication, offline caching, and production administration are not connected.
- Before a real pilot, validate the crop rules and data sources with local experts, build and test translations and voice flows with farmers, evaluate any prediction model against baselines, and define privacy, safety, and operational processes.

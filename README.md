# Purchasing Power Dashboard -- Dollar Debasement vs Bitcoin

An interactive data visualization dashboard that tracks the erosion of US dollar purchasing power since 1971 and compares it to Bitcoin's performance. Built with Astro, Chart.js, and Tailwind CSS.

![Screenshot](screenshot.png)

[![Astro](https://img.shields.io/badge/Astro-5.x-BC52EE?logo=astro&logoColor=white)](https://astro.build)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.x-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Chart.js](https://img.shields.io/badge/Chart.js-4.x-FF6384?logo=chartdotjs&logoColor=white)](https://www.chartjs.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Features

- **Dollar purchasing power chart** -- interactive line chart showing the decline from $1.00 (1971) to present, indexed to the Nixon Shock
- **Bitcoin price history chart** -- annual average BTC price with a toggle between linear and logarithmic scale
- **Stats cards** -- at-a-glance metrics: total debasement percentage, average annual CPI inflation, Bitcoin CAGR, and Bitcoin total return multiple
- **Purchasing power calculator** -- enter any dollar amount and year to see its real purchasing power today vs. what it would be worth if converted to Bitcoin
- **Educational section** -- expandable cards explaining CPI, the Cantillon Effect, the Nixon Shock, and Bitcoin's fixed supply
- **Dark theme** -- deep navy palette with Bitcoin-orange accents and JetBrains Mono for data display
- **Custom color system** -- navy/BTC-orange/red-accent/green-accent defined via Tailwind 4 `@theme`
- **Interactive tooltips** -- hover over any chart data point for detailed values
- **Responsive layout** -- works on mobile through wide desktop
- **Static output** -- pre-rendered HTML, deploys anywhere (Vercel, Netlify, Cloudflare Pages)
- **Zero JavaScript frameworks** -- vanilla JS for Chart.js initialization and calculator logic only

## Tech Stack

| Layer         | Technology                                                         |
| ------------- | ------------------------------------------------------------------ |
| Framework     | [Astro 5.x](https://astro.build) (static output)                  |
| Styling       | [Tailwind CSS 4](https://tailwindcss.com) via `@tailwindcss/vite`  |
| Charts        | [Chart.js 4](https://www.chartjs.org)                              |
| Fonts         | Google Fonts (Inter + JetBrains Mono)                              |
| Data          | Static JSON (BLS CPI-U data, CoinGecko/CoinMetrics BTC averages)  |

## Project Structure

```
btc-dashboard/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── BtcPriceChart.astro         # BTC price chart with log-scale toggle
│   │   ├── ComparisonCalculator.astro  # Interactive purchasing power calculator
│   │   ├── Education.astro             # Explainer cards (CPI, Cantillon, etc.)
│   │   ├── PurchasingPowerChart.astro  # Dollar purchasing power decline chart
│   │   └── StatsCards.astro            # Summary statistics grid
│   ├── data/
│   │   ├── btc.json                    # Annual BTC price data
│   │   └── cpi.json                    # Annual CPI-U data from 1971
│   ├── layouts/
│   │   └── Layout.astro                # Base HTML shell with meta tags
│   ├── pages/
│   │   └── index.astro                 # Main dashboard page
│   └── styles/
│       └── global.css                  # Tailwind 4 theme (navy + BTC-orange palette)
├── astro.config.mjs
├── tsconfig.json
└── package.json
```

## Quick Start

```bash
# Clone the repository
git clone https://github.com/SeekerErebus/btc-dashboard.git
cd btc-dashboard

# Install dependencies
npm install

# Start the dev server
npm run dev
```

The site will be running at `http://localhost:4321`.

## Commands

| Command           | Action                                      |
| :---------------- | :------------------------------------------ |
| `npm install`     | Install dependencies                        |
| `npm run dev`     | Start dev server at `localhost:4321`         |
| `npm run build`   | Build production site to `./dist/`           |
| `npm run preview` | Preview the production build locally         |

## Customization

1. **Data** -- Update `src/data/cpi.json` and `src/data/btc.json` with newer annual figures
2. **Colors** -- Modify the `@theme` block in `src/styles/global.css` to adjust the navy/orange palette
3. **Educational content** -- Edit the sections array in `src/components/Education.astro`
4. **Calculator defaults** -- Change the default amount and year in `ComparisonCalculator.astro`

## Live Demo

[View Live Demo](#) <!-- Replace with deployed URL -->

## License

MIT

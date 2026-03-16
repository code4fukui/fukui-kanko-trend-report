# Fukui Tourism Location Trend Report
日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

An interactive web application that visualizes tourism activity trends for Fukui Prefecture, Japan by aggregating and analyzing impression counts from online maps and web search tools.

## Features

- **Area-Level & Prefectural Aggregation**: View data for individual regions or all of Fukui Prefecture combined
- **Time Series Analysis**: Analyze data at daily, weekly, or monthly granularity
- **Dual-Period Comparison**: Compare trends across two different time periods side-by-side
- **Comprehensive Metrics**: Map impressions, web searches, route searches, call button clicks, website clicks, review submissions, review ratings, and average rating
- **Data Export**: Download visualized data in CSV format

## Requirements

- Node.js 20.19+ or 22.12+

## Usage

```bash
# Clone the repository
git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
cd fukui-kanko-trend-report

# Ensure Node.js is installed
nvm install 22.12.0
nvm use 22.12.0

# Install dependencies
corepack enable
corepack use pnpm@10.11.0
pnpm install

# Start the development server
pnpm dev
```

After the development server starts, open the URL shown in your terminal (typically `http://localhost:5173`) in your browser.

## Data

This application uses tourism activity data for Fukui Prefecture, Japan. The data is collected and maintained in a [separate repository](https://github.com/code4fukui/fukui-kanko-trend-data).

## License
This project is licensed under the [MIT License](LICENSE).

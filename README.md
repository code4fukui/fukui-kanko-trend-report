# Fukui Tourism Location Trend Report

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

An interactive web application that visualizes tourism activity trends for Fukui Prefecture, Japan by aggregating and analyzing impression counts from online maps and web search tools.

**[View the Application](https://code4fukui.github.io/fukui-kanko-trend-report/)**

## Key Features

-   **Area-Level & Prefectural Aggregation**: View data for 13 individual regions or all of Fukui Prefecture combined.
-   **Time Series Analysis**: Analyze data at daily, weekly, or monthly granularity.
-   **Dual-Period Comparison**: Compare trends across two different time periods side-by-side.
-   **Comprehensive Metrics**: Visualize trends for map searches, web searches, route searches, calls, website clicks, review submissions, and star ratings.
-   **Data Export**: Download the visualized data in CSV format for further analysis.

## Data Source

The data for this application is sourced from the [fukui-kanko-trend-data](https://github.com/code4fukui/fukui-kanko-trend-data) repository, which is included as a Git submodule.

-   **Format**: CSV
-   **Columns**: `Date`, `Map Searches`, `Web Searches`, `Route Searches`, `Calls`, `Website Clicks`, `Reviews Submitted`, `5-Star Reviews`, `4-Star Reviews`, `3-Star Reviews`, `2-Star Reviews`, `1-Star Reviews`, `Average Rating`.
-   **Automation**: Data is updated automatically via a scheduled GitHub Actions workflow.

## Technology Stack

-   **Frontend**: React 19, TypeScript
-   **Build Tool**: Vite
-   **Styling**: Tailwind CSS, shadcn/ui
-   **Charts**: Recharts
-   **State Management**: React Context API
-   **Package Manager**: pnpm

## Getting Started

### Prerequisites

-   Node.js 20.19+ or 22.12+
-   Git

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
    cd fukui-kanko-trend-report
    ```

2.  **Enable Corepack and set pnpm version:**
    Corepack is a script that acts as a bridge between Node.js and package managers. It is included with all Node.js versions starting from 16.9.0.
    ```bash
    corepack enable
    corepack use pnpm@10.11.0
    ```

3.  **Initialize the data submodule and install dependencies:**
    ```bash
    git submodule update --init --recursive
    pnpm install
    ```

4.  **Run the development server:**
    ```bash
    pnpm dev
    ```
    Open your browser to `http://localhost:5173`.

## Available Scripts

| Command        | Description                               |
| -------------- | ----------------------------------------- |
| `pnpm dev`     | Starts the development server.            |
| `pnpm build`   | Builds the app for production.            |
| `pnpm preview` | Serves the production build locally.      |
| `pnpm lint`    | Runs ESLint to check for code quality.    |

## Deployment

Changes pushed to the `main` branch are automatically built and deployed to GitHub Pages via the workflow defined in `.github/workflows/pages.yml`.

## Contributing

Contributions are welcome. Please follow the existing code style and submit a pull request.

## License

This project is licensed under the MIT License.

---

Maintained by [Code for FUKUI](https://github.com/code4fukui).
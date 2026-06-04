# Fukui Tourism Location Trend Report

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

An interactive web application that visualizes tourism activity trends for Fukui Prefecture, Japan by aggregating and analyzing impression counts from online maps and web search tools.

**[View the Application](https://code4fukui.github.io/fukui-kanko-trend-report/)**

## Overview

This application aggregates impression data from online maps and web search tools for tourist locations across Fukui Prefecture and visualizes trends through interactive charts. It helps stakeholders understand tourism patterns and popularity of different regions within Fukui.

## Key Features

- **Area-Level & Prefectural Aggregation**: View data for individual regions or all of Fukui Prefecture combined  
- **Time Series Analysis**: Analyze data at daily, weekly, or monthly granularity  
- **Dual-Period Comparison**: Compare trends across two different time periods side-by-side  
- **Comprehensive Metrics**:  
  - Map impressions and searches  
  - Web search impressions  
  - Route search impressions  
  - Call button clicks  
  - Website clicks  
  - Review submissions  
  - Review count by star rating (1-5 stars)  
  - Average rating  
- **Data Export**: Download visualized data in CSV format  

## Supported Regions

The application collects data for 13 cities within Fukui Prefecture:

- Awara City (あわら市)  
- Ikeda Town (池田町)  
- Ōi Town (おおい町)  
- Eihei-ji Town (永平寺町)  
- Echizen City (越前市)  
- Katsuyama City (勝山市)  
- Minamiechizen Town (南越前町)  
- Takahama Town (高浜町)  
- Tsuruga City (敦賀市)  
- Wakasa Town (若狭町)  
- Obama City (小浜市)  
- Mihama Town (美浜町)  
- Ōno City (大野市)  

## Usage Guide

1. **Select Area**: Choose between viewing data for the entire Fukui Prefecture ("All Areas") or a specific region  
2. **Select Time Unit**: Choose the time granularity - daily, weekly, or monthly aggregation  
3. **Select Date Range**: Use the calendar picker to choose the analysis period  
4. **Enable Comparison** (Optional): Check the comparison checkbox to enable a second date range for side-by-side comparison  
5. **View Analysis**: Examine two chart views:  
   - **Impression Trends**: Shows impression and interaction counts over time  
   - **Review Trends**: Shows review submission and rating data over time  
6. **Export Data** (Optional): Download the displayed data as a CSV file for further analysis  

## Data Source

The data for this application is sourced from the [fukui-kanko-trend-data](https://github.com/code4fukui/fukui-kanko-trend-data) repository, included as a Git submodule.  

- **Format**: CSV  
- **Columns**:  
  | Column Name | Description |  
  | --- | --- |  
  | `Date` | Date in YYYY-MM-DD format |  
  | `Map Searches` | Number of map searches |  
  | `Web Searches` | Number of web searches |  
  | `Route Searches` | Number of route searches |  
  | `Calls` | Number of call button clicks |  
  | `Website Clicks` | Number of website clicks |  
  | `Reviews Submitted` | Number of reviews submitted |  
  | `5-Star Reviews` | Count of 5-star reviews |  
  | `4-Star Reviews` | Count of 4-star reviews |  
  | `3-Star Reviews` | Count of 3-star reviews |  
  | `2-Star Reviews` | Count of 2-star reviews |  
  | `1-Star Reviews` | Count of 1-star reviews |  
  | `Average Rating` | Average rating score |  
- **Automation**: Data is updated automatically via a scheduled GitHub Actions workflow.  

## Technology Stack

- **Frontend Framework**: React 19 with TypeScript  
- **Build Tool**: Vite  
- **Styling**: Tailwind CSS with shadcn/ui components  
- **Charts**: Recharts for data visualization  
- **State Management**: React Context API  
- **Data Processing**: PapaParse (CSV), Tidy.js (data transformation)  
- **Date Utilities**: date-fns, dayjs, react-day-picker  
- **Package Manager**: pnpm  

## Getting Started

### Prerequisites

- Node.js 20.19+ or 22.12+  
- Git  

### Installation

1. **Clone the repository:**  
   ```bash
   git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
   cd fukui-kanko-trend-report
   ```

2. **Enable Corepack and set pnpm version:**  
   Corepack is a script that acts as a bridge between Node.js and package managers. It is included with all Node.js versions starting from 16.9.0.  
   ```bash
   corepack enable
   corepack use pnpm@10.11.0
   ```

3. **Initialize the data submodule and install dependencies:**  
   ```bash
   git submodule update --init --recursive
   pnpm install
   ```

4. **Run the development server:**  
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

Changes pushed to the `main` branch are automatically built and deployed to GitHub Pages via a workflow defined in the repository.

## License

This project is licensed under the terms of the [MIT license](LICENSE).

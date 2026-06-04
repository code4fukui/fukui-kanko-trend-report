# 福井県観光地トレンドレポート

> [English](README.md)

オンライン地図やウェブ検索ツールからのインプレッション数を集計・分析し、福井県の観光地活動トレンドを可視化するインタラクティブなウェブアプリケーション。

**[アプリケーションの表示](https://code4fukui.github.io/fukui-kanko-trend-report/)**

## 概要

このアプリケーションは、福井県内の観光地に関するオンライン地図やウェブ検索ツールからのインプレッションデータを集計し、インタラクティブなチャートを通じてトレンドを可視化します。福井県内の地域ごとの観光パターンや人気度を関係者が理解するのに役立ちます。

## 主な機能

- **地域別・県全体の集計**: 個別の地域または福井県全体のデータを表示  
- **時系列分析**: 日別、週別、月別の粒度でデータを分析  
- **期間比較**: 2つの異なる期間のトレンドを並列して比較  
- **包括的な指標**:  
  - 地図インプレッションと検索  
  - ウェブ検索インプレッション  
  - ルート検索インプレッション  
  - 電話ボタンクリック  
  - ウェブサイトクリック  
  - レビュー投稿  
  - スター評価別のレビュー数（1～5つ星）  
  - 平均評価  
- **データエクスポート**: 可視化データをCSV形式でダウンロード  

## 対応地域

アプリケーションは福井県内の13市町のデータを収集しています:

- あわら市 (Awara City)  
- 池田町 (Ikeda Town)  
- おおい町 (Ōi Town)  
- 永平寺町 (Eihei-ji Town)  
- 越前市 (Echizen City)  
- 勝山市 (Katsuyama City)  
- 南越前町 (Minamiechizen Town)  
- 高浜町 (Takahama Town)  
- 敦賀市 (Tsuruga City)  
- 若狭町 (Wakasa Town)  
- 小浜市 (Obama City)  
- 美浜町 (Mihama Town)  
- 大野市 (Ōno City)  

## 使い方ガイド

1. **地域の選択**: 福井県全体（"All Areas"）または特定の地域のデータを表示  
2. **時間単位の選択**: 日別、週別、または月別の集計を選択  
3. **日付範囲の選択**: カレンダーピッカーを使用して分析期間を選択  
4. **比較の有効化**（オプション）: 比較チェックボックスをオンにして、2つの日付範囲を並列比較  
5. **分析の表示**: 2つのチャートビューを確認:  
   - **インプレッショントレンド**: 時間経過に伴うインプレッションとインタラクション数の表示  
   - **レビュートレンド**: 時間経過に伴うレビュー投稿と評価データの表示  
6. **データのエクスポート**（オプション）: 表示されたデータをCSVファイルとしてダウンロードしてさらなる分析に使用  

## データソース

このアプリケーションのデータは、[fukui-kanko-trend-data](https://github.com/code4fukui/fukui-kanko-trend-data) リポジトリから取得され、Gitサブモジュールとして含まれています。

- **形式**: CSV  
- **列**:  
  | 列名 | 説明 |  
  | --- | --- |  
  | `Date` | YYYY-MM-DD形式の日付 |  
  | `Map Searches` | 地図検索数 |  
  | `Web Searches` | ウェブ検索数 |  
  | `Route Searches` | ルート検索数 |  
  | `Calls` | 電話ボタンクリック数 |  
  | `Website Clicks` | ウェブサイトクリック数 |  
  | `Reviews Submitted` | 投稿されたレビュー数 |  
  | `5-Star Reviews` | 5つ星のレビュー数 |  
  | `4-Star Reviews` | 4つ星のレビュー数 |  
  | `3-Star Reviews` | 3つ星のレビュー数 |  
  | `2-Star Reviews` | 2つ星のレビュー数 |  
  | `1-Star Reviews` | 1つ星のレビュー数 |  
  | `Average Rating` | 平均評価スコア |  
- **自動化**: データはスケジュールされたGitHub Actionsワークフローを通じて自動的に更新されます。  

## 技術スタック

- **フロントエンドフレームワーク**: React 19 with TypeScript  
- **ビルドツール**: Vite  
- **スタイリング**: Tailwind CSS with shadcn/uiコンポーネント  
- **チャート**: データ可視化のためのRecharts  
- **状態管理**: React Context API  
- **データ処理**: PapaParse (CSV), Tidy.js (データ変換)  
- **日付ユーティリティ**: date-fns, dayjs, react-day-picker  
- **パッケージマネージャー**: pnpm  

## はじめに

### 必要な環境

- Node.js 20.19+ または 22.12+  
- Git  

### インストール

1. **リポジトリのクローン**:  
   ```bash
   git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
   cd fukui-kanko-trend-report
   ```

2. **Corepackの有効化とpnpmバージョンの設定**:  
   CorepackはNode.jsとパッケージマネージャーの橋渡しを行うスクリプトです。Node.js 16.9.0以降のバージョンに含まれています。  
   ```bash
   corepack enable
   corepack use pnpm@10.11.0
   ```

3. **データサブモジュールの初期化と依存関係のインストール**:  
   ```bash
   git submodule update --init --recursive
   pnpm install
   ```

4. **開発サーバーの起動**:  
   ```bash
   pnpm dev
   ```
   ブラウザで `http://localhost:5173` を開きます。

## 利用可能なスクリプト

| コマンド        | 説明                               |
| -------------- | ----------------------------------------- |
| `pnpm dev`     | 開発サーバーを起動します。            |
| `pnpm build`   | 本番用にアプリケーションをビルドします。            |
| `pnpm preview` | 本番ビルドをローカルで実行します。      |
| `pnpm lint`    | コード品質を確認するためのESLintを実行します。    |

## 配備

`main` ブランチへの変更は、リポジトリに定義されたワークフローを通じてGitHub Pagesに自動的にビルドされ、配備されます。

## ライセンス

このプロジェクトは[LICENSE](LICENSE)に記載されたMITライセンスの条項に従ってライセンスされています。

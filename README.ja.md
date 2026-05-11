# 福井県観光ロケーション・トレンドレポート

オンライン地図やウェブ検索ツールからのインプレッション数を集計・分析し、福井県の観光活動のトレンドを可視化するインタラクティブなWebアプリケーションです。

**[アプリケーションを開く](https://code4fukui.github.io/fukui-kanko-trend-report/)**

## 主な機能

- **エリア別・県全体の集計**: 13の個別エリア、または福井県全体のデータを表示できます。
- **時系列分析**: 日別、週別、月別の粒度でデータを分析できます。
- **2期間比較**: 2つの異なる期間のトレンドを並べて比較できます。
- **包括的な指標**: 地図検索、Web検索、ルート検索、電話、Webサイトクリック、レビュー投稿、星評価のトレンドを可視化します。
- **データエクスポート**: 可視化されたデータをCSV形式でダウンロードし、さらに詳細な分析に活用できます。

## データソース

本アプリケーションのデータは、Gitサブモジュールとして組み込まれている [fukui-kanko-trend-data](https://github.com/code4fukui/fukui-kanko-trend-data) リポジトリから取得しています。

- **形式**: CSV
- **カラム**: `Date`, `Map Searches`, `Web Searches`, `Route Searches`, `Calls`, `Website Clicks`, `Reviews Submitted`, `5-Star Reviews`, `4-Star Reviews`, `3-Star Reviews`, `2-Star Reviews`, `1-Star Reviews`, `Average Rating`
- **自動化**: GitHub Actionsのスケジュールワークフローにより、データは自動的に更新されます。

## 技術スタック

- **フロントエンド**: React 19, TypeScript
- **ビルドツール**: Vite
- **スタイリング**: Tailwind CSS, shadcn/ui
- **チャート**: Recharts
- **状態管理**: React Context API
- **パッケージマネージャー**: pnpm

## はじめに

### 前提条件

- Node.js 20.19+ または 22.12+
- Git

### インストール手順

1. **リポジトリのクローン:**
    ```bash
    git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
    cd fukui-kanko-trend-report
    ```

2. **Corepackの有効化とpnpmバージョンの設定:**
    CorepackはNode.jsとパッケージマネージャーの橋渡しをするスクリプトで、Node.js 16.9.0以降に標準で同梱されています。
    ```bash
    corepack enable
    corepack use pnpm@10.11.0
    ```

3. **データサブモジュールの初期化と依存関係のインストール:**
    ```bash
    git submodule update --init --recursive
    pnpm install
    ```

4. **開発サーバーの起動:**
    ```bash
    pnpm dev
    ```
    ブラウザで `http://localhost:5173` を開きます。

## 利用可能なスクリプト

| コマンド | 説明 |
| --- | --- |
| `pnpm dev` | 開発サーバーを起動します。 |
| `pnpm build` | 本番環境用にアプリケーションをビルドします。 |
| `pnpm preview` | 本番ビルドをローカルでプレビューします。 |
| `pnpm lint` | ESLintを実行してコードの品質をチェックします。 |

## デプロイ

`main` ブランチに変更がプッシュされると、`.github/workflows/pages.yml` で定義されたワークフローにより、自動的にビルドされ GitHub Pages にデプロイされます。

## コントリビューション

コントリビューションを歓迎します。既存のコードスタイルに従い、プルリクエストを送信してください。

## ライセンス

このプロジェクトは MIT License のもとで公開されています。

---

保守・運用: [Code for FUKUI](https://github.com/code4fukui)

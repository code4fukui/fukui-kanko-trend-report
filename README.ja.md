# 福井県の観光地トレンドレポート
The Japanese README is here: [README.ja.md](README.ja.md)

福井県の観光活動のトレンドを視覚化するインタラクティブなWebアプリケーションです。オンラインマップやウェブ検索ツールからの印象数を集計・分析しています。

## 機能

- **地域レベル＆県レベルの集計**: 個別の地域またはすべての福井県の合計データを表示できます
- **時系列分析**: 1日、1週間、1か月単位で詳細に分析できます
- **2つの期間の比較**: 2つの異なる期間のトレンドを並べて比較できます
- **包括的なメトリクス**: インプレッション、web検索、ルート検索、コールボタンクリック、ウェブサイトクリック、レビュー投稿、レビュー評価、平均評価を把握できます
- **データエクスポート**: 視覚化したデータをCSV形式でダウンロードできます

## 要件

- Node.js 20.19+ または 22.12+

## 使い方

```bash
# リポジトリをクローンする
git clone https://github.com/code4fukui/fukui-kanko-trend-report.git
cd fukui-kanko-trend-report

# Node.jsがインストールされていることを確認する
nvm install 22.12.0
nvm use 22.12.0

# 依存関係をインストールする
corepack enable
corepack use pnpm@10.11.0
pnpm install

# 開発サーバを起動する
pnpm dev
```

開発サーバが起動したら、ターミナルに表示されたURLを（通常は `http://localhost:5173`）ブラウザで開いてください。

## データ

このアプリケーションでは、日本の福井県の観光活動データを使用します。このデータは、[別のリポジトリ](https://github.com/code4fukui/fukui-kanko-trend-data)で収集および管理されています。

## ライセンス
このプロジェクトは [MIT License](LICENSE) のもとで公開されています。

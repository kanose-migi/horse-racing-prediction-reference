# Horse Racing Prediction Reference

競馬予測を設計・研究・評価するための一般的な技術リファレンスです。

このリポジトリは特定プロジェクトの仕様書ではなく、競馬予測というドメイン全体について、既存の競馬研究・実装と、他分野から転用可能な技術を整理する Knowledge Base です。

## Scope

- データ取得・時点整合・特徴量設計
- Fundamental prediction / Learning to Rank / Probability calibration
- Market modeling / Odds time series
- Uncertainty / BET-SKIP / Ticket probability / Decision optimization
- Backtest / Shadow operation / Drift / Online adaptation
- 競馬分野の既存手法と、金融・推薦・時系列・OR・安全AI等からの転用候補

## Structure

- `docs/architecture/` — 4層アーキテクチャ
- `docs/process/` — 各工程の詳細
- `docs/technologies/` — 技術索引
- `docs/glossary/` — 用語集
- `docs/sources/` — 論文・OSS・データソース

ドキュメントは Zensical で静的サイト化し、GitHub Pages で閲覧できる構成を想定しています。

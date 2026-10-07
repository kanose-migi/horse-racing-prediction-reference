# Horse Racing Prediction Reference

競馬予測を設計・研究・評価するための一般的な技術リファレンスです。

このリポジトリは特定プロジェクトの仕様書ではなく、競馬予測というドメイン全体について、既存の競馬研究・実装と、他分野から転用可能な技術を整理する Knowledge Base です。

### Terminology notation

専門用語の日本語併記では、以下の記号を使用します。

- `（通常対訳）` — 当該分野で通常使用されている日本語対訳
- `〈説明訳〉` — 通常の対訳がない場合に、本リファレンスが理解補助のため付した説明訳
- `［訳文内補足］` — 原語には明示されていない対象・文脈を、訳文中で補った部分

単なるカタカナ転記で意味情報が増えない場合は、原則として日本語を併記しません。

編集時の規則は [AGENTS.md](AGENTS.md) を参照してください。

## Scope

- Data acquisition（データ取得） / Point-in-time correctness〈予測時点における情報整合性〉 / Feature engineering（特徴量設計）
- Fundamental prediction〈［競走能力・条件要因などの］基礎要因に基づく予測〉 / Learning to Rank（ランキング学習） / Probability calibration（確率校正）
- Market modeling〈市場・価格形成のモデル化〉 / Odds time series（オッズ時系列）
- Uncertainty（不確実性） / BET-SKIP〈購入・見送り判定〉 / Ticket probability〈買い目の的中確率〉 / Decision optimization（意思決定最適化）
- Backtest〈過去データによる検証〉 / Shadow operation〈実取引を伴わない並行運用〉 / Drift〈データ分布・予測関係の経時変化〉 / Online adaptation〈運用中の逐次適応〉
- 競馬分野の既存手法と、金融・推薦・時系列・OR・安全AI等からの転用候補

## Structure

- `docs/architecture/` — 4層アーキテクチャ
- `docs/process/` — 各工程の詳細
- `docs/technologies/` — 技術索引
- `docs/glossary/` — 用語集
- `docs/sources/` — 論文・OSS・データソース

ドキュメントは Zensical で静的サイト化し、GitHub Pages で閲覧できる構成を想定しています。

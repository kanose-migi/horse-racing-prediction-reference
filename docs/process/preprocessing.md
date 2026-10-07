# A3. Preprocessing

## 目的

raw dataをモデルが扱える安定した表現へ変換します。

## 競馬分野のアプローチ

- 欠損値処理
- category encoding
- CatBoost native categorical handling
- expanding target encoding
- race内percentile / relative normalization

## 他分野からの転用候補

- entity embeddings
- learned encoders
- hashing / high-cardinality encoding

## 評価観点

OOS性能だけでなく、未知馬・未知騎手・カテゴリ追加への頑健性を確認します。

## 注意点

target encodingの統計値を全期間から計算するとleakageになります。

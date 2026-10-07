# A5. Representation Learning

## 目的

人手集計だけでは表しにくい履歴、血統、テキスト等からlatent representationを学習します。

## 競馬分野のアプローチ

- 過去走sequenceをLSTM / Attentionで表現
- horse / jockey / trainer embedding
- 血統IDや系統のカテゴリ・集計特徴

## 他分野からの転用候補

- Event Transformer / event-sequence foundation model
- GNN / Graph Transformerによるpedigree representation
- LLMによる調教・厩舎・騎手コメントのstructured feature extraction
- multimodal representation（映像・テキスト・表形式）

## 評価観点

得られたembeddingを既存GBDT等へ追加し、OOSでincremental valueがあるかを見るのが実用的です。

## 注意点

高コストな深層モデルをGBDTの代替と決めつけず、representation generatorとして比較する価値があります。

# A4. Feature Engineering

## 目的

競走能力・適性・近況・相手関係を表す説明変数を構築します。

## 競馬分野のアプローチ

- 過去N走の着順・着差・タイム・上がり
- 距離 / 馬場 / 競馬場適性
- 斤量・馬体重・休養日数と変化量
- 騎手・調教師のrolling / expanding成績
- Speed Figure / Form Rating
- race内relative rank / percentile

## 他分野からの転用候補

- Elo / TrueSkill
- opponent-strength adjustment
- exponentially weighted statistics
- dynamic latent rating

## 評価観点

feature ablationとfuture holdoutで、本当に追加情報を持つ特徴量かを確認します。

## 注意点

特徴量数を増やすこと自体を目的にしません。複雑なドメイン特徴量が単純な履歴特徴量をOOSで上回るとは限りません。

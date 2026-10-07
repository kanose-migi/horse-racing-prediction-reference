# Open Source

公開実装は「そのまま採用するもの」ではなく、データ処理・評価・実験設計を確認するための参考資料として扱います。

## Horse racing

- anton-schwarberg/Hongkong-Horse-Racing-Prediction  
  https://github.com/anton-schwarberg/Hongkong-Horse-Racing-Prediction  
  16 seasonsのHKJCデータ、leak-free feature engineering、LightGBM classifier / ranker比較、calibration。

- tsukasaI/keiba-ai  
  https://github.com/tsukasaI/keiba-ai  
  GBDT系、calibration、walk-forward、Kelly、複数券種を扱う公開実装。

- jerrydaphantom/hkjc-ml-research  
  https://github.com/jerrydaphantom/hkjc-ml-research  
  market-free / market-aware比較、ROIとprediction metricの分離。

## Transferable

- Amazon Chronos forecasting  
  https://github.com/amazon-science/chronos-forecasting

- FOB / Full-order ranking reference implementation  
  https://github.com/tyxaaron/FOB

## Review checklist

公開repoを見るときは、以下を確認します。

1. splitは時系列か
2. oddsの時点は固定されているか
3. leakage防止が説明されているか
4. calibrationを見ているか
5. ROIのbet ruleが固定されているか
6. test setがhyperparameter tuningから隔離されているか

# Home Credit Default Risk

[コンペ](https://www.kaggle.com/competitions/home-credit-default-risk)

- [日程](#日程)
- [結果](#結果)
- [振り返り](#振り返り)
- [Google Colab](#google-colab)
- [参考リンク](#参考リンク)

### 日程

2023年5月3日〜2023年5月4日。

GWの休みを利用して取り組んだ。

### 結果

Score: 0.74863

Private score: 0.74717

### 振り返り

今回はベースラインモデルの作成と特徴量エンジニアリングを行った。

アルゴリズムはXGBoostに比べて処理時間が短かったLightGBMで、`application_train.csv`を学習させたモデルベースラインとした。

ベースラインモデルの作成では、書籍を参考に交差検証したモデル毎の確率の平均値を採用した。

特徴量エンジニアリングでは、`bureau.csv`から集約して加算可能な量的パラメータを追加してスコアの向上を目指した。

実際のスコアは0.04程度の僅かな上昇で、特徴量エンジニアリングも一筋縄でいかないと感じた。

各テーブル単体でどれくらいの精度が出るのか試しても良かったかもしれない。

次回はモデルのアンサンブルやパラメータのチューニングも行いたい。

### Google Colab

| |
| - |
| [submission 1 ベースラインモデルの作成](https://colab.research.google.com/drive/1rSySMOeWTKt_H1u-Nni-8SCVOj3AJqpi) | 
| [submission 2 特徴量エンジニアリング](https://colab.research.google.com/drive/1GyctB5CO0EuFHLKXfN0M0WYsMGoIHTni) | 

### 参考リンク

- [Home Credit Default Riskの1位の訳と振り返り](https://qiita.com/sh-tatsuno/items/8eca6fbf1de5e66794f0)
- [KaggleのHome Creditコンペで銀メダルを取った話と、チームで動く際のノウハウとか](https://amalog.hateblo.jp/entry/kaggle-home-credit)

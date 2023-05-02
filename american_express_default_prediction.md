# American Express - Default Prediction

[コンペ](https://www.kaggle.com/competitions/amex-default-prediction)

[Google Colab](https://colab.research.google.com/drive/1SLBV97-P9iZ7BKbylzvydTgumnxU-_qj)

- [日程](#日程)
- [結果](#結果)
- [振り返り](#振り返り)
- [参考リンク](#参考リンク)

### 日程

2023年5月1日〜2023年5月2日。

GWの休みを利用して取り組んだ。

### 結果

データ量が非常に大きく取り回しに時間がかかり、特徴量も匿名化されていて試行錯誤がしにくいため途中で断念。

dtypeの変換など行えたのは良かった。

### 振り返り

#### データ圧縮

訓練データが16.39 GBでテストデータが33.82 GBもあり、Google Colabのメモリに乗り切らずDriveの容量も圧迫する。

そのためdtypeの変換とCSV ⇒ Dask ⇒ Feather/Parquetフォーマットでの出力を行い、訓練データを3.3 Gまで圧縮できた。

dtypeはint64とfloat64をFeatherフォーマットで出力できる範囲でint8とfloat32に変換した。

floatのカテゴリ変数は欠損値を埋めればさらにint8に変換できそうだった。

また、解法を読むとデータの分布からfloatをintに変換可能とのことだったが、詳しくは確認していない。

#### 分析

分析の際はデータを10分の1程度にサンプリングして行う事が考えられる。

結果に書いた通り試行錯誤がしにくく、最初に取り組むコンペとしてはやや不向きだったかもしれない。

### 参考リンク

- [【kaggle】Amexコンペティションに参加して得られた知見](https://blog.recruit.co.jp/data/articles/kaggle-amex/)
- [【kaggle】AMEXコンペで銀メダルを獲得してKaggle Masterになりました【AMEX解法】](https://cpptake.com/archives/956)
- [【Kaggle】Amexコンペを振り返る【ソロ銀】](https://qiita.com/tetsuro731/items/296de8ca593386de4774)
- [Kaggle 2022 Amex解法まとめ](https://zenn.dev/ycarbon/articles/67d35bfe61b0f1)
- [9x Data Compression achieved with Feather](https://www.kaggle.com/competitions/amex-default-prediction/discussion/327143)
- [AMEX data - integer dtypes - parquet format](https://www.kaggle.com/datasets/raddar/amex-data-integer-dtypes-parquet-format)
- [AMEX data int types - train](https://www.kaggle.com/code/raddar/amex-data-int-types-train/notebook)

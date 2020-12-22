# STS_biLSTM_with_SelfAttention

このソースコードは,SemEval-2014のSemanticTextualSimilarityというタスクを想定して作成した物である。

## データセット
モデルの入力は"GoogleNews-vectors-negative300.bin.gz"という学習済みのWord2Vecを利用して単語を分散表現にした物である。 訓練データは、STS.input.OnWN.txt、STS.input.MSRvid.txt、STS.input.SMTeuroparl.txt、STS.input.tweet-news.txtの4つである。

## モデルの特徴
- 入力の分散表現を、双方向LSTMに入力することで、時系列を考慮した特徴を抽出
- 各時系列の出力に対し、Self-Attentionを計算することで各単語の重要度を考慮
- 出力された系列長分のベクトルにGlobalAveragePoolingを施すことで、文ベクトルを生成
- 類似度はcos類似度で算出

## 精度
テストデータSTS.input.images.txtに対して0.73である。

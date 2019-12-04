# STS_biLSTM_with_SelfAttention

このソースコードは,SemEval-2014のSemanticTextualSimilarityというタスクを想定して作成した物である。

モデルの入力は"GoogleNews-vectors-negative300.bin.gz"という学習済みのWord2Vecを利用して単語を分散表現にした物である。 訓練データは、STS.input.OnWN.txt、STS.input.MSRvid.txt、STS.input.SMTeuroparl.txt、STS.input.tweet-news.txtの4つである。

モデルの特徴は、入力の分散表現を、双方向LSTMに入力することで、時系列を考慮した計算を行なっている。また、各時系列の出力に対し、SelfAttentionを施すことで各単語(時間)の出力に重み付けを行なっている。
出力された系列長分のベクトルにGlobalAveragePoolingを施すことで、文ベクトルを作っている。

類似度の求め方はcos類似度で求めている。
精度は、テストデータSTS.input.images.txtに対して0.73である。

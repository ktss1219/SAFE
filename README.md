# SAFE : Self Attentive Function Embedding

引用
---
```bibtex
@inproceedings{massarelli2018safe,
  title={SAFE: Self-Attentive Function Embeddings for Binary Similarity},
  author={Massarelli, Luca and Di Luna, Giuseppe Antonio and Petroni, Fabio and Querzoni, Leonardo and Baldoni, Roberto},
  booktitle={Proceedings of 16th Conference on Detection of Intrusions and Malware & Vulnerability Assessment (DIMVA)},
  year={2019}
}
```

必要なフレームワーク  
-----
[radare2](https://github.com/radare/radare2) がインストールされている必要があります。
  
類似度の計算
-----
 ```embedding_x``` と ```embedding_y``` の2つの埋め込みを用いて、以下のように類似度の計算ができます。
```
from sklearn.metrics.pairwise import cosine_similarity

sim=cosine_similarity(embedding_x, embedding_y)
 
```


必要なデータ
-----
以下のスクリプトでi2vモデルとSAFEモデルがダウンロードできます。
```
./download_model.sh
```
ダウンロード後のディレクトリ階層は以下のようになります。
```
safe/-- githubcode
     \
      \--data/-----safe.pb
               \
                \---i2v/
            
```

モデルのトレーニング
----
モデルのトレーニングを行う場合、以下のコマンドでデータセットをダウンロードします。
```
 python3 downloader.py -td
```
データセットはダウンロード後、解凍する必要があります。

謝辞
---
In our code we use [godown](https://github.com/circulosmeos/gdown.pl) to download data from Google drive. We thank 
circulosmeos, the creator of godown.

We thank Davide Italiano for the useful discussions. 

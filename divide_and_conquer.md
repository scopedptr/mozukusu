# Mozc 辞書データの、意味グループでの分割

[Mozc](https://github.com/google/mozc) の公式な辞書データは、「[`dictionary00.txt`](https://github.com/google/mozc/blob/master/src/data/dictionary_oss/dictionary00.txt)」から「[`dictionary09.txt`](https://github.com/google/mozc/blob/master/src/data/dictionary_oss/dictionary09.txt)」の 10 ファイルに分かれています。

辞書データのバージョンが変わると収録されている単語の総数も変わりますが、辞書データは「常に 10 ファイル」です。

これらはどうやら、各ファイルの件数が均等になるように単純分割されているだけのようです。つまり、ある単語が「`dictionary02.txt`」と「`dictionary03.txt`」のどちらに収録されているかには、意味がありません。

しかしその一方で、辞書データの並び順自体には、何らかの意味、もしくは秩序があるように見えます。少なくとも、ただの五十音順でもランダムでもありません。

これはあくまで私見ですが、辞書データ中の単語の並びには いくつもの小さなグループがあり、そのグループ内で五十音順に並んでいるようです。

例えば、カタカナ単語が「あ」から順に並んだあとに続いて、今度は人名が「あ」から並ぶ、といった具合です。

そこで、それらのグループ単位で辞書データを分割してみました。分割ファイルは「`0001.txt`」からの連番になっており、連番順にすべての分割ファイルを結合すると、オジリナルの辞書データと同じものが得られます。

この分割により、「辞書データファイルの取り回し」や「語彙の変更管理」、「グループ単位での取り込みや除外」が容易になることを期待しています。



## 謝辞

本文書で言及しているすべての分割ファイルは、[Mozc](https://github.com/google/mozc) に含まれているファイルの直接的な派生物です。

Mozc のライセンスについては「[`third_party_licenses/LICENSE.mozc`](third_party_licenses/LICENSE.mozc)」をご参照ください。



## 分割ファイルの一覧

注意: 以下の一覧における「id」は、私的な管理上の都合で付与したものであり、何の意味もない非公式な文字列です。

また、「最新」「1世代前」等は、 2026年5月末現在での、Mozc 辞書データのバージョンの世代を意味します。

id|最新<br>[`975d7d6`](https://github.com/google/mozc/commit/975d7d6b344500c3d83b3ac4873cad0ced6b26f1)|1世代前<br>[`c9163b6`](https://github.com/google/mozc/commit/c9163b6bb1010671781b8acd358b025c519fc1e0)|2世代前<br>`2efeece`|説明|備考
:---:|:---:|:---:|:---:|---|---
`00sg`|[`0001.txt`](20260331_975d7d6/split/files/0001.txt)|[`0001.txt`](20260312_c9163b6/split/files/0001.txt)|[`0001.txt`](20250917_2efeece/split/files/0001.txt)||
`01kw`|[`0002.txt`](20260331_975d7d6/split/files/0002.txt)|[`0002.txt`](20260312_c9163b6/split/files/0002.txt)|[`0002.txt`](20250917_2efeece/split/files/0002.txt)||
`02dc`|[`0003.txt`](20260331_975d7d6/split/files/0003.txt)|[`0003.txt`](20260312_c9163b6/split/files/0003.txt)|[`0003.txt`](20250917_2efeece/split/files/0003.txt)||
`035s`|[`0004.txt`](20260331_975d7d6/split/files/0004.txt)|[`0004.txt`](20260312_c9163b6/split/files/0004.txt)|[`0004.txt`](20250917_2efeece/split/files/0004.txt)||
`03y8`|[`0005.txt`](20260331_975d7d6/split/files/0005.txt)|[`0005.txt`](20260312_c9163b6/split/files/0005.txt)|[`0005.txt`](20250917_2efeece/split/files/0005.txt)|アルファベット＋接尾辞|
`04qo`|[`0006.txt`](20260331_975d7d6/split/files/0006.txt)|[`0006.txt`](20260312_c9163b6/split/files/0006.txt)|[`0006.txt`](20250917_2efeece/split/files/0006.txt)|カタカナ単語|
`054w`|-|[`0007.txt`](20260312_c9163b6/split/files/0007.txt)|-|「マジックコート」|おそらく↑「 `04qo`」の欠片
`05j4`|[`0007.txt`](20260331_975d7d6/split/files/0007.txt)|[`0008.txt`](20260312_c9163b6/split/files/0008.txt)|[`0007.txt`](20250917_2efeece/split/files/0007.txt)|カタカナで始まる単語|
`06bk`|[`0008.txt`](20260331_975d7d6/split/files/0008.txt)|[`0009.txt`](20260312_c9163b6/split/files/0009.txt)|[`0008.txt`](20250917_2efeece/split/files/0008.txt)|「ナンパ男」|おそらく↑「`05j4`」の欠片
`0740`|[`0009.txt`](20260331_975d7d6/split/files/0009.txt)|[`0010.txt`](20260312_c9163b6/split/files/0010.txt)|[`0009.txt`](20250917_2efeece/split/files/0009.txt)|カタカナ単語|
`07wg`|[`0010.txt`](20260331_975d7d6/split/files/0010.txt)|[`0011.txt`](20260312_c9163b6/split/files/0011.txt)|[`0010.txt`](20250917_2efeece/split/files/0010.txt)|カタカナで始まる単語|
`08ow`|[`0011.txt`](20260331_975d7d6/split/files/0011.txt)|[`0012.txt`](20260312_c9163b6/split/files/0012.txt)|[`0011.txt`](20250917_2efeece/split/files/0011.txt)|人名（姓＋名）|
`09hc`|[`0012.txt`](20260331_975d7d6/split/files/0012.txt)|[`0013.txt`](20260312_c9163b6/split/files/0013.txt)|[`0012.txt`](20250917_2efeece/split/files/0012.txt)|人名＋人名接尾辞|
`0a9s`|[`0013.txt`](20260331_975d7d6/split/files/0013.txt)|[`0014.txt`](20260312_c9163b6/split/files/0014.txt)|[`0013.txt`](20250917_2efeece/split/files/0013.txt)|「似たよう」|
`0b28`|[`0014.txt`](20260331_975d7d6/split/files/0014.txt)|[`0015.txt`](20260312_c9163b6/split/files/0015.txt)|[`0014.txt`](20250917_2efeece/split/files/0014.txt)|「何」で始まる単語|
`0buo`|[`0015.txt`](20260331_975d7d6/split/files/0015.txt)|[`0016.txt`](20260312_c9163b6/split/files/0016.txt)|[`0015.txt`](20250917_2efeece/split/files/0015.txt)||
`0cn4`|[`0016.txt`](20260331_975d7d6/split/files/0016.txt)|[`0017.txt`](20260312_c9163b6/split/files/0017.txt)|[`0016.txt`](20250917_2efeece/split/files/0016.txt)||
`0dfk`|[`0017.txt`](20260331_975d7d6/split/files/0017.txt)|[`0018.txt`](20260312_c9163b6/split/files/0018.txt)|[`0017.txt`](20250917_2efeece/split/files/0017.txt)||
`0e80`|[`0018.txt`](20260331_975d7d6/split/files/0018.txt)|[`0019.txt`](20260312_c9163b6/split/files/0019.txt)|[`0018.txt`](20250917_2efeece/split/files/0018.txt)|〜しよう、等|
`0f0g`|[`0019.txt`](20260331_975d7d6/split/files/0019.txt)|[`0020.txt`](20260312_c9163b6/split/files/0020.txt)|[`0019.txt`](20250917_2efeece/split/files/0019.txt)|「搾り取ろう」|おそらく↑「`0e80`」の欠片
`0fsw`|[`0020.txt`](20260331_975d7d6/split/files/0020.txt)|[`0021.txt`](20260312_c9163b6/split/files/0021.txt)|[`0020.txt`](20250917_2efeece/split/files/0020.txt)|〜しがち、等|
`0glc`|[`0021.txt`](20260331_975d7d6/split/files/0021.txt)|[`0022.txt`](20260312_c9163b6/split/files/0022.txt)|[`0021.txt`](20250917_2efeece/split/files/0021.txt)|〜次第|
`0hds`|[`0022.txt`](20260331_975d7d6/split/files/0022.txt)|[`0023.txt`](20260312_c9163b6/split/files/0023.txt)|[`0022.txt`](20250917_2efeece/split/files/0022.txt)|〜せない|
`0i68`|[`0023.txt`](20260331_975d7d6/split/files/0023.txt)|[`0024.txt`](20260312_c9163b6/split/files/0024.txt)|[`0023.txt`](20250917_2efeece/split/files/0023.txt)|〜しそう、等|
`0ikg`|-|[`0025.txt`](20260312_c9163b6/split/files/0025.txt)|-|「堕ちそう」|おそらく↑「`0i68`」の欠片
`0iyo`|[`0024.txt`](20260331_975d7d6/split/files/0024.txt)|[`0026.txt`](20260312_c9163b6/split/files/0026.txt)|[`0024.txt`](20250917_2efeece/split/files/0024.txt)|〜しちゃ、等|
`0jr4`|[`0025.txt`](20260331_975d7d6/split/files/0025.txt)|[`0027.txt`](20260312_c9163b6/split/files/0027.txt)|[`0025.txt`](20250917_2efeece/split/files/0025.txt)|〜しちゃう、等|
`0kjk`|[`0026.txt`](20260331_975d7d6/split/files/0026.txt)|[`0028.txt`](20260312_c9163b6/split/files/0028.txt)|[`0026.txt`](20250917_2efeece/split/files/0026.txt)|〜しちゃう、等 (2)|おそらく↑「`0jr4`」の欠片
`0lc0`|[`0027.txt`](20260331_975d7d6/split/files/0027.txt)|[`0029.txt`](20260312_c9163b6/split/files/0029.txt)|[`0027.txt`](20250917_2efeece/split/files/0027.txt)|〜つける、等|
`0m4g`|[`0028.txt`](20260331_975d7d6/split/files/0028.txt)|[`0030.txt`](20260312_c9163b6/split/files/0030.txt)|[`0028.txt`](20250917_2efeece/split/files/0028.txt)|〜つける、等 (2)|おそらく↑「`0lc0`」の欠片
`0mww`|[`0029.txt`](20260331_975d7d6/split/files/0029.txt)|[`0031.txt`](20260312_c9163b6/split/files/0031.txt)|[`0029.txt`](20250917_2efeece/split/files/0029.txt)|〜ってほしい|
`0npc`|[`0030.txt`](20260331_975d7d6/split/files/0030.txt)|[`0032.txt`](20260312_c9163b6/split/files/0032.txt)|[`0030.txt`](20250917_2efeece/split/files/0030.txt)|〜ていれば|
`0ohs`|[`0031.txt`](20260331_975d7d6/split/files/0031.txt)|[`0033.txt`](20260312_c9163b6/split/files/0033.txt)|[`0031.txt`](20250917_2efeece/split/files/0031.txt)|〜ておくれ|
`0pa8`|[`0032.txt`](20260331_975d7d6/split/files/0032.txt)|[`0034.txt`](20260312_c9163b6/split/files/0034.txt)|[`0032.txt`](20250917_2efeece/split/files/0032.txt)|〜っとけ、等|
`0q2o`|[`0033.txt`](20260331_975d7d6/split/files/0033.txt)|[`0035.txt`](20260312_c9163b6/split/files/0035.txt)|[`0033.txt`](20250917_2efeece/split/files/0033.txt)|〜なくなる、等|
`0qv4`|[`0034.txt`](20260331_975d7d6/split/files/0034.txt)|[`0036.txt`](20260312_c9163b6/split/files/0036.txt)|[`0034.txt`](20250917_2efeece/split/files/0034.txt)|〜なくなる、等 (2)|おそらく↑「`0q2o`」の欠片
`0rnk`|[`0035.txt`](20260331_975d7d6/split/files/0035.txt)|[`0037.txt`](20260312_c9163b6/split/files/0037.txt)|[`0035.txt`](20250917_2efeece/split/files/0035.txt)|〜なんだ|
`0sg0`|[`0036.txt`](20260331_975d7d6/split/files/0036.txt)|[`0038.txt`](20260312_c9163b6/split/files/0038.txt)|[`0036.txt`](20250917_2efeece/split/files/0036.txt)|〜に行く、〜に来る、等|
`0t8g`|[`0037.txt`](20260331_975d7d6/split/files/0037.txt)|[`0039.txt`](20260312_c9163b6/split/files/0039.txt)|[`0037.txt`](20250917_2efeece/split/files/0037.txt)|「届けに来」|おそらく↑「`0sg0`」の欠片
`0u0w`|[`0038.txt`](20260331_975d7d6/split/files/0038.txt)|[`0040.txt`](20260312_c9163b6/split/files/0040.txt)|[`0038.txt`](20250917_2efeece/split/files/0038.txt)|〜に来て|
`0utc`|[`0039.txt`](20260331_975d7d6/split/files/0039.txt)|[`0041.txt`](20260312_c9163b6/split/files/0041.txt)|[`0039.txt`](20250917_2efeece/split/files/0039.txt)|〜に行く、〜に来る、等 (2)|
`0vls`|-|[`0042.txt`](20260312_c9163b6/split/files/0042.txt)|[`0040.txt`](20250917_2efeece/split/files/0040.txt)|「代わりにもなる」|
`0we8`|[`0040.txt`](20260331_975d7d6/split/files/0040.txt)|[`0043.txt`](20260312_c9163b6/split/files/0043.txt)|[`0041.txt`](20250917_2efeece/split/files/0041.txt)||
`0x6o`|[`0041.txt`](20260331_975d7d6/split/files/0041.txt)|[`0044.txt`](20260312_c9163b6/split/files/0044.txt)|[`0042.txt`](20250917_2efeece/split/files/0042.txt)|〜れん、〜けん|
`0xz4`|[`0042.txt`](20260331_975d7d6/split/files/0042.txt)|[`0045.txt`](20260312_c9163b6/split/files/0045.txt)|[`0043.txt`](20250917_2efeece/split/files/0043.txt)|〜んかった|
`0yrk`|[`0043.txt`](20260331_975d7d6/split/files/0043.txt)|[`0046.txt`](20260312_c9163b6/split/files/0046.txt)|[`0044.txt`](20250917_2efeece/split/files/0044.txt)|〜会場|
`0zk0`|-|-|[`0045.txt`](20250917_2efeece/split/files/0045.txt)|「話すわ（はなしすわ）」|読みが変
`10cg`|[`0044.txt`](20260331_975d7d6/split/files/0044.txt)|[`0047.txt`](20260312_c9163b6/split/files/0047.txt)|[`0046.txt`](20250917_2efeece/split/files/0046.txt)|〜間違い|
`114w`|[`0045.txt`](20260331_975d7d6/split/files/0045.txt)|[`0048.txt`](20260312_c9163b6/split/files/0048.txt)|[`0047.txt`](20250917_2efeece/split/files/0047.txt)|〜様|
`11xc`|[`0046.txt`](20260331_975d7d6/split/files/0046.txt)|[`0049.txt`](20260312_c9163b6/split/files/0049.txt)|[`0048.txt`](20250917_2efeece/split/files/0048.txt)|〜難い、〜づらい、〜やすい、等|
`12ps`|[`0047.txt`](20260331_975d7d6/split/files/0047.txt)|[`0050.txt`](20260312_c9163b6/split/files/0050.txt)|[`0049.txt`](20250917_2efeece/split/files/0049.txt)||
`13i8`|[`0048.txt`](20260331_975d7d6/split/files/0048.txt)|[`0051.txt`](20260312_c9163b6/split/files/0051.txt)|[`0050.txt`](20250917_2efeece/split/files/0050.txt)|「履きっぱなし」|おそらく↑「`12ps`」の欠片
`14ao`|[`0049.txt`](20260331_975d7d6/split/files/0049.txt)|[`0052.txt`](20260312_c9163b6/split/files/0052.txt)|[`0051.txt`](20250917_2efeece/split/files/0051.txt)||
`1534`|[`0050.txt`](20260331_975d7d6/split/files/0050.txt)|[`0053.txt`](20260312_c9163b6/split/files/0053.txt)|[`0052.txt`](20250917_2efeece/split/files/0052.txt)|〜しな、〜筋|
`15vk`|-|-|[`0053.txt`](20250917_2efeece/split/files/0053.txt)|「行く先々（いくせんせん）」<br>「声高々（こえたかたか）」|読みが変
`16o0`|[`0051.txt`](20260331_975d7d6/split/files/0051.txt)|[`0054.txt`](20260312_c9163b6/split/files/0054.txt)|[`0054.txt`](20250917_2efeece/split/files/0054.txt)|〜から〜|
`17gg`|[`0052.txt`](20260331_975d7d6/split/files/0052.txt)|[`0055.txt`](20260312_c9163b6/split/files/0055.txt)|[`0055.txt`](20250917_2efeece/split/files/0055.txt)|〜がかかる、〜がかかっ、等|
`188w`|[`0053.txt`](20260331_975d7d6/split/files/0053.txt)|[`0056.txt`](20260312_c9163b6/split/files/0056.txt)|[`0056.txt`](20250917_2efeece/split/files/0056.txt)|〜がかかっ|おそらく↑「`17gg`」の欠片
`191c`|[`0054.txt`](20260331_975d7d6/split/files/0054.txt)|[`0057.txt`](20260312_c9163b6/split/files/0057.txt)|[`0057.txt`](20250917_2efeece/split/files/0057.txt)|〜がする、〜もする、等|
`19ts`|[`0055.txt`](20260331_975d7d6/split/files/0055.txt)|[`0058.txt`](20260312_c9163b6/split/files/0058.txt)|[`0058.txt`](20250917_2efeece/split/files/0058.txt)|〜しがち|
`1am8`|[`0056.txt`](20260331_975d7d6/split/files/0056.txt)|[`0059.txt`](20260312_c9163b6/split/files/0059.txt)|[`0059.txt`](20250917_2efeece/split/files/0059.txt)|〜だ、〜で、〜なら、等|
`1beo`|[`0057.txt`](20260331_975d7d6/split/files/0057.txt)|[`0060.txt`](20260312_c9163b6/split/files/0060.txt)|[`0060.txt`](20250917_2efeece/split/files/0060.txt)|〜で〜|
`1c74`|[`0058.txt`](20260331_975d7d6/split/files/0058.txt)|[`0061.txt`](20260312_c9163b6/split/files/0061.txt)|[`0061.txt`](20250917_2efeece/split/files/0061.txt)|〜と〜|
`1czk`|[`0059.txt`](20260331_975d7d6/split/files/0059.txt)|[`0062.txt`](20260312_c9163b6/split/files/0062.txt)|[`0062.txt`](20250917_2efeece/split/files/0062.txt)|〜のないように|
`1ds0`|[`0060.txt`](20260331_975d7d6/split/files/0060.txt)|[`0063.txt`](20260312_c9163b6/split/files/0063.txt)|[`0063.txt`](20250917_2efeece/split/files/0063.txt)|〜になる、等|
`1ekg`|[`0061.txt`](20260331_975d7d6/split/files/0061.txt)|[`0064.txt`](20260312_c9163b6/split/files/0064.txt)|[`0064.txt`](20250917_2efeece/split/files/0064.txt)|〜にはなる、〜にもなる、等|
`1eyo`|[`0062.txt`](20260331_975d7d6/split/files/0062.txt)|-|-||
`1fcw`|[`0063.txt`](20260331_975d7d6/split/files/0063.txt)|[`0065.txt`](20260312_c9163b6/split/files/0065.txt)|[`0065.txt`](20250917_2efeece/split/files/0065.txt)|〜の〜|
`1g5c`|[`0064.txt`](20260331_975d7d6/split/files/0064.txt)|[`0066.txt`](20260312_c9163b6/split/files/0066.txt)|[`0066.txt`](20250917_2efeece/split/files/0066.txt)|〜の〜 (2)|おそらく↑「`1fcw`」の欠片
`1gxs`|[`0065.txt`](20260331_975d7d6/split/files/0065.txt)|[`0067.txt`](20260312_c9163b6/split/files/0067.txt)|[`0067.txt`](20250917_2efeece/split/files/0067.txt)|○月のこと|読みが算用数字始まり
`1hq8`|[`0066.txt`](20260331_975d7d6/split/files/0066.txt)|[`0068.txt`](20260312_c9163b6/split/files/0068.txt)|[`0068.txt`](20250917_2efeece/split/files/0068.txt)|〜のこと、〜のもの、等|
`1iio`|[`0067.txt`](20260331_975d7d6/split/files/0067.txt)|[`0069.txt`](20260312_c9163b6/split/files/0069.txt)|[`0069.txt`](20250917_2efeece/split/files/0069.txt)|〜や〜|
`1jb4`|[`0068.txt`](20260331_975d7d6/split/files/0068.txt)|[`0070.txt`](20260312_c9163b6/split/files/0070.txt)|[`0070.txt`](20250917_2efeece/split/files/0070.txt)|〜よう|おそらく↓「`1k3k`」の欠片
`1k3k`|[`0069.txt`](20260331_975d7d6/split/files/0069.txt)|[`0071.txt`](20260312_c9163b6/split/files/0071.txt)|[`0071.txt`](20250917_2efeece/split/files/0071.txt)|〜よう (2)|
`1kw0`|[`0070.txt`](20260331_975d7d6/split/files/0070.txt)|-|[`0072.txt`](20250917_2efeece/split/files/0072.txt)|○月クール（、○月オープン）|読みが算用数字始まり
`1log`|[`0071.txt`](20260331_975d7d6/split/files/0071.txt)|[`0072.txt`](20260312_c9163b6/split/files/0072.txt)|[`0073.txt`](20250917_2efeece/split/files/0073.txt)|なにか＋カタカナ|
`1mgw`|[`0072.txt`](20260331_975d7d6/split/files/0072.txt)|[`0073.txt`](20260312_c9163b6/split/files/0073.txt)|[`0074.txt`](20250917_2efeece/split/files/0074.txt)|なにか＋カタカナ (2)|おそらく↑「`1log`」の欠片
`1n9c`|[`0073.txt`](20260331_975d7d6/split/files/0073.txt)|-|[`0075.txt`](20250917_2efeece/split/files/0075.txt)|○月生まれ、等|読みが算用数字始まり
`1o1s`|[`0074.txt`](20260331_975d7d6/split/files/0074.txt)|[`0074.txt`](20260312_c9163b6/split/files/0074.txt)|[`0076.txt`](20250917_2efeece/split/files/0076.txt)||
`1ou8`|[`0075.txt`](20260331_975d7d6/split/files/0075.txt)|[`0075.txt`](20260312_c9163b6/split/files/0075.txt)|[`0077.txt`](20250917_2efeece/split/files/0077.txt)|複合語で右側が名詞一般|
`1pmo`|[`0076.txt`](20260331_975d7d6/split/files/0076.txt)|[`0076.txt`](20260312_c9163b6/split/files/0076.txt)|[`0078.txt`](20250917_2efeece/split/files/0078.txt)|複合語で右側が五段動詞の連用形|
`1qf4`|[`0077.txt`](20260331_975d7d6/split/files/0077.txt)|[`0077.txt`](20260312_c9163b6/split/files/0077.txt)|[`0079.txt`](20250917_2efeece/split/files/0079.txt)||
`1r7k`|[`0078.txt`](20260331_975d7d6/split/files/0078.txt)|[`0078.txt`](20260312_c9163b6/split/files/0078.txt)|[`0080.txt`](20250917_2efeece/split/files/0080.txt)||おそらく↑「`1qf4`」の欠片
`1s00`|[`0079.txt`](20260331_975d7d6/split/files/0079.txt)|[`0079.txt`](20260312_c9163b6/split/files/0079.txt)|[`0081.txt`](20250917_2efeece/split/files/0081.txt)|○月辺り、○月ごろ|読みが算用数字始まり
`1ssg`|[`0080.txt`](20260331_975d7d6/split/files/0080.txt)|[`0080.txt`](20260312_c9163b6/split/files/0080.txt)|[`0082.txt`](20250917_2efeece/split/files/0082.txt)||
`1tkw`|[`0081.txt`](20260331_975d7d6/split/files/0081.txt)|[`0081.txt`](20260312_c9163b6/split/files/0081.txt)|[`0083.txt`](20250917_2efeece/split/files/0083.txt)||
`1udc`|[`0082.txt`](20260331_975d7d6/split/files/0082.txt)|[`0082.txt`](20260312_c9163b6/split/files/0082.txt)|[`0084.txt`](20250917_2efeece/split/files/0084.txt)|「あん時」「地味そう」|
`1v5s`|[`0083.txt`](20260331_975d7d6/split/files/0083.txt)|[`0083.txt`](20260312_c9163b6/split/files/0083.txt)|[`0085.txt`](20250917_2efeece/split/files/0085.txt)|○月あたり、○月並み|読みが算用数字始まり
`1vy8`|[`0084.txt`](20260331_975d7d6/split/files/0084.txt)|[`0084.txt`](20260312_c9163b6/split/files/0084.txt)|[`0086.txt`](20250917_2efeece/split/files/0086.txt)||
`1wqo`|[`0085.txt`](20260331_975d7d6/split/files/0085.txt)|[`0085.txt`](20260312_c9163b6/split/files/0085.txt)|[`0087.txt`](20250917_2efeece/split/files/0087.txt)||おそらく↑「`1vy8`」の欠片
`1xj4`|[`0086.txt`](20260331_975d7d6/split/files/0086.txt)|[`0086.txt`](20260312_c9163b6/split/files/0086.txt)|[`0088.txt`](20250917_2efeece/split/files/0088.txt)|〜さん、〜ちゃん、等|
`1ybk`|[`0087.txt`](20260331_975d7d6/split/files/0087.txt)|[`0087.txt`](20260312_c9163b6/split/files/0087.txt)|[`0089.txt`](20250917_2efeece/split/files/0089.txt)||
`1z40`|[`0088.txt`](20260331_975d7d6/split/files/0088.txt)|[`0088.txt`](20260312_c9163b6/split/files/0088.txt)|[`0090.txt`](20250917_2efeece/split/files/0090.txt)|○月校、○月後、○月末、等|読みが算用数字始まり
`1zwg`|[`0089.txt`](20260331_975d7d6/split/files/0089.txt)|[`0089.txt`](20260312_c9163b6/split/files/0089.txt)|[`0091.txt`](20250917_2efeece/split/files/0091.txt)||
`20ow`|[`0090.txt`](20260331_975d7d6/split/files/0090.txt)|[`0090.txt`](20260312_c9163b6/split/files/0090.txt)|[`0092.txt`](20250917_2efeece/split/files/0092.txt)||おそらく↑「`1zwg`」の欠片
`21hc`|[`0091.txt`](20260331_975d7d6/split/files/0091.txt)|[`0091.txt`](20260312_c9163b6/split/files/0091.txt)|[`0093.txt`](20250917_2efeece/split/files/0093.txt)|〜好き、〜不足、等|
`229s`|[`0092.txt`](20260331_975d7d6/split/files/0092.txt)|[`0092.txt`](20260312_c9163b6/split/files/0092.txt)|[`0094.txt`](20250917_2efeece/split/files/0094.txt)|〜さ、〜っぷり|
`2328`|[`0093.txt`](20260331_975d7d6/split/files/0093.txt)|[`0093.txt`](20260312_c9163b6/split/files/0093.txt)|[`0095.txt`](20250917_2efeece/split/files/0095.txt)|後ろに漢数字|
`23uo`|[`0094.txt`](20260331_975d7d6/split/files/0094.txt)|[`0094.txt`](20260312_c9163b6/split/files/0094.txt)|[`0096.txt`](20250917_2efeece/split/files/0096.txt)|複合語の形容詞？|
`24n4`|[`0095.txt`](20260331_975d7d6/split/files/0095.txt)|-|[`0097.txt`](20250917_2efeece/split/files/0097.txt)|「胸糞悪い」|おそらく↑「`23uo`」の欠片
`25fk`|[`0096.txt`](20260331_975d7d6/split/files/0096.txt)|[`0095.txt`](20260312_c9163b6/split/files/0095.txt)|[`0098.txt`](20250917_2efeece/split/files/0098.txt)|○月期決算、他|読みが算用数字始まり
`2680`|[`0097.txt`](20260331_975d7d6/split/files/0097.txt)|[`0096.txt`](20260312_c9163b6/split/files/0096.txt)|[`0099.txt`](20250917_2efeece/split/files/0099.txt)||
`270g`|[`0098.txt`](20260331_975d7d6/split/files/0098.txt)|[`0097.txt`](20260312_c9163b6/split/files/0097.txt)|[`0100.txt`](20250917_2efeece/split/files/0100.txt)|○月下旬頃、他|読みが算用数字始まり
`27sw`|[`0099.txt`](20260331_975d7d6/split/files/0099.txt)|[`0098.txt`](20260312_c9163b6/split/files/0098.txt)|[`0101.txt`](20250917_2efeece/split/files/0101.txt)||
`28bu`|-|[`0099.txt`](20260312_c9163b6/split/files/0099.txt)|-||
`28lc`|-|-|[`0102.txt`](20250917_2efeece/split/files/0102.txt)|○月中旬予定|読みが算用数字始まり
`28ut`|[`0100.txt`](20260331_975d7d6/split/files/0100.txt)|[`0100.txt`](20260312_c9163b6/split/files/0100.txt)|-||
`29ds`|[`0101.txt`](20260331_975d7d6/split/files/0101.txt)|[`0101.txt`](20260312_c9163b6/split/files/0101.txt)|[`0103.txt`](20250917_2efeece/split/files/0103.txt)||
`2a68`|[`0102.txt`](20260331_975d7d6/split/files/0102.txt)|[`0102.txt`](20260312_c9163b6/split/files/0102.txt)|[`0104.txt`](20250917_2efeece/split/files/0104.txt)||
`2ayo`|[`0103.txt`](20260331_975d7d6/split/files/0103.txt)|[`0103.txt`](20260312_c9163b6/split/files/0103.txt)|[`0105.txt`](20250917_2efeece/split/files/0105.txt)|○月頃、○月末、等|読みが算用数字始まり
`2br4`|[`0104.txt`](20260331_975d7d6/split/files/0104.txt)|[`0104.txt`](20260312_c9163b6/split/files/0104.txt)|[`0106.txt`](20250917_2efeece/split/files/0106.txt)||
`2cjk`|[`0105.txt`](20260331_975d7d6/split/files/0105.txt)|[`0105.txt`](20260312_c9163b6/split/files/0105.txt)|[`0107.txt`](20250917_2efeece/split/files/0107.txt)||おそらく↑「`2br4`」の欠片
`2cxs`|[`0106.txt`](20260331_975d7d6/split/files/0106.txt)|-|-||
`2dc0`|[`0107.txt`](20260331_975d7d6/split/files/0107.txt)|[`0106.txt`](20260312_c9163b6/split/files/0106.txt)|[`0108.txt`](20250917_2efeece/split/files/0108.txt)|長めの単語|
`2e4g`|[`0108.txt`](20260331_975d7d6/split/files/0108.txt)|[`0107.txt`](20260312_c9163b6/split/files/0107.txt)|[`0109.txt`](20250917_2efeece/split/files/0109.txt)|「否か」|
`2eww`|[`0109.txt`](20260331_975d7d6/split/files/0109.txt)|[`0108.txt`](20260312_c9163b6/split/files/0108.txt)|[`0110.txt`](20250917_2efeece/split/files/0110.txt)|地名との複合語？|
`2fb4`|[`0110.txt`](20260331_975d7d6/split/files/0110.txt)|[`0109.txt`](20260312_c9163b6/split/files/0109.txt)|-|「FC東京戦」|読みがアルファベット始まり
`2fpc`|[`0111.txt`](20260331_975d7d6/split/files/0111.txt)|[`0110.txt`](20260312_c9163b6/split/files/0110.txt)|[`0111.txt`](20250917_2efeece/split/files/0111.txt)|地名との複合語？|
`2g3k`|-|[`0111.txt`](20260312_c9163b6/split/files/0111.txt)|-||
`2ghs`|[`0112.txt`](20260331_975d7d6/split/files/0112.txt)|[`0112.txt`](20260312_c9163b6/split/files/0112.txt)|[`0112.txt`](20250917_2efeece/split/files/0112.txt)|〜行|
`2ha8`|[`0113.txt`](20260331_975d7d6/split/files/0113.txt)|[`0113.txt`](20260312_c9163b6/split/files/0113.txt)|[`0113.txt`](20250917_2efeece/split/files/0113.txt)|〜人|
`2i2o`|[`0114.txt`](20260331_975d7d6/split/files/0114.txt)|[`0114.txt`](20260312_c9163b6/split/files/0114.txt)|[`0114.txt`](20250917_2efeece/split/files/0114.txt)|〜支社|
`2iv4`|[`0115.txt`](20260331_975d7d6/split/files/0115.txt)|[`0115.txt`](20260312_c9163b6/split/files/0115.txt)|[`0115.txt`](20250917_2efeece/split/files/0115.txt)|「大にする」「尽くした」等|
`2jnk`|[`0116.txt`](20260331_975d7d6/split/files/0116.txt)|[`0116.txt`](20260312_c9163b6/split/files/0116.txt)|[`0116.txt`](20250917_2efeece/split/files/0116.txt)|「差が出る」等|
`2kg0`|[`0117.txt`](20260331_975d7d6/split/files/0117.txt)|[`0117.txt`](20260312_c9163b6/split/files/0117.txt)|[`0117.txt`](20250917_2efeece/split/files/0117.txt)|〜なシ（師/死/市/詩）|
`2l8g`|[`0118.txt`](20260331_975d7d6/split/files/0118.txt)|[`0118.txt`](20260312_c9163b6/split/files/0118.txt)|[`0118.txt`](20250917_2efeece/split/files/0118.txt)|〜なし|
`2m0w`|[`0119.txt`](20260331_975d7d6/split/files/0119.txt)|[`0119.txt`](20260312_c9163b6/split/files/0119.txt)|[`0119.txt`](20250917_2efeece/split/files/0119.txt)|形容詞＋名詞|
`2mtc`|[`0120.txt`](20260331_975d7d6/split/files/0120.txt)|[`0120.txt`](20260312_c9163b6/split/files/0120.txt)|[`0120.txt`](20250917_2efeece/split/files/0120.txt)||
`2n7k`|-|[`0121.txt`](20260312_c9163b6/split/files/0121.txt)|-||
`2nls`|[`0121.txt`](20260331_975d7d6/split/files/0121.txt)|[`0122.txt`](20260312_c9163b6/split/files/0122.txt)|[`0121.txt`](20250917_2efeece/split/files/0121.txt)|「思いで」「押した」等|
`2oe8`|[`0122.txt`](20260331_975d7d6/split/files/0122.txt)|[`0123.txt`](20260312_c9163b6/split/files/0123.txt)|[`0122.txt`](20250917_2efeece/split/files/0122.txt)||
`2p6o`|[`0123.txt`](20260331_975d7d6/split/files/0123.txt)|[`0124.txt`](20260312_c9163b6/split/files/0124.txt)|[`0123.txt`](20250917_2efeece/split/files/0123.txt)||
`2pz4`|[`0124.txt`](20260331_975d7d6/split/files/0124.txt)|[`0125.txt`](20260312_c9163b6/split/files/0125.txt)|[`0124.txt`](20250917_2efeece/split/files/0124.txt)|「おしき」「即退学」等|
`2qrk`|[`0125.txt`](20260331_975d7d6/split/files/0125.txt)|[`0126.txt`](20260312_c9163b6/split/files/0126.txt)|[`0125.txt`](20250917_2efeece/split/files/0125.txt)||
`2rk0`|[`0126.txt`](20260331_975d7d6/split/files/0126.txt)|[`0127.txt`](20260312_c9163b6/split/files/0127.txt)|[`0126.txt`](20250917_2efeece/split/files/0126.txt)|「小悪魔系」「新作動画」|おそらく↑「`2qrk`」の欠片
`2scg`|[`0127.txt`](20260331_975d7d6/split/files/0127.txt)|[`0128.txt`](20260312_c9163b6/split/files/0128.txt)|[`0127.txt`](20250917_2efeece/split/files/0127.txt)||
`2t4w`|[`0128.txt`](20260331_975d7d6/split/files/0128.txt)|[`0129.txt`](20260312_c9163b6/split/files/0129.txt)|[`0128.txt`](20250917_2efeece/split/files/0128.txt)||
`2txc`|[`0129.txt`](20260331_975d7d6/split/files/0129.txt)|[`0130.txt`](20260312_c9163b6/split/files/0130.txt)|[`0129.txt`](20250917_2efeece/split/files/0129.txt)||
`2ups`|[`0130.txt`](20260331_975d7d6/split/files/0130.txt)|[`0131.txt`](20260312_c9163b6/split/files/0131.txt)|[`0130.txt`](20250917_2efeece/split/files/0130.txt)|後ろに漢数字|
`2vi8`|[`0131.txt`](20260331_975d7d6/split/files/0131.txt)|[`0132.txt`](20260312_c9163b6/split/files/0132.txt)|[`0131.txt`](20250917_2efeece/split/files/0131.txt)|左側が助数詞|
`2wao`|[`0132.txt`](20260331_975d7d6/split/files/0132.txt)|[`0133.txt`](20260312_c9163b6/split/files/0133.txt)|[`0132.txt`](20250917_2efeece/split/files/0132.txt)|○歳児、○時台、等|読みが算用数字始まり
`2x34`|[`0133.txt`](20260331_975d7d6/split/files/0133.txt)|[`0134.txt`](20260312_c9163b6/split/files/0134.txt)|[`0133.txt`](20250917_2efeece/split/files/0133.txt)|数字で始まる単語|読みに算用数字を含まない
`2xhc`|-|[`0135.txt`](20260312_c9163b6/split/files/0135.txt)|-||
`2xvk`|[`0134.txt`](20260331_975d7d6/split/files/0134.txt)|[`0136.txt`](20260312_c9163b6/split/files/0136.txt)|[`0134.txt`](20250917_2efeece/split/files/0134.txt)|漢数字で始まる単語|読みに算用数字を含まない
`2yo0`|[`0135.txt`](20260331_975d7d6/split/files/0135.txt)|[`0137.txt`](20260312_c9163b6/split/files/0137.txt)|[`0135.txt`](20250917_2efeece/split/files/0135.txt)|漢数字で始まる単語 (2)|読みに算用数字を含まない
`2zgg`|[`0136.txt`](20260331_975d7d6/split/files/0136.txt)|[`0138.txt`](20260312_c9163b6/split/files/0138.txt)|[`0136.txt`](20250917_2efeece/split/files/0136.txt)|漢数字で始まる単語 (3)|読みに算用数字を含まない
`308w`|[`0137.txt`](20260331_975d7d6/split/files/0137.txt)|[`0139.txt`](20260312_c9163b6/split/files/0139.txt)|[`0137.txt`](20250917_2efeece/split/files/0137.txt)|「五十」「三十」等|読みに算用数字を含まない
`311c`|[`0138.txt`](20260331_975d7d6/split/files/0138.txt)|[`0140.txt`](20260312_c9163b6/split/files/0140.txt)|[`0138.txt`](20250917_2efeece/split/files/0138.txt)|数十〜、数百〜、等|
`31ts`|[`0139.txt`](20260331_975d7d6/split/files/0139.txt)|[`0141.txt`](20260312_c9163b6/split/files/0141.txt)|[`0139.txt`](20250917_2efeece/split/files/0139.txt)|幾〜、数〜、何〜、等|
`32m8`|[`0140.txt`](20260331_975d7d6/split/files/0140.txt)|[`0142.txt`](20260312_c9163b6/split/files/0142.txt)|[`0140.txt`](20250917_2efeece/split/files/0140.txt)||
`33eo`|[`0141.txt`](20260331_975d7d6/split/files/0141.txt)|[`0143.txt`](20260312_c9163b6/split/files/0143.txt)|[`0141.txt`](20250917_2efeece/split/files/0141.txt)||
`3474`|[`0142.txt`](20260331_975d7d6/split/files/0142.txt)|[`0144.txt`](20260312_c9163b6/split/files/0144.txt)|[`0142.txt`](20250917_2efeece/split/files/0142.txt)||
`34zk`|[`0143.txt`](20260331_975d7d6/split/files/0143.txt)|[`0145.txt`](20260312_c9163b6/split/files/0145.txt)|[`0143.txt`](20250917_2efeece/split/files/0143.txt)||
`35s0`|[`0144.txt`](20260331_975d7d6/split/files/0144.txt)|[`0146.txt`](20260312_c9163b6/split/files/0146.txt)|[`0144.txt`](20250917_2efeece/split/files/0144.txt)||
`36kg`|[`0145.txt`](20260331_975d7d6/split/files/0145.txt)|[`0147.txt`](20260312_c9163b6/split/files/0147.txt)|[`0145.txt`](20250917_2efeece/split/files/0145.txt)||
`37cw`|[`0146.txt`](20260331_975d7d6/split/files/0146.txt)|[`0148.txt`](20260312_c9163b6/split/files/0148.txt)|[`0146.txt`](20250917_2efeece/split/files/0146.txt)||
`385c`|[`0147.txt`](20260331_975d7d6/split/files/0147.txt)|[`0149.txt`](20260312_c9163b6/split/files/0149.txt)|[`0147.txt`](20250917_2efeece/split/files/0147.txt)||
`38xs`|[`0148.txt`](20260331_975d7d6/split/files/0148.txt)|[`0150.txt`](20260312_c9163b6/split/files/0150.txt)|[`0148.txt`](20250917_2efeece/split/files/0148.txt)||
`39q8`|-|-|[`0149.txt`](20250917_2efeece/split/files/0149.txt)|「3月のライオン」<br>「三月のライオン」|読みが算用数字始まり
`3aio`|[`0149.txt`](20260331_975d7d6/split/files/0149.txt)|[`0151.txt`](20260312_c9163b6/split/files/0151.txt)|[`0150.txt`](20250917_2efeece/split/files/0150.txt)||
`3bb4`|[`0150.txt`](20260331_975d7d6/split/files/0150.txt)|[`0152.txt`](20260312_c9163b6/split/files/0152.txt)|[`0151.txt`](20250917_2efeece/split/files/0151.txt)||
`3c3k`|[`0151.txt`](20260331_975d7d6/split/files/0151.txt)|[`0153.txt`](20260312_c9163b6/split/files/0153.txt)|[`0152.txt`](20250917_2efeece/split/files/0152.txt)||
`3cw0`|[`0152.txt`](20260331_975d7d6/split/files/0152.txt)|[`0154.txt`](20260312_c9163b6/split/files/0154.txt)|[`0153.txt`](20250917_2efeece/split/files/0153.txt)||
`3dog`|[`0153.txt`](20260331_975d7d6/split/files/0153.txt)|[`0155.txt`](20260312_c9163b6/split/files/0155.txt)|[`0154.txt`](20250917_2efeece/split/files/0154.txt)||
`3egw`|[`0154.txt`](20260331_975d7d6/split/files/0154.txt)|[`0156.txt`](20260312_c9163b6/split/files/0156.txt)|[`0155.txt`](20250917_2efeece/split/files/0155.txt)||
`3f9c`|[`0155.txt`](20260331_975d7d6/split/files/0155.txt)|[`0157.txt`](20260312_c9163b6/split/files/0157.txt)|[`0156.txt`](20250917_2efeece/split/files/0156.txt)||
`3g1s`|[`0156.txt`](20260331_975d7d6/split/files/0156.txt)|[`0158.txt`](20260312_c9163b6/split/files/0158.txt)|[`0157.txt`](20250917_2efeece/split/files/0157.txt)||
`3gu8`|[`0157.txt`](20260331_975d7d6/split/files/0157.txt)|[`0159.txt`](20260312_c9163b6/split/files/0159.txt)|[`0158.txt`](20250917_2efeece/split/files/0158.txt)||
`3hmo`|[`0158.txt`](20260331_975d7d6/split/files/0158.txt)|[`0160.txt`](20260312_c9163b6/split/files/0160.txt)|[`0159.txt`](20250917_2efeece/split/files/0159.txt)||
`3if4`|[`0159.txt`](20260331_975d7d6/split/files/0159.txt)|[`0161.txt`](20260312_c9163b6/split/files/0161.txt)|[`0160.txt`](20250917_2efeece/split/files/0160.txt)||
`3itc`|-|[`0162.txt`](20260312_c9163b6/split/files/0162.txt)|-||
`3j7k`|[`0160.txt`](20260331_975d7d6/split/files/0160.txt)|[`0163.txt`](20260312_c9163b6/split/files/0163.txt)|[`0161.txt`](20250917_2efeece/split/files/0161.txt)||
`3k00`|[`0161.txt`](20260331_975d7d6/split/files/0161.txt)|[`0164.txt`](20260312_c9163b6/split/files/0164.txt)|[`0162.txt`](20250917_2efeece/split/files/0162.txt)||
`3ksg`|[`0162.txt`](20260331_975d7d6/split/files/0162.txt)|[`0165.txt`](20260312_c9163b6/split/files/0165.txt)|[`0163.txt`](20250917_2efeece/split/files/0163.txt)||
`3lkw`|[`0163.txt`](20260331_975d7d6/split/files/0163.txt)|[`0166.txt`](20260312_c9163b6/split/files/0166.txt)|[`0164.txt`](20250917_2efeece/split/files/0164.txt)||
`3mdc`|[`0164.txt`](20260331_975d7d6/split/files/0164.txt)|[`0167.txt`](20260312_c9163b6/split/files/0167.txt)|[`0165.txt`](20250917_2efeece/split/files/0165.txt)||
`3n5s`|[`0165.txt`](20260331_975d7d6/split/files/0165.txt)|[`0168.txt`](20260312_c9163b6/split/files/0168.txt)|[`0166.txt`](20250917_2efeece/split/files/0166.txt)||
`3ny8`|[`0166.txt`](20260331_975d7d6/split/files/0166.txt)|[`0169.txt`](20260312_c9163b6/split/files/0169.txt)|[`0167.txt`](20250917_2efeece/split/files/0167.txt)||
`3oqo`|[`0167.txt`](20260331_975d7d6/split/files/0167.txt)|[`0170.txt`](20260312_c9163b6/split/files/0170.txt)|[`0168.txt`](20250917_2efeece/split/files/0168.txt)||
`3pj4`|[`0168.txt`](20260331_975d7d6/split/files/0168.txt)|[`0171.txt`](20260312_c9163b6/split/files/0171.txt)|[`0169.txt`](20250917_2efeece/split/files/0169.txt)||
`3qbk`|[`0169.txt`](20260331_975d7d6/split/files/0169.txt)|[`0172.txt`](20260312_c9163b6/split/files/0172.txt)|[`0170.txt`](20250917_2efeece/split/files/0170.txt)||
`3r40`|[`0170.txt`](20260331_975d7d6/split/files/0170.txt)|[`0173.txt`](20260312_c9163b6/split/files/0173.txt)|[`0171.txt`](20250917_2efeece/split/files/0171.txt)||
`3rwg`|[`0171.txt`](20260331_975d7d6/split/files/0171.txt)|[`0174.txt`](20260312_c9163b6/split/files/0174.txt)|[`0172.txt`](20250917_2efeece/split/files/0172.txt)||
`3sow`|[`0172.txt`](20260331_975d7d6/split/files/0172.txt)|[`0175.txt`](20260312_c9163b6/split/files/0175.txt)|[`0173.txt`](20250917_2efeece/split/files/0173.txt)||
`3thc`|[`0173.txt`](20260331_975d7d6/split/files/0173.txt)|[`0176.txt`](20260312_c9163b6/split/files/0176.txt)|[`0174.txt`](20250917_2efeece/split/files/0174.txt)||
`3u9s`|[`0174.txt`](20260331_975d7d6/split/files/0174.txt)|[`0177.txt`](20260312_c9163b6/split/files/0177.txt)|[`0175.txt`](20250917_2efeece/split/files/0175.txt)||
`3v28`|[`0175.txt`](20260331_975d7d6/split/files/0175.txt)|[`0178.txt`](20260312_c9163b6/split/files/0178.txt)|[`0176.txt`](20250917_2efeece/split/files/0176.txt)||
`3vuo`|[`0176.txt`](20260331_975d7d6/split/files/0176.txt)|[`0179.txt`](20260312_c9163b6/split/files/0179.txt)|[`0177.txt`](20250917_2efeece/split/files/0177.txt)||
`3wn4`|[`0177.txt`](20260331_975d7d6/split/files/0177.txt)|[`0180.txt`](20260312_c9163b6/split/files/0180.txt)|[`0178.txt`](20250917_2efeece/split/files/0178.txt)||
`3xfk`|[`0178.txt`](20260331_975d7d6/split/files/0178.txt)|[`0181.txt`](20260312_c9163b6/split/files/0181.txt)|[`0179.txt`](20250917_2efeece/split/files/0179.txt)||
`3y80`|[`0179.txt`](20260331_975d7d6/split/files/0179.txt)|[`0182.txt`](20260312_c9163b6/split/files/0182.txt)|[`0180.txt`](20250917_2efeece/split/files/0180.txt)||
`3z0g`|[`0180.txt`](20260331_975d7d6/split/files/0180.txt)|[`0183.txt`](20260312_c9163b6/split/files/0183.txt)|[`0181.txt`](20250917_2efeece/split/files/0181.txt)||
`3zsw`|[`0181.txt`](20260331_975d7d6/split/files/0181.txt)|[`0184.txt`](20260312_c9163b6/split/files/0184.txt)|[`0182.txt`](20250917_2efeece/split/files/0182.txt)||
`40lc`|[`0182.txt`](20260331_975d7d6/split/files/0182.txt)|[`0185.txt`](20260312_c9163b6/split/files/0185.txt)|[`0183.txt`](20250917_2efeece/split/files/0183.txt)||
`41ds`|[`0183.txt`](20260331_975d7d6/split/files/0183.txt)|[`0186.txt`](20260312_c9163b6/split/files/0186.txt)|[`0184.txt`](20250917_2efeece/split/files/0184.txt)||
`41s0`|-|[`0187.txt`](20260312_c9163b6/split/files/0187.txt)|-||
`4268`|[`0184.txt`](20260331_975d7d6/split/files/0184.txt)|[`0188.txt`](20260312_c9163b6/split/files/0188.txt)|[`0185.txt`](20250917_2efeece/split/files/0185.txt)||
`42yo`|[`0185.txt`](20260331_975d7d6/split/files/0185.txt)|[`0189.txt`](20260312_c9163b6/split/files/0189.txt)|[`0186.txt`](20250917_2efeece/split/files/0186.txt)||
`43r4`|[`0186.txt`](20260331_975d7d6/split/files/0186.txt)|[`0190.txt`](20260312_c9163b6/split/files/0190.txt)|[`0187.txt`](20250917_2efeece/split/files/0187.txt)||
`44jk`|[`0187.txt`](20260331_975d7d6/split/files/0187.txt)|[`0191.txt`](20260312_c9163b6/split/files/0191.txt)|[`0188.txt`](20250917_2efeece/split/files/0188.txt)||
`45c0`|[`0188.txt`](20260331_975d7d6/split/files/0188.txt)|[`0192.txt`](20260312_c9163b6/split/files/0192.txt)|[`0189.txt`](20250917_2efeece/split/files/0189.txt)||
`45q8`|[`0189.txt`](20260331_975d7d6/split/files/0189.txt)|-|-||
`464g`|[`0190.txt`](20260331_975d7d6/split/files/0190.txt)|[`0193.txt`](20260312_c9163b6/split/files/0193.txt)|[`0190.txt`](20250917_2efeece/split/files/0190.txt)||
`46ww`|[`0191.txt`](20260331_975d7d6/split/files/0191.txt)|[`0194.txt`](20260312_c9163b6/split/files/0194.txt)|[`0191.txt`](20250917_2efeece/split/files/0191.txt)||
`47pc`|[`0192.txt`](20260331_975d7d6/split/files/0192.txt)|[`0195.txt`](20260312_c9163b6/split/files/0195.txt)|[`0192.txt`](20250917_2efeece/split/files/0192.txt)||
`48hs`|[`0193.txt`](20260331_975d7d6/split/files/0193.txt)|[`0196.txt`](20260312_c9163b6/split/files/0196.txt)|[`0193.txt`](20250917_2efeece/split/files/0193.txt)||
`49a8`|[`0194.txt`](20260331_975d7d6/split/files/0194.txt)|[`0197.txt`](20260312_c9163b6/split/files/0197.txt)|[`0194.txt`](20250917_2efeece/split/files/0194.txt)||
`4a2o`|[`0195.txt`](20260331_975d7d6/split/files/0195.txt)|[`0198.txt`](20260312_c9163b6/split/files/0198.txt)|[`0195.txt`](20250917_2efeece/split/files/0195.txt)||
`4av4`|[`0196.txt`](20260331_975d7d6/split/files/0196.txt)|[`0199.txt`](20260312_c9163b6/split/files/0199.txt)|[`0196.txt`](20250917_2efeece/split/files/0196.txt)||
`4bnk`|[`0197.txt`](20260331_975d7d6/split/files/0197.txt)|[`0200.txt`](20260312_c9163b6/split/files/0200.txt)|[`0197.txt`](20250917_2efeece/split/files/0197.txt)||
`4cg0`|[`0198.txt`](20260331_975d7d6/split/files/0198.txt)|[`0201.txt`](20260312_c9163b6/split/files/0201.txt)|[`0198.txt`](20250917_2efeece/split/files/0198.txt)||
`4d8g`|[`0199.txt`](20260331_975d7d6/split/files/0199.txt)|[`0202.txt`](20260312_c9163b6/split/files/0202.txt)|[`0199.txt`](20250917_2efeece/split/files/0199.txt)||
`4e0w`|[`0200.txt`](20260331_975d7d6/split/files/0200.txt)|[`0203.txt`](20260312_c9163b6/split/files/0203.txt)|[`0200.txt`](20250917_2efeece/split/files/0200.txt)||
`4etc`|[`0201.txt`](20260331_975d7d6/split/files/0201.txt)|[`0204.txt`](20260312_c9163b6/split/files/0204.txt)|[`0201.txt`](20250917_2efeece/split/files/0201.txt)||
`4fls`|[`0202.txt`](20260331_975d7d6/split/files/0202.txt)|[`0205.txt`](20260312_c9163b6/split/files/0205.txt)|[`0202.txt`](20250917_2efeece/split/files/0202.txt)||
`4ge8`|[`0203.txt`](20260331_975d7d6/split/files/0203.txt)|[`0206.txt`](20260312_c9163b6/split/files/0206.txt)|[`0203.txt`](20250917_2efeece/split/files/0203.txt)||
`4h6o`|[`0204.txt`](20260331_975d7d6/split/files/0204.txt)|[`0207.txt`](20260312_c9163b6/split/files/0207.txt)|[`0204.txt`](20250917_2efeece/split/files/0204.txt)||
`4hz4`|[`0205.txt`](20260331_975d7d6/split/files/0205.txt)|[`0208.txt`](20260312_c9163b6/split/files/0208.txt)|[`0205.txt`](20250917_2efeece/split/files/0205.txt)||
`4irk`|[`0206.txt`](20260331_975d7d6/split/files/0206.txt)|[`0209.txt`](20260312_c9163b6/split/files/0209.txt)|[`0206.txt`](20250917_2efeece/split/files/0206.txt)||
`4jk0`|[`0207.txt`](20260331_975d7d6/split/files/0207.txt)|[`0210.txt`](20260312_c9163b6/split/files/0210.txt)|[`0207.txt`](20250917_2efeece/split/files/0207.txt)||
`4kcg`|[`0208.txt`](20260331_975d7d6/split/files/0208.txt)|[`0211.txt`](20260312_c9163b6/split/files/0211.txt)|[`0208.txt`](20250917_2efeece/split/files/0208.txt)||
`4l4w`|[`0209.txt`](20260331_975d7d6/split/files/0209.txt)|[`0212.txt`](20260312_c9163b6/split/files/0212.txt)|[`0209.txt`](20250917_2efeece/split/files/0209.txt)||
`4lxc`|[`0210.txt`](20260331_975d7d6/split/files/0210.txt)|[`0213.txt`](20260312_c9163b6/split/files/0213.txt)|[`0210.txt`](20250917_2efeece/split/files/0210.txt)||
`4mps`|[`0211.txt`](20260331_975d7d6/split/files/0211.txt)|[`0214.txt`](20260312_c9163b6/split/files/0214.txt)|[`0211.txt`](20250917_2efeece/split/files/0211.txt)||
`4ni8`|[`0212.txt`](20260331_975d7d6/split/files/0212.txt)|[`0215.txt`](20260312_c9163b6/split/files/0215.txt)|[`0212.txt`](20250917_2efeece/split/files/0212.txt)||
`4oao`|[`0213.txt`](20260331_975d7d6/split/files/0213.txt)|[`0216.txt`](20260312_c9163b6/split/files/0216.txt)|[`0213.txt`](20250917_2efeece/split/files/0213.txt)||
`4p34`|[`0214.txt`](20260331_975d7d6/split/files/0214.txt)|[`0217.txt`](20260312_c9163b6/split/files/0217.txt)|[`0214.txt`](20250917_2efeece/split/files/0214.txt)||
`4pvk`|[`0215.txt`](20260331_975d7d6/split/files/0215.txt)|[`0218.txt`](20260312_c9163b6/split/files/0218.txt)|[`0215.txt`](20250917_2efeece/split/files/0215.txt)||
`4qo0`|[`0216.txt`](20260331_975d7d6/split/files/0216.txt)|[`0219.txt`](20260312_c9163b6/split/files/0219.txt)|[`0216.txt`](20250917_2efeece/split/files/0216.txt)||
`4rgg`|[`0217.txt`](20260331_975d7d6/split/files/0217.txt)|[`0220.txt`](20260312_c9163b6/split/files/0220.txt)|[`0217.txt`](20250917_2efeece/split/files/0217.txt)||
`4s8w`|[`0218.txt`](20260331_975d7d6/split/files/0218.txt)|[`0221.txt`](20260312_c9163b6/split/files/0221.txt)|[`0218.txt`](20250917_2efeece/split/files/0218.txt)||
`4t1c`|[`0219.txt`](20260331_975d7d6/split/files/0219.txt)|[`0222.txt`](20260312_c9163b6/split/files/0222.txt)|[`0219.txt`](20250917_2efeece/split/files/0219.txt)||
`4tts`|-|-|[`0220.txt`](20250917_2efeece/split/files/0220.txt)|「ニコニコVIP2ch」|おそらく↑「`4t1c`」の欠片
`4um8`|[`0220.txt`](20260331_975d7d6/split/files/0220.txt)|[`0223.txt`](20260312_c9163b6/split/files/0223.txt)|[`0221.txt`](20250917_2efeece/split/files/0221.txt)||
`4veo`|[`0221.txt`](20260331_975d7d6/split/files/0221.txt)|[`0224.txt`](20260312_c9163b6/split/files/0224.txt)|[`0222.txt`](20250917_2efeece/split/files/0222.txt)||
`4w74`|[`0222.txt`](20260331_975d7d6/split/files/0222.txt)|[`0225.txt`](20260312_c9163b6/split/files/0225.txt)|[`0223.txt`](20250917_2efeece/split/files/0223.txt)||
`4wzk`|[`0223.txt`](20260331_975d7d6/split/files/0223.txt)|[`0226.txt`](20260312_c9163b6/split/files/0226.txt)|[`0224.txt`](20250917_2efeece/split/files/0224.txt)||
`4xds`|[`0224.txt`](20260331_975d7d6/split/files/0224.txt)|[`0227.txt`](20260312_c9163b6/split/files/0227.txt)|-||
`4xs0`|[`0225.txt`](20260331_975d7d6/split/files/0225.txt)|[`0228.txt`](20260312_c9163b6/split/files/0228.txt)|[`0225.txt`](20250917_2efeece/split/files/0225.txt)||
`4ykg`|[`0226.txt`](20260331_975d7d6/split/files/0226.txt)|[`0229.txt`](20260312_c9163b6/split/files/0229.txt)|[`0226.txt`](20250917_2efeece/split/files/0226.txt)||
`4zcw`|[`0227.txt`](20260331_975d7d6/split/files/0227.txt)|[`0230.txt`](20260312_c9163b6/split/files/0230.txt)|[`0227.txt`](20250917_2efeece/split/files/0227.txt)||
`505c`|[`0228.txt`](20260331_975d7d6/split/files/0228.txt)|[`0231.txt`](20260312_c9163b6/split/files/0231.txt)|[`0228.txt`](20250917_2efeece/split/files/0228.txt)||
`50xs`|[`0229.txt`](20260331_975d7d6/split/files/0229.txt)|[`0232.txt`](20260312_c9163b6/split/files/0232.txt)|[`0229.txt`](20250917_2efeece/split/files/0229.txt)||
`51q8`|[`0230.txt`](20260331_975d7d6/split/files/0230.txt)|[`0233.txt`](20260312_c9163b6/split/files/0233.txt)|[`0230.txt`](20250917_2efeece/split/files/0230.txt)||
`52io`|[`0231.txt`](20260331_975d7d6/split/files/0231.txt)|[`0234.txt`](20260312_c9163b6/split/files/0234.txt)|[`0231.txt`](20250917_2efeece/split/files/0231.txt)||
`53b4`|[`0232.txt`](20260331_975d7d6/split/files/0232.txt)|[`0235.txt`](20260312_c9163b6/split/files/0235.txt)|[`0232.txt`](20250917_2efeece/split/files/0232.txt)||
`543k`|[`0233.txt`](20260331_975d7d6/split/files/0233.txt)|[`0236.txt`](20260312_c9163b6/split/files/0236.txt)|[`0233.txt`](20250917_2efeece/split/files/0233.txt)||
`54w0`|[`0234.txt`](20260331_975d7d6/split/files/0234.txt)|[`0237.txt`](20260312_c9163b6/split/files/0237.txt)|[`0234.txt`](20250917_2efeece/split/files/0234.txt)||
`55og`|[`0235.txt`](20260331_975d7d6/split/files/0235.txt)|[`0238.txt`](20260312_c9163b6/split/files/0238.txt)|[`0235.txt`](20250917_2efeece/split/files/0235.txt)||
`56gw`|[`0236.txt`](20260331_975d7d6/split/files/0236.txt)|[`0239.txt`](20260312_c9163b6/split/files/0239.txt)|[`0236.txt`](20250917_2efeece/split/files/0236.txt)||
`579c`|[`0237.txt`](20260331_975d7d6/split/files/0237.txt)|[`0240.txt`](20260312_c9163b6/split/files/0240.txt)|[`0237.txt`](20250917_2efeece/split/files/0237.txt)||
`581s`|[`0238.txt`](20260331_975d7d6/split/files/0238.txt)|[`0241.txt`](20260312_c9163b6/split/files/0241.txt)|[`0238.txt`](20250917_2efeece/split/files/0238.txt)||
`58u8`|[`0239.txt`](20260331_975d7d6/split/files/0239.txt)|[`0242.txt`](20260312_c9163b6/split/files/0242.txt)|[`0239.txt`](20250917_2efeece/split/files/0239.txt)||
`59mo`|[`0240.txt`](20260331_975d7d6/split/files/0240.txt)|[`0243.txt`](20260312_c9163b6/split/files/0243.txt)|[`0240.txt`](20250917_2efeece/split/files/0240.txt)||
`5af4`|[`0241.txt`](20260331_975d7d6/split/files/0241.txt)|[`0244.txt`](20260312_c9163b6/split/files/0244.txt)|[`0241.txt`](20250917_2efeece/split/files/0241.txt)||
`5b7k`|[`0242.txt`](20260331_975d7d6/split/files/0242.txt)|[`0245.txt`](20260312_c9163b6/split/files/0245.txt)|[`0242.txt`](20250917_2efeece/split/files/0242.txt)||
`5c00`|[`0243.txt`](20260331_975d7d6/split/files/0243.txt)|[`0246.txt`](20260312_c9163b6/split/files/0246.txt)|[`0243.txt`](20250917_2efeece/split/files/0243.txt)||
`5csg`|[`0244.txt`](20260331_975d7d6/split/files/0244.txt)|[`0247.txt`](20260312_c9163b6/split/files/0247.txt)|[`0244.txt`](20250917_2efeece/split/files/0244.txt)||
`5dkw`|[`0245.txt`](20260331_975d7d6/split/files/0245.txt)|[`0248.txt`](20260312_c9163b6/split/files/0248.txt)|[`0245.txt`](20250917_2efeece/split/files/0245.txt)||
`5edc`|[`0246.txt`](20260331_975d7d6/split/files/0246.txt)|[`0249.txt`](20260312_c9163b6/split/files/0249.txt)|[`0246.txt`](20250917_2efeece/split/files/0246.txt)||
`5f5s`|[`0247.txt`](20260331_975d7d6/split/files/0247.txt)|[`0250.txt`](20260312_c9163b6/split/files/0250.txt)|[`0247.txt`](20250917_2efeece/split/files/0247.txt)||
`5fy8`|[`0248.txt`](20260331_975d7d6/split/files/0248.txt)|[`0251.txt`](20260312_c9163b6/split/files/0251.txt)|[`0248.txt`](20250917_2efeece/split/files/0248.txt)||
`5gqo`|[`0249.txt`](20260331_975d7d6/split/files/0249.txt)|[`0252.txt`](20260312_c9163b6/split/files/0252.txt)|[`0249.txt`](20250917_2efeece/split/files/0249.txt)||
`5hj4`|[`0250.txt`](20260331_975d7d6/split/files/0250.txt)|[`0253.txt`](20260312_c9163b6/split/files/0253.txt)|[`0250.txt`](20250917_2efeece/split/files/0250.txt)||
`5ibk`|[`0251.txt`](20260331_975d7d6/split/files/0251.txt)|[`0254.txt`](20260312_c9163b6/split/files/0254.txt)|[`0251.txt`](20250917_2efeece/split/files/0251.txt)||
`5j40`|[`0252.txt`](20260331_975d7d6/split/files/0252.txt)|[`0255.txt`](20260312_c9163b6/split/files/0255.txt)|[`0252.txt`](20250917_2efeece/split/files/0252.txt)||
`5jwg`|[`0253.txt`](20260331_975d7d6/split/files/0253.txt)|[`0256.txt`](20260312_c9163b6/split/files/0256.txt)|[`0253.txt`](20250917_2efeece/split/files/0253.txt)||
`5kow`|[`0254.txt`](20260331_975d7d6/split/files/0254.txt)|[`0257.txt`](20260312_c9163b6/split/files/0257.txt)|[`0254.txt`](20250917_2efeece/split/files/0254.txt)||
`5lhc`|[`0255.txt`](20260331_975d7d6/split/files/0255.txt)|[`0258.txt`](20260312_c9163b6/split/files/0258.txt)|[`0255.txt`](20250917_2efeece/split/files/0255.txt)||
`5m9s`|[`0256.txt`](20260331_975d7d6/split/files/0256.txt)|[`0259.txt`](20260312_c9163b6/split/files/0259.txt)|[`0256.txt`](20250917_2efeece/split/files/0256.txt)||
`5n28`|[`0257.txt`](20260331_975d7d6/split/files/0257.txt)|[`0260.txt`](20260312_c9163b6/split/files/0260.txt)|[`0257.txt`](20250917_2efeece/split/files/0257.txt)||
`5nuo`|[`0258.txt`](20260331_975d7d6/split/files/0258.txt)|[`0261.txt`](20260312_c9163b6/split/files/0261.txt)|[`0258.txt`](20250917_2efeece/split/files/0258.txt)||
`5on4`|[`0259.txt`](20260331_975d7d6/split/files/0259.txt)|[`0262.txt`](20260312_c9163b6/split/files/0262.txt)|[`0259.txt`](20250917_2efeece/split/files/0259.txt)||
`5pfk`|[`0260.txt`](20260331_975d7d6/split/files/0260.txt)|[`0263.txt`](20260312_c9163b6/split/files/0263.txt)|[`0260.txt`](20250917_2efeece/split/files/0260.txt)||
`5q80`|[`0261.txt`](20260331_975d7d6/split/files/0261.txt)|[`0264.txt`](20260312_c9163b6/split/files/0264.txt)|[`0261.txt`](20250917_2efeece/split/files/0261.txt)||
`5r0g`|[`0262.txt`](20260331_975d7d6/split/files/0262.txt)|[`0265.txt`](20260312_c9163b6/split/files/0265.txt)|[`0262.txt`](20250917_2efeece/split/files/0262.txt)||
`5rsw`|[`0263.txt`](20260331_975d7d6/split/files/0263.txt)|[`0266.txt`](20260312_c9163b6/split/files/0266.txt)|[`0263.txt`](20250917_2efeece/split/files/0263.txt)||
`5slc`|[`0264.txt`](20260331_975d7d6/split/files/0264.txt)|[`0267.txt`](20260312_c9163b6/split/files/0267.txt)|[`0264.txt`](20250917_2efeece/split/files/0264.txt)||
`5tds`|[`0265.txt`](20260331_975d7d6/split/files/0265.txt)|[`0268.txt`](20260312_c9163b6/split/files/0268.txt)|[`0265.txt`](20250917_2efeece/split/files/0265.txt)||
`5u68`|[`0266.txt`](20260331_975d7d6/split/files/0266.txt)|[`0269.txt`](20260312_c9163b6/split/files/0269.txt)|[`0266.txt`](20250917_2efeece/split/files/0266.txt)||
`5uyo`|[`0267.txt`](20260331_975d7d6/split/files/0267.txt)|[`0270.txt`](20260312_c9163b6/split/files/0270.txt)|[`0267.txt`](20250917_2efeece/split/files/0267.txt)||
`5vr4`|[`0268.txt`](20260331_975d7d6/split/files/0268.txt)|[`0271.txt`](20260312_c9163b6/split/files/0271.txt)|[`0268.txt`](20250917_2efeece/split/files/0268.txt)||
`5wjk`|[`0269.txt`](20260331_975d7d6/split/files/0269.txt)|[`0272.txt`](20260312_c9163b6/split/files/0272.txt)|[`0269.txt`](20250917_2efeece/split/files/0269.txt)||



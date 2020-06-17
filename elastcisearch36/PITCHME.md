## 公式 token/char filters 総ざらい

---

## @kaiba

- Rails, iOS
- 最近はサーバサイド Kotlin + GraphQL
- DB 設計したい Night 主催
- ロードバイク、温泉、日本酒、ギター、DTM
- 検索だけじゃない Elasticsearch 入門
- 💜Elasticsearch

---

## https://kaiba.booth.pm/

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/era.jpg?raw=true)

---

## 今日話すこと

- Elasticsearch token/char filters
- Query の filter ではないです
- 数が多いのでよく使いそうなやつを重点的に
- 試していないのもあるので動かない例もあるかも…

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/filter.png?raw=true)

---

## きっかけ

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/wakaran.png?raw=true)

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/discuss.png?raw=true)

結局 filter でできた…

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/ebi.png?raw=true)

---

## filter 勉強するぞ!

---

## 感謝の登壇駆動学習！

お付き合いいただきありがとうございます 😊  
登壇駆動学習で #37 で登壇だ！

---

## filter とは？

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/filter-coffee-bubble-drip.jpg?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter1.png?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter2.png?raw=true)

余計なものを捨てるだけじゃなく「加工する」意味合いです。

---

## 全部調べてみました(一部の plugin を除く)

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter_list.png?raw=true)

正直登壇を後悔しました…

---

## 全部見ていくと日が暮れるので今日は有用なやつをチョイスしてお届けします!

---

## HTML strip

- HTML を取り除く
- `<em>やばい</em>` を `やばい` にしてくれる
  - `em` でヒットしてほしくない
- スクレイピングした結果をそのまま入れるときとか良さそう

---

## HTML strip

- HTML を取り除く
- `<em>やばい</em>` を `やばい` にしてくれる
  - `em` でヒットしてほしくない
- スクレイピングした結果をそのまま入れるときとか良さそう

---

## Mapping

- 文字の変換を行う Char filter
- 🍣 => 寿司
- 頑張れば emoji もヒットするようにできそう

---

## CJK width

- Chinese-Japanese-Korean の全角、半角を統一する
- ﾊﾝｶｸが生まれる前に消し去りたい
- ICU plugin ではない

---

## Lowercase / Uppercase

- 英語の大文字小文字の統一

---

## ICU Normalization Token Filter

- ICU plugin の char filter
- 丸数字、㌀、全角半角、旧字体などを正規化する
- International Components for Unicode

---

## ICU Folding Token Filter

- å などを a に正規化する。濁点、伸ばし棒も消える。
- スマホ入力のサジェストにいいかも。孫を探すとき「まこ」でサジェストできる。

---

## kuromoji_readingform

- kuromoji plugin の token filter
- よみがなを生成する

---

## kuromoji_stemmer

- サーバー => サーバ などの揺れを統一する

---

## kuromoji_baseform

- 基本形に変換する(飲み=>飲む)

---

## Stop

- 指定の Stop word(a とか the などの検索に使用しない token)を取り除く
- 日本語だと、あの、その、こと、する、いる、てにおは、などが stop words に指定されることが多い
- NG ワードとかここに入れてもいいのかな？

---

## Trim

- 前後のスペースを除去する

---

## Pattern Replace Char Filter

- 正規表現で置換ができる。080-1234-1234 を 08012341234 にしたりできる

---

## Edge n-gram

- n-gram で分割された token を生成する。先頭からヒットする。
- suggest に便利
- 昔は engram と呼ばれていたようです

---

## Synonym

- 同義語を設定できる
- エラスティックサーチ、ElasticSearch => Elasticsearch

---

## その他面白かったこと

- 他の国も形態素解析には苦労している
- ステミング(語形の統一)にも苦労している
- 検索だけではなく、類似文書、クラスタリングのためのフィルタもある
- ドイツ語は 1 単語に複数の単語があるケースがあるらしい、とか各国様々なルールがある

---

## ありがとうございました！ 質問があればどうぞ！

- [調査資料](https://docs.google.com/spreadsheets/d/1Jrtc81Wv1XEBFz_HeMkj1HJjrJcoTVW-xn_aL12AjLk/edit?usp=sharing)
- 次回は filter を書いて見ようかなぁ…

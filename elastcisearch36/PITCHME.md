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

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/filter.png?raw=true)

---

## きっかけ

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/wakaran.png?raw=true)

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/discuss.png?raw=true)

実は filter に触ったことなかった。  
filter のドキュメント漁ったけど、わからなかったので質問させてもらいましたが、結局 filter でできた…

---

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/ebi.png?raw=true)

---

## 全種類 の token/char filters 全員と対話を終えていく!

---

## 感謝の登壇駆動学習！

お付き合いいただきありがとうございます 😊

---

## filter とは？

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/filter-coffee-bubble-drip.jpg?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter1.png?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter2.png?raw=true)

---

## 100 近くあるフィルタ、全部調べてみました

![](https://github.com/kaibadash/gitpitch/blob/master/elastcisearch36/es_filter_list.png?raw=true)

正直登壇を後悔しました…

---

## HTML strip

- HTML を取り除く
- `<em>やばい</em>` を `やばい` にしてくれる
  - `em` でヒットしてほしくない
- スクレイピングした結果をそのまま入れるときとか良さそう

---

## 全部見ていくと日が暮れるので今日は有用なやつをチョイスしてお届けします!

- 全部調べたのでそこは資料を公開します

---

## HTML strip

- HTML を取り除く
- `<em>やばい</em>` を `やばい` にしてくれる
  - `em` でヒットしてほしくない
- スクレイピングした結果をそのまま入れるときとか良さそう

---

## 続きは頑張って書きます！

---

## 多分答えられないけど質問があればどうぞ！

- チャットで全員宛で送ってください

## Elasticsearch 公式フィルタ総ざらい

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

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/era.jpg?raw=true)

---

## 今日のお話

- Elasticsearch token/char filters
- Query の filter やつじゃないです
- 数が多いのでよく使いそうなやつを重点的に

![](https://github.com/kaibadash/gitpitch/blob/master/elasticsearch36/filter.png?raw=true)

---

## きっかけ

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/discuss.png?raw=true)

実は filter に触ったことなかった。  
filter のドキュメント漁ったけど、わからなかったので質問させてもらいましたが、結局 filter でできた…

---

## 全種類 の token/char filters 全員と対話を終えていく!

---

## 感謝の登壇駆動学習！

お付き合いいただきありがとうございます 😊

---

## filter とは？

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/filter-coffee-bubble-drip.jpg?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/es_filter1.png?raw=true)

---

## 例

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/es_filter2.png?raw=true)

---

# 100 近くあるフィルタ、全部調べてみました

個人的に重要と思った順にいくつか紹介します。

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/es_filter_list.png?raw=true)

---

## HTML strip

- HTML を取り除く
- スクレイピングした結果をそのまま入れるとか良さそう

---

## TBD

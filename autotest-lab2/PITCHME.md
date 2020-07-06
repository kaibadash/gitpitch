## Rails 使いが久しぶりに Kotlin でテスト書いたり悩んだり

---

- [てすらぼみーとあっぷ #2](https://autotest-lab.connpass.com/event/181312/)
- [プレゼンのリンク](https://gitpitch.com/kaibadash/gitpitch/master?p=autotest-lab2#/)

---

## @kaiba

- Rails, iOS
- 最近はサーバサイド Kotlin + GraphQL
- DB 設計したい Night 主催
- ロードバイク、温泉、日本酒、ギター、DTM
- 💜Elasticsearch

---

## [kaiba.booth.pm](https://kaiba.booth.pm/)

![](https://github.com/kaibadash/gitpitch/blob/master/autotest-lab2/ebook.png?raw=true)

---

## 経歴

- Java,C#,C,Android,Objective-C,JavaScript,TypeScript,Angular,PHP
- Rails, Swift
- PHP
- Kotlin

---

## 今日話すこと

- Rails はいいぞ
- RSpec はいいぞ
- Factory Bot はいいぞ
- JVM でどうすればいいぞ？
- テストダブルはつらいぞ?

---

## Rails はいいぞ

---

## Ruby on Rails

- Rack の実装
- Rack アプリケーションは他にも Cinatora とか Hanami がある
- DHH が作者

---

## Rails は全部入り

- 強力な ORM、Active Record
- 強力なコードジェネレータ
- テンプレートエンジン ERB
- Migration
- minitest or RSpec
  - DHH は minitest 派
- Ruby は書いてて気持ちがいい! 楽しい!

---

## RSpec はいいぞ

- DSL で英語っぽく書けるが DSL なので癖はある
- ここだけちょっと違うんだけど…が書きやすい
- テストの出力も英語っぽい
- RSpec も書いてて気持ちがいい! 楽しい!

---

## RSpec の例

TODO

---

## RSpec の出力例

---

## RSpec のテストデータ生成

- ライブラリ Factory Bot が事実上標準
- デフォルトのデータを定義し、特定のカラムを上書きする形でテストデータを定義できる

---

## Factory Bot の例

TODO

---

## JVM でどうすればいいぞ？

---

## システム構成図

TODO

きれいにフロントとバックエンドが別れている。

---

## 必要になったこと

- API の入出力を担保したい
- フロントの開発を待たずに開発を進めたい
- 認証、認可をモックしたい
- 外部サービスをモックしたい

---

## JVM では好きなのを組み合わせて使う

JVM はそれぞれ自分で選んで組み合わせる

- JUnit or TestNG
- DBSetup or DBUnit
- Mockito or PowerMock

---

## テストのフレームワーク

TODO:それぞれの役割をシステム構成図に重ねる

---

## 外部サービスのモック

- Docker VS Mock
- Docker: S3, Elasticsearch
- Mock: 独自サービス

---

TODO: オチを考える

---

TODO: まとめる

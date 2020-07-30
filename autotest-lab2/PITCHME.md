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

![](https://github.com/kaibadash/gitpitch/blob/master/autotest-lab2/career.png?raw=true)

---

## 今日話すこと

- Rails, RSpec, Factory Bot はいいぞ
- そんな Rails 使いは Kotlin(JVM) ではどうした?
- リクエストスペックを書いたよ

---

## Rails, RSpec, Factory Bot はいいぞ

---

## Ruby on Rails

- DHH が作者
- Rack の実装
- Rack アプリケーションは他にも Sinatora とか Hanami がある

---

## Rails はいいぞ

- 強力な ORM、Active Record
- 強力なコードジェネレータ
- 豊富な gem
- テンプレートエンジン ERB
- Migration
- minitest or RSpec
  - DHH は minitest 派
- Ruby は書いてて気持ちがいい! 楽しい!

---

## RSpec はいいぞ

- DSL で英語っぽく書けるが癖はある
- ここだけちょっと違うんだけど…が書きやすい
- テストの出力も英語っぽい
- RSpec も書いてて気持ちがいい! 楽しい!

---

## RSpec の例

```ruby
subject { Omikujibashira.omikuji(*args) }

context "with nil" do
  let (:args) { [nil] }
  it { is_expected.to eq nil }
end

context "with string args" do
  let (:args) { [["kaiba", "taki", "yasai", "neco"]] }
  it { is_expected.to be_kind_of(String) }
end
```

---

## RSpec のテストデータ生成

- Factory Bot が事実上標準(?)
- デフォルトのデータを定義し、特定のカラムを上書きする形でテストデータを定義できる

---

## Factory Bot の例

```ruby
FactoryBot.define do
  factory :user, class: User do
    name { "kaiba" }
    status { "active" }
  end
end
```

```ruby
user = create(:user, status: "banned")
```

---

## Rails 使いは Kotlin でどんなテストを書いたか

---

## システム構成図

![](https://github.com/kaibadash/gitpitch/blob/master/autotest-lab2/system1.png?raw=true)

---

## 状況

- フロントエンドの開発がプロトタイプとして先行
- フロントエンド「API はよ」
- API はフロントから呼んで実装してた
- やがてバックエンドが先行の箇所もでてきた
- フロントエンドがないのでテスト書いてテストした

---

## 必要になったこと

- API の入出力を担保したい
- フロントの開発を待たずに開発を進めたい
- 外部サービスをモックして CI の環境として使いたい

---

## こうしたい

![](https://github.com/kaibadash/gitpitch/blob/master/autotest-lab2/system2.png?raw=true)

---

## リクエストスペック

- API の入出力を担保する
  - どんな GraphQL の Query を受け取るか
  - どんな JSON を返すか
- テストケースを書きやすい
- 実行が速い。E2E に比べて安定。
- フロントエンドのデザイン変更の可能性があった

---

## JVM では好きなのを組み合わせて使う

JVM はそれぞれ自分で選んで組み合わせる

- JUnit or TestNG
- DBSetup or DBUnit
- Mockito or PowerMock
- 今回は好みで前者を選びました

---

## Docker にできるところは Docker

- MySQL
- S3
  - Minio
- 自社サービスはモック… モックはやっぱり辛い。
  - どこをいつモックするか…
  - モックにした部分が実行されない…
  - Mockito と Kotlin の相性もあんまり…

---

## HTTP スタブサーバを見つけた!

- https://github.com/2do2go/mocky

```javascript
var mocky = require("mocky");

mocky
  .createServer([
    {
      url: "/someurl1?a=b&c=d",
      method: "get",
      res: "response for GET request",
    },
  ])
  .listen(4321);
```

---

## 結果

- フロントの開発を待たずに開発ができるようになった
- デプロイ前にバグに気づけてデグレが減った
- バグ修正の際に「テスト書いたからもう多分大丈夫」と言える
- フロントからポチポチせずに開発できるので開発速度は上がった
- TDD もできるようになった。ちょっとやった。
- 運気が上がって健康になり、宝くじも高額当選しました(嘘)

---

## まとめ

- 何をテストしたいか考えて何のテストを書くか選択する
- モックは難しいのでできれば Docker に寄せる
  - Docker にないようなサービスをうまく外だしする方法ないかなぁ…
- 最初のテストは辛いけど、テストを書くと開発速度は上がる
  - 0 と 1 の差は大きい

---

## 俺たちの自動テストはまだ始まったばかりだ！

ありがとうございました

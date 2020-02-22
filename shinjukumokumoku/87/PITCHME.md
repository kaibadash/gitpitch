# shinjukumokumoku #87

---

## 予実

- [x] Contentful
- [x] Esのお仕事mtg
- [ ] Instagram風アプリケーション
  - [ ] Twitter認証
  - [ ] EXIF

---

## Contentful

- 完全に理解した

---

## はまったところ

- contentful-jekyll-data-import で jekyll に contentful を表示する
- 関連情報(ex: 本 => 本の著者)をどうする?
- markdownどう吐く?

---

## うまくいった(ﾄﾞﾔｧ)

- gem jekyll-contentful-data-import 完全に理解した
  - rake contentful すると yaml が吐かれる
  - 一覧ページはyamlから生成できた
  - GraphQLでとって来てくれるのではなく、バッチ
  - contentfulをいじっても更新されないが、jekyllらしいアプローチで好感が持てる(個人比)

---

## うまくいった(ﾄﾞﾔｧ2)

- しかし、詳細ページはmarkdownを吐く必要がありそうだ
- jekyll-contentful-data-import で mapper をかけるので markdown を吐いた
  - あんまりこだわりたくないので erb をテンプレートにして md を吐いた
- なんか普通だけど、そこそこきれいに書けた気がする





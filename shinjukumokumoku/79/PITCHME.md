# shinjukumokumoku #79

---

## Instagram 風アプリケーションの実装

- ユーザ登録 by yszk0123
- サーバの証明書のエラー
  - デバッグ用の cert を見ていました。CloudFront に任せました。
- heroku へのデプロイ
- ~~Twitter 認証~~
- ~~サイレントリリース! try 3~~

---

## Cannot GET / みたいなエラーがでる(404)

- User => Route53 => CloudFront => Heroku => Heroku Router => Node
- Heroku Router が怒ってる

---

## yszk0123: API なのになんで CloudFront?

- そういえば… なんでだっけ… 消すか…

---

## よくよく考えたら

1. User => Route53 => CloudFront => S3
2. User(JS) => API

- なので、API サーバに対して GET / not found なのは当たり前

---

## CloudFront 消しちゃったよ!

- 🤬🤬🤬🤬🤬

---

## 以下の構成になりました

- CloudFront => S3
- CloudFront => Heroku(API)

---

## ここまでになりそう

---

## 本日の気づき

- 間が空いちゃうとやったこと忘れちゃって変なことしちゃう
- ドキュメントとか残すようにする
  - それがここか?
- `もしくは毎週来る!!!!!!`

---

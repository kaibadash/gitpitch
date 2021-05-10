## Firebase Authentication なら多分これが一番早いと思います

---

## @kaiba

- もう 1 年も経ったんですね…
- サーバサイド Kotlin + GraphQL
- DB 設計したい Night 主催
- ロードバイク、温泉、日本酒、ギター、DTM
- 💜 Elasticsearch
- Firebase Authentication を導入しようとしている

---

## 認証の実装が嫌い

- アプリの本質的な価値を提供する場所ではない
- でもミスると怒られて死ぬ
- アカウント登録メールが届かない…? docomo.ne.jp…?
- 認証は厳しい人が多い?
- でも Web アプリでは認証は必須…

---

## そこで Firebase Authentication

- Auth0 もいいぞ

---

## 多分これが一番早い実演だと思います

- Google認証だとスムーズです
- 今回は悩ましいEmail認証をお見せします

---

## 多分これが一番早い実装だと思います

- Rails + React

---

```typescript
return (
  <div className="Login">
    <StyledFirebaseAuth uiConfig={uiConfig} firebaseAuth={firebase.auth()} />
  </div>
);
```

---

```typescript
await axios.post("/api/authorizations", {
  id_token: idToken,
});
```

- JWTをセッションにいれるとかだめだぞ!

---

```ruby
def create
  # JWTをvalidateして保存
  @user = User.register(user_params)
  if @user.present?
    session[:user_id] = @user.id # logged in
    render json: @user, status: :created
  end
end
```

---

## やったー! 認証処理もう終わったんですかー!?

- これまで 1 つ 1 つ実装してい認証プロバイダ増やしたい放題！
- SMS 認証もできるぞ
- 無料でいいんですか?

---

## しかし、ディレクターから…

- ログインと登録が同一画面なの? このフローでは離脱が発生する
- メールアドレス認証が済んでいないのにログイン済みになる
- UI が気に食わない
- 確実に存在するメールアドレスなの?
- パスワードのルールは?
- メールと SNS 両方でログインするとどうなる?
- PC で登録してスマホでアカウント登録メールを開いても OK?
- パスワードリマインダは? SNS の場合それやると…?

---

## できることできないこと

- 何ができる？ 何ができない？
- できなかったことは折り合いがつく？
- 多分これが一番楽だと思いますけど、苦労してやる価値ある？

---

## [PR] 続きは技術書典で！

![](https://techbookfest.org/assets/tbf11/images/top.jpg)

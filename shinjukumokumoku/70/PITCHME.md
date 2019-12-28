# shinjukumokumoku #70

---

## Instagram風アプリケーションの実装

- AWS Amplifyを使った認証
- GraphQLのAuthorized Headerにつける

---

## AWS Amplify

```html
<button onClick={() => Auth.federatedSignIn({ provider: CognitoHostedUIIdentityProvider.Facebook })}>Open Facebook</button>
```

---

## JWTのID tokenがとれた

```javascript
Auth.currentSession()
  .then(data => {
    console.log("JWT", data.getIdToken())
  })
  .catch(err => console.log(err));
```

---

## 完全勝利

```json
  "token_use": "id",
  "auth_time": 1570951707,
  "exp": 1572062824,
  "iat": 1572059224,
  "email": "kaibadash@gmail.com"
}
```

---

## Authorizationに渡して検証して復号すれば認証はOK

- バックエンドはGraphQL(Applo)
- GraphQLわからん

---

## GraphQLのチュートリアルを始める

- GraphQL公式は言語仕様が書かれているだけでチュートリアルみたいなのは実装を見ないといけない
- Apolloのチュートリアルありがたい https://www.apollographql.com/docs/apollo-server/

---

## GraphQL完全に理解したこと

- フロントエンドは好きなリソースをリクエストするとまとめて得られる
- バックエンドの実装もいる。リソースの定義をする必要がある
- 認証はどうやってやるのか

---

## 実践

- タイムアップ!
- 続きは家で!

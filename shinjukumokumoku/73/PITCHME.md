# shinjukumokumoku #73

---

## Instagram風アプリケーションの実装

- cognitoから得たJWTの検証

---

## Applo clientのヘッダでJWTを渡す

## バックエンドで検証

```javascript
let jwk: any = {
  "alg": "RS256",
  "e": "AQAB",
  "kid": "vdW71mMIq3hXIDemz4te2OfiezQ29MykQrfHtEPia90=",
  "kty": "RSA",
  "n": "03AqAXb--QNuKTEav8O8CbTwqaH_sy1hDnvKy3xyjUfsBRQMRUYd_A95ApTew7OSJ5Lsxs34XO8kmJRVmYbAo8AzgWBOyO9yq4yLQAUWnTCJiEoS2aek5UF09x8ptYBjG9S_YKJC9bGQS-UAx6AXAzlSHisSvX2YU3S2CFFLFPVLPlTOYt0z4za5ZOiFfrfVE9diH6pmo_2zoDXRLDxl2co1xG_3l97TE_Xmat0uQcdGH-Tx_utNi7cKzNISlPRaN13KOy-V4e2HeKwgqqZ--yXu7qSTIoR2pEONNyF9r9cJGkuzy3EtAuJQjddR6C_ruAx6smm64xVdssdUG-xAZw",
  "use": "sig"
};

jwt.verify(token2, publicPem, { algorithms: ['RS256'] }, function (error, decodedToken) {
  console.log(1111111, error, decodedToken);
});
```

## 無慈悲なエラー！

```
at new Promise (<anonymous>) name: 'JsonWebTokenError', message: 'invalid signature' } undefined
```



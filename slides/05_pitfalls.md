# 05. 設計上の誤解とよくある落とし穴
─ OpenID Connect との混同、トークン管理の誤用、セキュリティ設計の見落とし


## ❌ よくある誤解と落とし穴

### 🔻 OpenID Connect（OIDC）との混同
- 「OAuthでログインしてるからOK」と思い込む
- 実際には**IDトークンを伴うOIDC**でないと、ユーザーの識別は保証されない

> ✅ 対策：  
> 認証（Authentication）目的なら **OIDCの採用が必須**  
> Symfonyでは `openid` スコープの利用とIDトークンの検証が必要


### 🔻 アクセストークンを万能視する
- 有効期限切れを無視して設計
- 永続化／更新手段を持たないため、APIエラー頻発

> ✅ 対策：  
> `refresh_token` を活用し、**自動更新の仕組み**を設計に含める  
> Symfonyでは `oauth2-client` バンドルのリフレッシュ対応を明示的に実装


### 🔻 トークンをブラウザに平文保存
- `localStorage` や `sessionStorage` にトークンを保存 → XSSで盗まれる

> ✅ 対策：  
> フロントにはアクセストークンを露出させず、**HttpOnly Cookie** で管理  
> API設計に応じて**SameSite属性・CSRF対策**もセットで検討


## ✅ まとめ：設計で意識すべき三原則

| 項目                        | 最低限の設計意識                           |
|-----------------------------|--------------------------------------------|
| **ログインの仕組み**       | OAuthではなく、OIDCでIDトークンを得る    |
| **トークンの扱い方**       | 期限・更新・失効を考慮して制御を設計     |
| **セキュリティ**           | フロントから見えない形でトークンを管理   |


> ❗設計の曖昧さは、後からの修正が困難になる最大の原因。  
> **「とりあえず動く」OAuthから卒業することが、チームの未来を守る一歩ですわ。**


🖼️ *（図解：OAuth vs OIDC ／ トークンの安全な保存場所）*  
👉 `assets/diagrams/oauth_vs_oidc.png`  
👉 `assets/diagrams/token_storage_risks.png`

[README.md](../README.md)<br>
[4. Symfony × OAuthBundle 実装の内部構造](../slides/04_symfony_structure.md)<br>
[6. それでも Symfony なら安心できる理由](../slides/06_why_symfony.md)<br>

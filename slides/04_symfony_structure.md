# 4. Symfony × OAuthBundle 実装の内部構造
─ *KnpUOAuth2ClientBundle における各コンポーネントの連携と、自動化の仕組み*


## 🧩 主要構成の流れ

```
[1] User
      │
      ▼
[2] Controller (/connect/google)
      │
      ▼
[3] ClientRegistry
      │
      ▼
[4] GoogleClient (OAuth2Client)
      │
      ▼
[5] Google Login Page ───────────▶ [ユーザーがログイン]
      │                                  │
      │◀─────────────── コールバック (/check/google)
      ▼
[6] Controller (再び)
      │
      ▼
[7] fetchAccessToken() ─ トークン取得
      │
      ▼
[8] fetchUserFromToken() ─ ユーザー情報取得
      │
      ▼
[9] ResourceOwner
      │
      ▼
[10] Symfony Security (ログイン完了)
```
| ステップ | 内容                                    |
| ---- | ------------------------------------- |
| ①〜②  | ユーザーがログインリンクをクリックし、Controller が発火     |
| ②〜③  | ClientRegistry 経由で Google 用のクライアントを取得 |
| ③〜⑤  | Google の認証画面にリダイレクト                   |
| ⑤〜⑥  | 認証成功後、Google から code を含んだリダイレクト       |
| ⑥〜⑦  | アクセストークンを取得                           |
| ⑦〜⑧  | トークンを元にユーザーデータ取得                      |
| ⑧〜⑨  | ResourceOwner 経由で必要な情報に抽象化（名前・メールなど）  |
| ⑨〜⑩  | Symfony Security に渡してログイン処理完了         |

[README.md](../README.md)
[3. 登場人物とデータフローの全体像](../slides/03_flow_and_roles.md)
[5. 設計上の誤解とよくある落とし穴](../slides/05_pitfalls.md)

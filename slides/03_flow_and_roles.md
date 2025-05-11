# 3. 登場人物とデータフローの全体像
─ Resource Owner から Resource Server まで、実際の通信と責務の整理。

OAuth 2.0 の本質を理解するためには、まず関係者（登場人物）とその間で交わされるリクエストの流れを把握することが不可欠です。  
ここでは「Authorization Code Flow（認可コードフロー）」を軸に、主要構成要素とデータフローを整理します。

---

## 🧑‍🤝‍🧑 登場人物（Roles）

| 役割                | 概要                                                |
|---------------------|-----------------------------------------------------|
| **Resource Owner**  | リソースの所有者（一般にユーザー）                      |
| **Client**          | アクセスを代行するアプリケーション                      |
| **Authorization Server** | アクセス許可とトークンの発行を行うサーバー              |
| **Resource Server** | 実際のユーザーデータを保持し、トークンによるアクセスを許可するサーバー |

---

## 🔄 データフロー（Authorization Code Flow）

```plaintext
① Client → Authorization Server  
   認可コード（authorization code）をリクエスト

② Resource Owner → Authorization Server  
   ログインしてアクセスを許可（認証と認可）

③ Authorization Server → Client  
   認可コードをリダイレクトで返却

④ Client → Authorization Server  
   認可コードを元にアクセストークンを要求

⑤ Authorization Server → Client  
   アクセストークンを発行

⑥ Client → Resource Server  
   アクセストークンを付与してリソース要求

⑦ Resource Server → Client  
   要求されたデータを返却

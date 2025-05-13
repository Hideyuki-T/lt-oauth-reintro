# OAuth──“なんとなく使っている”を卒業するための再入門（Symfony編）

本資料は、業務でOAuthを利用しているエンジニアに向けて、  
その本質的な理解と設計への応用力を高めることを目的とした再入門LT資料です。

---

## 📖 目次

1. **[序章：再入門のすすめ](slides/01_intro.md)**  
   ─ 業務で使ってはいるものの、構造や思想まで理解できていると言えるでしょうか。
  

2. **[OAuthの本質とは何か](slides/02_what_is_oauth.md)**  
   ─ 「認証」と「認可」の違い、およびトークンベース設計の根幹を見直す。
  

3. **[登場人物とデータフローの全体像](slides/03_flow_and_roles.md)**  
   ─ Resource Owner から Resource Server まで、実際の通信と責務の整理。
  

4. **[Symfony × OAuthBundle 実装の内部構造](slides/04_symfony_structure.md)**  
   ─ KnpUOAuth2ClientBundle における各コンポーネントの連携と、自動化の仕組み。
  

5. **[設計上の誤解とよくある落とし穴](slides/05_pitfalls.md)**  
   ─ OpenID Connect との混同、トークン管理の誤用、セキュリティ設計の見落とし。
  

6. **[それでも Symfony なら安心できる理由](slides/06_why_symfony.md)**  
   ─ 導入の容易さと、設計に応じた柔軟な拡張性の両立。
  

7. **[Laravelとの比較にみる設計哲学の違い](slides/07_compare_laravel.md)**  
   ─ Breeze + Socialite による構成との違いを通じ、フレームワークの思想を考察。
  

8. **[まとめと技術者への提言](slides/08_summary.md)**  
   ─ 「動くOAuth」から「設計できるOAuth」へ──再入門の意義と今後への展望。
  

9. **[終章：ライブラリ任せの時代を超えて](slides/09_final_message.md)**  
   ─ 真に理解あるエンジニアとして、選び・設計し・実装する力を。
  

10. **[付録：マイクロサービス化に備えるLaravelの設計力](slides/10_microservice_laravel.md)**  
    ─ 認証を独立基盤とし、分散環境での共通化を図る。

---


## 📁 ディレクトリ構成

```
LT-OAuth-Symfony/
├── README.md                               # 全体構成と目次
├── slides/
│ ├── 01_intro.md                           # 再入門のすすめ
│ ├── 02_what_is_oauth.md                   # OAuthの本質
│ ├── 03_flow_and_roles.md                  # 登場人物とデータフロー
│ ├── 04_symfony_structure.md               # Symfony内構造解説
│ ├── 05_pitfalls.md                        # 誤解と落とし穴
│ ├── 06_why_symfony.md                     # Symfonyの強み
│ ├── 07_compare_laravel.md                 # Laravelとの比較
│ ├── 08_summary.md                         # まとめと提言
│ ├── 09_final_message.md                   # 終章：設計者の矜持
│ └── 10_microservice_laravel.md            # Laravel × OAuth × マイクロサービス
└── assets/
  ├── diagrams/                             # 登場人物図、トークンフロー図など
  └── code_samples/                         # YAML設定やPHPコード抜粋
```


---

## 📌 補足

- `slides/*.md` 各ファイルは、5〜10分LTの各スライドの原稿・図解に相当します。
- `assets/` はGitHub表示やプレゼン投影の視覚補助として活用できます。
- マイクロサービス化において、Laravelは認証基盤として切り出すのに最適な選択肢。
---

### フレームワーク全体ではなく、「認証におけるLaravelの設計力」を信頼するといいという結論に向かいます。
  

#### この構成で `LT-OAuth-Symfony` リポジトリを始めます。、  


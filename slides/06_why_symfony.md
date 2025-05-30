# 6. それでも Symfony なら安心できる理由
### ─ 導入の容易さと、設計に応じた柔軟な拡張性の両立


## ✅ なぜ「安心」なのか？

OAuthのような複雑な設計を扱う際、  
**「設計思想に合った道具か？」** は極めて重要です。

Symfonyは、その問いに対してこう応えます：

> 🧭 **「シンプルにも、大規模にも設計できる」**


## 🚀 導入のしやすさ

- `symfony new my_project --webapp` で即スタート
- Symfony CLI による **環境診断・開発支援機能** が充実
- `maker-bundle` による認証フロー・エンティティ生成の自動化


## 🧩 設計に応じた拡張性

- **Event Dispatcher × DIコンテナ** によるカスタマイズ性
- 認証・セキュリティ・メール・キャッシュ…あらゆる要件が**公式バンドル**で拡張可能
- SOLID原則に沿った設計思想が、複雑なOAuth設計にも耐えうる堅牢さを提供


## 🛡 実運用での堅牢さ

- **「PoC → 本番」** へのスムーズなスケールアップ
- 長期保守を想定した構成：サービス層、契約指向設計、テスト容易性
- 複数環境・複数サービス間の**接続・認可の構成**が綺麗に整う


## 🔚 まとめ

> ✅ **OAuthにおける「安心」とは、正しく設計できること。**  
> Symfonyは、コードだけでなく「設計の道筋」をも提供してくれる。

[README.md](../README.md)<br>
[5. 設計上の誤解とよくある落とし穴](../slides/05_pitfalls.md)<br>
[7. Laravelとの比較にみる設計哲学の違い](../slides/07_compare_laravel.md)<br>

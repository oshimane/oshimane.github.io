# oshimane-lp（推し活マネージャー LP・公開サイト）

GitHub Pages 公開用の静的サイト（site-only / Public 想定）。
**未公開（ローカルのみ）**。公開は別途ユーザー承認後。

- `index.html` … LP（推し活マネージャー）。og は絶対URL化済（https://kakutajurai-bot.github.io/oshimane-lp/）。**公開準備中のため `noindex` 付与**（本ローンチ時に削除）
- `privacy.html` … プライバシーポリシー（{{事業者名/連絡先}} 埋め待ち）
- `assets/` … favicon / apple-touch-icon / OG画像

## 公開前ゲート（クローズしてから公開）
1. privacy.html の {{事業者名}}/{{連絡先}}/{{最終更新日}} 確定（＋専門家レビュー）
2. Apps Script デプロイ→URL を index.html の `CONFIG.ENDPOINT` に設定
3. （任意）独自ドメイン

## 公開手順（承認後）
```
gh repo create kakutajurai-bot/oshimane-lp --public --source=. --remote=origin --push
gh api -X POST repos/kakutajurai-bot/oshimane-lp/pages -f 'source[branch]=main' -f 'source[path]=/'
# 公開後: index.html の noindex を削除
```

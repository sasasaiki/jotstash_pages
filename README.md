# jotstash_pages

ボードゲーム向け手番タイマー & リソース管理アプリ **JotStash** の公開ページ用リポジトリです。
`sasasaiki/bodogen_pages` をクローンして作成しました。

## 構成

`main` ブランチのルートを GitHub Pages で公開します。

```
CNAME          jotstash-prapori.saiki.app
_config.yml    Jekyll 設定（テーマ: cayman）
index.md       トップページ
privacy.md     プライバシーポリシー（日本語）
privacy-en.md  Privacy Policy (English)
```

## 公開URL

| ページ | URL |
| --- | --- |
| トップ | https://jotstash-prapori.saiki.app/ |
| プライバシーポリシー（日本語） | https://jotstash-prapori.saiki.app/privacy |
| Privacy Policy (English) | https://jotstash-prapori.saiki.app/privacy-en |

ストアへの登録先:

| 項目 | 値 |
| --- | --- |
| App Store Connect / App情報 / プライバシーポリシーURL | `/privacy` |
| App Store Connect / バージョン情報 / サポートURL | `/` |
| Play Console / ポリシー / アプリのコンテンツ / プライバシーポリシー | `/privacy` |

## Pages の設定

- Settings → Pages
  - Source: `Deploy from a branch`
  - Branch: `main` / `/ (root)`
  - Custom domain: `jotstash-prapori.saiki.app`
  - 証明書が発行されたら `Enforce HTTPS` を有効化
- DNS（`saiki.app`）: CNAME `jotstash-prapori` → `sasasaiki.github.io`（Cloudflare の場合は Proxy を DNS only に）

## ポリシー本文について

本アプリは Google Play Services / AdMob / Firebase Analytics / Crashlytics を利用する前提で記述しています。
**SDK構成を変更したら、本文（3章 ログデータ・5章 第三者サービス・6章 広告）と、
App Store の App Privacy / Google Play のデータセーフティの申告を必ず揃えてください。**

更新は `privacy.md` / `privacy-en.md` を編集して push すれば数分で反映されます。

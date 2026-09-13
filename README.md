# jotstash_pages

メモアプリ **JotStash**（メモを利用者自身の GitHub リポジトリに同期）の公開ページ用リポジトリです。
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

本アプリの実装（`pubspec.yaml` の依存）に合わせて、以下を前提に記述しています。

- 保存先: 端末内 + 利用者自身の GitHub リポジトリ（Personal Access Token 認証、トークンは端末の安全な保存領域）
- 第三者サービス: **GitHub / Google AdMob / RevenueCat** の3つ
- 収益化: AdMob による広告表示 + 広告非表示の買い切り課金（購入管理は RevenueCat）
- 解析SDK・クラッシュレポートSDK: **なし**（Firebase Analytics / Crashlytics いずれも未使用）
- カメラ利用なし

**SDK構成や同期方式を変えたら、本文の該当章と、
App Store の App Privacy / Google Play のデータセーフティの申告を必ず揃えてください。**

| 変更した内容 | 見直す章 |
| --- | --- |
| 広告SDK | 1章 収集する情報・4章 第三者サービス・5章 広告・9章 児童のプライバシー・10章 通信 |
| 課金・購入管理 | 1章 収集する情報・4章 第三者サービス・6章 購入・10章 通信 |
| 解析・クラッシュレポートSDK | 1章 収集する情報・4章 第三者サービス（現在は「行っていない」と明記しているので要修正） |
| 同期方式・保存項目 | 2章 端末内保存・3章 GitHub連携・8章 保持と削除 |

実装に無いサービスを「利用している」と書くのも、有るものを書き漏らすのも、どちらもストア審査で問題になります。
**実測（`pubspec.yaml` の依存）と本文が一致していることを毎リリース確認すること。**
ストア申告では「ユーザーコンテンツ（メモ）が第三者（GitHub）へ送信される」点と、
広告識別子の利用（iOS は ATT の許可ダイアログ）の記載を忘れないこと。

更新は `privacy.md` / `privacy-en.md` を編集して push すれば数分で反映されます。

# Wytel SES Web Mock

Wytel公式ホームページ刷新案のうち、SES問い合わせ獲得向けの静的Webモックです。
現時点では見た目と導線確認を目的としており、メール送信・DB保存・認証・管理画面などの機能は実装していません。

## ファイル構成

- `index.html` - 画面構成と文言
- `styles.css` - `#1F2F54` と白を中心にしたデザイン調整
- `_headers` - Cloudflare Pages配信用のレスポンスヘッダー設定

## Cloudflare Pagesでのデプロイ設定

GitHubリポジトリをCloudflare Pagesに接続して配信する場合は、静的HTMLサイトとして以下を指定してください。

| 項目 | 設定値 |
| --- | --- |
| Framework preset | `None` |
| Build command | 空欄 |
| Build output directory | `/` |
| Root directory | `/` |

このリポジトリはビルド工程のない静的サイトなので、Cloudflare Pages側でビルドコマンドは不要です。
`index.html`、`styles.css`、`_headers` がリポジトリ直下にある状態で配信できます。

## ローカル確認

ブラウザで `index.html` を直接開くか、以下のように簡易サーバーを起動して確認してください。

```bash
python3 -m http.server 8000
```

その後、`http://localhost:8000` を開きます。

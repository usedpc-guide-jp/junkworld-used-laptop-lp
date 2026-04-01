# Deploy Notes

このディレクトリは、`index.html` をルートに置いた静的サイトとしてそのまま公開できます。

## 公開前チェック

`[index.html](C:\Users\myste\Desktop\事業化 - コピー\index.html)` 末尾の `CONFIG` を実値に差し替える。

- `AFF_LINK`
- `OPERATOR_LINK`
- `PRIVACY_LINK`

未設定のままだと、ページ上部に警告が出て CTA は無効のままです。

## GitHub Pages

1. GitHub に新規リポジトリを作成する
2. このディレクトリをそのリポジトリへ push する
3. GitHub の `Settings` → `Pages` を開く
4. `Build and deployment` の `Source` を `Deploy from a branch` にする
5. `Branch` は `main`、フォルダは `/ (root)` を選ぶ
6. 数分待って公開 URL を確認する

参考:
- [GitHub Pages documentation](https://docs.github.com/en/pages)
- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## Cloudflare Pages

1. GitHub に新規リポジトリを作成して、このディレクトリを push する
2. Cloudflare の `Workers & Pages` から `Create application` を押す
3. `Pages` → `Import an existing Git repository` を選ぶ
4. 対象の GitHub リポジトリを接続する
5. `Production branch` は `main`
6. `Build command` は `exit 0`
7. `Build output directory` は `.` を指定する
8. 初回デプロイ完了後、`*.pages.dev` で表示確認する

参考:
- [Static HTML · Cloudflare Pages docs](https://developers.cloudflare.com/pages/framework-guides/deploy-anything/)

## 補足

- `index.html` がルートにあるので、追加ビルドは不要です
- CTA は2か所とも同じ `AFF_LINK` を参照します
- 価格帯と保証表記は公開直前に公式表示を再確認してください

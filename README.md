# gigacity — 戯画県戯画市 公式サイト（架空・動画教材用）

YouTube教育動画「Googleサイトで作る学習ポータルサイト」シリーズで、**外部サイトのURLを埋め込む練習**をするために作った架空の自治体サイト。

- 公開URL: https://johnnymaeta.github.io/gigacity/
- 舞台設定: 戯画県戯画市（ICTとAIを最大限に活かしたまちづくりを進める市）。動画シリーズの「戯画市立戯画小学校」と同じ世界観
- **戯画県・戯画市・戯画小学校は実在しない。** 掲載した人名・数値・お知らせ・施策・データはすべて架空。各ページに架空である旨を明記している（上部の告知バー・フッター・`about.html`）

## ページ構成

| ファイル | ページ |
|---|---|
| `index.html` | トップ（お知らせ・よく使うサービス・スマートシティの取り組み・数字・市長挨拶） |
| `kurashi.html` | くらしの手続き（証明書のオンライン請求・AI相談窓口・ごみ・引っ越し） |
| `kyoiku.html` | 教育・子育て（学校ICT・戯画小学校の概要・子育て支援） |
| `shisei.html` | 市政・AI戦略（推進計画・AI活用6原則・防災・オープンデータ・市議会） |
| `kanko.html` | 観光・イベント |
| `about.html` | このサイトについて（架空である旨・埋め込み用URL一覧・利用条件・更新履歴） |
| `assets/style.css` | 共通スタイル |
| `assets/ogp.png` | 埋め込み時のサムネイル（1200×630） |
| `assets/ogp-source.html` | ↑の元データ（HTML） |
| `favicon.svg` / `favicon.ico` / `apple-touch-icon.png` | 市章（架空） |

## 埋め込み時の表示

全ページに OGP（`og:title` / `og:description` / `og:image` / `og:site_name`）と Twitter Card を設定済み。GoogleサイトなどにURLを貼ると、**「戯画市公式サイト」** というタイトルとサムネイル画像がカード表示される。GitHub Pages は `X-Frame-Options` を付けないので、ページ全体を枠内に表示する埋め込みもできる。

## サムネイル画像の作り直し

`assets/ogp-source.html` を編集し、ヘッドレスChromeで撮り直す。

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --hide-scrollbars --force-device-scale-factor=1 \
  --window-size=1200,630 \
  --screenshot="$PWD/assets/ogp.png" \
  "file://$PWD/assets/ogp-source.html"
```

ファビコンは `favicon.svg` を512pxで撮って `favicon.ico`（16/32/48/64）と `apple-touch-icon.png`（180）に変換している。

## 更新のしかた

このディレクトリで編集して `git push`。GitHub Pages（`main` ブランチ / `root`）に自動反映される。**URLは変えない**（動画で読み上げているため）。

## 注意

実在の自治体・団体・学校・人物・サービスとは一切関係ない。スクリーンショットを資料に使う場合は、架空のサイトである旨を必ず添える。

# hechizan-site

Hechizan(ノ山)の事業サイト(静的 HTML/CSS、ビルド不要)。GitHub Pages で公開する想定。

## 構成
- `index.html` トップ / `privacy/` プライバシーポリシー / `contact/` お問い合わせ / `404.html`
- `app-ads.txt`(`ads.txt` も同じ内容): AdMob のアプリ確認用。ストアの開発者サイトにこのドメインを登録したときに使われる
- `style.css` 共通スタイル(外部読み込みなし、外部トラッキングなし)

## 公開前に差し替えるプレースホルダー
| 文字列 | 内容 |
|---|---|
| `info@hechizan.com` | 独自ドメインで作る問い合わせ用アドレス(取得後) |
| `【住所(バーチャルオフィス契約住所・確定後に記入)】` | DMM バーチャルオフィスの契約住所を、確定した表記のまま |
| `【公開日を記入】` | プライバシーポリシーの最終更新日 |

一括置換の例: `grep -rl 'info@hechizan.com' . | xargs sed -i '' 's/info@hechizan.com/contact@example.com/g'`

## 公開手順(各ステップは事前に確認する)
1. 公開リポジトリを作成して push(おすすめ名: `HechiZan13.github.io`。ルートに `app-ads.txt` を置くため)
2. Settings → Pages で公開
3. ドメイン取得後、ルートに `CNAME`(中身は `hechizan.com` の1行)を置き、DNS を設定、HTTPS を有効化
4. Search Console で、DNS の TXT レコード方式で所有権を確認(HTML ファイル方式の場合は、確認用ファイルをルート直下に置く)

## 守ること
- 自宅住所・個人の電話番号・本名を載せない
- 鍵・個人情報をリポジトリに入れない(公開リポジトリのため)

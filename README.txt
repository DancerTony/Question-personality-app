# 配布用PWAパッケージ（20の質問 性格判断）

このフォルダを **そのまま静的ホスティングにアップ**すると、URLで動くPWAになります（HTTPS必須）。
- 入口: `index.html`
- PWA設定: `manifest.webmanifest`
- オフライン対応: `sw.js`
- アイコン: `icons/`

## すぐ公開する方法（おすすめ順）

### 1) GitHub Pages
1. GitHubで新規リポジトリ作成（Public推奨）
2. このフォルダの中身をリポジトリ直下にアップロード
3. Settings → Pages → Branch: `main` / folder: `/ (root)` を選択
4. 表示されたURLにアクセス（例: https://xxxx.github.io/xxxxx/）

### 2) Netlify（ドラッグ&ドロップ）
1. Netlifyにログイン
2. Sites → **Deploy manually**
3. このフォルダをzipにしてドラッグ&ドロップ（または本zipをそのまま）

### 3) Vercel / Cloudflare Pages
いずれも「静的サイト」としてデプロイするだけでOKです。

## PWAとしてホーム画面に追加
- iOS Safari: 共有 → **ホーム画面に追加**
- Android Chrome: メニュー → **アプリをインストール**

## 開発確認（ローカル）
Service Workerの都合で `file://` 直開きは非推奨です。簡易サーバで確認してください。

- Python:
  - `python -m http.server 8000`
  - http://localhost:8000

## 更新方法（キャッシュ対策）
更新したら `sw.js` の `CACHE_NAME` を `gpt-pwa-v2` のように変えると確実です。

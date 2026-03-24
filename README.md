# HUD v0.0.0 — Car Head-Up Display PWA

スマートフォンで車の窓に投影するヘッドアップディスプレイ (PWA)

## 機能

- **速度** — GPS速度をシアン色の7セグ風大字で表示
- **時計** — 時分（白）＋秒（黄緑）の2段表示
- **方位角** — 戦闘機HUD風横テープコンパス（マゼンタ▼インジケーター）
- **明るさ調整** — スワイプ↑↓で調整
- **反転表示** — 左右・上下反転（フロントガラス投影用）
- **台形補正** — 左右・上下歪み補正スライダー
- **縦横レイアウト切替**

## ファイル構成

```
/
├── index.html      # メインアプリ
├── sw.js           # Service Worker（オフライン対応）
├── manifest.json   # PWA Manifest
├── icon-192.png    # アイコン 192×192
├── icon-512.png    # アイコン 512×512
└── README.md
```

## GitHub Pages へのデプロイ手順

### 1. リポジトリを作成

```bash
# 新しいリポジトリを作成（例: hud-pwa）
git init
git add .
git commit -m "HUD v0.0.0 initial release"
```

### 2. GitHub にプッシュ

```bash
git remote add origin https://github.com/<あなたのユーザー名>/hud-pwa.git
git branch -M main
git push -u origin main
```

### 3. GitHub Pages を有効化

1. リポジトリの **Settings** → **Pages** を開く
2. **Source** で `Deploy from a branch` を選択
3. Branch: `main` / Folder: `/ (root)` を選択して **Save**
4. 数分後に `https://<ユーザー名>.github.io/hud-pwa/` で公開される

## 注意事項

- GPS・コンパスは **HTTPS** 必須のため、GitHub Pages（https）での動作が前提です
- iOSの場合、コンパスのアクセス許可ダイアログが表示されます（タップで許可）
- ホーム画面に追加するとフルスクリーンのPWAとして動作します

## 使い方

1. ページを開いたら説明オーバーレイをタップして開始
2. スマホをダッシュボードに置き、フロントガラスへ反射投影
3. **⋮** メニューから反転・台形補正を調整して正像に合わせる

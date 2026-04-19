# 朝の体操 — Morning Exercise Web App

朝の運動習慣化を支援する PWA（Progressive Web App）です。  
GitHub Pages にデプロイしてスマホのホーム画面から即起動できます。

## 機能（MVP）

| # | 機能 | 内容 |
|---|------|------|
| 1 | ホーム画面 | ストリーク日数・月間カレンダー・今日の状態・開始ボタン |
| 2 | 運動実施画面 | カウントダウンタイマー＋円形プログレス＋音声再生 |
| 3 | 完了画面 | 称賛メッセージ（ストリーク連動）＋節目演出＋紙吹雪 |
| 4 | PWA対応 | ホーム画面追加・オフライン動作・スタンドアロン表示 |

## 技術スタック対応表

| iOS (元の定義) | Web App (今回) |
|---------------|---------------|
| SwiftUI | HTML / CSS / Vanilla JS |
| WidgetKit | PWA「ホーム画面に追加」 |
| SwiftData / UserDefaults | localStorage |
| UserNotifications | (v2 で Notification API) |
| ローカル音源バンドル | 設定画面から音声ファイル読み込み |

## GitHub Pages へのデプロイ手順

```bash
# 1. リポジトリを作成（GitHub上で新規リポジトリ作成）

# 2. ローカルで初期化 & プッシュ
cd morning-exercise-app
git init
git add .
git commit -m "Initial commit: MVP"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/<REPO_NAME>.git
git push -u origin main

# 3. GitHub Pages を有効化
#    リポジトリ Settings → Pages → Source: "main" / root → Save

# 4. 数分後にアクセス可能
#    https://<YOUR_USERNAME>.github.io/<REPO_NAME>/
```

## 使い方

1. スマホのブラウザで URL にアクセス
2. 「ホーム画面に追加」でアプリ化（iOS: 共有→ホーム画面に追加）
3. 毎朝アイコンをタップ → 「ラジオ体操をはじめる」
4. タイマー完了で達成記録 → ストリーク更新

### 音声ファイルの設定

⚙ 設定 → 音声ファイル「選択」からラジオ体操の音源を読み込めます。  
音声は localStorage に保存され、次回以降も再生されます。

## ファイル構成

```
morning-exercise-app/
├── index.html      … アプリ本体（HTML/CSS/JS 一体型）
├── manifest.json   … PWA マニフェスト
├── sw.js           … Service Worker（オフライン対応）
├── icon-192.png    … アプリアイコン 192x192
├── icon-512.png    … アプリアイコン 512x512
└── README.md       … このファイル
```

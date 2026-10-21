# 🐱 AI猫のポモドーロ・タイマー

> 作業と休憩を、猫と一緒に。

![Python](https://img.shields.io/badge/Python-3.10+-3776ab?logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/UI-Tkinter-ffd43b)
![React](https://img.shields.io/badge/Web-React%2018-61dafb?logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Build-Vite-646cff?logo=vite&logoColor=white)

ポモドーロ・テクニック用のシンプルなタイマーです。デスクトップ版（Python / Tkinter）と、
ブラウザで動く Web 版（React + Vite）の2つが入っています。

| 作業中 | 休憩中 |
| --- | --- |
| <img src="cat-timer-web/public/work_cat.jpg" width="320" alt="作業中の猫" /> | <img src="cat-timer-web/public/sleep_cat.jpg" width="320" alt="休憩中の猫" /> |

## 機能

- 作業時間・休憩時間を分単位で設定
- カウントダウン終了時に音とダイアログで通知
- 作業終了時にタスク名を記録（デスクトップ版は `tasks.txt` に追記）
- 作業 → 休憩 → 作業 … を自動で繰り返し
- Web 版は GitHub Pages へ自動デプロイ

## デスクトップ版（Python）

### 必要なもの

- Python 3.10+
- Pillow

```bash
pip install pillow
python promodo.py
```

`work_cat.png` / `break_cat.png` をスクリプトと同じディレクトリに置くと画像が表示されます。
見つからない場合は白いプレースホルダーで動作します。

完了したタスクは `tasks.txt` に追記されます（git 管理外）。

## Web 版（React + Vite）

```bash
cd cat-timer-web
npm install
npm run dev      # http://localhost:5173
```

本番ビルド:

```bash
npm run build
npm run preview
```

`main` ブランチに push すると、GitHub Actions（`.github/workflows/deploy.yml`）が
`cat-timer-web/dist` を GitHub Pages にデプロイします。

## 構成

```
promodo.py                 # デスクトップ版（Tkinter）
tasks.txt                  # 完了タスクのログ（実行時に生成）
cat-timer-web/
├── index.html
├── src/
│   ├── main.ts            # タイマー UI とロジック
│   ├── counter.ts
│   └── style.css
└── public/
    ├── work_cat.jpg
    └── sleep_cat.jpg
.github/workflows/deploy.yml
```

## ライセンス

特に指定がなければリポジトリの所有者に帰属します。

# Task Board

## プロジェクト概要

Vite + React で構築したタスク管理ボードアプリケーション。

## デプロイ先

https://takuyatokuoka.github.io/task-board/

`main` ブランチへのプッシュで GitHub Actions が自動ビルド・デプロイする。

## 技術スタック

| カテゴリ | 技術 |
|---|---|
| UI ライブラリ | React 19 |
| ビルドツール | Vite 8 |
| 言語 | JavaScript (JSX) |
| スタイリング | CSS Modules (`.css` ファイル) |
| 状態管理 | React 組み込み (`useState` / `useEffect`) |
| 永続化 | `localStorage` |
| CI/CD | GitHub Actions |
| ホスティング | GitHub Pages |

## コンポーネント命名規約

- **ファイル名**: PascalCase（例: `TaskItem.jsx`, `AddTaskForm.jsx`）
- **コンポーネント関数**: PascalCase で `export default`（例: `export default function TaskItem() {}`）
- **CSS クラス名**: kebab-case（例: `.task-item`, `.add-btn`）
- **props / 変数名**: camelCase（例: `onDelete`, `isDone`）
- **1ファイル1コンポーネント**を原則とし、`src/` 直下に配置する

## 開発コマンド

```bash
npm install       # 依存パッケージのインストール
npm run dev       # 開発サーバー起動 (http://localhost:5173)
npm run build     # プロダクションビルド
npm run preview   # ビルド成果物のプレビュー
```

## Git 運用ルール

### 基本方針

- コードを変更するたびに GitHub へプッシュする
- `main` ブランチへの直接プッシュは禁止。必ずフィーチャーブランチを作成してプルリクエスト経由でマージする

### ブランチ命名規則

```
feature/<機能名>      # 新機能追加
fix/<バグ内容>        # バグ修正
refactor/<対象>       # リファクタリング
docs/<対象>           # ドキュメント更新
```

### コミット・プッシュの手順

1. 変更をステージング: `git add <ファイル名>`（`git add .` は機密ファイルの誤追加防止のため避ける）
2. コミット: 変更内容を簡潔に表すメッセージで作成
3. **プッシュ: 変更のたびに必ず実行する**

```bash
git push origin <ブランチ名>
```

### コミットメッセージ規約

日本語・英語どちらでも可。変更の「なぜ」を伝える一文を心がける。

```
feat: タスクのドラッグ＆ドロップを追加
fix: 期限切れタスクが削除できない問題を修正
refactor: タスク一覧のレンダリングを最適化
```

### 禁止事項

- `--force` プッシュ（`main` ブランチへは絶対禁止）
- `--no-verify` によるフック回避
- `.env` や認証情報を含むファイルのコミット

## 開発フロー

1. フィーチャーブランチを作成
2. 実装・テスト
3. **コード変更のたびに GitHub へプッシュ**（WIP コミットでも可）
4. 実装完了後にプルリクエストを作成
5. レビュー・マージ

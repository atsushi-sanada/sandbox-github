# sandbox-github

GitHub Actions 上で [Cursor CLI](https://cursor.com/docs/cli/github-actions) を動かし、リポジトリ内のドキュメントを自動更新する POC 用リポジトリです。

## 使い方

1. リポジトリ Secrets に `CURSOR_API_KEY` を登録する（[Cursor Dashboard](https://cursor.com) で API キーを発行）
2. **Actions** → **Cursor CLI POC** → **Run workflow** を実行
3. `docs/poc-report.md` が Cursor CLI により作成・更新され、`main` に push される

## ワークフロー

| ファイル | 説明 |
|----------|------|
| `.github/workflows/cursor-cli-poc.yml` | Cursor CLI インストール → Agent 実行 → git commit/push |

## 注意

- LLM 推論は Cursor クラウド上で実行されます（ランナー上ではありません）
- Agent はファイル編集のみ。commit / push はワークフロー側で決定論的に実行します

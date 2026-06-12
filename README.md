# 2026 Codex

班級互動工具與 Codex 教學工作模式專案。技術基礎是 React + Vite + TypeScript，並已連接 GitHub、Obsidian Markdown 工作區與 Firebase Firestore。

## Project Links

- Obsidian home: [docs/Home.md](docs/Home.md)
- Second brain entry: [歡迎來到你的第二大腦.md](歡迎來到你的第二大腦.md)
- Second brain guide: [歡迎來到專案第二大腦.md](歡迎來到專案第二大腦.md)
- Knowledge base: [知識庫/index.md](知識庫/index.md)
- Firebase setup: [docs/Firebase%20Setup.md](docs/Firebase%20Setup.md)
- Project workflow cockpit: [docs/專案工作流程.md](docs/專案工作流程.md)
- Project board: [docs/tasks/Project%20Board.md](docs/tasks/Project%20Board.md)
- Development log: [docs/logs/Development%20Log.md](docs/logs/Development%20Log.md)

## Work Mode

- Say `開工` to run the startup workflow.
- Say `收工` to update the cockpit, commit relevant changes, and push when appropriate.
- Say `新專案初始化` to audit and initialize a classroom-tool project workflow.
- Gemini CLI context is available in [GEMINI.md](GEMINI.md).

Global Codex skills:

- `startup-sync`
- `shutdown-sync`
- `project-init-sync`

## Firebase

- Project ID: `codex-jacob`
- Firestore: Standard, `asia-east1`
- Current public collection: `wordcloud_words`

Student-facing data should use class codes and seat numbers only. Do not store real student names.

## Obsidian

Open this folder as the Obsidian vault:

```text
/Users/jacob/Projects/2026 codex
```

> [!NOTE]
> 舊 Google Drive 雲端路徑已於 2026-06-12 遷移至本地 /Users/jacob/Projects/... 並停用，防範 AI 走錯路。

Main entry:

```text
歡迎來到你的第二大腦.md
```

## Setup

```bash
npm install
npm run dev
```

## GitHub

This repository includes GitHub Actions CI and issue / pull request templates.

GitHub remote is already configured:

```bash
git remote -v
```

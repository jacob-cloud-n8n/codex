# Development Log

## 2026-04-26

- 初始化 React + Vite + TypeScript 專案。
- 初始化 Git 並建立第一次提交。
- 加入 GitHub CI、issue 範本與 PR 範本。
- 建立 Obsidian 文件入口、任務看板、開發日誌與決策紀錄。
- 連接 GitHub 遠端倉庫並完成第一次 push。
- 依據 `04-第二大腦設定指南.md` 建立適合本專案的第二大腦結構與 Codex 工作規則。
- 依據 `01.5-Codex必裝Skills與Plugins.md` 檢查 Codex Skills / Plugins 與基礎工具，補裝 `gh` 與 `uv`。
- 完成 GitHub CLI 登入，確認 `jacob-cloud-n8n/codex` repo 可存取。
- 依據 `04.5-連接-Firebase-資料庫.md` 安裝 Firebase CLI，建立 `firestore.rules`、`firebase.json` 與 Firebase 設定文件。
- 依據 Firebase Console 截圖設定 Firebase 專案 ID：`codex-jacob`。
- 完成 Firebase CLI 登入並部署 Firestore rules 到 `codex-jacob`。
- 重啟 Codex 後完成 Firebase MCP 驗證：新增、讀取、列出、刪除 Firestore 測試文件皆成功。
- 依據 `07-初始化班級工具工作模式.md` 套用既有專案工作模式，補齊全域開工/收工/初始化 skills 與專案駕駛艙。

## 2026-05-10

- 從 `https://github.com/mathruffian-dot/2026-YouTube` 安裝 `codex-youtube-video-workflow`、`audio-to-srt`、`smart-cut`。

## 2026-05-11

- 重新檢查 `04-第二大腦設定指南.md` 所需結構。
- 補上 `CLAUDE.md`、Obsidian Daily Notes / Templates 設定與正式歡迎筆記。
- 將 2026-04-26 至 2026-05-11 的工作紀錄轉移到 `每日筆記/` 與 `知識庫/`。
- 更新知識庫索引與操作紀錄。
- 安裝 Gemini CLI `0.41.2` 到 `~/.local/bin/gemini`，並新增 `GEMINI.md` 專案 context。

## 2026-05-12

- 安裝 Anthropic `skill-creator`，以 `anthropic-skill-creator` 名稱保存，避免覆蓋 Codex 內建系統 skill。
- 安裝 `PyYAML` 以支援該 skill 的驗證腳本。
- 執行 `quick_validate.py`，結果為 `Skill is valid!`。
- 安裝 Vercel `find-skills`，驗證通過，並確認 `npx skills find react testing` 可正常搜尋。

## 2026-05-19

- 暫緩文字雲實作，改先導入程式開發品質規則。
- 依 `CLAUDE-md-12rules.md` 建立 `docs/development-quality-rules.md`，作為網站、n8n 工作流與助理機器人的共用 12 條品質規則。
- 更新 `AGENTS.md`、`CLAUDE.md`、`GEMINI.md`，讓不同工具都能讀到同一份品質標準。

## 2026-05-30

- 安裝 OpenCode CLI `1.15.12` 到使用者目錄，並建立 `/Users/jacob/.local/bin/opencode` 連結。
- 修正 OpenCode 設定檔環境變數格式：`{env:MIMO_API_KEY}`。
- 以 `zsh -ic 'opencode run ...'` 完成最小測試，確認 Codex 可交辦任務給 OpenCode。
- 確認 Agent 團隊分工模式：Jacob 發令、Codex 拆解與驗收、OpenCode 執行明確任務、GitHub/Obsidian 留紀錄。
- 將 OpenDesign 列為待接入角色，等有 CLI、connector 或官方安裝方式後再接入。

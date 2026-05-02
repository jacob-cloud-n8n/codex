# 2026 Codex — AGENTS.md

## 專案入口

專案名稱：2026 Codex
專案用途：班級互動工具與 Codex 教學工作模式專案
主要工作目錄：`/Users/jacob/Library/CloudStorage/GoogleDrive-chen.uvtai12@gmail.com/我的雲端硬碟/2026 codex`
GitHub repo：`https://github.com/jacob-cloud-n8n/codex`
預設 branch：`main`

## Obsidian 對應筆記

Obsidian vault：`/Users/jacob/Library/CloudStorage/GoogleDrive-chen.uvtai12@gmail.com/我的雲端硬碟/2026 codex`
專案駕駛艙：`docs/專案工作流程.md`
收工時優先更新：`docs/專案工作流程.md`

> 本專案目前把 repo 同時作為 Obsidian vault 使用；固定規則放 `AGENTS.md`，進度與踩坑放專案駕駛艙。

## 工作桌 + 三個家

- 工作桌：Google Drive 工作資料夾
- GitHub：`https://github.com/jacob-cloud-n8n/codex`
- Obsidian：本 repo 內 Markdown vault
- Firebase：`codex-jacob`

## 同步規則

開工時：

- 使用 `startup-sync` 流程
- 讀本檔
- 讀 `docs/專案工作流程.md`
- 檢查 Git 狀態
- 檢查 Firebase MCP 狀態
- 不自動 pull / commit / push

收工時：

- 使用 `shutdown-sync` 流程
- 更新 `docs/專案工作流程.md`
- 如規則、路徑、專案邊界改變才更新本檔
- 需要時 commit + push GitHub

新專案初始化時：

- 使用 `project-init-sync` 流程
- 既有專案先盤點，只補缺口，不覆蓋既有設定

## 關於這個專案

- 這個專案使用 React + Vite + TypeScript。
- 專案文件同時服務 GitHub 和 Obsidian。
- 預設溝通語言是繁體中文。
- 回答與文件應該清楚、可執行、避免不必要的技術術語。

## 第二大腦結構

| 資料夾 | 用途 | 內容 |
|---|---|---|
| `Clippings/` | 輸入 | 外部文章、參考資料、原始剪藏 |
| `知識庫/` | 消化 | 整理後的概念、決策、專案知識 |
| `創作庫/` | 輸出 | 原創內容、規格、企劃、可交付文件 |
| `每日筆記/` | 時間管理 | 每日紀錄、週報、工作回顧 |
| `Templates/` | 模板 | 常用 Markdown 模板 |
| `docs/` | 專案文件 | README 延伸、決策紀錄、任務看板 |

## 主要檔案

入口檔：`src/main.tsx`、`src/App.tsx`
設定檔：`package.json`、`vite.config.ts`、`tsconfig.json`、`eslint.config.js`
Firebase：`firebase.json`、`firestore.rules`、`.firebaserc`
專案駕駛艙：`docs/專案工作流程.md`
部署位置：尚未設定；目前 GitHub repo 已連接

## 工作規則

### 新增筆記時

- 一律加入 frontmatter：`title`、`date`、`type`、`tags`。
- 外部資料放 `Clippings/`，不要直接改寫原文。
- AI 整理後的知識放 `知識庫/`，並更新 `知識庫/index.md`。
- 專案輸出或規格放 `創作庫/`。
- 每日或每週紀錄放 `每日筆記/`。

### 開發任務

- 修改前先理解現有檔案與 Git 狀態。
- 優先遵循既有架構，不做無關重構。
- 完成後更新相關文件或任務看板。
- 重要決策寫入 `docs/decisions/` 或 `知識庫/log.md`。

### Git 與 GitHub

- 小步提交，commit message 用英文祈使句或清楚短句。
- 推送前確認工作區狀態。
- 若新增 GitHub workflow，需要 token 具備 workflow 權限。
- 只提交本次工作相關檔案，不納入無關變更。

### Obsidian 協作

- 使用者說「新增到筆記」時，代表存到這個 vault。
- 使用者說「消化資料」時，先讀 `Clippings/`，再整理到 `知識庫/`。
- 使用者說「跑一次知識重整」時，執行週知識重整流程。

### Firebase

- Firebase project id：`codex-jacob`。
- Firestore database：`(default)`，位置 `asia-east1`。
- 目前 `wordcloud_words` 依教學文字雲需求允許公開讀寫；其他集合拒絕讀寫。
- 新增互動工具時，先更新 `firestore.rules`，再部署規則。
- 學生資料只存座號與班級代號，不存真名。

## 不要做

- 不要把每日進度寫進 `AGENTS.md`。
- 不要自動納入無關 Git 變更。
- 不要把 API key、token、密碼、Admin 憑證寫進 repo。
- 不要儲存學生姓名；正式資料只用座號與班級代號。
- 不要覆蓋既有 Firebase、GitHub、Obsidian 設定。

---
title: Firebase Setup
date: 2026-05-02
type: setup
tags:
  - Firebase
  - Firestore
  - MCP
---

# Firebase Setup

依據 `04.5-連接-Firebase-資料庫.md` 建立 Firebase / Firestore 設定。

## 已完成

| 項目 | 狀態 | 備註 |
|---|---|---|
| Firebase CLI | 已安裝 | `15.16.0`，位置：`~/.local/bin/firebase` |
| Firestore rules | 已建立 | `firestore.rules` |
| Firebase config | 已建立 | `firebase.json` |
| Firebase project template | 已建立 | `.firebaserc.example` |
| Firebase project | 已設定 | `codex-jacob` |
| Firebase CLI login | 已完成 | 可列出 `codex-jacob` |
| Firestore rules deploy | 已完成 | `Deploy complete!` |
| Firebase MCP validation | 已完成 | 新增、讀取、列出、刪除測試文件成功 |

## 尚需手動完成

### 1. 建立 Firebase 專案

到 Firebase Console 建立專案：

- 網址：https://console.firebase.google.com
- 建議專案名稱：`my-teaching-tools`
- Google Analytics：可不啟用

### 2. 啟用 Cloud Firestore

在 Firebase Console：

- Firestore Database
- 建立資料庫
- Standard 版
- 位置：`asia-east1 (Taiwan)` 或 `asia-northeast1 (Tokyo)`
- 安全性規則：以正式版模式啟動

### 3. 登入 Firebase CLI

已完成 Firebase CLI 登入。

原始指令：

```bash
firebase login
```

如果終端機找不到 `firebase`，先執行：

```bash
source "$HOME/.local/bin/env"
```

或使用完整路徑：

```bash
/Users/jacob/.local/bin/firebase login
```

### 4. 列出 Firebase 專案

登入後執行：

```bash
firebase projects:list
```

找到要使用的 Firebase 專案 ID。

### 5. 建立 `.firebaserc`

已建立 `.firebaserc`，使用專案 ID：`codex-jacob`。

格式：

```json
{
  "projects": {
    "default": "codex-jacob"
  }
}
```

### 6. 部署 Firestore 規則

已部署完成。

原始指令：

```bash
firebase deploy --only firestore:rules
```

部署結果：`Deploy complete!`

目前規則允許 `wordcloud_words` 公開讀寫，其餘集合拒絕讀寫。這是依照 `04.5-連接-Firebase-資料庫.md` 的課堂文字雲預設規則。

## Codex MCP 設定

本機目前沒有 `npx`，所以不使用文件中的 `npx firebase-tools@latest mcp`。改用已安裝的 standalone Firebase CLI：

```toml
[mcp_servers.firebase]
command = "/Users/jacob/.local/bin/firebase"
args = ["mcp"]
startup_timeout_sec = 60
tool_timeout_sec = 120
```

設定後需要完整重啟 Codex Desktop，Firebase MCP 工具才會載入。

## 測試流程

登入、建立 `.firebaserc`、部署規則後，已完成 MCP 測試。

測試環境：

- Active project：`codex-jacob`
- Database：`projects/codex-jacob/databases/(default)`
- Edition：Standard
- Location：`asia-east1`
- Realtime updates：enabled

測試文件：

- Collection：`test_collection`
- Document：`codex_mcp_test_20260502`
- Message：`Firebase MCP 連接測試成功`

測試結果：

- 成功讀取 Firebase environment
- 成功列出 Firestore database
- 成功新增測試文件
- 成功讀回測試文件
- 成功列出 `test_collection`
- 成功刪除測試文件
- 刪除後再次讀取，確認文件不存在

注意：`firestore_add_document` 的 `document` 參數需要傳 Firestore document 物件，不要包成 JSON 字串。

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

在本機終端機執行：

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

複製 `.firebaserc.example` 成 `.firebaserc`，並把 `your-firebase-project-id` 換成實際專案 ID。

格式：

```json
{
  "projects": {
    "default": "your-firebase-project-id"
  }
}
```

### 6. 部署 Firestore 規則

```bash
firebase deploy --only firestore:rules
```

成功時會看到 `Deploy complete!`。

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

登入、建立 `.firebaserc`、部署規則後，請執行：

```bash
firebase projects:list
firebase firestore:databases:list
```

重啟 Codex 後，可以請 Codex 測試：

- 列出 Firebase 專案
- 列出 Firestore 集合
- 新增 `test_collection` 測試文件
- 讀回測試文件
- 刪除測試文件

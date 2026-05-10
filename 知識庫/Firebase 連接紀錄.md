---
title: Firebase 連接紀錄
date: 2026-05-11
type: 知識庫
tags:
  - Firebase
  - Firestore
related:
  - docs/Firebase Setup
---

# Firebase 連接紀錄

## 專案資訊

- Firebase project id：`codex-jacob`
- Project number：`820916777644`
- Firestore database：`(default)`
- Location：`asia-east1`
- Edition：Standard

## 已完成

- 安裝 Firebase CLI。
- 建立 `firebase.json`。
- 建立 `firestore.rules`。
- 建立 `.firebaserc`。
- 完成 Firebase CLI 登入。
- 部署 Firestore rules。
- 重啟 Codex 後驗證 Firebase MCP。

## MCP 驗證

已成功完成：

- 讀取 Firebase environment。
- 列出 Firestore database。
- 新增測試文件。
- 讀回測試文件。
- 列出測試 collection。
- 刪除測試文件。
- 刪除後確認文件不存在。

## 安全規則

目前規則：

- `wordcloud_words`：公開 read/write。
- 其他集合：拒絕 read/write。

這是為了課堂文字雲測試而設定；正式工具新增集合前，需先確認資料類型與安全規則。

---
title: Codex Skills and Plugins Check
date: 2026-04-28
type: check
tags:
  - Codex
  - plugins
  - skills
---

# Codex Skills and Plugins Check

依據 `01.5-Codex必裝Skills與Plugins.md` 進行檢查與補齊。

## 基礎工具

| 工具 | 狀態 | 備註 |
|---|---|---|
| Git | 已安裝 | `git version 2.50.1` |
| GitHub CLI (`gh`) | 已補裝 | `gh version 2.91.0`，安裝於 `~/.local/bin/gh` |
| Node.js | 已安裝 | `v24.14.0` |
| uv | 已補裝 | `uv 0.11.8`，安裝於 `~/.local/bin/uv` |

## GitHub CLI 狀態

`gh` 已安裝，但尚未登入 GitHub。

下一步請在本機終端機執行：

```bash
gh auth login
```

建議選擇：

- GitHub.com
- HTTPS
- Login with a web browser

## 必裝外掛程式

| 外掛程式 | 狀態 | 備註 |
|---|---|---|
| GitHub | 未啟用 / 目前 marketplace 未提供 | 目前本機 Codex marketplace 沒有 `github@openai-curated` |
| Browser Use | 已啟用 | `browser-use@openai-bundled` |
| Documents | 已啟用 | `documents@openai-primary-runtime` |
| Presentations | 已啟用 | `presentations@openai-primary-runtime` |
| Spreadsheets | 已啟用 | `spreadsheets@openai-primary-runtime` |

## 推薦技能

| 技能 | 狀態 | 用途 |
|---|---|---|
| imagegen | 已安裝 | 生圖與改圖 |
| openai-docs | 已安裝 | 查 OpenAI / Codex 官方文件 |
| skill-installer | 已安裝 | 安裝其他 skills |
| skill-creator | 已安裝 | 建立自己的 skills |
| plugin-creator | 已安裝 | 建立本機 plugin，進階用 |

## 進階項目

| 項目 | 狀態 | 備註 |
|---|---|---|
| Gmail | 未啟用 | 需要信件整理時再連接 |
| Google Calendar | 未啟用 | 需要行程整理時再連接 |
| Obsidian / MCPVault | 後續處理 | 本專案已先建立 Obsidian 第二大腦資料夾結構 |

## 尚需手動完成

1. 執行 `gh auth login` 完成 GitHub CLI 登入。
2. 到 Codex Desktop 的 Settings / Plugins 檢查是否出現 GitHub 外掛；若出現，手動啟用並登入。
3. 重新開啟終端機或 Codex，讓 `~/.local/bin` 路徑生效。

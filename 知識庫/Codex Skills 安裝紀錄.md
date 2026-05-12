---
title: Codex Skills 安裝紀錄
date: 2026-05-11
type: 知識庫
tags:
  - Codex
  - skills
related:
  - docs/Codex Skills and Plugins Check
---

# Codex Skills 安裝紀錄

## 系統 skills

- `imagegen`
- `openai-docs`
- `skill-installer`
- `skill-creator`
- `plugin-creator`

## 工作模式 skills

- `startup-sync`
- `shutdown-sync`
- `project-init-sync`

## YouTube workflow skills

來源：`https://github.com/mathruffian-dot/2026-YouTube`

- `codex-youtube-video-workflow`
- `audio-to-srt`
- `smart-cut`

## Anthropic skills

來源：`https://github.com/anthropics/skills/blob/main/skills/skill-creator/SKILL.md`

- 安裝名稱：`anthropic-skill-creator`
- 原始 skill 名稱：`skill-creator`
- 調整原因：避免和 Codex 內建 `.system/skill-creator` 撞名
- 驗證結果：`Skill is valid!`

## Vercel skills

來源：`https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md`

- 安裝名稱：`find-skills`
- 用途：當使用者想找某種能力、詢問是否有某類 skill，或想擴充 agent 能力時，先協助搜尋與評估 skill。
- 驗證結果：`Skill is valid!`
- CLI 測試：`npx skills find react testing` 可正常回傳候選 skills、安裝數與 skills.sh 連結。

## 注意事項

- 新安裝 skills 後，需要重啟 Codex 才會載入。
- `codex-youtube-video-workflow` 會依賴 `audio-to-srt` 與 `smart-cut`。
- `anthropic-skill-creator` 的 eval scripts 需要 Python 套件 `PyYAML`，已安裝到使用者 Python。
- `find-skills` 不負責建立或改寫 skill；它主要負責發現、篩選與建議安裝來源。

## Gemini CLI

- 安裝版本：`0.41.2`
- 安裝位置：`/Users/jacob/.local/bin/gemini`
- 專案 context：`GEMINI.md`

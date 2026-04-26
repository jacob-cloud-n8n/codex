# 0001 Project Foundation

## Status

Accepted

## Context

專案需要先具備可開發的前端基礎、版本管理，以及能同步到 GitHub 和 Obsidian 的文件結構。

## Decision

使用 React + Vite + TypeScript 作為前端基礎。使用 Git 管理版本。使用 Markdown 文件放在 `docs/`，讓 GitHub 和 Obsidian 都能直接讀取同一份資料。

## Consequences

- 專案程式碼與文件可以一起被 Git 追蹤。
- Obsidian 可以直接開啟此專案資料夾作為 vault。
- GitHub Actions 會在推送到 GitHub 後執行 lint 和 build。

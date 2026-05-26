---
type: index
language: zh-TW
domain: web-app guideline
aliases:
  - Wiki Index
created: 2026-05-26
updated: 2026-05-26
---

# Wiki Index

這是 `web-app guideline` wiki 的內容索引。回答問題或 ingest 新資料時，AI agent 應先讀取本頁，再搜尋相關頁面。

## Entry Points

- [[index|Wiki Index]] - 內容導覽與頁面清單。
- [[log|Wiki Log]] - ingest、查詢歸檔、lint 與結構調整的時間紀錄。

## Scope

本 wiki 用於長期維護 web app 開發與維運準則，涵蓋：

- 開發與維護流程
- 版本控制
- 部署流程
- 專案術語
- 可長期沉澱為 guideline 的實務決策、流程與標準

## Source Summaries

- [[開發與維護 Summary]] - Ray、Vincent、Joe 關於 component 分層、共用元件查找順序、Storybook 與 CSS 技術方向的討論摘要。日期：2026-05-26。

## Topics

- [[Component 分層與共用策略]] - 定義 `base component`、`ui layer component` 與新增元件時的查找/共用順序。
- [[CSS 模組與 SCSS 遷移]] - 記錄 CSS 與 component 共置慣例，以及從 `stylus` 朝 `scss` 收斂的方向。

## Entities

- [[web-common]] - 共用元件來源，主要承載 `base component` 並以 Storybook 作為文件。
- [[web-app]] - 主要 web app 專案，使用 `web-common`，並在 `web-app/modules/components` 保存 ui layer component。
- [[web-front]] - `web-common` 的使用專案之一，目前待補更多專案職責。

## Syntheses

目前尚無綜合分析頁。經使用者確認後，耐久且可重複使用的問答或決策可歸檔於 `wiki/syntheses/`。

## Open Questions

- 尚未建立專案術語表。
- `web-front` 的專案職責、技術棧與 component 使用方式尚未明確。
- `stylus` 到 `scss` 的遷移範圍、時程與相容策略尚未定義。
- `web-common` 與 `web-app/modules/components` 中的正式可複用元件清單尚未建立。
